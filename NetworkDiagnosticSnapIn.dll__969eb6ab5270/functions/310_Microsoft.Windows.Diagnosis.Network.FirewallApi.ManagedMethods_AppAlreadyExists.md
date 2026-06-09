# Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::AppAlreadyExists

- ea: `0x310`
- end: `0x356`
- name: `Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::AppAlreadyExists`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x230`
- `0x310`

## pseudocode

```c

```

## disassembly

```asm
0x310  ldarg.1
0x311  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo>::GetEnumerator()
0x316  stloc.0
0x317  br.s     loc_339
0x319  ldloca.s 0
0x31b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo>::get_Current()
0x320  stloc.1
0x321  ldloc.1
0x322  callvirt instance string Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo::get_Path()
0x327  ldarg.0
0x328  ldfld    string Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp::AppPath
0x32d  ldc.i4.1
0x32e  call     int32 [mscorlib]System.String::Compare(string, string, bool)
0x333  brtrue.s loc_339
0x335  ldc.i4.1
0x336  stloc.2
0x337  leave.s  loc_354
0x339  ldloca.s 0
0x33b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo>::MoveNext()
0x340  brtrue.s loc_319
0x342  leave.s  loc_352
0x344  ldloca.s 0
0x346  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo>
0x34c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x351  endfinally
0x352  ldc.i4.0
0x353  ret
0x354  ldloc.2
0x355  ret
```
