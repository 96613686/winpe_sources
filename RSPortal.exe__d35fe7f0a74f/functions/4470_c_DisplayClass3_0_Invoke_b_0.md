# <>c__DisplayClass3_0::<Invoke>b__0

- ea: `0x4470`
- end: `0x4481`
- name: `<>c__DisplayClass3_0::<Invoke>b__0`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x4470`: `CSRF Token not generated due to exception:\n {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4470  ldstr    aCsrfTokenNotGe// "CSRF Token not generated due to excepti"...
0x4475  ldarg.0
0x4476  ldfld    class [mscorlib]System.Exception <>c__DisplayClass3_0::e
0x447b  call     string [mscorlib]System.String::Format(string, object)
0x4480  ret
```
