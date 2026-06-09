# NGenTask.BindingContext::Equals

- ea: `0x33b0`
- end: `0x33e6`
- name: `NGenTask.BindingContext::Equals`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x32a0`
- `0x32c0`
- `0x33b0`

## pseudocode

```c

```

## disassembly

```asm
0x33b0  ldarg.1
0x33b1  isinst   NGenTask.BindingContext
0x33b6  stloc.0
0x33b7  ldloc.0
0x33b8  brtrue.s loc_33BC
0x33ba  ldc.i4.0
0x33bb  ret
0x33bc  ldarg.0
0x33bd  call     instance string NGenTask.BindingContext::get_NGenArgs()
0x33c2  ldloc.0
0x33c3  callvirt instance string NGenTask.BindingContext::get_NGenArgs()
0x33c8  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x33cd  brtrue.s loc_33E4
0x33cf  ldarg.0
0x33d0  call     instance string NGenTask.BindingContext::get_Container()
0x33d5  ldloc.0
0x33d6  callvirt instance string NGenTask.BindingContext::get_Container()
0x33db  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x33e0  ldc.i4.0
0x33e1  ceq
0x33e3  ret
0x33e4  ldc.i4.0
0x33e5  ret
```
