# Microsoft.Office.Server.Security.SecurityContext::InitializeDiagnosticSettings

- ea: `0x2cc20`
- end: `0x2ccaf`
- name: `Microsoft.Office.Server.Security.SecurityContext::InitializeDiagnosticSettings`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x2cb80`

## callees

- `0x2cc20`

## string_xrefs

- `0x2cc3c`: `SOFTWARE\Microsoft\Shared Tools\Web Server Extensions\Diagnostics`
- `0x2cc4c`: `SecurityContextStackTrace`

## pseudocode

```c

```

## disassembly

```asm
0x2cc20  ldc.i4.0
0x2cc21  stloc.2
0x2cc22  ldsfld   object Microsoft.Office.Server.Security.SecurityContext::s_DiagnosticsInitializationLock
0x2cc27  dup
0x2cc28  stloc.3
0x2cc29  ldloca.s 2
0x2cc2b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2cc30  ldsfld   valuetype DiagnosticSettings Microsoft.Office.Server.Security.SecurityContext::s_DiagnosticSettings
0x2cc35  brtrue.s loc_2CCA2
0x2cc37  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x2cc3c  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\Shared Tools\\Web "...
0x2cc41  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x2cc46  stloc.0
0x2cc47  ldloc.0
0x2cc48  brfalse.s loc_2CC76
0x2cc4a  ldc.i4.0
0x2cc4b  ldloc.0
0x2cc4c  ldstr    aSecuritycontex// "SecurityContextStackTrace"
0x2cc51  ldc.i4.0
0x2cc52  box      [mscorlib]System.Int32
0x2cc57  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x2cc5c  unbox.any [mscorlib]System.Int32
0x2cc61  ceq
0x2cc63  ldc.i4.0
0x2cc64  ceq
0x2cc66  stloc.1
0x2cc67  ldloc.1
0x2cc68  brfalse.s loc_2CC76
0x2cc6a  ldsfld   valuetype DiagnosticSettings Microsoft.Office.Server.Security.SecurityContext::s_DiagnosticSettings
0x2cc6f  ldc.i4.1
0x2cc70  or
0x2cc71  stsfld   valuetype DiagnosticSettings Microsoft.Office.Server.Security.SecurityContext::s_DiagnosticSettings
0x2cc76  leave.s  loc_2CC82
0x2cc78  ldloc.0
0x2cc79  brfalse.s loc_2CC81
0x2cc7b  ldloc.0
0x2cc7c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2cc81  endfinally
0x2cc82  ldsfld   valuetype DiagnosticSettings Microsoft.Office.Server.Security.SecurityContext::s_DiagnosticSettings
0x2cc87  brtrue.s loc_2CC93
0x2cc89  ldc.i4   0x8000
0x2cc8e  stsfld   valuetype DiagnosticSettings Microsoft.Office.Server.Security.SecurityContext::s_DiagnosticSettings
0x2cc93  leave.s  loc_2CCA2
0x2cc95  pop
0x2cc96  ldc.i4   0x8000
0x2cc9b  stsfld   valuetype DiagnosticSettings Microsoft.Office.Server.Security.SecurityContext::s_DiagnosticSettings
0x2cca0  leave.s  loc_2CCA2
0x2cca2  leave.s  loc_2CCAE
0x2cca4  ldloc.2
0x2cca5  brfalse.s loc_2CCAD
0x2cca7  ldloc.3
0x2cca8  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2ccad  endfinally
0x2ccae  ret
```
