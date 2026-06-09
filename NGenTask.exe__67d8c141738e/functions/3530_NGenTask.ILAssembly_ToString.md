# NGenTask.ILAssembly::ToString

- ea: `0x3530`
- end: `0x3547`
- name: `NGenTask.ILAssembly::ToString`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x3460`
- `0x3480`

## string_xrefs

- `0x3530`: `ILAssembly NGEN Command: "{0}" in Container "{1}"`

## pseudocode

```c

```

## disassembly

```asm
0x3530  ldstr    aIlassemblyNgen// "ILAssembly NGEN Command: \"{0}\" in Con"...
0x3535  ldarg.0
0x3536  call     instance string NGenTask.ILAssembly::get_NGenArgs()
0x353b  ldarg.0
0x353c  call     instance string NGenTask.ILAssembly::get_Container()
0x3541  call     string [mscorlib]System.String::Format(string, object, object)
0x3546  ret
```
