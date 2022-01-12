<template>
  <div>
    <div>
      <q-input
        outlined
        v-model="text"
        prefix="PRE"
        suffix="SUF"
        :clearable="false"
      >
      </q-input>
    </div>
    <div>
      <q-btn-group class="bg-grey-3">
        <q-btn icon="timeline" />
        <q-btn icon="visibility" />
        <q-btn icon="update" />
        <q-select
          v-bind="props"
          v-model="stringSingle"
          :options="stringOptions"
          dense
          :clearable="false"
          borderless
        >
        </q-select>
      </q-btn-group>
    </div>
    <div>
      <q-select
        v-bind="props"
        v-model="stringSingle"
        :options="stringOptions"
        dense
        :clearable="false"
        outlined
        style="width: 200px; margin-left: 50px"
      >
      </q-select>
    </div>
    <div>
      <q-radio v-model="option" val="opt1" label="Option 1" color="red" :keep-color="true" />
      <q-radio v-model="option" val="opt2" label="Option 2" color="red" :keep-color="true" />
      <q-radio v-model="option" val="opt3" label="Option 3" color="red" :keep-color="true" />
      <q-radio v-model="option" val="opt4" label="Option 4" color="red" :keep-color="true" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      option: "",
      text: "",
      stringSingle: "Facebook",
      stringOptions: ["Google", "Facebook", "Twitter", "Apple", "Oracle"],
    };
  },

  computed: {
    props() {
      const props = {
        hideBottomSpace: this.hideBottomSpace,
        dark: this.dark,
        type: this.type,
        autogrow: this.autogrow,
        hideHint: this.hideHint,
        disable: this.disable,
        readonly: this.readonly,
        prefix: this.prefix,
        suffix: this.suffix,
        placeholder: this.placeholder === true ? "Placeholder text" : null,
        dense: this.dense,
        clearable: true,
        square: this.square,
        style: { fontSize: `${this.fontSize}px` },
      };

      if (this.rows !== "") {
        props.rows = this.rows;
      }

      return props;
    },
  },
};
</script>
