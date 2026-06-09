# Microsoft.ReportingServices.ReportIntermediateFormat.Visibility::ComputeHidden

- ea: `0x135400`
- end: `0x135499`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Visibility::ComputeHidden`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x125340`
- `0x139b90`

## callees

- `0x75350`
- `0x11ae40`
- `0x11ae70`
- `0x11aee0`
- `0x134f50`
- `0x134fb0`
- `0x135050`
- `0x135400`
- `0x1354a0`

## string_xrefs

- `0x135455`: `Missing Persisted Toggle Receiver -> Sender Link`

## pseudocode

```c

```

## disassembly

```asm
0x135400  ldarg.3
0x135401  ldc.i4.0
0x135402  stind.i1
0x135403  ldc.i4.0
0x135404  stloc.0
0x135405  ldarg.0
0x135406  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Visibility Microsoft.ReportingServices.ReportIntermediateFormat.IVisibilityOwner::get_Visibility()
0x13540b  stloc.1
0x13540c  ldloc.1
0x13540d  brfalse  loc_135497
0x135412  ldloc.1
0x135413  call     valuetype Microsoft.ReportingServices.OnDemandReportRendering.SharedHiddenState Microsoft.ReportingServices.ReportIntermediateFormat.Visibility::GetSharedHidden(class Microsoft.ReportingServices.ReportIntermediateFormat.Visibility visibility)
0x135418  stloc.2
0x135419  ldloc.2
0x13541a  switch   loc_13542D, loc_135431, loc_135435
0x13542b  br.s     loc_13548C
0x13542d  ldc.i4.1
0x13542e  stloc.0
0x13542f  br.s     loc_135497
0x135431  ldc.i4.0
0x135432  stloc.0
0x135433  br.s     loc_135497
0x135435  ldarg.0
0x135436  ldarg.1
0x135437  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.IVisibilityOwner::ComputeStartHidden(class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext renderingContext)
0x13543c  stloc.0
0x13543d  ldloc.1
0x13543e  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Visibility::get_IsToggleReceiver()
0x135443  brfalse.s loc_135497
0x135445  ldloc.1
0x135446  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.TextBox Microsoft.ReportingServices.ReportIntermediateFormat.Visibility::get_ToggleSender()
0x13544b  stloc.3
0x13544c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x135451  ldloc.3
0x135452  ldnull
0x135453  cgt.un
0x135455  ldstr    aMissingPersist// "Missing Persisted Toggle Receiver -> Se"...
0x13545a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x13545f  ldarg.0
0x135460  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.IVisibilityOwner::get_SenderUniqueName()
0x135465  stloc.s  4
0x135467  ldloc.s  4
0x135469  brfalse.s loc_13547A
0x13546b  ldarg.1
0x13546c  ldloc.s  4
0x13546e  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::IsSenderToggled(string uniqueName)
0x135473  brfalse.s loc_13547A
0x135475  ldloc.0
0x135476  ldc.i4.0
0x135477  ceq
0x135479  stloc.0
0x13547a  ldloc.0
0x13547b  brtrue.s loc_135487
0x13547d  ldloc.0
0x13547e  ldarg.0
0x13547f  ldarg.2
0x135480  ldarg.1
0x135481  call     bool Microsoft.ReportingServices.ReportIntermediateFormat.Visibility::ComputeDeepHidden(bool hidden, class Microsoft.ReportingServices.ReportIntermediateFormat.IVisibilityOwner visibilityOwner, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.ToggleCascadeDirection direction, class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext renderingContext)
0x135486  stloc.0
0x135487  ldarg.3
0x135488  ldc.i4.1
0x135489  stind.i1
0x13548a  br.s     loc_135497
0x13548c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x135491  ldc.i4.0
0x135492  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x135497  ldloc.0
0x135498  ret
```
