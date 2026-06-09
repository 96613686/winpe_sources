# NGenTask.BindingContext::ToString

- ea: `0x3410`
- end: `0x3427`
- name: `NGenTask.BindingContext::ToString`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x32a0`
- `0x32c0`

## string_xrefs

- `0x3410`: `Binding Context NGEN Command: "{0}" in Container "{1}"`

## pseudocode

```c

```

## disassembly

```asm
0x3410  ldstr    aBindingContext// "Binding Context NGEN Command: \"{0}\" i"...
0x3415  ldarg.0
0x3416  call     instance string NGenTask.BindingContext::get_NGenArgs()
0x341b  ldarg.0
0x341c  call     instance string NGenTask.BindingContext::get_Container()
0x3421  call     string [mscorlib]System.String::Format(string, object, object)
0x3426  ret
```
