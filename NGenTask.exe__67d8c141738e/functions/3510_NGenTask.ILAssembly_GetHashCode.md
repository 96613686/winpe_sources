# NGenTask.ILAssembly::GetHashCode

- ea: `0x3510`
- end: `0x3528`
- name: `NGenTask.ILAssembly::GetHashCode`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x3460`
- `0x3480`

## pseudocode

```c

```

## disassembly

```asm
0x3510  ldarg.0
0x3511  call     instance string NGenTask.ILAssembly::get_NGenArgs()
0x3516  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x351b  ldarg.0
0x351c  call     instance string NGenTask.ILAssembly::get_Container()
0x3521  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x3526  add
0x3527  ret
```
