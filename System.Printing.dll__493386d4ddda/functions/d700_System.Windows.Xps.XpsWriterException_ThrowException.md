# System.Windows.Xps.XpsWriterException::ThrowException

- ea: `0xd700`
- end: `0xd71c`
- name: `System.Windows.Xps.XpsWriterException::ThrowException`
- size: `28`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0xb670`
- `0xbab0`
- `0xbb30`
- `0xbc20`
- `0xbc90`
- `0xc6e0`
- `0xcce0`
- `0xcf30`
- `0xd010`
- `0xd330`

## callees

- `0xac40`
- `0xd6e0`

## pseudocode

```c

```

## disassembly

```asm
0xd700  newobj   instance void System.Printing.InternalExceptionResourceManager::.ctor()
0xd705  ldarg.0
0xd706  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xd70b  call     instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0xd710  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xd715  newobj   instance void System.Windows.Xps.XpsWriterException::.ctor(string message)
0xd71a  throw
0xd71b  ret
```
