<template>
  <div id="pdf" class="page-content page-pdf">
    <div class="clear pdf-btns">
      <a @click="downloadPdf()" class="c-right btn btn-save">导出PDF</a>
    </div>
    <div class="pdf-pages-holder"></div>
    <div class="pdf-pages">
      <!-- 封面 -->
      <div
        class="pdf-page pdf-homepage blueBg"
        :class="summaryData.customer_info ?(summaryData.customer_info.company_type.split('').length>2?`home1Class` : `homeClass`) : ''"
      >
        <div class="header_top">
          <p>{{summaryData.customer_info ? summaryData.customer_info.company_type :''}}</p>
        </div>
        <div class="header_content">
          <div class="time">
            <p>
              <span>{{summaryData.create_time ? new Date(summaryData.create_time).getMonth()+1 : ''}}</span>月
            </p>
            <p>{{summaryData.create_time? new Date(summaryData.create_time).getFullYear():''}}年</p>
          </div>
          <div class="name">
            <h2>定制报告</h2>
            <h1>
              {{summaryData.customer_info?summaryData.customer_info.company_abbreviation :''}}
              <span>{{summaryData.customer_info?summaryData.customer_info.company_location :''}}</span>
            </h1>
          </div>
        </div>
        <div class="header_bottom">
          <div>
            <img src="../../static/img/logo.png">
          </div>
        </div>
      </div>
      <!-- 保密声明 -->
      <div class="pdf-page pdf-page-secret whiteBg withBg1">
        <div class="pdf-page-content">
          <h3>薪智数据保密责任声明</h3>
          <div class="page-secret-msg">
            <p>保护用户隐私是薪智严格遵守的一项基本原则。用户无需提供任何与个人隐私相关的信息即可使用薪智提供的薪酬分析工具。</p>
            <img src="../../static/img/icon-s.png" alt>
          </div>
          <div class="secret-content-sections">
            <p
              class="secret-content-section"
              style="top:280px;"
            >薪智与用户之间经互联网传输的数据信息，为协议双方认同的有效信息，除双方另有约定的情况外，即使用户主动上传，薪智也不接受、不读取、不保存任何可以识别个人隐私的相关数据。薪智同时对获得的不包括个人隐私数据的用户数据（以下简称“用户信息”）负有保密义务，未经用户同意不向任何第三方公开、披露。用户自行公开、有关机关依照法定程序要求披露的除外。</p>
            <div class="secret-content-section" style="top:277px;right:27px;">
              <p>用户授权薪智可以在以下事项中使用用户信息：</p>
              <div>
                <p class="dian">·</p>
                <p class="msg">依本协议约定，管理、审查用户信息及进行处理措施；</p>
              </div>
              <div>
                <p class="dian">·</p>
                <p class="msg">向用户发送重要通知，如软件更新、本协议条款的变更；</p>
              </div>
              <div>
                <p class="dian">·</p>
                <p class="msg">在不透露单独用户信息的前提下，为了改善平台功能、提供更好的服务而进行同类型企业的汇总分析；</p>
              </div>
              <div>
                <p class="dian">·</p>
                <p class="msg">法律、法规允许使用的其他情形</p>
              </div>
            </div>
            <p
              class="secret-content-section"
              style="top:494px;"
            >薪智将采取技术措施和其他必要措施，保障用户信息安全，防止在本服务中收集的用户信息泄露、毁损或丢失。如受黑客攻击、电脑病毒侵入及其他不可抗力事件导致用户信息的泄露，用户同意薪智不因此而承担任何形式的责任，但薪智™将尽可能采取补救措施，降低用户因此可能遭受不利影响的可能性。</p>
            <p
              class="secret-content-section"
              style="top:490px;right:27px;"
            >本保密协议以及薪智提供数据、工具，报告不视为易路软件向企业用户提供了任何咨询服务。平台使用、数据报告和分析报告仅供企业用户参考，用户不能就其依赖和使用报告的行为向易路软件追究任何责任。用户应遵守本协议的各项条款，正确、适当地使用薪智平台，并对通过其账号所进行的任何活动自担风险和责任。如因用户违反本协议中的任何条款，薪智在通知用户后有权中断或终止对违约用户的薪智账号提供服务，并保留其他权利。</p>
          </div>
        </div>
      </div>
      <!-- 前言 -->
      <div class="pdf-page pdf-page-firstword whiteBg">
        <div class="pdf-page-content">
          <div class="page-firstword-title">
            <h3>前言</h3>
            <p>PREFACE</p>
          </div>
          <div class="page-firstword-content">
            <div class="left-part">
              <p>
                <span></span>
                PREFACE
                <span></span>
              </p>
            </div>
            <div class="line"></div>
            <div class="right-part">
              <img src="../../static/img/ai.png" alt>
              <p
                style="margin-top:83px;margin-bottom:49px;"
              >薪智作为目前国内顶级的行业薪酬数据库，旨在为人力资源从业者提供专业的、准确的、精准的岗位薪酬数据信息。</p>
              <p>随着市场人才竞争的白热化，如何精准定位招聘岗位的薪酬水平，成为了提高招聘效率、缩短招聘周期、合理利用薪酬预算的关键点。另一面，人力资源成本已经逐步成为企业成本中占比极大的一部分，如何给予员工合理的岗位薪酬，在保障人员稳定性，降低离职率的同时，给到员工一定的激励性，也是一个薪酬工作的关键点。</p>
              <p>薪智数据从薪酬管理的两大重点：人才吸引、人才保留两方面入手，为企业提供专业的行业薪酬数据，助力薪酬预算利用率最大化。</p>
              <p>本次提供的薪酬数据服务是以报告形式呈现，将从行业宏观数据分析和岗位薪酬详细数据两方面，为您呈现同行业精准的市场薪酬数据，希望我们提供的行业数据报告能够给您的薪酬工作提供参考和帮助。</p>
            </div>
          </div>
        </div>
      </div>
      <!-- 目录 -->
      <div class="pdf-page pdf-page-catalog whiteBg">
        <div class="pdf-page-content">
          <h3>目 录</h3>

          <div
            v-for="(item,i) in catalogArrF"
            :key="i"
            :class="item.level==1? 'everyPage firstC' : 'everyPage secondC'"
          >
            <div
              style="z-index:1;width:470px;overflow:hidden;"
            >.....................................................................................................................................................................</div>
            <p style="z-index:9" class="right">{{item.pageNum}}</p>
            <p style="z-index:9" class="left">{{item.title}}</p>
          </div>
        </div>
      </div>
      <div class="pdf-page pdf-page-catalog whiteBg" v-for="(el,i) in catalogArrS" :key="i+1000">
        <div class="pdf-page-content">
          <div
            v-for="(item,index) in el"
            :key="index"
            :class="item.level==1? 'everyPage firstC' : 'everyPage secondC'"
          >
            <div
              style="z-index:1;width:470px;overflow:hidden;"
            >...................................................................................................................................................</div>
            <p style="z-index:9" class="right">{{item.pageNum}}</p>
            <p style="z-index:9" class="left">{{item.title}}</p>
          </div>
        </div>
      </div>
      <!-- 宏观经济 -->
      <div class="pdf-page pdf-page-macEcon whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <h2>一、宏观经济及薪酬增长率</h2>
          <p class="macEcon-msg">1.全国居民消费价格指数（CPI）增长率、工业品出厂价格指数（PPI）增长率</p>

          <div id="macEcon-line">
            <img src="../../static/img/macEcon.png" alt>
          </div>

          <table class="col3-table">
            <thead>
              <tr>
                <th>月份</th>
                <th>CPI同比增长</th>
                <th>PPI同比增长</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>2018年3月</td>
                <td>2.1%</td>
                <td>3.1%</td>
              </tr>
              <tr>
                <td>2018年4月</td>
                <td>1.8%</td>
                <td>3.4%</td>
              </tr>
              <tr>
                <td>2018年5月</td>
                <td>1.8%</td>
                <td>4.1%</td>
              </tr>
              <tr>
                <td>2018年6月</td>
                <td>1.9%</td>
                <td>4.7%</td>
              </tr>
              <tr>
                <td>2018年7月</td>
                <td>2.1%</td>
                <td>4.6%</td>
              </tr>
              <tr>
                <td>2018年8月</td>
                <td>2.3%</td>
                <td>4.1%</td>
              </tr>
              <tr>
                <td>2018年9月</td>
                <td>2.5%</td>
                <td>3.6%</td>
              </tr>
              <tr>
                <td>2018年10月</td>
                <td>2.5%</td>
                <td>3.3%</td>
              </tr>
              <tr>
                <td>2018年11月</td>
                <td>2.2%</td>
                <td>2.7%</td>
              </tr>
              <tr>
                <td>2018年12月</td>
                <td>1.9%</td>
                <td>0.9%</td>
              </tr>
              <tr>
                <td>2019年1月</td>
                <td>1.7%</td>
                <td>0.1%</td>
              </tr>
              <tr>
                <td>2019年2月</td>
                <td>1.5%</td>
                <td>0.1%</td>
              </tr>
            </tbody>
          </table>
          <h4 style="text-align:right;margin-top:-20px;">数据来源：国家统计局</h4>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <div class="pdf-page pdf-page-macEcon whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <p class="macEcon-msg" style="margin:0;">2，不同性质企业薪酬水平差异指数</p>
          <table class="col4-table">
            <thead>
              <tr>
                <th>企业性质</th>
                <th>薪酬指数</th>
                <th>企业性质</th>
                <th>薪酬指数</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>上市公司</td>
                <td>1.14</td>
                <td>国有</td>
                <td>1.06</td>
              </tr>
              <tr>
                <td>外资</td>
                <td>1.20</td>
                <td>民营</td>
                <td>1.00</td>
              </tr>
              <tr>
                <td>合资</td>
                <td>1.17</td>
                <td>其他</td>
                <td>0.98</td>
              </tr>
            </tbody>
          </table>
          <p class="macEcon-msg" style="margin: 16px 0 3px;">3，不同地区企业薪酬水平差异指数</p>
          <table class="col4-table" style="margin-top:-50px;">
            <thead>
              <tr>
                <th>地区</th>
                <th>薪酬指数</th>
                <th>地区</th>
                <th>薪酬指数</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>上海</td>
                <td>1.023</td>
                <td>济南</td>
                <td>0.621</td>
              </tr>
              <tr>
                <td>北京</td>
                <td>1.000</td>
                <td>宁波</td>
                <td>0.861</td>
              </tr>
              <tr>
                <td>深圳</td>
                <td>0.992</td>
                <td>沈阳</td>
                <td>0.651</td>
              </tr>
              <tr>
                <td>广州</td>
                <td>0.934</td>
                <td>青岛</td>
                <td>0.733</td>
              </tr>
              <tr>
                <td>杭州</td>
                <td>0.903</td>
                <td>昆明</td>
                <td>0.617</td>
              </tr>
              <tr>
                <td>武汉</td>
                <td>0.742</td>
                <td>无锡</td>
                <td>0.851</td>
              </tr>
              <tr>
                <td>成都</td>
                <td>0.814</td>
                <td>佛山</td>
                <td>0.873</td>
              </tr>
              <tr>
                <td>南京</td>
                <td>0.842</td>
                <td>福州</td>
                <td>0.673</td>
              </tr>
              <tr>
                <td>重庆</td>
                <td>0.772</td>
                <td>大连</td>
                <td>0.739</td>
              </tr>
              <tr>
                <td>苏州</td>
                <td>0.872</td>
                <td>石家庄</td>
                <td>0.612</td>
              </tr>
              <tr>
                <td>西安</td>
                <td>0.694</td>
                <td>南宁</td>
                <td>0.571</td>
              </tr>
              <tr>
                <td>郑州</td>
                <td>0.709</td>
                <td>哈尔滨</td>
                <td>0.603</td>
              </tr>
              <tr>
                <td>东莞</td>
                <td>0.881</td>
                <td>南昌</td>
                <td>0.622</td>
              </tr>
              <tr>
                <td>合肥</td>
                <td>0.701</td>
                <td>常州</td>
                <td>0.824</td>
              </tr>
              <tr>
                <td>长沙</td>
                <td>0.714</td>
                <td>长春</td>
                <td>0.604</td>
              </tr>
              <tr>
                <td>厦门</td>
                <td>0.833</td>
                <td>太原</td>
                <td>0.607</td>
              </tr>
              <tr>
                <td>天津</td>
                <td>0.794</td>
                <td>贵阳</td>
                <td>0.684</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <!-- 样本企业调研名录 -->
      <div class="pdf-page pdf-page-macEcon whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <h2>二、薪酬调研企业样本分析</h2>
          <p class="macEcon-msg">1.样本企业调研名录</p>
          <table :style="{marginTop:-3*comArr1.length+'px'}">
            <thead>
              <tr>
                <th>样本企业名录</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item,index) in comArr1" :key="index">
                <td>{{item.company_name}}</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <div class="pdf-page pdf-page-macEcon whiteBg" v-for="(el,i) in comArr2" :key="i">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <table :style="{marginTop:-3*el.length+'px'}">
            <thead>
              <tr>
                <th>样本企业名录</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item,index) in el" :key="index">
                <td>{{item.company_name}}</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <!-- 样本企业学历分布 -->
      <div class="pdf-page pdf-page-macEcon whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <p class="macEcon-msg">2.样本岗位学历分布</p>
          <div id="chart-bar1"></div>
          <table class="col2-table" :style="{marginTop:-3*eduData.length+'px'}">
            <thead>
              <tr>
                <th>学历</th>
                <th>占比</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item,index) in eduData" :key="index">
                <td>{{item.name}}</td>
                <td>{{Math.round(item.percent*100)}}%</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <!-- 样本企业年龄分布  -->
      <div class="pdf-page pdf-page-macEcon whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <p class="macEcon-msg">3.样本岗位年龄分布</p>
          <div id="chart-bar2"></div>
          <table class="col2-table" :style="{marginTop:-3*ageData.length+'px'}">
            <thead>
              <tr>
                <th>年龄（岁）</th>
                <th>占比</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item,index) in ageData" :key="index">
                <td>{{item.name.split( '岁' ).join( '' )}}</td>
                <td>{{Math.round(item.percent*100)}}%</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <!-- 样本企业薪酬水平结构分析（图表） -->
      <div class="pdf-page pdf-page-macEcon whiteBg" v-for="(el,i) in chart_bar3_data" :key="i+600">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <h2 v-if="i==0">三、样本企业薪酬水平结构分析</h2>
          <div v-if="i==0" class="table-title">各职位薪酬结构分析</div>
          <div v-if="i==0" class="bar-legend">
            <ul>
              <li>
                <span style="background-color:rgb(43, 116, 237)"></span>年固定薪酬比例
              </li>
              <li>
                <span style="background-color:rgb(160, 193, 255)"></span>年浮动薪酬比例
              </li>
            </ul>
          </div>
          <div :id="'chart-barr'+i"></div>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>

      <!-- 样本企业薪酬水平结构分析（表格） -->
      <div class="pdf-page pdf-page-macEcon whiteBg" v-for="(el,i) in jobArr" :key="i+200">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <table class="col3-table" :style="{marginTop:-3*el.length+'px'}">
            <thead>
              <tr>
                <th>职位</th>
                <th>年固定薪酬比例</th>
                <th>年浮动薪酬比例</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item,index) in el" :key="index">
                <td>{{item.job_name}}</td>
                <td>{{(Math.round(item.salary_component_percent*10000)/100).toString().split('.')[1] ? ((Math.round(item.salary_component_percent*10000)/100).toString().split('.')[1].split('').length==1? Math.round(item.salary_component_percent*10000)/100+'1' :Math.round(item.salary_component_percent*10000)/100):Math.round(item.salary_component_percent*10000)/100+'.00'}}%</td>
                <td>{{(Math.round((1-item.salary_component_percent)*10000)/100).toString().split('.')[1]? ((Math.round((1-item.salary_component_percent)*10000)/100).toString().split('.')[1].split('').length==1? Math.round((1-item.salary_component_percent)*10000)/100+'1' :Math.round((1-item.salary_component_percent)*10000)/100):Math.round((1-item.salary_component_percent)*10000)/100+'.00'}}%</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <!-- 年固定薪酬分析 -->
      <div class="pdf-page pdf-page-macEcon whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <h2>四、样本企业薪酬水平整体分析</h2>
          <p class="macEcon-msg">1.年固定薪酬分析</p>
          <div class="table-title">年固定薪酬回归分析</div>
          <div id="chart-line1"></div>
          <div class="line-legend">
            <ul>
              <li>
                <span style="background:#12D3C6"></span>10分位
              </li>
              <li>
                <span style="background:#22BB6E"></span>25分位
              </li>
              <li>
                <span style="background:#2B74ED"></span>50分位
              </li>
              <li>
                <span style="background:#873DDA"></span>75分位
              </li>
              <li>
                <span style="background:#FFA800"></span>90分位
              </li>
            </ul>
          </div>
          <table class="col6-table">
            <thead>
              <tr>
                <th>职级</th>
                <th>10分位</th>
                <th>25分位</th>
                <th>50分位</th>
                <th>75分位</th>
                <th>90分位</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item,index) in rankData" :key="index">
                <td>{{item.grade_name}}</td>
                <td>{{Math.round(item.fix10).toLocaleString()}}</td>
                <td>{{Math.round(item.fix25).toLocaleString()}}</td>
                <td>{{Math.round(item.fix50).toLocaleString()}}</td>
                <td>{{Math.round(item.fix75).toLocaleString()}}</td>
                <td>{{Math.round(item.fix90).toLocaleString()}}</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <!-- 年总现金收入分析 -->
      <div class="pdf-page pdf-page-macEcon whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <p class="macEcon-msg">2.年总现金收入分析</p>
          <div class="table-title">年总现金薪酬回归分析</div>
          <div id="chart-line2"></div>
          <div class="line-legend">
            <ul>
              <li>
                <span style="background:#12D3C6"></span>10分位
              </li>
              <li>
                <span style="background:#22BB6E"></span>25分位
              </li>
              <li>
                <span style="background:#2B74ED"></span>50分位
              </li>
              <li>
                <span style="background:#873DDA"></span>75分位
              </li>
              <li>
                <span style="background:#FFA800"></span>90分位
              </li>
            </ul>
          </div>
          <table class="col6-table">
            <thead>
              <tr>
                <th>职级</th>
                <th>10分位</th>
                <th>25分位</th>
                <th>50分位</th>
                <th>75分位</th>
                <th>90分位</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item,index) in rankData" :key="index">
                <td>{{item.grade_name}}</td>
                <td>{{Math.round(item.tcc10).toLocaleString()}}</td>
                <td>{{Math.round(item.tcc25).toLocaleString()}}</td>
                <td>{{Math.round(item.tcc50).toLocaleString()}}</td>
                <td>{{Math.round(item.tcc75).toLocaleString()}}</td>
                <td>{{Math.round(item.tcc90).toLocaleString()}}</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <!-- 样本企业部分及岗位薪酬分析 -->
      <div class="pdf-page pdf-page-macEcon whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <h2>五、样本企业部门及岗位薪酬分析</h2>
          <div
            v-for="(item,index) in part5dataF"
            :key="index"
            :style="{marginTop:item.category_name? '20px' : '10px'}"
          >
            <p class="macEcon-msg" v-if="item.category_name">{{item.category_name}}</p>
            <p
              class="macEcon-msg"
              style="font-size:12px;font-weight:400;margin:26px 0 10px;"
              v-if="!item.category_name"
            >{{item.job_name}}</p>
            <div class="table-msg" v-if="!item.category_name">
              <p>
                职级：
                <span>{{item.rank_name}}</span>
              </p>
              <p>
                公司数：
                <span>{{item.company_count}}</span>
              </p>
              <p>
                员工数：
                <span>{{item.employee_count}}</span>
              </p>
            </div>
            <table class="col7-table" v-if="!item.category_name">
              <thead>
                <tr>
                  <th>薪酬项目</th>
                  <th>平均值</th>
                  <th>10分位</th>
                  <th>25分位</th>
                  <th>50分位</th>
                  <th>75分位</th>
                  <th>90分位</th>
                </tr>
              </thead>
              <tbody>
                <tr style="background-color:#fff;">
                  <td>年固定薪酬</td>
                  <td>{{Math.round(item.fix_average).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix10).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix25).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix50).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix75).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix90).toLocaleString()}}</td>
                </tr>
                <tr style="background-color:#fff;">
                  <td>年总现金收入</td>
                  <td>{{Math.round(item.tcc_average).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc10).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc25).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc50).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc75).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc90).toLocaleString()}}</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <div class="pdf-page pdf-page-macEcon whiteBg" v-for="(el,i) in part5dataS" :key="i+400">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <div
            v-for="(item,index) in el"
            :key="index"
            :style="{marginTop: index==0? '0':  ( item.category_name? '20px' : '10px')}"
          >
            <p
              class="macEcon-msg"
              v-if="item.category_name"
              :style="{marginTop:index==0?'0':'16px'}"
            >{{item.category_name}}</p>
            <p
              class="macEcon-msg"
              style="font-size:12px;font-weight:400;margin:26px 0 15px;"
              :style="{marginTop:index==0?'0':'26px'}"
              v-if="!item.category_name"
            >{{item.job_name}}</p>
            <div class="table-msg" v-if="!item.category_name">
              <p>
                职级：
                <span>{{item.rank_name}}</span>
              </p>
              <p>
                公司数：
                <span>{{item.company_count}}</span>
              </p>
              <p>
                员工数：
                <span>{{item.employee_count}}</span>
              </p>
            </div>
            <table class="col7-table" v-if="!item.category_name">
              <thead>
                <tr>
                  <th>薪酬项目</th>
                  <th>平均值</th>
                  <th>10分位</th>
                  <th>25分位</th>
                  <th>50分位</th>
                  <th>75分位</th>
                  <th>90分位</th>
                </tr>
              </thead>
              <tbody>
                <tr style="background-color:#fff;">
                  <td>年固定薪酬</td>
                  <td>{{Math.round(item.fix_average).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix10).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix25).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix50).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix75).toLocaleString()}}</td>
                  <td>{{Math.round(item.fix90).toLocaleString()}}</td>
                </tr>
                <tr style="background-color:#fff;">
                  <td>年总现金收入</td>
                  <td>{{Math.round(item.tcc_average).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc10).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc25).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc50).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc75).toLocaleString()}}</td>
                  <td>{{Math.round(item.tcc90).toLocaleString()}}</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <!-- 附录 -->
      <div class="pdf-page pdf-page-appendix whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <h3>六、附录 概念与定义</h3>
          <p class="title">1.薪酬概念</p>
          <div class="page-appendix-main">
            <div class="page-appendix-main1">
              <img src="../../static/img/money1.png" alt>
              <div class="main-part1">年基本薪酬</div>
              <p>年基本薪酬</p>
            </div>
            <div class="page-appendix-main2">
              <img src="../../static/img/money2.png" alt>
              <div class="main-part2">年固定薪酬津贴</div>
              <div class="main-part1">年基本薪酬</div>
              <p>年固定薪酬</p>
            </div>
            <div class="page-appendix-main3">
              <img src="../../static/img/money3.png" alt>
              <div class="main-part3">年浮动薪酬</div>
              <div class="main-part2">年固定薪酬津贴</div>
              <div class="main-part1">年基本薪酬</div>
              <p>年总现金收入</p>
            </div>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>年基本薪酬
            </h4>
            <p>全职员工的税前12个月基本薪酬或固定薪酬</p>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>年固定薪酬
            </h4>
            <p>年基本薪酬 + 年固定现金津贴</p>
            <p>年固定现金津贴：包括固定发放的13薪、岗位津贴、住房津贴、餐补、通讯津贴、交通及其它固定发放的津贴或补贴</p>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>年总现金收入
            </h4>
            <p>年固定薪酬 + 年浮动薪酬（如：奖金、佣金/销售激励）。不含股票期权等长期激励</p>
          </div>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <div class="pdf-page pdf-page-appendix whiteBg withBg2">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <p class="title">2,统计术语</p>

          <div class="page-appendix-msg">
            <h4>
              <span></span>同比薪酬增长率
            </h4>
            <p>本期薪酬和上一年度同一时期相比的增长幅度。</p>
            <p>同比薪酬增长率 = (本期薪酬－去年同期薪酬) ÷ 去年同期薪酬 × 100%</p>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>环比薪酬增长率
            </h4>
            <p>本期薪酬和上一期相比的增长幅度。</p>
            <p>环比薪酬增长率 = (本期薪酬－上一期薪酬) ÷ 上一期薪酬 × 100%</p>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>10分位
            </h4>
            <p>将适用的样本数据从小到大排列后，只有10%的数据小于此数值。反映市场极低水平</p>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>25分位
            </h4>
            <p>将适用的样本数据从小到大排列后，只有25%的数据小于此数值。反映市场较低水平</p>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>50分位
            </h4>
            <p>将适用的样本数据从小到大排列后位置居中的数，又称“中位值”，反映市场的中等水平</p>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>75分位
            </h4>
            <p>将适用的样本数据从小到大排列后，75%的数据小于此数值。反映市场的高端水平</p>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>90分位
            </h4>
            <p>将适用的样本数据从小到大排列后，90%的数据小于此数值。反映市场的极高端水平</p>
          </div>
          <div class="page-appendix-msg">
            <h4>
              <span></span>平均值
            </h4>
            <p>平均值是样本值之和除以样本个数得出的。平均值不同于中位值。平均值受到样本中所有数值的影响，容易受极端值影响；而中位值仅代表中点的值，不受极端值影响。</p>
          </div>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <div class="pdf-page pdf-page-appendix whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <p class="title">3.区域说明</p>
          <table style="margin-top: -272px;">
            <thead>
              <tr>
                <th>区域</th>
                <th>包括范围</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>一线城市</td>
                <td>北京、上海、深圳、广州</td>
              </tr>
              <tr>
                <td>新一线城市</td>
                <td>成都、杭州、重庆、武汉、苏州、西安、天津、南京、郑州、长沙、沈阳、青岛、宁波、东莞、无锡</td>
              </tr>
              <tr style="border-bottom: #E7E7E7 1px solid;">
                <td>二线城市</td>
                <td>昆明、大连、厦门、合肥、佛山、福州、哈尔滨、济南、温州、长春、石家庄、常州、泉州、南宁、贵阳、南昌、南通、金华、徐州、太原、嘉兴、烟台、惠州、保定、台州、中山、绍兴、乌鲁木齐、潍坊、兰州</td>
              </tr>
              <tr>
                <td>长三角</td>
                <td>上海市、浙江、江苏</td>
              </tr>
              <tr>
                <td>珠三角</td>
                <td>广东</td>
              </tr>
              <tr>
                <td>华东</td>
                <td>上海、浙江、江苏、安徽、浙江、福建、山东</td>
              </tr>
              <tr>
                <td>华南</td>
                <td>广东、广西、海南</td>
              </tr>
              <tr>
                <td>华中</td>
                <td>湖北、湖南、河南、江西</td>
              </tr>
              <tr>
                <td>华北</td>
                <td>北京、天津、河北、山西、内蒙古</td>
              </tr>
              <tr>
                <td>西北</td>
                <td>宁夏、新疆、青海、陕西、甘肃</td>
              </tr>
              <tr>
                <td>西南</td>
                <td>四川、云南、贵州、西藏、重庆</td>
              </tr>
              <tr style="border-bottom: #EBEDF8 1px solid;">
                <td>东北</td>
                <td>辽宁、吉林、黑龙江</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <div class="pdf-page pdf-page-appendix whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <p class="title">4.职级说明</p>
          <table style="margin-top: -312px;">
            <thead>
              <tr>
                <th>职级名称</th>
                <th>职级描述</th>
              </tr>
            </thead>
            <tbody>
              <tr style="border-bottom: #E7E7E7 1px solid;">
                <td>副总及以上</td>
                <td>
                  <p>范围：总经理、副总经理、区域总经理、分公司总经理</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      领导和协调公司各团体及团体间的关系
                      <br>制定战略，对关键问题进行决策，并对结果负责
                      <br>选拔中高层管理人员，建立公司组织框架
                    </p>
                  </div>
                </td>
              </tr>
              <tr style="border-bottom: #E7E7E7 1px solid;">
                <td>总监/专家</td>
                <td>
                  <h5>总监</h5>
                  <p>范围：各部门总监、事业部总监</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      管控和制定所负责领域的资源和政策
                      <br>制定业务、生产、营运和组织重心
                      <br>监督公司各项政策、制度实施情况
                    </p>
                  </div>
                  <h5>专家</h5>
                  <p>范围：某一专业领域内的专家、行家、大师</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      对公司战略、规划、政策、方针提出建议
                      <br>制定并实施新产品、流程、标准、规划
                    </p>
                  </div>
                </td>
              </tr>
              <tr style="border-bottom: #E7E7E7 1px solid;">
                <td>经理/资深</td>
                <td>
                  <h5>经理</h5>
                  <p>范围：部门经理、高级经理</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      根据政策、程序和业务计划制定决策
                      <br>协调部门内部人员关系
                      <br>带领团队完成项目和解决问题\u2028
                      <br>接受总监的领导及监督
                    </p>
                  </div>
                  <h5>资深</h5>
                  <p>范围：某一专业领域资深人员</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      对某一专业领域有深入的洞察
                      <br>利用创造性和独创性支持重要的项目、规划、业务计划
                      <br>对低级员工进行技术指导、工作分配和审核
                    </p>
                  </div>
                </td>
              </tr>
              <tr style="border-bottom: #EBEDF8 1px solid;">
                <td>主管/高级</td>
                <td>
                  <h5>主管</h5>
                  <p>范围：部门主管</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      通过业务监督和帮助指导等方式参与并带领团队开展日常的工作
                      <br>根据政策、程序和业务规划制定决策和解决问题
                      <br>接受经理的领导和监督
                    </p>
                  </div>
                  <h5>高级</h5>
                  <p>范围：某一专业领域高级人员</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      精通某一专业领域的职业技能
                      <br>协助主管开展团队日常工作
                      <br>面对非常规且较为复杂的问题
                    </p>
                  </div>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <div class="pdf-page pdf-page-appendix whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <table style="margin-top: -132px;">
            <thead>
              <tr>
                <th>职级名称</th>
                <th>职级描述</th>
              </tr>
            </thead>
            <tbody>
              <tr style="border-bottom: #E7E7E7 1px solid;">
                <td>中级</td>
                <td>
                  <p>范围：某一专业领域中级人员</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      熟练工作内容，能独立完成工作
                      <br>具有一定的应用知识和经验技能
                      <br>接受高级/资深人员的监督和指导
                    </p>
                  </div>
                </td>
              </tr>
              <tr style="border-bottom: #E7E7E7 1px solid;">
                <td>初级</td>
                <td>
                  <p>范围：某一专业领域入门人员，包含助理、初级专员</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      具备基础的职业技能和专业知识
                      <br>协助中级或高级人员完成工作
                      <br>执行简单、常规性工作
                    </p>
                  </div>
                </td>
              </tr>
              <tr style="border-bottom: #E7E7E7 1px solid;">
                <td>文员/操作</td>
                <td>
                  <h5>文员</h5>
                  <p>范围：各类初级、中级、高级文员</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      需要其他人员指导下从事一些单一、局部的工作
                      <br>通常面对不困难也不复杂的常规问题
                    </p>
                  </div>
                  <h5>操作</h5>
                  <p>范围：熟练、非熟练操作工人</p>
                  <div>
                    <p>定义：</p>
                    <p>
                      对某一专业领域有深入的洞察
                      <br>经过简单技术培训即可上岗
                      <br>按照常规或者标准程序进行工作
                    </p>
                  </div>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <!-- 应用场景深化 -->
      <div class="pdf-page pdf-page-banner blueBg">
        <p>薪智报告</p>
        <h2>应用场景深化</h2>
        <div class="footer">
          <span class="m w"></span>
        </div>
      </div>
      <div class="pdf-page pdf-page-useDeep whiteBg">
        <div class="page-top">
          <span>定制报告</span>
          <img src="../../static/img/logo3.png" alt>
        </div>
        <div class="pdf-page-content">
          <h3>应用场景深化</h3>
          <div class="page-useDeep-main">
            <div class="pdf-page-main-section1">
              <div class="title" style="background: #FFD800;">薪酬及预算</div>
              <div class="msg">
                <p>·</p>
                <p>结合薪酬市场竞争力和绩效，进行年度调薪</p>
              </div>
              <div class="msg">
                <p>·</p>
                <p>根据最新市场行情，调整及分配预算</p>
              </div>
            </div>
            <div class="pdf-page-main-section2">
              <div class="title" style="background: #FFB100;">招聘定薪</div>
              <div class="msg">
                <p>·</p>
                <p>为招聘岗位提供有吸引力的薪酬</p>
              </div>
              <div class="msg">
                <p>·</p>
                <p>随时跟踪市场职位动态</p>
              </div>
              <div class="msg">
                <p>·</p>
                <p>候选人期望值，市场薪酬自动对比分析</p>
              </div>
            </div>
            <div class="pdf-page-main-section3">
              <div class="title" style="background: #1D277A;">薪酬体系</div>
              <div class="msg">
                <p>·</p>
                <p>根据企业战略，制定薪酬策略和定位</p>
              </div>
              <div class="msg">
                <p>·</p>
                <p>设置薪酬体系，确保内部公平外部竞争</p>
              </div>
              <div class="msg">
                <p>·</p>
                <p>调整薪酬体系，进行成本测算</p>
              </div>
            </div>
            <div class="pdf-page-main-section4">
              <div class="title" style="background: #FF1657;">组织人效</div>
              <div class="msg">
                <p>·</p>
                <p>整体分析公司人力投入产出比</p>
              </div>
              <div class="msg">
                <p>·</p>
                <p>多周期，多部门对比分析</p>
              </div>
              <div class="msg">
                <p>·</p>
                <p>员工人效排序，优胜劣汰</p>
              </div>
            </div>
          </div>
          <div class="page-useDeep-msg">
            <p>薪智并不止步于同时提供薪酬市场数据和薪酬分析工具，薪智与市场上主流的的核心人力资源模块和薪资核算模块无缝集成，同步数据共享，打通人力资源招聘定岗定薪、绩效激励、薪酬管理和组织人效等的各个业务场景，真正实现薪酬管理一体化。</p>
            <p>薪智坚持以用户为中心，运用领先的大数据和AI技术，在薪酬分析专业领域的沉淀上勇于突破，在数据收集、处理、匹配、分析、交互全过程颠覆创新，给用户带来全新体验和价值，给企业带来市场趋势、行业最佳实践和商业洞察力。</p>
            <p>感谢您使用薪智，我们持续不断地在增加薪智职位，扩展行业数据，地域覆盖范围，以及提供更多在线图形报告。您的反馈将是对我们最大的动力，请主动联系我们告知薪智不能满足的需求，我们将竭尽所能为您服务。</p>
          </div>
          <div class="telAndadd">
            <div class="tel">
              <p>
                <img src="../../static/img/tel.png">联系电话
              </p>
              <span>400-101-9070</span>
            </div>
            <div class="line"></div>
            <div class="add">
              <p>
                <img src="../../static/img/link.png">网址
              </p>
              <span>www.smartsalary.cn</span>
            </div>
          </div>
          <div></div>
        </div>
        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
      <div class="pdf-page pdf-page-reportMsg whiteBg">
        <div class="page-reportMsg-main">
          <div class="top">Compensation + AI</div>
          <div class="title">定制报告</div>
          <div class="msg">
            <p>Copyright©版权所有2018 薪郅互联⽹科技(上海)有限公司。保留所有权利。</p>
            <p>本文提及的公司和产品名称均为商标或注册商标。</p>
            <p>不得未经授权以任何形式或通过任何手段对这本书的任何部分进行复制或进行商业用途。</p>
            <p>薪智产品可能会用到下列开源软件：LSTM (LONG-ShORT TERM MEMORY)，WORD2VEC，DBSCAN，REINFORCEMENT LEARNING，KERAS，TENSORFLOW，APACHE.</p>
            <p>薪智对任何开源软件或共享软件或文档的使用和分发，以及由于使用此类软件或文档所造成的任何责任或损害概不负责。</p>
            <p>采购或咨询，请联系我们的企业销售部400-101-9070.</p>
            <p style="opacity:1;">
              <span style="opacity:.4;">更多内容请登录官网查询：</span>
              <span style="text-decoration: underline;">WWW.SMARTSALARY.CN</span>
            </p>
          </div>
          <div class="bottom">您的智能薪酬管理专家</div>
        </div>

        <div class="footer">
          <span class="m b"></span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import chart from "../../static/js/chart.js";
const eachPagetdSize = 25;

function chunk(array, size) {
  //获取数组的长度，如果你传入的不是数组，那么获取到的就是undefined
  const length = array.length;
  //判断不是数组，或者size没有设置，size小于1，就返回空数组
  if (!length || !size || size < 1) {
    return [];
  }
  //核心
  let index = 0;
  let resIndex = 0;
  let result = new Array(Math.ceil(length / size));
  //进行循环
  while (index < length) {
    result[resIndex++] = array.slice(index, (index += size));
  }
  //输出新数组
  return result;
}

function sliceArr(num, arr, size) {
  let arr1 = [];
  let arr2 = [];
  if (arr.length <= num) {
    arr1 = arr;
  } else {
    arr1 = arr.slice(0, num);
    arr2 = chunk(arr.slice(num, arr.length), size ? size : eachPagetdSize);
  }
  return {
    arr1: arr1,
    arr2: arr2
  };
}
export default {
  mixins: [chart],
  name: "HelloWorld",

  data() {
    return {
      report_id: "bbc3a620d29d11e8a9a31782a2f83786",
      comArr1: [],
      comArr2: [],
      ageData: [],
      jobArr: [],
      eduData: [],
      rankData: [],
      chart_line1_data: [],
      chart_line1_data2: [],
      chart_bar1_data: [],
      chart_bar2_data: [],
      chart_bar3_data: [],
      part5dataF: [],
      part5dataS: [],
      summaryData: {},
      catalogArrF: [],
      catalogArrS: [],
      fixChartleft: ""
    };
  },
  methods: {
    async getData() {
      await this.$http
        .get(`/api/xz/mg/base/custom_report/${this.report_id}/summary`)
        .then(res => {
          if (res.data.code == 0) {
            this.summaryData = res.data.result;
          }
        })
        .catch(e => {
          console.log(e);
        });
      await this.$http
        .get(`/api/xz/mg/base/custom_report/${this.report_id}/distribution/age`)
        .then(res => {
          if (res.data.code == 0) {
            console.log("success1");
            this.ageData = res.data.result;
            let myArr = [];
            res.data.result.forEach(el => {
              myArr.push({
                xLabel: el.name.split("岁").join(""),
                type: "dep",
                value1: el.percent * 100
              });
            });
            this.chart_bar2_data = myArr;
          }
        })
        .catch(e => {
          console.log(e);
        });
      await this.$http
        .get(
          `/api/xz/mg/base/custom_report/${
            this.report_id
          }/distribution/education`
        )
        .then(res => {
          if (res.data.code == 0) {
            console.log("success2");
            this.eduData = res.data.result;
            let myArr = [];
            res.data.result.forEach(el => {
              myArr.push({
                xLabel: el.name,
                type: "dep",
                value1: el.percent * 100
              });
            });
            this.chart_bar1_data = myArr;
          }
        })
        .catch(e => {
          console.log(e);
        });
      await this.$http
        .get(
          `/api/xz/mg/base/custom_report/${this.report_id}/salary/structure/job`
        )
        .then(res => {
          if (res.data.code == 0) {
            console.log("success3");
            let jobData = res.data.result;
            this.jobArr = chunk(res.data.result, 28);
            let myArr = [];
            res.data.result.forEach(el => {
              myArr.push({
                xLabel: el.job_name,
                value1: Math.round(el.salary_component_percent * 10000) / 100,
                value2:
                  Math.round((1 - el.salary_component_percent) * 10000) / 100
              });
            });
            let yLength = [];
            myArr.forEach(el => {
              yLength.push(el.xLabel.split("").length);
            });
            this.fixChartleft = Math.max(...yLength) * 11.5;
            this.chart_bar3_data = sliceArr(25, myArr, 28).arr2;
            this.chart_bar3_data.unshift(sliceArr(25, myArr, 28).arr1);
          }
        })
        .catch(e => {
          console.log(e);
        });
      await this.$http
        .get(
          `/api/xz/mg/base/custom_report/${this.report_id}/salary/percent/rank`
        )
        .then(res => {
          if (res.data.code == 0) {
            console.log("success4");
            this.rankData = res.data.result;
            //chart-line1数组
            let myArr = [],
              myArr2 = [];

            res.data.result.forEach(el => {
              myArr.push({
                xLabel: el.grade_name,
                market_10: Math.round(el.fix10),
                market_25: Math.round(el.fix25),
                market_50: Math.round(el.fix50),
                market_75: Math.round(el.fix75),
                market_90: Math.round(el.fix90)
              });
              myArr2.push({
                xLabel: el.grade_name,
                market_10: Math.round(el.tcc10),
                market_25: Math.round(el.tcc25),
                market_50: Math.round(el.tcc50),
                market_75: Math.round(el.tcc75),
                market_90: Math.round(el.tcc90)
              });
            });
            this.chart_line2_data = myArr2;
            this.chart_line1_data = myArr;
          }
        })
        .catch(e => {
          console.log(e);
        });
      await this.$http
        .get(`/api/xz/mg/base/custom_report/${this.report_id}/salary/percent`)
        .then(res => {
          if (res.data.code == 0) {
            console.log("success5");
            let myArr = [];
            res.data.result.forEach((el, i) => {
              myArr.push({
                category_name: i + 1 + "." + el.category_name
              });
              el.jobs.forEach(element => {
                myArr.push({
                  job_name: element.job_name,
                  rank_name: element.rank_name,
                  company_count: element.company_count,
                  employee_count: element.employee_count,
                  fix10: element.fix10,
                  tcc10: element.tcc10,
                  fix25: element.fix25,
                  tcc25: element.tcc25,
                  fix50: element.fix50,
                  tcc50: element.tcc50,
                  fix75: element.fix75,
                  tcc75: element.tcc75,
                  fix90: element.fix90,
                  tcc90: element.tcc90,
                  fix_average: element.fix_average,
                  tcc_average: element.tcc_average
                });
              });
            });
            // console.log(myArr, "ssss");
            this.part5dataF = sliceArr(4, myArr, 4).arr1;
            this.part5dataS = sliceArr(4, myArr, 4).arr2;
            // console.log(this.part5dataS, "ssszss");
            // this.part5dataS.forEach(el=>{
            //   el.forEach(element=>{

            //   })
            // })
          }
        })
        .catch(e => {
          console.log(e);
        });
      await this.$http
        .get(`/api/xz/mg/base/custom_report/${this.report_id}/company`)
        .then(res => {
          if (res.data.code == 0) {
            console.log("success6");
            this.comArr1 = sliceArr(25, res.data.result, 28).arr1;
            this.comArr2 = sliceArr(25, res.data.result, 28).arr2;
          }
        })
        .catch(e => {
          console.log(e);
        });

      return this;
    },
    //目录
    getCatalog() {
      let myArr = [];
      myArr.push(
        {
          title: "一、宏观经济及薪酬增长率",
          pageNum: 1,
          level: 1
        },
        {
          title:
            "1.全国居民消费价格指数（CPI）增长率、工业品出厂价格指数（PPI）增长率",
          pageNum: 1,
          level: 2
        },
        {
          title: "2.不同性质企业薪酬水平差异指数",
          pageNum: 2,
          level: 2
        },
        {
          title: "3.不同地区企业薪酬水平差异指数",
          pageNum: 2,
          level: 2
        },
        {
          title: "二、薪酬调研企业样本分析",
          pageNum: 3,
          level: 1
        },
        {
          title: "1.样本企业调研名录",
          pageNum: 3,
          level: 2
        },
        {
          title: "2.样本岗位学历分布",
          pageNum: this.comArr2.length + 4,
          level: 2
        },
        {
          title: "3.样本岗位年龄分布",
          pageNum: this.comArr2.length + 5,
          level: 2
        },
        {
          title: "三、样本企业薪酬水平结构分析",
          pageNum: this.comArr2.length + 6,
          level: 1
        },
        {
          title: "四、样本企业薪酬水平整体分析",
          pageNum:
            this.comArr2.length +
            this.chart_bar3_data.length +
            this.jobArr.length +
            6,
          level: 1
        },
        {
          title: "1.年固定薪酬分析",
          pageNum:
            this.comArr2.length +
            this.chart_bar3_data.length +
            this.jobArr.length +
            6,
          level: 2
        },
        {
          title: "2.年总现金收入分析",
          pageNum:
            this.comArr2.length +
            this.chart_bar3_data.length +
            this.jobArr.length +
            7,
          level: 2
        },
        {
          title: "五、样本企业部分及岗位薪酬分析",
          pageNum:
            this.comArr2.length +
            this.chart_bar3_data.length +
            this.jobArr.length +
            8,
          level: 1
        }
      );
      this.part5dataF.forEach((el, i) => {
        if (el.category_name) {
          myArr.push({
            title: el.category_name,
            pageNum:
              this.comArr2.length +
              this.chart_bar3_data.length +
              this.jobArr.length +
              8,
            level: 2
          });
        }
      });
      this.part5dataS.forEach((el, i) => {
        el.forEach(element => {
          if (element.category_name) {
            myArr.push({
              title: element.category_name,
              pageNum:
                this.comArr2.length +
                this.chart_bar3_data.length +
                this.jobArr.length +
                9 +
                i,
              level: 2
            });
          }
        });
      });
      myArr.push(
        {
          title: "六、附录 概念与定义",
          pageNum:
            this.comArr2.length +
            this.chart_bar3_data.length +
            this.jobArr.length +
            this.part5dataS.length +
            9,
          level: 1
        },
        {
          title: "1.薪酬概念",
          pageNum:
            this.comArr2.length +
            this.chart_bar3_data.length +
            this.jobArr.length +
            this.part5dataS.length +
            9,
          level: 2
        },
        {
          title: "2.统计术语",
          pageNum:
            this.comArr2.length +
            this.chart_bar3_data.length +
            this.jobArr.length +
            this.part5dataS.length +
            10,
          level: 2
        },
        {
          title: "3.区域说明",
          pageNum:
            this.comArr2.length +
            this.chart_bar3_data.length +
            this.jobArr.length +
            this.part5dataS.length +
            11,
          level: 2
        },
        {
          title: "4.职级说明",
          pageNum:
            this.comArr2.length +
            this.chart_bar3_data.length +
            this.jobArr.length +
            this.part5dataS.length +
            12,
          level: 2
        }
      );
      this.catalogArrF = sliceArr(22, myArr).arr1;
      this.catalogArrS = sliceArr(22, myArr).arr2;
    },

    async downloadPdf() {
      let html = "";
      // css
      // for( let i = 0; i < document.styleSheets.length; i++ ) {
      //   for( let j = 0; j < document.styleSheets[ i ].rules.length; j++ ) {
      //     html += document.styleSheets[ i ].rules[ j ].cssText
      //   }
      // }
      for (let style of document.querySelectorAll("style")) {
        html += style.innerHTML;
      }
      html = `<style>${html} .pdf-page{margin-bottom: 0!important;}</style>`;
      // html
      html += document.querySelector("#pdf .pdf-pages").outerHTML;
      html = html.replace(
        /\.\/static\/img/g,
        `${window.location.origin}/custom_report_pdf/static/img`
      );

      await this.$http
        .post(`/api/xz/mg/base/custom_report/${this.report_id}/pdf`, {
          data: html,
          name: `${this.summaryData.report_name}.pdf`
        })
        .then(res => {
          if (res.data.code === 0) {
            console.log("ss");
            window.location.href = `/api/xz/mg/base/custom_report/${
              this.report_id
            }/pdf`;
          }
          // console.log( res )
        });
    }
  },
  created() {
    if (window.location.href.split("=")[1]) {
      this.report_id = window.location.href.split("=")[1];
    }
  },
  async mounted() {
    await this.getData();
    this.getCatalog();
    this.drawLine({
      id: "#chart-line1",
      dataArr: this.chart_line1_data
    });
    this.drawLine({
      id: "#chart-line2",
      dataArr: this.chart_line2_data
    });
    this.drawBar({
      id: "#chart-bar1",
      type: "single",
      dataArr: this.chart_bar1_data,
      height: this.chart_bar2_data.length * 40,
      colorArr: ["#2b74ed"]
    });
    this.drawBar({
      id: "#chart-bar2",
      type: "single",
      dataArr: this.chart_bar2_data,
      height: this.chart_bar2_data.length * 40,
      colorArr: ["#2b74ed"]
    });
    // console.log( this.chart_bar3_data );
    for (let i = 0; i < this.chart_bar3_data.length; i++) {
      this.drawBar({
        id: `#chart-barr${i}`,
        type: "fix",
        dataArr: this.chart_bar3_data[i],
        height: this.chart_bar3_data[i].length * 26,
        colorArr: ["#2b74ed", "rgb(160, 193, 255)"],
        fixChartleft: this.fixChartleft
      });
    }

    let createPagesNum = () => {
      let nodePages = [...document.querySelectorAll("#pdf .pdf-page")];
      let a = 1;
      nodePages.forEach((n, i) => {
        if (n.querySelector(".footer .m")) {
          n.querySelector(".footer .m").innerHTML = a < 10 ? "0" + a++ : a++;
        }
      });
    };
    createPagesNum();
  }
};
</script>

<style lang='less' scoped>
// @import "../../static/css/pdf.less";
@width: 595px;
@height: 842px;

h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0;
}

.form-padding {
  padding: 100px 20px 0px 20px !important;
}

.hide {
  opacity: 0.1;
}

p {
  margin: 0;
}

.loading {
  background-color: rgba(255, 255, 255, 0.8);
}

.page-content.page-pdf {
  color: #000;
  background-color: #f5f5f5;
  overflow: hidden;
  text-align: left;

  .pdf-btns {
    position: fixed;
    z-index: 100;
    left: 50%;
    background: #f5f5f5;
    -webkit-transform: translateX(-50%);
    -moz-transform: translateX(-50%);
    -ms-transform: translateX(-50%);
    -o-transform: translateX(-50%);
    transform: translateX(-50%);
    padding: 10px 0;
    width: @width + 2;
    font-size: 14px;

    .btn-back {
      display: inline-block;
      margin-left: 20px;
      line-height: 30px;
      color: #4990e2;
    }

    .btn-save {
      cursor: pointer;
      margin-left: 20px;
      padding: 2px 20px;
      color: #4990e2;
      border: 2px solid #4990e2;
      border-radius: 20px;
      background-color: #fff;
    }
  }
}

.pdf-pages-holder {
  height: 40px;
}

.pdf-pages {
  .pdf-nopage,
  .pdf-page {
    position: relative;
    width: @width;
    height: @height;
    margin: 0 auto;
    margin-bottom: 20px;
    box-shadow: 1px 1px 2px #eee;
    overflow: hidden;

    .col3-table {
      thead {
        th {
          width: 33.3%;
        }
      }
    }

    .col2-table {
      thead {
        th {
          width: 50%;
        }
      }
    }

    .col4-table {
      thead {
        th {
          width: 25%;
        }
      }
    }

    .col6-table {
      margin-top: 40px;

      thead {
        th {
          width: 16.6%;
        }
      }
    }

    .col7-table {
      thead {
        th {
          width: 13.5%;
        }

        th:nth-child(1) {
          width: 19%;
        }

        border-bottom: 1px solid #dcdcdc;
      }
    }

    .page-top {
      position: absolute;
      width: 706px;
      height: 16px;
      font-size: 12.5px;
      line-height: 9px;
      transform: scale(0.8);
      -o-transform: scale(0.8);
      -moz-transform: scale(0.8);
      -webkit-transform: scale(0.8);
      border-bottom: 2px solid #c8cdd6;
      margin-left: -55px;
      margin-top: 23px;
      color: #6c6c6c;

      span {
        padding: 2px;
        font-size: 12.5px;
        background-color: #c8cdd6;
        color: #fff;
        margin-right: 4px;
      }

      img {
        display: inline-block;
        width: 40px;
        height: 14px;
        margin-bottom: -3px;
      }
    }

    table {
      width: 125%;
      transform: scale(0.8);
      -o-transform: scale(0.8);
      -moz-transform: scale(0.8);
      -webkit-transform: scale(0.8);
      margin-left: -58px;
      border-collapse: collapse;
      border-spacing: 0;
      border-bottom: 2px solid #363636;

      thead {
        tr {
          td,
          th {
            text-align: center;
          }
        }
      }

      tbody {
        td {
          text-align: center;
        }

        tr:nth-child(even) {
          background: #f8f8f8;
        }

        tr:nth-child(odd) {
          background: #ffffff;
        }
      }
    }
  }

  .footer {
    position: absolute;
    right: 0;
    bottom: 16px;
    left: 0;
    padding: 0 12px;
    text-align: center;
    font-size: 12px;

    .w {
      color: #fff;
    }

    .b {
      color: #333;
    }

    &:before,
    &:after {
      content: "";
      display: table;
    }

    &:after {
      clear: both;
    }
  }

  .pdf-page-content {
    padding-top: 72px;
    width: 475px;
    margin: 0 auto;
    overflow: hidden;
  }
}

.pdf-pages {
  .home1Class {
    background: url("../../static/img/home1.png") no-repeat;
  }

  .homeClass {
    background: url("../../static/img/home.png") no-repeat;
  }

  .pdf-homepage {
    .header_top {
      position: absolute;
      top: 0;
      left: 478px;
      background-color: #12397b;
      opacity: 0.6;
      width: 75.5px;

      p {
        width: 26px;
        line-height: 30px;
        font-size: 26px;
        margin: 0 auto;
        padding-top: 17px;
      }
    }

    .header_content {
      width: 495px;
      margin: 0 auto;
      overflow: hidden;
      padding-top: 620px;

      .time {
        float: right;

        p {
          font-size: 14px;

          line-height: 18px;

          span {
            font-size: 36px;
          }
        }

        p:nth-child(2) {
          opacity: 0.6;
        }
      }

      .name {
        float: left;

        h2 {
          font-size: 24px;
          font-weight: 300;
        }

        h1 {
          font-size: 49px;

          span {
            font-size: 24px;
          }
        }
      }
    }

    .header_bottom {
      width: 60px;
      margin: 0 auto;
      margin-top: 72px;

      img {
        display: inline-block;
        width: 59px;
      }
    }

    .footer {
      display: none;
    }
  }

  .pdf-page-secret {
    h3 {
      font-size: 24px;
      color: #041c44;
      // background: url('../img/icon-s.png') no-repeat right;
      // background-size: 36px;
    }

    .page-secret-msg {
      margin: 59px 0 48px;

      p {
        float: left;
        font-size: 12px;
        width: 396px;
      }

      img {
        float: right;
        width: 33px;
        height: 30px;
        margin-left: 23px;
      }
    }

    .secret-content-sections {
      .secret-content-section {
        font-size: 12.5px;
        position: absolute;
        width: 280px;
        transform: scale(0.8);
        -o-transform: scale(0.8);
        -moz-transform: scale(0.8);
        -webkit-transform: scale(0.8);
        margin-left: -30px;
        line-height: 23px;

        div {
          overflow: hidden;

          p {
            float: left;
          }

          .dian {
            width: 10%;
            text-align: center;
          }

          .msg {
            width: 90%;
          }
        }
      }
    }
  }

  .pdf-page-firstword {
    .page-firstword-title {
      margin-bottom: 70px;

      h3 {
        color: #041c44;
        font-size: 24px;
      }

      p {
        color: #041c44;
        font-size: 16px;
        margin-top: 16px;
      }
    }

    .page-firstword-content {
      overflow: hidden;
      height: 514px;

      .line,
      .right-part,
      .left-part {
        float: left;
      }

      .left-part {
        width: 20%;
        height: 100%;
        position: relative;

        p {
          font-size: 16px;
          width: 200px;
          position: absolute;
          top: 360px;
          left: -90px;
          transform: rotate(-90deg);
          -o-transform: rotate(-90deg);
          -moz-transform: rotate(-90deg);
          -webkit-transform: rotate(-90deg);

          span {
            display: inline-block;
            height: 6px;
            width: 46px;
            background-color: #041c44;
            opacity: 0.32;
            margin-bottom: 3px;
          }
        }
      }

      .line {
        width: 1%;
        height: 100%;
        background-color: #041c44;
        margin-right: 50px;
      }

      .right-part {
        width: 68%;

        img {
          width: 81px;
          height: 69px;
          display: block;
        }

        p {
          width: 372.5px;
          line-height: 20px;
          font-size: 12.5px;
          transform: scale(0.8);
          -o-transform: scale(0.8);
          -moz-transform: scale(0.8);
          -webkit-transform: scale(0.8);
          margin-left: -38px;
        }
      }
    }
  }

  .pdf-page-catalog {
    h3 {
      font-size: 18px;
      text-align: center;
    }

    .everyPage {
      position: relative;
      line-height: 30px;
      height: 30px;
      overflow: hidden;

      p {
        position: absolute;
        top: 0;
      }

      .left {
        left: 0;
        background-color: #fff;
      }

      .right {
        right: 0;
        // overflow: hidden;
        padding-right: 10px;
        text-align: right;
        background-color: #fff;
      }
    }

    .firstC {
      p {
        font-size: 14px;
      }
    }

    .secondC {
      .left {
        padding-left: 20px;
        font-size: 12px;
      }
    }
  }

  .pdf-page-macEcon {
    h2 {
      font-size: 18px;
      color: #041c44;
    }

    .macEcon-msg {
      color: #333;
      font-size: 14px;
      font-weight: 900;
      margin: 16px 0 20px;
    }

    .table-msg {
      overflow: hidden;
      width: 593px;
      transform: scale(0.8);
      -o-transform: scale(0.8);
      -moz-transform: scale(0.8);
      -webkit-transform: scale(0.8);
      margin-left: -58px;

      p {
        font-size: 12.5px;
        float: left;
        width: 33%;
        color: #333;

        span {
          font-size: 12.5px;
          color: #333;
          font-weight: 900;
        }
      }

      p:nth-child(2) {
        text-align: center;
      }

      p:nth-child(3) {
        text-align: right;
      }
    }

    .bar-legend {
      width: 593px;
      transform: scale(0.8);
      -o-transform: scale(0.8);
      -moz-transform: scale(0.8);
      -webkit-transform: scale(0.8);
      margin-left: -58px;

      ul {
        width: 230px;
        margin: 0 auto;
        overflow: hidden;
        padding: 0;

        li {
          list-style: none;
          float: left;
          margin-right: 10px;
          font-size: 12.5px;

          span {
            width: 8px;
            height: 8px;
            display: inline-block;
            background-color: #333;
            margin-bottom: 1px;
            margin-right: 3px;
          }
        }

        li:last-child {
          margin: 0;
        }
      }
    }

    .line-legend {
      width: 593px;
      transform: scale(0.8);
      -o-transform: scale(0.8);
      -moz-transform: scale(0.8);
      -webkit-transform: scale(0.8);
      margin-left: -58px;
      margin-top: -35px;

      ul {
        width: 440px;
        margin: 0 auto;
        overflow: hidden;
        padding: 0;

        li {
          list-style: none;
          float: left;
          margin-right: 10px;
          font-size: 12.5px;

          span {
            width: 33px;
            height: 2px;
            display: inline-block;
            background-color: #333;
            margin-bottom: 3px;
            margin-right: 3px;
          }
        }

        li:last-child {
          margin: 0;
        }
      }
    }

    .table-title {
      font-size: 14px;
      text-align: center;
      margin: 10px 0;
    }

    table {
      thead {
        tr {
          height: 45px;
          background-color: #12397b;

          th {
            font-size: 15px;
            color: #fff;
          }
        }
      }

      tbody {
        tr {
          height: 30px;

          td {
            font-size: 12.5px;
          }
        }
      }
    }
  }

  .pdf-page-appendix {
    h3 {
      color: #041c44;
      font-size: 16px;
      margin-bottom: 35px;
    }

    .title {
      color: #041c44;
      font-size: 14px;
      font-weight: 900;
      margin-bottom: 32px;
    }

    .page-appendix-main {
      overflow: hidden;

      .page-appendix-main1,
      .page-appendix-main2,
      .page-appendix-main3 {
        width: 110px;
        float: left;

        .main-part1,
        .main-part2,
        .main-part3 {
          text-align: center;
          color: #fff;
        }

        .main-part1 {
          height: 68px;
          line-height: 68px;
          font-size: 12px;
          background-color: #123b7c;
        }

        .main-part2 {
          height: 32px;
          line-height: 32px;
          background-color: #2b96b8;
        }

        .main-part3 {
          height: 32px;
          line-height: 32px;
          background-color: #64e7e6;
          color: #123b7c;
        }

        p {
          font-size: 12px;
          color: #333;
          text-align: center;
          height: 49px;
          line-height: 49px;
        }
      }

      .page-appendix-main1,
      .page-appendix-main2 {
        margin-right: 70px;
      }

      .page-appendix-main1 {
        padding-top: 75px;

        img {
          width: 46px;
          height: 25px;
          display: block;
          margin: 0 auto;
        }
      }

      .page-appendix-main2 {
        padding-top: 38px;

        img {
          width: 46px;
          height: 28px;
          display: block;
          margin: 0 auto;
        }
      }

      .page-appendix-main3 {
        img {
          width: 53px;
          height: 36px;
          display: block;
          margin: 0 auto;
        }
      }
    }

    .page-appendix-msg {
      margin-bottom: 20px;

      h4 {
        color: #2b74ed;
        font-weight: normal;
        font-size: 12px;

        span {
          width: 8px;
          height: 8px;
          background-color: #2b74ed;
          margin-right: 12px;
          display: inline-block;
          transform: rotate(45deg);
          -o-transform: rotate(45deg);
          -moz-transform: rotate(45deg);
          -webkit-transform: rotate(45deg);
        }
      }

      p {
        font-size: 12.5px;
        width: 560px;
        color: #333;
        transform: scale(0.8);
        -o-transform: scale(0.8);
        -moz-transform: scale(0.8);
        -webkit-transform: scale(0.8);
        line-height: 20px;
        margin-left: -36px;
      }
    }

    table {
      width: 200%;
      transform: scale(0.5);
      -o-transform: scale(0.5);
      -webkit-transform: scale(0.5);
      -moz-transform: scale(0.5);
      margin-left: -237px;

      tr {
        height: 72px;
      }

      thead {
        tr {
          background-color: #12397b;

          th {
            color: #fff;
            font-size: 24px;
          }

          th:nth-child(1) {
            width: 20%;
            background: rgba(220, 229, 244, 0.28);
          }

          th:nth-child(2) {
            text-align: left;
            text-indent: 20px;
          }
        }
      }

      tbody {
        tr {
          td {
            font-size: 24px;
            padding: 25px 42px;
            color: #6c6c6c;
          }

          td:nth-child(1) {
            background: rgba(220, 229, 244, 0.28);
            font-size: 20px;
            color: #333;
          }

          td:nth-child(2) {
            text-align: left;
            font-size: 20px;

            h5 {
              font-size: 24px;
              margin: 10px 0;
              color: #12397b;
              font-weight: normal;
            }

            p {
              color: #6c6c6c;
              font-size: 16px;
            }

            div {
              overflow: hidden;

              p {
                float: left;
                line-height: 24px;
              }

              p:nth-child(1) {
                width: 7.1%;
              }

              p:nth-child(2) {
                width: 92%;
              }
            }
          }
        }
      }
    }
  }

  .pdf-page-banner {
    background: url("../../static/img/banner.png");

    p,
    h2 {
      text-indent: 61px;
    }

    p {
      font-size: 24px;
      margin-top: 322px;
    }

    h2 {
      font-size: 48px;
    }
  }

  .pdf-page-useDeep {
    h3 {
      color: #041c44;
      font-size: 24px;
    }

    .page-useDeep-main {
      background: url("../../static/img/pie.png") no-repeat center;
      background-size: 193px;
      height: 380px;
      position: relative;
      margin: 30px 0 45px;

      .pdf-page-main-section1,
      .pdf-page-main-section2,
      .pdf-page-main-section3,
      .pdf-page-main-section4 {
        position: absolute;

        .title {
          width: 82px;
          height: 26px;
          line-height: 26px;
          text-align: center;
          background-color: #dcdcdc;
          margin-bottom: 9px;
          color: #7e6b02;
        }

        .msg {
          width: 250px;
          font-size: 12.5px;
          transform: scale(0.8);
          -o-transform: scale(0.8);
          -moz-transform: scale(0.8);
          -webkit-transform: scale(0.8);
          margin-left: -24px;
        }

        div {
          overflow: hidden;

          p {
            float: left;
          }

          p:nth-child(1) {
            width: 5%;
            font-size: 18px;
            line-height: 18px;
          }
        }
      }

      .pdf-page-main-section3,
      .pdf-page-main-section4 {
        .title {
          color: #fff;
        }
      }

      .pdf-page-main-section2 {
        right: -41px;
      }

      .pdf-page-main-section3 {
        bottom: 0;
      }

      .pdf-page-main-section4 {
        right: -41px;
        bottom: 0;
      }
    }

    .page-useDeep-msg {
      p {
        width: 540px;
        font-size: 12.5px;
        transform: scale(0.8);
        -o-transform: scale(0.8);
        -moz-transform: scale(0.8);
        -webkit-transform: scale(0.8);
        margin-left: -55px;
      }
    }

    .telAndadd {
      box-sizing: border-box;
      background: #f0f5ff;
      border: 1px solid rgba(168, 196, 244, 0.23);
      border-radius: 6px;
      overflow: hidden;
      height: 71px;
      padding: 17px 0 14px;
      margin-top: 18px;

      .tel,
      .line,
      .add {
        float: left;
      }

      .line {
        width: 1px;
        background-color: #12397b;
        height: 100%;
      }

      .tel,
      .add {
        width: 49.5%;

        p {
          font-size: 12px;
          color: #12397b;
          text-indent: 65px;

          img {
            display: inline-block;
            width: 12px;
            height: 12px;
            margin-right: 8px;
          }
        }

        span {
          display: block;
          text-indent: 78px;
          color: #12397b;
          font-size: 12.5px;
          transform: scale(0.8);
          -o-transform: scale(0.8);
          -moz-transform: scale(0.8);
          -webkit-transform: scale(0.8);
        }
      }
    }
  }

  .pdf-page-reportMsg {
    background: url("../../static/img/last.png");

    .footer {
      display: none;
    }

    .page-reportMsg-main {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 485px;
      height: 642px;

      .top {
        width: 195px;
        height: 25px;
        line-height: 25px;
        color: #fff;
        font-size: 12px;
        text-indent: 61px;
        margin-top: 40px;
      }

      .title {
        font-size: 36px;
        text-align: center;
        color: #fff;
        width: 216px;
        position: relative;
        margin: 95px auto 58px;
      }

      .msg {
        p {
          color: #fff;
          width: 85%;
          font-size: 12.5px;
          transform: scale(0.8);
          -o-transform: scale(0.8);
          -moz-transform: scale(0.8);
          -webkit-transform: scale(0.8);
          margin: 0 auto;
          line-height: 20px;
          opacity: 0.4;
        }
      }

      .bottom {
        text-align: center;
        font-size: 14px;
        color: #fff;
        margin-top: 88px;
        opacity: 0.7;
      }
    }
  }

  .withBg1 {
    background: url("../../static/img/penBg.png") no-repeat bottom center;
    background-size: @width;
  }

  .withBg2 {
    background: url("../../static/img/people.png") no-repeat;
    background-position: center 650px;
    background-size: 475px;
  }
}

.pdf-pages {
  margin: 0 auto;
  padding: 0;
  width: @width;
  font-size: 12px;
}

.pdf-pages {
  .blueBg {
    background-color: #12397b;
    color: #fff;

    .rightToppart {
      span {
        background-color: #fff;
      }
    }
  }

  .whiteBg {
    background-color: #fff;
    color: #333;

    .rightToppart {
      span {
        background-color: #979797;
      }
    }
  }

  #macEcon-line {
    height: 230px;

    img {
      display: block;
      height: 230px;
    }
  }

  #chart-bar1 {
    // height: 270px;
  }

  #chart-bar2 {
    // height: 270px;
  }

  #chart-line1 {
    height: 300px;
    margin: 20px 0;
  }

  #chart-line2 {
    height: 300px;
    margin: 20px 0;
  }
}
</style>