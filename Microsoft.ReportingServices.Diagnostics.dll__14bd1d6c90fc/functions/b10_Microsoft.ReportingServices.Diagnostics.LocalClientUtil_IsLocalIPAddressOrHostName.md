# Microsoft.ReportingServices.Diagnostics.LocalClientUtil::IsLocalIPAddressOrHostName

- ea: `0xb10`
- end: `0xb52`
- name: `Microsoft.ReportingServices.Diagnostics.LocalClientUtil::IsLocalIPAddressOrHostName`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x10d40`

## callees

- `0xa70`
- `0xb10`
- `0xda0`
- `0x10170`

## pseudocode

```c

```

## disassembly

```asm
0xb10  ldarg.0
0xb11  call     bool Microsoft.ReportingServices.Diagnostics.WebUtil::IsWellKnownLocalServer(string server)
0xb16  brfalse.s loc_B1A
0xb18  ldc.i4.1
0xb19  ret
0xb1a  nop
0xb1b  newobj   instance void <>c__DisplayClass3_0::.ctor()
0xb20  stloc.0
0xb21  ldloc.0
0xb22  call     class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Net.IPAddress> Microsoft.ReportingServices.Diagnostics.LocalClientUtil::get_LocalIPAddresses()
0xb27  stfld    class [System.Core]System.Collections.Generic.HashSet`1<class [System]System.Net.IPAddress> <>c__DisplayClass3_0::addresses
0xb2c  ldarg.0
0xb2d  call     class [System]System.Net.IPHostEntry [System]System.Net.Dns::GetHostEntry(string)
0xb32  callvirt instance class [System]System.Net.IPAddress[] [System]System.Net.IPHostEntry::get_AddressList()
0xb37  ldloc.0
0xb38  ldftn    instance bool <>c__DisplayClass3_0::<IsLocalIPAddressOrHostName>b__0(class [System]System.Net.IPAddress a)
0xb3e  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Net.IPAddress, bool>::.ctor(object, native int)
0xb43  call     T0x2B000005
0xb48  stloc.1
0xb49  leave.s  loc_B50
0xb4b  pop
0xb4c  ldc.i4.0
0xb4d  stloc.1
0xb4e  leave.s  loc_B50
0xb50  ldloc.1
0xb51  ret
```
