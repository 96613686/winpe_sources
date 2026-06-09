# Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetWmiObjectEnumerator

- ea: `0x19c0`
- end: `0x19f1`
- name: `Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetWmiObjectEnumerator`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a40`
- `0x1a80`
- `0x1b40`

## callees

- `0x15f0`
- `0x19c0`

## pseudocode

```c

```

## disassembly

```asm
0x19c0  ldarg.1
0x19c1  newobj   instance void [System.Management]System.Management.ManagementClass::.ctor(string)
0x19c6  stloc.0
0x19c7  ldnull
0x19c8  stloc.1
0x19c9  ldloc.0
0x19ca  callvirt instance class [System.Management]System.Management.ManagementObjectCollection [System.Management]System.Management.ManagementClass::GetInstances()
0x19cf  callvirt instance class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator [System.Management]System.Management.ManagementObjectCollection::GetEnumerator()
0x19d4  stloc.1
0x19d5  ldloc.1
0x19d6  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0x19db  pop
0x19dc  leave.s  loc_19EF
0x19de  ldstr    aExceptionThrow// "Exception thrown while retrieving syste"...
0x19e3  call     T0x2B00000A
0x19e8  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x19ed  leave.s  loc_19EF
0x19ef  ldloc.1
0x19f0  ret
```
