# Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetCpuObject

- ea: `0x1a40`
- end: `0x1a75`
- name: `Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetCpuObject`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1af0`
- `0x1b10`

## callees

- `0x1930`
- `0x19c0`
- `0x1a40`

## pseudocode

```c

```

## disassembly

```asm
0x1a40  ldarg.0
0x1a41  ldstr    aWin32Processor// "Win32_Processor"
0x1a46  call     instance class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetWmiObjectEnumerator(string wmiClassName)
0x1a4b  ldstr    aProcessortype// "ProcessorType"
0x1a50  ldsfld   class [mscorlib]System.Predicate`1<string> <>c::<>9__2_0
0x1a55  dup
0x1a56  brtrue.s loc_1A6F
0x1a58  pop
0x1a59  ldsfld   class <>c <>c::<>9
0x1a5e  ldftn    instance bool <>c::<GetCpuObject>b__2_0(string type)
0x1a64  newobj   instance void class [mscorlib]System.Predicate`1<string>::.ctor(object, native int)
0x1a69  dup
0x1a6a  stsfld   class [mscorlib]System.Predicate`1<string> <>c::<>9__2_0
0x1a6f  call     class [System.Management]System.Management.ManagementObject Microsoft.BIServer.HostingEnvironment.ManagementObjectEnumeratorExtensions::SelectFirstBy(class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator enumerator, string propertyName, class [mscorlib]System.Predicate`1<string> criteria)
0x1a74  ret
```
