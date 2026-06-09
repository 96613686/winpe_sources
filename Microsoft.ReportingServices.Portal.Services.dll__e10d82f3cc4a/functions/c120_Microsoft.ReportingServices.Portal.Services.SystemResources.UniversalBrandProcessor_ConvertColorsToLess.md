# Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::ConvertColorsToLess

- ea: `0xc120`
- end: `0xc34b`
- name: `Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::ConvertColorsToLess`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbf70`

## callees

- `0xc120`
- `0x21870`

## pseudocode

```c

```

## disassembly

```asm
0xc120  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xc125  stloc.0
0xc126  ldarg.0
0xc127  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0xc12c  stloc.1
0xc12d  newobj   instance void <>c__DisplayClass17_0::.ctor()
0xc132  stloc.2
0xc133  ldloc.2
0xc134  ldloc.1
0xc135  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0xc13a  stfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc13f  br       loc_C314
0xc144  ldloc.2
0xc145  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc14a  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0xc14f  brfalse  loc_C314
0xc154  ldloc.2
0xc155  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc15a  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xc15f  ldc.i4.4
0xc160  bne.un   loc_C314
0xc165  ldloc.2
0xc166  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc16b  callvirt instance int32 [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Depth()
0xc170  ldc.i4.1
0xc171  bne.un   loc_C314
0xc176  ldloc.2
0xc177  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc17c  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0xc181  isinst   [mscorlib]System.String
0xc186  ldstr    aInterface// "interface"
0xc18b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc190  brfalse  loc_C314
0xc195  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0xc19a  stloc.3
0xc19b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::DefaultColors
0xc1a0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0xc1a5  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0xc1aa  stloc.s  4
0xc1ac  br.s     loc_C1C0
0xc1ae  ldloca.s 4
0xc1b0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0xc1b5  stloc.s  5
0xc1b7  ldloc.3
0xc1b8  ldloc.s  5
0xc1ba  ldc.i4.0
0xc1bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0xc1c0  ldloca.s 4
0xc1c2  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0xc1c7  brtrue.s loc_C1AE
0xc1c9  leave.s  loc_C1D9
0xc1cb  ldloca.s 4
0xc1cd  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0xc1d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc1d8  endfinally
0xc1d9  ldloc.2
0xc1da  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc1df  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xc1e4  pop
0xc1e5  br       loc_C270
0xc1ea  ldloc.3
0xc1eb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Keys()
0xc1f0  ldloc.2
0xc1f1  ldfld    class [mscorlib]System.Func`2<string, bool> <>c__DisplayClass17_0::<>9__0
0xc1f6  dup
0xc1f7  brtrue.s loc_C211
0xc1f9  pop
0xc1fa  ldloc.2
0xc1fb  ldloc.2
0xc1fc  ldftn    instance bool <>c__DisplayClass17_0::<ConvertColorsToLess>b__0(string x)
0xc202  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xc207  dup
0xc208  stloc.s  6
0xc20a  stfld    class [mscorlib]System.Func`2<string, bool> <>c__DisplayClass17_0::<>9__0
0xc20f  ldloc.s  6
0xc211  call     T0x2B000037
0xc216  brfalse.s loc_C22F
0xc218  ldloc.3
0xc219  ldloc.2
0xc21a  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc21f  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0xc224  castclass [mscorlib]System.String
0xc229  ldc.i4.1
0xc22a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0xc22f  ldloc.0
0xc230  ldstr    a0_0// "    @{0}:"
0xc235  ldloc.2
0xc236  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc23b  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0xc240  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xc245  pop
0xc246  ldloc.2
0xc247  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc24c  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xc251  pop
0xc252  ldloc.0
0xc253  ldstr    a0_1// "{0};"
0xc258  ldloc.2
0xc259  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc25e  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0xc263  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xc268  pop
0xc269  ldloc.0
0xc26a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xc26f  pop
0xc270  ldloc.2
0xc271  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc276  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xc27b  brfalse.s loc_C28F
0xc27d  ldloc.2
0xc27e  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc283  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xc288  ldc.i4.s 0xD
0xc28a  bne.un   loc_C1EA
0xc28f  ldloc.3
0xc290  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>, bool> <>c::<>9__17_1
0xc295  dup
0xc296  brtrue.s loc_C2AF
0xc298  pop
0xc299  ldsfld   class <>c <>c::<>9
0xc29e  ldftn    instance bool <>c::<ConvertColorsToLess>b__17_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool> x)
0xc2a4  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>, bool>::.ctor(object, native int)
0xc2a9  dup
0xc2aa  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>, bool> <>c::<>9__17_1
0xc2af  call     T0x2B0000B2
0xc2b4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>>::GetEnumerator()
0xc2b9  stloc.s  7
0xc2bb  br.s     loc_C2FD
0xc2bd  ldloc.s  7
0xc2bf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>>::get_Current()
0xc2c4  stloc.s  8
0xc2c6  ldloc.0
0xc2c7  ldstr    a0_0// "    @{0}:"
0xc2cc  ldloca.s 8
0xc2ce  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>::get_Key()
0xc2d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xc2d8  pop
0xc2d9  ldloc.0
0xc2da  ldstr    a0_1// "{0};"
0xc2df  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::DefaultColors
0xc2e4  ldloca.s 8
0xc2e6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>::get_Key()
0xc2eb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0xc2f0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xc2f5  pop
0xc2f6  ldloc.0
0xc2f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xc2fc  pop
0xc2fd  ldloc.s  7
0xc2ff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc304  brtrue.s loc_C2BD
0xc306  leave.s  loc_C314
0xc308  ldloc.s  7
0xc30a  brfalse.s loc_C313
0xc30c  ldloc.s  7
0xc30e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc313  endfinally
0xc314  ldloc.2
0xc315  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc31a  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xc31f  brtrue   loc_C144
0xc324  leave.s  loc_C344
0xc326  ldloc.2
0xc327  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc32c  brfalse.s loc_C339
0xc32e  ldloc.2
0xc32f  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader <>c__DisplayClass17_0::reader
0xc334  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc339  endfinally
0xc33a  ldloc.1
0xc33b  brfalse.s loc_C343
0xc33d  ldloc.1
0xc33e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc343  endfinally
0xc344  ldloc.0
0xc345  callvirt instance string [mscorlib]System.Object::ToString()
0xc34a  ret
```
