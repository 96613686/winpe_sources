# std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)

- ea: `0x18000f268`
- end: `0x18000f2a5`
- name: `??$_Uninitialized_move@PEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ee94`
- `0x180013be0`
- `0x180014158`

## callees

- `0x18000ee2c`
- `0x18000f268`
- `0x18000f2dc`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // r8
  __int64 i; // r9
  __int64 v6; // r8

  v4 = a1;
  for ( i = a2; v4 != i; v4 = v6 + 16 )
  {
    std::_Default_allocator_traits<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::construct<std::shared_ptr<PCLmWriter::IObject const>,std::shared_ptr<PCLmWriter::IObject const>>(
      a1,
      a3,
      v4,
      i);
    a3 += 16;
  }
  std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x18000f268  push    rbx
0x18000f26a  sub     rsp, 20h
0x18000f26e  mov     rbx, r8
0x18000f271  mov     r8, rcx
0x18000f274  mov     r9, rdx
0x18000f277  cmp     rcx, rdx
0x18000f27a  jz      short loc_18000F291
0x18000f27c  mov     rdx, rbx
0x18000f27f  call    ??$construct@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V12@@?$_Default_allocator_traits@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@SAXAEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@1@QEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::construct<std::shared_ptr<PCLmWriter::IObject const>,std::shared_ptr<PCLmWriter::IObject const>>(std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &,std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> &&)
0x18000f284  add     rbx, 10h
0x18000f288  add     r8, 10h
0x18000f28c  cmp     r8, r9
0x18000f28f  jnz     short loc_18000F27C
0x18000f291  mov     rdx, rbx
0x18000f294  mov     rcx, rbx
0x18000f297  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,std::shared_ptr<PCLmWriter::IObject const> * const,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x18000f29c  mov     rax, rbx
0x18000f29f  add     rsp, 20h
0x18000f2a3  pop     rbx
0x18000f2a4  retn
```
