# ThreadSafeObjectProvider`1::.ctor

- ea: `0x1540`
- end: `0x1552`
- name: `ThreadSafeObjectProvider`1::.ctor`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x1540  ldarg.0
0x1541  call     instance void [mscorlib]System.Object::.ctor()
0x1546  ldarg.0
0x1547  newobj   instance void class [Microsoft.VisualBasic]Microsoft.VisualBasic.MyServices.Internal.ContextValue`1<var<u1>>::.ctor()
0x154c  stfld    class [Microsoft.VisualBasic]Microsoft.VisualBasic.MyServices.Internal.ContextValue`1<var<u1>> class ThreadSafeObjectProvider`1<var<u1>>::m_Context
0x1551  ret
```
