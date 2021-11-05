<template>
  <div label="输入组件">
    <input-cron type="text" :hideSecond="false" :hideYear="false" placeholder="请输入cron表达式"/>
  </div>
</template>

<script>
import EasyCron from './easy-cron'
import InputCron from './easy-cron/input-cron'
import CronValidator from './easy-cron/validator'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Cron表达式测试页面',
      exeStartTime: '2015-09-02 12:23:10',
      formData: {
        url: 'http://www.easysb.cn',
        qq: '34538980',
        cronValue1: '',
        cronValue2: '4 1/2 5 7-8 1 ?',
        cronValue3: '1/2 5 7-8 1 ?',
        cronValue4: '1 2-4 3/5 3/12 4,5,8 ? *'
      },
      formDataValidator: {
        cronValue1: [
          {validator: CronValidator}
        ],
        cronValue2: [
          {validator: CronValidator}
        ],
        cronValue3: [
          {validator: CronValidator}
        ],
        cronValue4: [
          {validator: CronValidator}
        ]
      }
    }
  },
  methods: {
    remote (val, time, cb) {
      const msg = `remote called: ${val} ${time}`
      console.info(msg)
      setTimeout(() => {
        // get result for e via http...
        const result = msg
        // ...
        // callback
        cb(result)
      }, 200)
    }
  },
  components: {
    EasyCron,
    InputCron
  },
  created () {
    // console.info(aaa)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
