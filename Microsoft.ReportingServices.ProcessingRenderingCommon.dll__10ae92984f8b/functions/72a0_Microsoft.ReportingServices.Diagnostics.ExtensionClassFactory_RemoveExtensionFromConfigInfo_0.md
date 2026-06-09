# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::RemoveExtensionFromConfigInfo_0

- ea: `0x72a0`
- end: `0x7513`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::RemoveExtensionFromConfigInfo_0`
- size: `627`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6d10`
- `0x6d70`
- `0x7280`

## callees

- `0x5020`
- `0x51d0`
- `0x51e0`
- `0x51f0`
- `0x5200`
- `0x5240`
- `0x5250`
- `0x5260`
- `0x5270`
- `0x72a0`

## string_xrefs

- `0x731e`: `Security`

## pseudocode

```c

```

## disassembly

```asm
0x72a0  ldarg.0
0x72a1  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Type()
0x72a6  stloc.0
0x72a7  ldloc.0
0x72a8  brfalse  loc_7512
0x72ad  ldloc.0
0x72ae  call     instance int32 [mscorlib]System.String::get_Length()
0x72b3  stloc.1
0x72b4  ldloc.1
0x72b5  ldc.i4.4
0x72b6  sub
0x72b7  switch   loc_72FE, loc_7512, loc_7350, loc_7512, loc_72E6, loc_7512, loc_7372
0x72d8  ldloc.1
0x72d9  ldc.i4.s 0xE
0x72db  beq      loc_7361
0x72e0  ldloc.1
0x72e1  ldc.i4.s 0xF
0x72e3  beq.s    loc_733F
0x72e5  ret
0x72e6  ldloc.0
0x72e7  ldc.i4.2
0x72e8  call     instance char [mscorlib]System.String::get_Chars(int32)
0x72ed  stloc.2
0x72ee  ldloc.2
0x72ef  ldc.i4.s 0x63
0x72f1  beq.s    loc_731D
0x72f3  ldloc.2
0x72f4  ldc.i4.s 0x6C
0x72f6  beq.s    loc_730C
0x72f8  ldloc.2
0x72f9  ldc.i4.s 0x73
0x72fb  beq.s    loc_732E
0x72fd  ret
0x72fe  ldloc.0
0x72ff  ldstr    aData// "Data"
0x7304  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7309  brtrue.s loc_7383
0x730b  ret
0x730c  ldloc.0
0x730d  ldstr    aDelivery// "Delivery"
0x7312  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7317  brtrue   loc_73B6
0x731c  ret
0x731d  ldloc.0
0x731e  ldstr    aSecurity// "Security"
0x7323  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7328  brtrue   loc_744F
0x732d  ret
0x732e  ldloc.0
0x732f  ldstr    aDesigner// "Designer"
0x7334  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7339  brtrue   loc_74E2
0x733e  ret
0x733f  ldloc.0
0x7340  ldstr    aEventprocessin// "EventProcessing"
0x7345  call     bool [mscorlib]System.String::op_Equality(string, string)
0x734a  brtrue   loc_73E9
0x734f  ret
0x7350  ldloc.0
0x7351  ldstr    aRender// "Render"
0x7356  call     bool [mscorlib]System.String::op_Equality(string, string)
0x735b  brtrue   loc_741C
0x7360  ret
0x7361  ldloc.0
0x7362  ldstr    aAuthentication// "Authentication"
0x7367  call     bool [mscorlib]System.String::op_Equality(string, string)
0x736c  brtrue   loc_7482
0x7371  ret
0x7372  ldloc.0
0x7373  ldstr    aDeliveryui// "DeliveryUI"
0x7378  call     bool [mscorlib]System.String::op_Equality(string, string)
0x737d  brtrue   loc_74B2
0x7382  ret
0x7383  ldarg.1
0x7384  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Data()
0x7389  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0x738e  stloc.3
0x738f  ldc.i4.0
0x7390  stloc.s  4
0x7392  ldloc.3
0x7393  ldloca.s 4
0x7395  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x739a  ldarg.1
0x739b  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Data()
0x73a0  ldarg.0
0x73a1  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x73a6  leave    loc_7512
0x73ab  ldloc.s  4
0x73ad  brfalse.s loc_73B5
0x73af  ldloc.3
0x73b0  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x73b5  endfinally
0x73b6  ldarg.1
0x73b7  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Delivery()
0x73bc  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0x73c1  stloc.3
0x73c2  ldc.i4.0
0x73c3  stloc.s  4
0x73c5  ldloc.3
0x73c6  ldloca.s 4
0x73c8  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x73cd  ldarg.1
0x73ce  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Delivery()
0x73d3  ldarg.0
0x73d4  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x73d9  leave    loc_7512
0x73de  ldloc.s  4
0x73e0  brfalse.s loc_73E8
0x73e2  ldloc.3
0x73e3  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x73e8  endfinally
0x73e9  ldarg.1
0x73ea  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Event()
0x73ef  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0x73f4  stloc.3
0x73f5  ldc.i4.0
0x73f6  stloc.s  4
0x73f8  ldloc.3
0x73f9  ldloca.s 4
0x73fb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7400  ldarg.1
0x7401  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Event()
0x7406  ldarg.0
0x7407  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x740c  leave    loc_7512
0x7411  ldloc.s  4
0x7413  brfalse.s loc_741B
0x7415  ldloc.3
0x7416  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x741b  endfinally
0x741c  ldarg.1
0x741d  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Renderer()
0x7422  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0x7427  stloc.3
0x7428  ldc.i4.0
0x7429  stloc.s  4
0x742b  ldloc.3
0x742c  ldloca.s 4
0x742e  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7433  ldarg.1
0x7434  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Renderer()
0x7439  ldarg.0
0x743a  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x743f  leave    loc_7512
0x7444  ldloc.s  4
0x7446  brfalse.s loc_744E
0x7448  ldloc.3
0x7449  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x744e  endfinally
0x744f  ldarg.1
0x7450  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Security()
0x7455  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0x745a  stloc.3
0x745b  ldc.i4.0
0x745c  stloc.s  4
0x745e  ldloc.3
0x745f  ldloca.s 4
0x7461  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7466  ldarg.1
0x7467  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Security()
0x746c  ldarg.0
0x746d  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x7472  leave    loc_7512
0x7477  ldloc.s  4
0x7479  brfalse.s loc_7481
0x747b  ldloc.3
0x747c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7481  endfinally
0x7482  ldarg.1
0x7483  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Authentication()
0x7488  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0x748d  stloc.3
0x748e  ldc.i4.0
0x748f  stloc.s  4
0x7491  ldloc.3
0x7492  ldloca.s 4
0x7494  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7499  ldarg.1
0x749a  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Authentication()
0x749f  ldarg.0
0x74a0  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x74a5  leave.s  loc_7512
0x74a7  ldloc.s  4
0x74a9  brfalse.s loc_74B1
0x74ab  ldloc.3
0x74ac  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x74b1  endfinally
0x74b2  ldarg.1
0x74b3  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_DeliveryUI()
0x74b8  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0x74bd  stloc.3
0x74be  ldc.i4.0
0x74bf  stloc.s  4
0x74c1  ldloc.3
0x74c2  ldloca.s 4
0x74c4  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x74c9  ldarg.1
0x74ca  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_DeliveryUI()
0x74cf  ldarg.0
0x74d0  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x74d5  leave.s  loc_7512
0x74d7  ldloc.s  4
0x74d9  brfalse.s loc_74E1
0x74db  ldloc.3
0x74dc  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x74e1  endfinally
0x74e2  ldarg.1
0x74e3  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Designer()
0x74e8  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0x74ed  stloc.3
0x74ee  ldc.i4.0
0x74ef  stloc.s  4
0x74f1  ldloc.3
0x74f2  ldloca.s 4
0x74f4  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x74f9  ldarg.1
0x74fa  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Designer()
0x74ff  ldarg.0
0x7500  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x7505  leave.s  loc_7512
0x7507  ldloc.s  4
0x7509  brfalse.s loc_7511
0x750b  ldloc.3
0x750c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7511  endfinally
0x7512  ret
```
