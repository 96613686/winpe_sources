# std::unique_ptr<std::shared_ptr<CSession>,std::default_delete<std::shared_ptr<CSession>>>::~unique_ptr<std::shared_ptr<CSession>,std::default_delete<std::shared_ptr<CSession>>>(void)

- ea: `0x18000ace4`
- end: `0x18000ace9`
- name: `??1?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ec2a`

## callees

- `0x18000bedc`

## pseudocode

```c
// attributes: thunk
__int64 std::unique_ptr<std::shared_ptr<CSession>>::~unique_ptr<std::shared_ptr<CSession>>()
{
  return std::unique_ptr<std::shared_ptr<CSession>>::_Delete();
}

```

## disassembly

```asm
0x18000ace4  jmp     ?_Delete@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::shared_ptr<CSession>>::_Delete(void)
```
