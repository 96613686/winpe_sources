# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(std::shared_ptr<PCLmWriter::IObject const> &&)

- ea: `0x18000ee6c`
- end: `0x18000ee8d`
- name: `??$_Emplace_back_with_unused_capacity@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEAV21@@Z`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010290`
- `0x180014a14`
- `0x1800152f4`

## callees

- `0x18000ec38`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_back_with_unused_capacity<std::shared_ptr<PCLmWriter::IObject const>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r9
  __int64 result; // rax

  std::_Construct_in_place<std::shared_ptr<PCLmWriter::IObject const>,std::shared_ptr<PCLmWriter::IObject const>>(
    *(_QWORD *)(a1 + 8),
    a2,
    a3,
    a1);
  result = *(_QWORD *)(v3 + 8);
  *(_QWORD *)(v3 + 8) = result + 16;
  return result;
}

```

## disassembly

```asm
0x18000ee6c  sub     rsp, 28h
0x18000ee70  mov     r9, rcx
0x18000ee73  mov     rcx, [rcx+8]
0x18000ee77  call    ??$_Construct_in_place@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V12@@std@@YAXAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@$$QEAV10@@Z; std::_Construct_in_place<std::shared_ptr<PCLmWriter::IObject const>,std::shared_ptr<PCLmWriter::IObject const>>(std::shared_ptr<PCLmWriter::IObject const> &,std::shared_ptr<PCLmWriter::IObject const> &&)
0x18000ee7c  mov     rax, [r9+8]
0x18000ee80  lea     rdx, [rax+10h]
0x18000ee84  mov     [r9+8], rdx
0x18000ee88  add     rsp, 28h
0x18000ee8c  retn
```
