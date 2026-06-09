# System.Web.UI.ScriptComponentDescriptor::GetScript

- ea: `0x13190`
- end: `0x13257`
- name: `System.Web.UI.ScriptComponentDescriptor::GetScript`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x12c70`

## callees

- `0x12d20`
- `0x12d50`
- `0x12dd0`
- `0x12ea0`
- `0x12f10`
- `0x12fd0`
- `0x130b0`
- `0x13190`

## string_xrefs

- `0x131b5`: `$create(`

## pseudocode

```c

```

## disassembly

```asm
0x13190  ldarg.0
0x13191  callvirt instance string System.Web.UI.ScriptComponentDescriptor::get_ID()
0x13196  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1319b  brtrue.s loc_131AE
0x1319d  ldarg.0
0x1319e  ldstr    aId_1// "id"
0x131a3  ldarg.0
0x131a4  callvirt instance string System.Web.UI.ScriptComponentDescriptor::get_ID()
0x131a9  call     instance void System.Web.UI.ScriptComponentDescriptor::AddProperty(string name, object value)
0x131ae  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x131b3  stloc.0
0x131b4  ldloc.0
0x131b5  ldstr    aCreate// "$create("
0x131ba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x131bf  pop
0x131c0  ldloc.0
0x131c1  ldarg.0
0x131c2  call     instance string System.Web.UI.ScriptComponentDescriptor::get_Type()
0x131c7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x131cc  pop
0x131cd  ldloc.0
0x131ce  ldstr    asc_3F824// ", "
0x131d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x131d8  pop
0x131d9  ldarg.0
0x131da  ldloc.0
0x131db  call     instance void System.Web.UI.ScriptComponentDescriptor::AppendPropertiesScript(class [mscorlib]System.Text.StringBuilder builder)
0x131e0  ldloc.0
0x131e1  ldstr    asc_3F824// ", "
0x131e6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x131eb  pop
0x131ec  ldarg.0
0x131ed  ldloc.0
0x131ee  call     instance void System.Web.UI.ScriptComponentDescriptor::AppendEventsScript(class [mscorlib]System.Text.StringBuilder builder)
0x131f3  ldloc.0
0x131f4  ldstr    asc_3F824// ", "
0x131f9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x131fe  pop
0x131ff  ldarg.0
0x13200  ldloc.0
0x13201  call     instance void System.Web.UI.ScriptComponentDescriptor::AppendReferencesScript(class [mscorlib]System.Text.StringBuilder builder)
0x13206  ldarg.0
0x13207  call     instance string System.Web.UI.ScriptComponentDescriptor::get_ElementIDInternal()
0x1320c  brfalse.s loc_13244
0x1320e  ldloc.0
0x1320f  ldstr    asc_3F824// ", "
0x13214  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13219  pop
0x1321a  ldloc.0
0x1321b  ldstr    aGet_1// "$get(\""
0x13220  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13225  pop
0x13226  ldloc.0
0x13227  ldarg.0
0x13228  call     instance string System.Web.UI.ScriptComponentDescriptor::get_ElementIDInternal()
0x1322d  call     string [System.Web]System.Web.HttpUtility::JavaScriptStringEncode(string)
0x13232  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13237  pop
0x13238  ldloc.0
0x13239  ldstr    asc_40708// "\")"
0x1323e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13243  pop
0x13244  ldloc.0
0x13245  ldstr    asc_4070E// ");"
0x1324a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1324f  pop
0x13250  ldloc.0
0x13251  callvirt instance string [mscorlib]System.Object::ToString()
0x13256  ret
```
