# NGenTask.ILAssembly::Equals

- ea: `0x34d0`
- end: `0x3506`
- name: `NGenTask.ILAssembly::Equals`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x3460`
- `0x3480`
- `0x34d0`

## pseudocode

```c

```

## disassembly

```asm
0x34d0  ldarg.1
0x34d1  isinst   NGenTask.ILAssembly
0x34d6  stloc.0
0x34d7  ldloc.0
0x34d8  brtrue.s loc_34DC
0x34da  ldc.i4.0
0x34db  ret
0x34dc  ldarg.0
0x34dd  call     instance string NGenTask.ILAssembly::get_NGenArgs()
0x34e2  ldloc.0
0x34e3  callvirt instance string NGenTask.ILAssembly::get_NGenArgs()
0x34e8  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x34ed  brtrue.s loc_3504
0x34ef  ldarg.0
0x34f0  call     instance string NGenTask.ILAssembly::get_Container()
0x34f5  ldloc.0
0x34f6  callvirt instance string NGenTask.ILAssembly::get_Container()
0x34fb  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3500  ldc.i4.0
0x3501  ceq
0x3503  ret
0x3504  ldc.i4.0
0x3505  ret
```
