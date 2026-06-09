# <ToIEnumerable>d__1::MoveNext

- ea: `0x5770`
- end: `0x57be`
- name: `<ToIEnumerable>d__1::MoveNext`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x5770`

## pseudocode

```c

```

## disassembly

```asm
0x5770  ldarg.0
0x5771  ldfld    int32 <ToIEnumerable>d__1::<>1__state
0x5776  stloc.0
0x5777  ldloc.0
0x5778  brfalse.s loc_5780
0x577a  ldloc.0
0x577b  ldc.i4.1
0x577c  beq.s    loc_57A8
0x577e  ldc.i4.0
0x577f  ret
0x5780  ldarg.0
0x5781  ldc.i4.m1
0x5782  stfld    int32 <ToIEnumerable>d__1::<>1__state
0x5787  br.s     loc_57AF
0x5789  ldarg.0
0x578a  ldarg.0
0x578b  ldfld    class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator <ToIEnumerable>d__1::enumerator
0x5790  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0x5795  isinst   [System.Management]System.Management.ManagementObject
0x579a  stfld    class [System.Management]System.Management.ManagementObject <ToIEnumerable>d__1::<>2__current
0x579f  ldarg.0
0x57a0  ldc.i4.1
0x57a1  stfld    int32 <ToIEnumerable>d__1::<>1__state
0x57a6  ldc.i4.1
0x57a7  ret
0x57a8  ldarg.0
0x57a9  ldc.i4.m1
0x57aa  stfld    int32 <ToIEnumerable>d__1::<>1__state
0x57af  ldarg.0
0x57b0  ldfld    class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator <ToIEnumerable>d__1::enumerator
0x57b5  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0x57ba  brtrue.s loc_5789
0x57bc  ldc.i4.0
0x57bd  ret
```
