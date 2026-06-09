# Microsoft.VisualStudio.Setup.Services.UserSettingsSerializer::Deserialize_0

- ea: `0x47490`
- end: `0x47637`
- name: `Microsoft.VisualStudio.Setup.Services.UserSettingsSerializer::Deserialize_0`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x47460`

## callees

- `0x47340`
- `0x47490`
- `0x47710`

## string_xrefs

- `0x474d4`: `Failed to deserialize user settings due to missing start of object. Token found {0}`
- `0x475cd`: `Found unexpected token {0} at {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x47490  newobj   instance void Microsoft.VisualStudio.Setup.Services.UserSettings::.ctor()
0x47495  stloc.0
0x47496  ldc.i4.0
0x47497  stloc.1
0x47498  ldarg.1
0x47499  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.OptimizedJsonTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0x4749e  stloc.2
0x4749f  br       loc_4761C
0x474a4  ldloc.1
0x474a5  switch   loc_474BF, loc_47500, loc_47500, loc_475FD
0x474ba  br       loc_4761C
0x474bf  ldloc.2
0x474c0  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0x474c5  ldc.i4.1
0x474c6  beq.s    loc_474F9
0x474c8  ldarg.0
0x474c9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.UserSettingsSerializer::logger
0x474ce  dup
0x474cf  brtrue.s loc_474D4
0x474d1  pop
0x474d2  br.s     loc_474F2
0x474d4  ldstr    aFailedToDeseri// "Failed to deserialize user settings due"...
0x474d9  ldc.i4.1
0x474da  newarr   [mscorlib]System.Object
0x474df  dup
0x474e0  ldc.i4.0
0x474e1  ldloc.2
0x474e2  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0x474e7  box      [Newtonsoft.Json]Newtonsoft.Json.JsonToken
0x474ec  stelem.ref
0x474ed  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x474f2  ldloc.0
0x474f3  stloc.3
0x474f4  leave    loc_47635
0x474f9  ldc.i4.1
0x474fa  stloc.1
0x474fb  br       loc_4761C
0x47500  ldloc.2
0x47501  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0x47506  ldc.i4.s 0xD
0x47508  bne.un.s loc_47511
0x4750a  ldc.i4.3
0x4750b  stloc.1
0x4750c  br       loc_4761C
0x47511  ldloc.2
0x47512  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0x47517  ldc.i4.4
0x47518  bne.un   loc_475C1
0x4751d  ldc.i4.2
0x4751e  stloc.1
0x4751f  ldloc.2
0x47520  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0x47525  isinst   [mscorlib]System.String
0x4752a  stloc.s  4
0x4752c  ldloc.2
0x4752d  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0x47532  brtrue.s loc_4755D
0x47534  ldarg.0
0x47535  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.UserSettingsSerializer::logger
0x4753a  dup
0x4753b  brtrue.s loc_47543
0x4753d  pop
0x4753e  br       loc_4761C
0x47543  ldstr    aFailedToFindVa// "Failed to find value for property {0}. "...
0x47548  ldc.i4.1
0x47549  newarr   [mscorlib]System.Object
0x4754e  dup
0x4754f  ldc.i4.0
0x47550  ldloc.s  4
0x47552  stelem.ref
0x47553  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x47558  br       loc_4761C
0x4755d  ldloc.2
0x4755e  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0x47563  ldc.i4.2
0x47564  bne.un.s loc_475A8
0x47566  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4756b  stloc.s  5
0x4756d  br.s     loc_47589
0x4756f  ldloc.2
0x47570  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0x47575  isinst   [mscorlib]System.String
0x4757a  stloc.s  6
0x4757c  ldloc.s  6
0x4757e  brfalse.s loc_47589
0x47580  ldloc.s  5
0x47582  ldloc.s  6
0x47584  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x47589  ldloc.2
0x4758a  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0x4758f  brfalse.s loc_4759B
0x47591  ldloc.2
0x47592  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0x47597  ldc.i4.s 0xE
0x47599  bne.un.s loc_4756F
0x4759b  ldarg.0
0x4759c  ldloc.0
0x4759d  ldloc.s  4
0x4759f  ldloc.s  5
0x475a1  call     instance void Microsoft.VisualStudio.Setup.Services.UserSettingsSerializer::SetProperty(class Microsoft.VisualStudio.Setup.Services.UserSettings settings, string propertyName, object value)
0x475a6  br.s     loc_4761C
0x475a8  ldloc.2
0x475a9  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0x475ae  stloc.s  7
0x475b0  ldloc.s  7
0x475b2  brfalse.s loc_4761C
0x475b4  ldarg.0
0x475b5  ldloc.0
0x475b6  ldloc.s  4
0x475b8  ldloc.s  7
0x475ba  call     instance void Microsoft.VisualStudio.Setup.Services.UserSettingsSerializer::SetProperty(class Microsoft.VisualStudio.Setup.Services.UserSettings settings, string propertyName, object value)
0x475bf  br.s     loc_4761C
0x475c1  ldarg.0
0x475c2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.UserSettingsSerializer::logger
0x475c7  dup
0x475c8  brtrue.s loc_475CD
0x475ca  pop
0x475cb  br.s     loc_475F9
0x475cd  ldstr    aFoundUnexpecte// "Found unexpected token {0} at {1}."
0x475d2  ldc.i4.2
0x475d3  newarr   [mscorlib]System.Object
0x475d8  dup
0x475d9  ldc.i4.0
0x475da  ldloc.2
0x475db  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0x475e0  box      [Newtonsoft.Json]Newtonsoft.Json.JsonToken
0x475e5  stelem.ref
0x475e6  dup
0x475e7  ldc.i4.1
0x475e8  ldloc.2
0x475e9  callvirt instance int32 [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader::get_LinePosition()
0x475ee  box      [mscorlib]System.Int32
0x475f3  stelem.ref
0x475f4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x475f9  ldloc.0
0x475fa  stloc.3
0x475fb  leave.s  loc_47635
0x475fd  ldarg.0
0x475fe  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.UserSettingsSerializer::logger
0x47603  dup
0x47604  brtrue.s loc_47609
0x47606  pop
0x47607  br.s     loc_47618
0x47609  ldstr    aEndOfSettingsF// "End of settings found."
0x4760e  call     T0x2B000003
0x47613  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x47618  ldloc.0
0x47619  stloc.3
0x4761a  leave.s  loc_47635
0x4761c  ldloc.2
0x4761d  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0x47622  brtrue   loc_474A4
0x47627  leave.s  loc_47633
0x47629  ldloc.2
0x4762a  brfalse.s loc_47632
0x4762c  ldloc.2
0x4762d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47632  endfinally
0x47633  ldloc.0
0x47634  ret
0x47635  ldloc.3
0x47636  ret
```
