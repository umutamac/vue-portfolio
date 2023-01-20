<template>
  <div class="about">
    <h1>Send me a message</h1>
    <form :action="submit">
      <div class="form">
        <div>
          <label for="email">Email</label>
          <input
            type="email"
            name="email"
            id="email"
            v-model="email"
            placeholder="Email"
          />
        </div>

        <div>
          <label for="subject">Subject</label>
          <input
            type="text"
            name="subject"
            id="subject"
            v-model="subject"
            placeholder="Subject"
          />
        </div>

        <div>
          <label for="message">Message</label>
          <textarea
            id="w3review"
            name="message"
            rows="4"
            v-model="message"
            placeholder="Message"
          ></textarea>
        </div>

        <button type="submit" :disabled="IsFormValid">Click Me!</button>
      </div>
    </form>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      form: {
        valid: false,
        data: {
          email: "",
          subject: "",
          message: "",
        },
      },
    };
  },
  methods: {
    submit() {
      let form = {
        from: this.form.data.email,
        subject: this.form.data.subject,
        message: this.form.data.message,
      };
      console.log(form);
    },
  },
  computed: {
    IsFormValid(): boolean {
      let fields: string[] = Object.values(this.form.data);
      return !fields.includes("");
    },
  },
  watch: {},
  created() {},
  mounted() {},
};
</script>

<style scoped>
.form {
  padding: 15px;
}
</style>
