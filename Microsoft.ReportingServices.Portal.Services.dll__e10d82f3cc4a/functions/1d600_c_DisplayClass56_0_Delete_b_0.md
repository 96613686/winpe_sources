# <>c__DisplayClass56_0::<Delete>b__0

- ea: `0x1d600`
- end: `0x1d611`
- name: `<>c__DisplayClass56_0::<Delete>b__0`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## string_xrefs

- `0x1d600`: `Item deleted: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1d600  ldstr    aItemDeleted0// "Item deleted: {0}"
0x1d605  ldarg.0
0x1d606  ldfld    string <>c__DisplayClass56_0::path
0x1d60b  call     string [mscorlib]System.String::Format(string, object)
0x1d610  ret
```
