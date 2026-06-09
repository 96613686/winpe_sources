# Microsoft.BIServer.HostingEnvironment.ManagementObjectEnumeratorExtensions::ToIEnumerable

- ea: `0x19a0`
- end: `0x19af`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementObjectEnumeratorExtensions::ToIEnumerable`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1b40`

## callees

- `0x5740`

## pseudocode

```c

```

## disassembly

```asm
0x19a0  ldc.i4.s 0xFE
0x19a2  newobj   instance void <ToIEnumerable>d__1::.ctor(int32 <>1__state)
0x19a7  dup
0x19a8  ldarg.0
0x19a9  stfld    class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator <ToIEnumerable>d__1::<>3__enumerator
0x19ae  ret
```
