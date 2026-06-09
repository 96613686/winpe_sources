# <>c__DisplayClass137_0::<RemoveFromFavorites>b__0

- ea: `0x1e350`
- end: `0x1e366`
- name: `<>c__DisplayClass137_0::<RemoveFromFavorites>b__0`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x1e350`: `Favorite removed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1e350  ldstr    aFavoriteRemove// "Favorite removed: {0}"
0x1e355  ldarg.0
0x1e356  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass137_0::id
0x1e35b  box      [mscorlib]System.Guid
0x1e360  call     string [mscorlib]System.String::Format(string, object)
0x1e365  ret
```
