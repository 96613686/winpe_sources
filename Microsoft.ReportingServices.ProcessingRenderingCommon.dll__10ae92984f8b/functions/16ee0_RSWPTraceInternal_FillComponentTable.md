# RSWPTraceInternal::FillComponentTable

- ea: `0x16ee0`
- end: `0x1702f`
- name: `RSWPTraceInternal::FillComponentTable`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16c20`

## callees

- `0x16ee0`

## string_xrefs

- `0x16f36`: `bad configuration element`
- `0x16f86`: `bad component trace level in configuration file`

## pseudocode

```c

```

## disassembly

```asm
0x16ee0  ldc.i4.2
0x16ee1  newarr   [mscorlib]System.Char
0x16ee6  stloc.0
0x16ee7  ldloc.0
0x16ee8  ldc.i4.0
0x16ee9  ldc.i4.s 0x2C
0x16eeb  stelem.i2
0x16eec  ldloc.0
0x16eed  ldc.i4.1
0x16eee  ldc.i4.s 0x3B
0x16ef0  stelem.i2
0x16ef1  ldarg.1
0x16ef2  ldloc.0
0x16ef3  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x16ef8  stloc.1
0x16ef9  ldc.i4.0
0x16efa  stloc.s  4
0x16efc  br       loc_16FC2
0x16f01  ldloc.1
0x16f02  ldloc.s  4
0x16f04  ldelem.ref
0x16f05  callvirt instance string [mscorlib]System.String::Trim()
0x16f0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16f0f  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x16f14  stloc.s  5
0x16f16  ldc.i4.1
0x16f17  newarr   [mscorlib]System.Char
0x16f1c  stloc.s  6
0x16f1e  ldloc.s  6
0x16f20  ldc.i4.0
0x16f21  ldc.i4.s 0x3A
0x16f23  stelem.i2
0x16f24  ldloc.s  5
0x16f26  ldloc.s  6
0x16f28  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x16f2d  stloc.s  7
0x16f2f  ldloc.s  7
0x16f31  ldlen
0x16f32  conv.i4
0x16f33  ldc.i4.2
0x16f34  ble.s    loc_16F48
0x16f36  ldstr    aBadConfigurati// "bad configuration element"
0x16f3b  ldloc.s  5
0x16f3d  call     string [mscorlib]System.String::Concat(string, string)
0x16f42  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x16f47  throw
0x16f48  ldloc.s  7
0x16f4a  ldc.i4.0
0x16f4b  ldelem.ref
0x16f4c  stloc.s  8
0x16f4e  ldloc.s  7
0x16f50  ldlen
0x16f51  conv.i4
0x16f52  ldc.i4.2
0x16f53  bne.un.s loc_16FA9
0x16f55  ldloc.s  7
0x16f57  ldc.i4.1
0x16f58  ldelem.ref
0x16f59  brfalse.s loc_16FA9
0x16f5b  ldloc.s  7
0x16f5d  ldc.i4.1
0x16f5e  ldelem.ref
0x16f5f  stloc.s  9
0x16f61  ldarg.0
0x16f62  ldfld    valuetype [System]System.Diagnostics.TraceLevel RSWPTraceInternal::m_defaultTraceLevel
0x16f67  stloc.s  0xA
0x16f69  ldloc.s  0xA
0x16f6b  box      [System]System.Diagnostics.TraceLevel
0x16f70  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x16f75  ldloc.s  9
0x16f77  ldc.i4.1
0x16f78  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x16f7d  unbox.any [System]System.Diagnostics.TraceLevel
0x16f82  stloc.s  0xA
0x16f84  leave.s  loc_16F98
0x16f86  ldstr    aBadComponentTr// "bad component trace level in configurat"...
0x16f8b  ldloc.s  9
0x16f8d  call     string [mscorlib]System.String::Concat(string, string)
0x16f92  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x16f97  throw
0x16f98  ldarg.0
0x16f99  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> RSWPTraceInternal::m_Components
0x16f9e  ldloc.s  8
0x16fa0  ldloc.s  0xA
0x16fa2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::Add(var<u1>, !!T0)
0x16fa7  br.s     loc_16FBC
0x16fa9  ldarg.0
0x16faa  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> RSWPTraceInternal::m_Components
0x16faf  ldloc.s  5
0x16fb1  ldarg.0
0x16fb2  ldfld    valuetype [System]System.Diagnostics.TraceLevel RSWPTraceInternal::m_defaultTraceLevel
0x16fb7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::Add(var<u1>, !!T0)
0x16fbc  ldloc.s  4
0x16fbe  ldc.i4.1
0x16fbf  add
0x16fc0  stloc.s  4
0x16fc2  ldloc.s  4
0x16fc4  ldloc.1
0x16fc5  ldlen
0x16fc6  conv.i4
0x16fc7  blt      loc_16F01
0x16fcc  ldc.i4.s 0x29
0x16fce  stloc.s  0xB
0x16fd0  ldloca.s 0xB
0x16fd2  constrained. [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace/TraceComponents
0x16fd8  callvirt instance string [mscorlib]System.Object::ToString()
0x16fdd  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x16fe2  stloc.2
0x16fe3  ldarg.0
0x16fe4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> RSWPTraceInternal::m_Components
0x16fe9  ldloc.2
0x16fea  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::Remove(var<u1>)
0x16fef  pop
0x16ff0  ldarg.0
0x16ff1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> RSWPTraceInternal::m_Components
0x16ff6  ldloc.2
0x16ff7  ldc.i4.0
0x16ff8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::Add(var<u1>, !!T0)
0x16ffd  ldc.i4.s 0x32
0x16fff  stloc.s  0xB
0x17001  ldloca.s 0xB
0x17003  constrained. [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace/TraceComponents
0x17009  callvirt instance string [mscorlib]System.Object::ToString()
0x1700e  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x17013  stloc.3
0x17014  ldarg.0
0x17015  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> RSWPTraceInternal::m_Components
0x1701a  ldloc.3
0x1701b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::Remove(var<u1>)
0x17020  pop
0x17021  ldarg.0
0x17022  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> RSWPTraceInternal::m_Components
0x17027  ldloc.3
0x17028  ldc.i4.0
0x17029  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::Add(var<u1>, !!T0)
0x1702e  ret
```
