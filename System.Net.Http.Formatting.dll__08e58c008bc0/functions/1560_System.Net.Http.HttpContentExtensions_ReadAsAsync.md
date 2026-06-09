# System.Net.Http.HttpContentExtensions::ReadAsAsync

- ea: `0x1560`
- end: `0x156d`
- name: `System.Net.Http.HttpContentExtensions::ReadAsAsync`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1540`
- `0x1580`

## pseudocode

```c

```

## disassembly

```asm
0x1560  ldarg.0
0x1561  ldarg.1
0x1562  call     class System.Net.Http.Formatting.MediaTypeFormatterCollection System.Net.Http.HttpContentExtensions::get_DefaultMediaTypeFormatterCollection()
0x1567  call     class [mscorlib]System.Threading.Tasks.Task`1<object> System.Net.Http.HttpContentExtensions::ReadAsAsync(class [System.Net.Http]System.Net.Http.HttpContent content, class [mscorlib]System.Type type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Net.Http.Formatting.MediaTypeFormatter> formatters)
0x156c  ret
```
