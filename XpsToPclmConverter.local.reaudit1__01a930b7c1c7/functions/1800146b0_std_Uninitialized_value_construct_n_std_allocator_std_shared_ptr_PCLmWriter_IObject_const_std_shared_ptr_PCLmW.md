# std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,unsigned __int64,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)

- ea: `0x1800146b0`
- end: `0x1800146f9`
- name: `??$_Uninitialized_value_construct_n@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@PEAV10@_KAEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180014158`
- `0x180014a14`

## callees

- `0x18000ee2c`
- `0x18001395c`
- `0x1800146b0`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+30h] [rbp-18h]

  v5 = a1;
  v6 = a1;
  v3 = a1;
  v7 = a3;
  if ( a2 )
  {
    while ( std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Emplace_back<>(&v5) != 1 )
      ;
    v3 = v6;
  }
  std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(v3, v3);
  return v3;
}

```

## disassembly

```asm
0x1800146b0  push    rbx
0x1800146b2  sub     rsp, 40h
0x1800146b6  mov     [rsp+48h+var_28], rcx
0x1800146bb  mov     rax, rdx
0x1800146be  mov     [rsp+48h+var_20], rcx
0x1800146c3  mov     rbx, rcx
0x1800146c6  mov     [rsp+48h+var_18], r8
0x1800146cb  test    rdx, rdx
0x1800146ce  jz      short loc_1800146E5
0x1800146d0  lea     rcx, [rsp+48h+var_28]
0x1800146d5  call    ??$_Emplace_back@$$V@?$_Uninitialized_backout_al@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@QEAAXXZ; std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Emplace_back<>(void)
0x1800146da  sub     rax, 1
0x1800146de  jnz     short loc_1800146D0
0x1800146e0  mov     rbx, [rsp+48h+var_20]
0x1800146e5  mov     rdx, rbx
0x1800146e8  mov     rcx, rbx
0x1800146eb  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,std::shared_ptr<PCLmWriter::IObject const> * const,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x1800146f0  mov     rax, rbx
0x1800146f3  add     rsp, 40h
0x1800146f7  pop     rbx
0x1800146f8  retn
```
