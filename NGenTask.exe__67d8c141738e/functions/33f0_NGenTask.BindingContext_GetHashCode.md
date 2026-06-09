# NGenTask.BindingContext::GetHashCode

- ea: `0x33f0`
- end: `0x3408`
- name: `NGenTask.BindingContext::GetHashCode`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x32a0`
- `0x32c0`

## pseudocode

```c

```

## disassembly

```asm
0x33f0  ldarg.0
0x33f1  call     instance string NGenTask.BindingContext::get_NGenArgs()
0x33f6  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x33fb  ldarg.0
0x33fc  call     instance string NGenTask.BindingContext::get_Container()
0x3401  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x3406  add
0x3407  ret
```
