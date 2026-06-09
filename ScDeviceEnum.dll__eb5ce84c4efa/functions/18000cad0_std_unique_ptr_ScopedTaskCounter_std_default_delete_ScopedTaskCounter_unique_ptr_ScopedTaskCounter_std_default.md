# std::unique_ptr<ScopedTaskCounter,std::default_delete<ScopedTaskCounter>>::~unique_ptr<ScopedTaskCounter,std::default_delete<ScopedTaskCounter>>(void)

- ea: `0x18000cad0`
- end: `0x18000cad5`
- name: `??1?$unique_ptr@VScopedTaskCounter@@U?$default_delete@VScopedTaskCounter@@@std@@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001ed17`

## callees

- `0x18000db50`

## pseudocode

```c
// attributes: thunk
__int64 std::unique_ptr<ScopedTaskCounter>::~unique_ptr<ScopedTaskCounter>()
{
  return std::unique_ptr<ScopedTaskCounter>::_Delete();
}

```

## disassembly

```asm
0x18000cad0  jmp     ?_Delete@?$unique_ptr@VScopedTaskCounter@@U?$default_delete@VScopedTaskCounter@@@std@@@std@@AEAAXXZ; std::unique_ptr<ScopedTaskCounter>::_Delete(void)
```
