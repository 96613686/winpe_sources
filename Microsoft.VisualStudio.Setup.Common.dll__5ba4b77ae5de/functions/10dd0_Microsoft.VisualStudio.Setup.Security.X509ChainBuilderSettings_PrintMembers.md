# Microsoft.VisualStudio.Setup.Security.X509ChainBuilderSettings::PrintMembers

- ea: `0x10dd0`
- end: `0x10e73`
- name: `Microsoft.VisualStudio.Setup.Security.X509ChainBuilderSettings::PrintMembers`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x10d90`

## callees

- `0x10d10`
- `0x10d30`
- `0x10d50`
- `0x10d70`

## pseudocode

```c

```

## disassembly

```asm
0x10dd0  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x10dd5  ldarg.1
0x10dd6  ldstr    aUsemachinecont// "UseMachineContext = "
0x10ddb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10de0  pop
0x10de1  ldarg.1
0x10de2  ldarg.0
0x10de3  call     instance bool Microsoft.VisualStudio.Setup.Security.X509ChainBuilderSettings::get_UseMachineContext()
0x10de8  stloc.0
0x10de9  ldloca.s 0
0x10deb  constrained. [mscorlib]System.Boolean
0x10df1  callvirt instance string [mscorlib]System.Object::ToString()
0x10df6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10dfb  pop
0x10dfc  ldarg.1
0x10dfd  ldstr    aAdditionalveri// ", AdditionalVerificationFlags = "
0x10e02  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10e07  pop
0x10e08  ldarg.1
0x10e09  ldarg.0
0x10e0a  call     instance valuetype [System]System.Security.Cryptography.X509Certificates.X509VerificationFlags Microsoft.VisualStudio.Setup.Security.X509ChainBuilderSettings::get_AdditionalVerificationFlags()
0x10e0f  stloc.1
0x10e10  ldloca.s 1
0x10e12  constrained. [System]System.Security.Cryptography.X509Certificates.X509VerificationFlags
0x10e18  callvirt instance string [mscorlib]System.Object::ToString()
0x10e1d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10e22  pop
0x10e23  ldarg.1
0x10e24  ldstr    aRevocationmode// ", RevocationMode = "
0x10e29  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10e2e  pop
0x10e2f  ldarg.1
0x10e30  ldarg.0
0x10e31  call     instance valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationMode Microsoft.VisualStudio.Setup.Security.X509ChainBuilderSettings::get_RevocationMode()
0x10e36  stloc.2
0x10e37  ldloca.s 2
0x10e39  constrained. [System]System.Security.Cryptography.X509Certificates.X509RevocationMode
0x10e3f  callvirt instance string [mscorlib]System.Object::ToString()
0x10e44  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10e49  pop
0x10e4a  ldarg.1
0x10e4b  ldstr    aOnlinetimeout// ", OnlineTimeout = "
0x10e50  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10e55  pop
0x10e56  ldarg.1
0x10e57  ldarg.0
0x10e58  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Security.X509ChainBuilderSettings::get_OnlineTimeout()
0x10e5d  stloc.3
0x10e5e  ldloca.s 3
0x10e60  constrained. [mscorlib]System.TimeSpan
0x10e66  callvirt instance string [mscorlib]System.Object::ToString()
0x10e6b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10e70  pop
0x10e71  ldc.i4.1
0x10e72  ret
```
