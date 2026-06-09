# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::GetRenderFormats

- ea: `0x21d0`
- end: `0x22a5`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::GetRenderFormats`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x21d0`
- `0x28c0`

## pseudocode

```c

```

## disassembly

```asm
0x21d0  ldarg.0
0x21d1  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_ReportServerInformation()
0x21d6  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation::get_ServerSettings()
0x21db  ldarg.0
0x21dc  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_ReportServerInformation()
0x21e1  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation::get_RenderingExtension()
0x21e6  stloc.0
0x21e7  ldc.i4.0
0x21e8  newarr   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ValidValue
0x21ed  stloc.1
0x21ee  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x21f3  stloc.2
0x21f4  stloc.3
0x21f5  ldc.i4.0
0x21f6  stloc.s  4
0x21f8  br.s     loc_2224
0x21fa  ldloc.3
0x21fb  ldloc.s  4
0x21fd  ldelem.ref
0x21fe  stloc.s  5
0x2200  ldloc.s  5
0x2202  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x2207  ldstr    aRenderFormat// "RENDER_FORMAT"
0x220c  ldc.i4.5
0x220d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2212  brtrue.s loc_221E
0x2214  ldloc.s  5
0x2216  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ValidValue[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_ValidValues()
0x221b  stloc.1
0x221c  br.s     loc_222B
0x221e  ldloc.s  4
0x2220  ldc.i4.1
0x2221  add
0x2222  stloc.s  4
0x2224  ldloc.s  4
0x2226  ldloc.3
0x2227  ldlen
0x2228  conv.i4
0x2229  blt.s    loc_21FA
0x222b  ldloc.0
0x222c  stloc.s  6
0x222e  ldc.i4.0
0x222f  stloc.s  4
0x2231  br.s     loc_2287
0x2233  ldloc.s  6
0x2235  ldloc.s  4
0x2237  ldelem.ref
0x2238  stloc.s  7
0x223a  ldloc.1
0x223b  stloc.s  8
0x223d  ldc.i4.0
0x223e  stloc.s  9
0x2240  br.s     loc_2279
0x2242  ldloc.s  8
0x2244  ldloc.s  9
0x2246  ldelem.ref
0x2247  stloc.s  0xA
0x2249  ldloc.s  7
0x224b  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension::get_Name()
0x2250  ldloc.s  0xA
0x2252  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ValidValue::get_Value()
0x2257  ldc.i4.5
0x2258  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x225d  brtrue.s loc_2273
0x225f  ldloc.s  7
0x2261  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension::get_Visible()
0x2266  brfalse.s loc_2281
0x2268  ldloc.2
0x2269  ldloc.s  7
0x226b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x2270  pop
0x2271  br.s     loc_2281
0x2273  ldloc.s  9
0x2275  ldc.i4.1
0x2276  add
0x2277  stloc.s  9
0x2279  ldloc.s  9
0x227b  ldloc.s  8
0x227d  ldlen
0x227e  conv.i4
0x227f  blt.s    loc_2242
0x2281  ldloc.s  4
0x2283  ldc.i4.1
0x2284  add
0x2285  stloc.s  4
0x2287  ldloc.s  4
0x2289  ldloc.s  6
0x228b  ldlen
0x228c  conv.i4
0x228d  blt.s    loc_2233
0x228f  ldloc.2
0x2290  ldtoken  [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension
0x2295  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x229a  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x229f  castclass class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension[]
0x22a4  ret
```
