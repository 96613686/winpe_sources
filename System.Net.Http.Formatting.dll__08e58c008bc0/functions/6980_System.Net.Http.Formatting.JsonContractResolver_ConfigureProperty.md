# System.Net.Http.Formatting.JsonContractResolver::ConfigureProperty

- ea: `0x6980`
- end: `0x69c8`
- name: `System.Net.Http.Formatting.JsonContractResolver::ConfigureProperty`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x69d0`

## callees

- `0x6930`
- `0x6980`
- `0x7ef0`

## pseudocode

```c

```

## disassembly

```asm
0x6980  ldarg.0
0x6981  ldfld    class System.Net.Http.Formatting.MediaTypeFormatter System.Net.Http.Formatting.JsonContractResolver::_formatter
0x6986  callvirt instance class System.Net.Http.Formatting.IRequiredMemberSelector System.Net.Http.Formatting.MediaTypeFormatter::get_RequiredMemberSelector()
0x698b  brfalse.s loc_69C0
0x698d  ldarg.0
0x698e  ldfld    class System.Net.Http.Formatting.MediaTypeFormatter System.Net.Http.Formatting.JsonContractResolver::_formatter
0x6993  callvirt instance class System.Net.Http.Formatting.IRequiredMemberSelector System.Net.Http.Formatting.MediaTypeFormatter::get_RequiredMemberSelector()
0x6998  ldarg.1
0x6999  callvirt instance bool System.Net.Http.Formatting.IRequiredMemberSelector::IsRequiredMember(class [mscorlib]System.Reflection.MemberInfo member)
0x699e  brfalse.s loc_69C0
0x69a0  ldarg.2
0x69a1  ldc.i4.1
0x69a2  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::set_Required(valuetype [Newtonsoft.Json]Newtonsoft.Json.Required)
0x69a7  ldarg.2
0x69a8  ldc.i4.0
0x69a9  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Newtonsoft.Json]Newtonsoft.Json.DefaultValueHandling>::.ctor(var<u1>)
0x69ae  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::set_DefaultValueHandling(valuetype [mscorlib]System.Nullable`1<valuetype [Newtonsoft.Json]Newtonsoft.Json.DefaultValueHandling>)
0x69b3  ldarg.2
0x69b4  ldc.i4.0
0x69b5  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Newtonsoft.Json]Newtonsoft.Json.NullValueHandling>::.ctor(var<u1>)
0x69ba  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::set_NullValueHandling(valuetype [mscorlib]System.Nullable`1<valuetype [Newtonsoft.Json]Newtonsoft.Json.NullValueHandling>)
0x69bf  ret
0x69c0  ldarg.2
0x69c1  ldc.i4.0
0x69c2  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::set_Required(valuetype [Newtonsoft.Json]Newtonsoft.Json.Required)
0x69c7  ret
```
