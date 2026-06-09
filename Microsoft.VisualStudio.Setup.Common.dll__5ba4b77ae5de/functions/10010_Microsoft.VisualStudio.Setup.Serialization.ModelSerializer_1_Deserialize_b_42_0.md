# Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::<Deserialize>b__42_0

- ea: `0x10010`
- end: `0x100b0`
- name: `Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::<Deserialize>b__42_0`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x61d0`
- `0x10010`
- `0x11b20`

## string_xrefs

- `0x10030`: `Failed to deserialize {0} in {1}: {2}`
- `0x10075`: `Failed to deserialize {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x10010  ldarg.2
0x10011  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorContext [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs::get_ErrorContext()
0x10016  stloc.0
0x10017  ldarg.0
0x10018  call     instance string class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::get_Location()
0x1001d  call     bool Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string source)
0x10022  brtrue.s loc_10069
0x10024  ldarg.0
0x10025  ldfld    class Microsoft.VisualStudio.Setup.Services.ILogger class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::logger
0x1002a  dup
0x1002b  brtrue.s loc_10030
0x1002d  pop
0x1002e  br.s     loc_100A3
0x10030  ldstr    aFailedToDeseri_0// "Failed to deserialize {0} in {1}: {2}"
0x10035  ldc.i4.3
0x10036  newarr   [mscorlib]System.Object
0x1003b  dup
0x1003c  ldc.i4.0
0x1003d  ldloc.0
0x1003e  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorContext::get_Path()
0x10043  stelem.ref
0x10044  dup
0x10045  ldc.i4.1
0x10046  ldarg.0
0x10047  call     instance string class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::get_Location()
0x1004c  stelem.ref
0x1004d  dup
0x1004e  ldc.i4.2
0x1004f  ldloc.0
0x10050  callvirt instance class [mscorlib]System.Exception [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorContext::get_Error()
0x10055  dup
0x10056  brtrue.s loc_1005C
0x10058  pop
0x10059  ldnull
0x1005a  br.s     loc_10061
0x1005c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x10061  stelem.ref
0x10062  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string format, object[] args)
0x10067  br.s     loc_100A3
0x10069  ldarg.0
0x1006a  ldfld    class Microsoft.VisualStudio.Setup.Services.ILogger class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::logger
0x1006f  dup
0x10070  brtrue.s loc_10075
0x10072  pop
0x10073  br.s     loc_100A3
0x10075  ldstr    aFailedToDeseri_1// "Failed to deserialize {0}: {1}"
0x1007a  ldc.i4.2
0x1007b  newarr   [mscorlib]System.Object
0x10080  dup
0x10081  ldc.i4.0
0x10082  ldloc.0
0x10083  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorContext::get_Path()
0x10088  stelem.ref
0x10089  dup
0x1008a  ldc.i4.1
0x1008b  ldloc.0
0x1008c  callvirt instance class [mscorlib]System.Exception [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorContext::get_Error()
0x10091  dup
0x10092  brtrue.s loc_10098
0x10094  pop
0x10095  ldnull
0x10096  br.s     loc_1009D
0x10098  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1009d  stelem.ref
0x1009e  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string format, object[] args)
0x100a3  ldloc.0
0x100a4  ldarg.0
0x100a5  call     instance bool class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::get_ContinueOnError()
0x100aa  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorContext::set_Handled(bool)
0x100af  ret
```
