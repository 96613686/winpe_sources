# System.Net.Http.HttpContentExtensions::ReadAsAsync_0

- ea: `0x1570`
- end: `0x157e`
- name: `System.Net.Http.HttpContentExtensions::ReadAsAsync_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1540`
- `0x1590`

## pseudocode

```c

```

## disassembly

```asm
0x1570  ldarg.0
0x1571  ldarg.1
0x1572  call     class System.Net.Http.Formatting.MediaTypeFormatterCollection System.Net.Http.HttpContentExtensions::get_DefaultMediaTypeFormatterCollection()
0x1577  ldarg.2
0x1578  call     class [mscorlib]System.Threading.Tasks.Task`1<object> System.Net.Http.HttpContentExtensions::ReadAsAsync(class [System.Net.Http]System.Net.Http.HttpContent content, class [mscorlib]System.Type type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Net.Http.Formatting.MediaTypeFormatter> formatters, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x157d  ret
```
