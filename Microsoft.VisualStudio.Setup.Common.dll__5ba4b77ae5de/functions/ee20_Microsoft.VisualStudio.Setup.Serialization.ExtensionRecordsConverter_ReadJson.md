# Microsoft.VisualStudio.Setup.Serialization.ExtensionRecordsConverter::ReadJson

- ea: `0xee20`
- end: `0xeec1`
- name: `Microsoft.VisualStudio.Setup.Serialization.ExtensionRecordsConverter::ReadJson`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x4e20`
- `0x4e90`
- `0xee20`
- `0x11b00`

## string_xrefs

- `0xee93`: `Catastrophic exception happened while deserializing extensions in the vsconfig: `

## pseudocode

```c

```

## disassembly

```asm
0xee20  ldarg.s  5
0xee22  ldarg.1
0xee23  callvirt T0x2B00006E
0xee28  stloc.0
0xee29  ldarg.0
0xee2a  ldfld    class Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Serialization.ExtensionRecordsConverter::logger
0xee2f  ldloc.0
0xee30  brtrue.s loc_EE35
0xee32  ldnull
0xee33  br.s     loc_EE7E
0xee35  ldloc.0
0xee36  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__2_0
0xee3b  dup
0xee3c  brtrue.s loc_EE55
0xee3e  pop
0xee3f  ldsfld   class <>c <>c::<>9
0xee44  ldftn    instance string <>c::<ReadJson>b__2_0(string x)
0xee4a  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xee4f  dup
0xee50  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__2_0
0xee55  ldsfld   class [mscorlib]System.Func`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> <>c::<>9__2_1
0xee5a  dup
0xee5b  brtrue.s loc_EE74
0xee5d  pop
0xee5e  ldsfld   class <>c <>c::<>9
0xee63  ldftn    instance valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin <>c::<ReadJson>b__2_1(string x)
0xee69  newobj   instance void class [mscorlib]System.Func`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor(object, native int)
0xee6e  dup
0xee6f  stsfld   class [mscorlib]System.Func`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> <>c::<>9__2_1
0xee74  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xee79  call     T0x2B00006F
0xee7e  call     class Microsoft.VisualStudio.Setup.ExtensionRecords Microsoft.VisualStudio.Setup.ExtensionRecords::FromStrings(class Microsoft.VisualStudio.Setup.Services.ILogger logger, class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> extensions)
0xee83  stloc.1
0xee84  leave.s  loc_EEBF
0xee86  stloc.2
0xee87  ldarg.0
0xee88  ldfld    class Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Serialization.ExtensionRecordsConverter::logger
0xee8d  dup
0xee8e  brtrue.s loc_EE93
0xee90  pop
0xee91  br.s     loc_EEAD
0xee93  ldstr    aCatastrophicEx// "Catastrophic exception happened while d"...
0xee98  ldloc.2
0xee99  callvirt instance string [mscorlib]System.Exception::get_Message()
0xee9e  call     string [mscorlib]System.String::Concat(string, string)
0xeea3  call     T0x2B000016
0xeea8  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0xeead  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0xeeb2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0xeeb7  newobj   instance void Microsoft.VisualStudio.Setup.ExtensionRecords::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Uris, class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> MarketPlaceItemNames)
0xeebc  stloc.1
0xeebd  leave.s  loc_EEBF
0xeebf  ldloc.1
0xeec0  ret
```
