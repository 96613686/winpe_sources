# Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::ParseCredential

- ea: `0x29d0`
- end: `0x2a34`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::ParseCredential`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x28c0`

## callees

- `0x2940`
- `0x2950`
- `0x2960`
- `0x2980`
- `0x2990`
- `0x29d0`

## pseudocode

```c

```

## disassembly

```asm
0x29d0  ldarg.1
0x29d1  brtrue.s loc_29DE
0x29d3  ldstr    aCredentialstr// "credentialStr"
0x29d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x29dd  throw
0x29de  ldarg.1
0x29df  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29e4  brfalse.s loc_29EF
0x29e6  ldarg.0
0x29e7  ldarg.1
0x29e8  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::set_Username(string value)
0x29ed  br.s     loc_2A22
0x29ef  ldarg.1
0x29f0  ldc.i4.1
0x29f1  newarr   [mscorlib]System.Char
0x29f6  dup
0x29f7  ldc.i4.0
0x29f8  ldc.i4.s 0x5C
0x29fa  stelem.i2
0x29fb  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2a00  stloc.0
0x2a01  ldloc.0
0x2a02  ldlen
0x2a03  conv.i4
0x2a04  ldc.i4.2
0x2a05  bne.un.s loc_2A1B
0x2a07  ldarg.0
0x2a08  ldloc.0
0x2a09  ldc.i4.0
0x2a0a  ldelem.ref
0x2a0b  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::set_Domain(string value)
0x2a10  ldarg.0
0x2a11  ldloc.0
0x2a12  ldc.i4.1
0x2a13  ldelem.ref
0x2a14  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::set_Username(string value)
0x2a19  br.s     loc_2A22
0x2a1b  ldarg.0
0x2a1c  ldarg.1
0x2a1d  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::set_Username(string value)
0x2a22  ldarg.0
0x2a23  ldarg.0
0x2a24  call     instance string Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::get_Username()
0x2a29  call     bool Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::IsUPNFormat(string accountName)
0x2a2e  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::set_IsUsernameUPN(bool value)
0x2a33  ret
```
