# ThreadSafeObjectProvider`1::get_GetInstance

- ea: `0x1510`
- end: `0x1538`
- name: `ThreadSafeObjectProvider`1::get_GetInstance`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1510`

## pseudocode

```c

```

## disassembly

```asm
0x1510  ldarg.0
0x1511  ldfld    class [Microsoft.VisualBasic]Microsoft.VisualBasic.MyServices.Internal.ContextValue`1<var<u1>> class ThreadSafeObjectProvider`1<var<u1>>::m_Context
0x1516  callvirt instance var<u1> class [Microsoft.VisualBasic]Microsoft.VisualBasic.MyServices.Internal.ContextValue`1<var<u1>>::get_Value()
0x151b  stloc.0
0x151c  ldloc.0
0x151d  box      var<u1>
0x1522  brtrue.s loc_1536
0x1524  call     T0x2B000002
0x1529  stloc.0
0x152a  ldarg.0
0x152b  ldfld    class [Microsoft.VisualBasic]Microsoft.VisualBasic.MyServices.Internal.ContextValue`1<var<u1>> class ThreadSafeObjectProvider`1<var<u1>>::m_Context
0x1530  ldloc.0
0x1531  callvirt instance void class [Microsoft.VisualBasic]Microsoft.VisualBasic.MyServices.Internal.ContextValue`1<var<u1>>::set_Value(var<u1>)
0x1536  ldloc.0
0x1537  ret
```
