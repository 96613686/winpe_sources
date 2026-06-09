# Keys::.cctor

- ea: `0x330`
- end: `0x364`
- name: `Keys::.cctor`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x330  ldtoken  Microsoft.ReportingServices.Portal.WebApi.SR
0x335  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33a  callvirt instance string [mscorlib]System.Type::get_FullName()
0x33f  ldtoken  Microsoft.ReportingServices.Portal.WebApi.SR
0x344  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x349  callvirt instance class [mscorlib]System.Reflection.Module [mscorlib]System.Type::get_Module()
0x34e  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Module::get_Assembly()
0x353  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x358  stsfld   class [mscorlib]System.Resources.ResourceManager Keys::resourceManager
0x35d  ldnull
0x35e  stsfld   class [mscorlib]System.Globalization.CultureInfo Keys::_culture
0x363  ret
```
