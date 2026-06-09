# NGenTask.ILAssembly::.ctor

- ea: `0x34a0`
- end: `0x34cc`
- name: `NGenTask.ILAssembly::.ctor`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x310`
- `0x3c10`

## callees

- `0x32a0`
- `0x32c0`
- `0x3450`
- `0x3470`
- `0x3490`

## pseudocode

```c

```

## disassembly

```asm
0x34a0  ldarg.0
0x34a1  call     instance void [mscorlib]System.Object::.ctor()
0x34a6  ldarg.0
0x34a7  ldarg.2
0x34a8  call     instance void NGenTask.ILAssembly::set_AssemblyName(string value)
0x34ad  ldarg.0
0x34ae  ldarg.1
0x34af  callvirt instance string NGenTask.BindingContext::get_NGenArgs()
0x34b4  ldarg.2
0x34b5  call     string [mscorlib]System.String::Format(string, object)
0x34ba  call     instance void NGenTask.ILAssembly::set_NGenArgs(string value)
0x34bf  ldarg.0
0x34c0  ldarg.1
0x34c1  callvirt instance string NGenTask.BindingContext::get_Container()
0x34c6  call     instance void NGenTask.ILAssembly::set_Container(string value)
0x34cb  ret
```
