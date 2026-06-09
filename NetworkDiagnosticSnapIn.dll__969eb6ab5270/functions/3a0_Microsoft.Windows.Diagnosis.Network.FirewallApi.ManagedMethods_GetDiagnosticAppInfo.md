# Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::GetDiagnosticAppInfo

- ea: `0x3a0`
- end: `0x3ff`
- name: `Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::GetDiagnosticAppInfo`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1f0`
- `0x260`
- `0x310`
- `0x360`
- `0x3a0`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  call     class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp> Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::GetFWDiagnosticApps()
0x3a5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo>::.ctor()
0x3aa  stloc.0
0x3ab  ldnull
0x3ac  stloc.1
0x3ad  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp>::GetEnumerator()
0x3b2  stloc.2
0x3b3  br.s     loc_3E4
0x3b5  ldloca.s 2
0x3b7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp>::get_Current()
0x3bc  stloc.3
0x3bd  ldloc.3
0x3be  ldloc.0
0x3bf  call     bool Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::AppAlreadyExists(valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp app, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo> diagnosticAppInfoList)
0x3c4  brtrue.s loc_3E4
0x3c6  ldloc.3
0x3c7  ldfld    string Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp::AppPath
0x3cc  call     string Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::GetFriendlyName(string appPath)
0x3d1  stloc.1
0x3d2  ldloc.0
0x3d3  ldloc.1
0x3d4  ldloc.3
0x3d5  ldfld    string Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp::AppPath
0x3da  newobj   instance void Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo::.ctor(string friendlyName, string path)
0x3df  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo>::Add(var<u1>)
0x3e4  ldloca.s 2
0x3e6  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp>::MoveNext()
0x3eb  brtrue.s loc_3B5
0x3ed  leave.s  loc_3FD
0x3ef  ldloca.s 2
0x3f1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp>
0x3f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3fc  endfinally
0x3fd  ldloc.0
0x3fe  ret
```
