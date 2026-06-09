# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ExtractDataFeedQueriesFromDeviceInfo

- ea: `0x1c70`
- end: `0x1ccf`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ExtractDataFeedQueriesFromDeviceInfo`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1bc0`

## callees

- `0x1c70`
- `0x50d0`

## pseudocode

```c

```

## disassembly

```asm
0x1c70  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1c75  stloc.0
0x1c76  ldarg.0
0x1c77  ldarg.1
0x1c78  ldstr    aTop// "Top"
0x1c7d  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x1c82  stloc.1
0x1c83  ldloc.1
0x1c84  brfalse.s loc_1CA1
0x1c86  ldloc.1
0x1c87  ldloca.s 3
0x1c89  call     bool [mscorlib]System.UInt32::TryParse(string, unsigned int32&)
0x1c8e  brfalse.s loc_1CA1
0x1c90  ldloc.0
0x1c91  ldstr    aTop// "Top"
0x1c96  ldloc.3
0x1c97  box      [mscorlib]System.UInt32
0x1c9c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1ca1  ldarg.0
0x1ca2  ldarg.1
0x1ca3  ldstr    aSelect// "Select"
0x1ca8  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x1cad  stloc.2
0x1cae  ldloc.2
0x1caf  brfalse.s loc_1CCD
0x1cb1  ldloc.0
0x1cb2  ldstr    aSelect// "Select"
0x1cb7  ldloc.2
0x1cb8  ldc.i4.1
0x1cb9  newarr   [mscorlib]System.Char
0x1cbe  dup
0x1cbf  ldc.i4.0
0x1cc0  ldc.i4.s 0x2C
0x1cc2  stelem.i2
0x1cc3  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1cc8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1ccd  ldloc.0
0x1cce  ret
```
