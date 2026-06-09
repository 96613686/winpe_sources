# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::~vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(void)

- ea: `0x18000f71c`
- end: `0x18000f721`
- name: `??1?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d493`
- `0x18001d4f8`
- `0x18001d7f8`
- `0x18001d859`
- `0x18001d9c1`
- `0x18001d9f7`

## callees

- `0x1800106c8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::~vector<std::shared_ptr<PCLmWriter::IObject const>>(
        _QWORD *a1)
{
  return std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(a1);
}

```

## disassembly

```asm
0x18000f71c  jmp     ?_Tidy@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(void)
```
