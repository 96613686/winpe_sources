# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Change_array(std::shared_ptr<PCLmWriter::IObject const> * const,unsigned __int64,unsigned __int64)

- ea: `0x180010124`
- end: `0x18001017f`
- name: `?_Change_array@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAXQEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@_K1@Z`
- size: `91`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ee94`
- `0x180013be0`
- `0x180014158`

## callees

- `0x18000edc0`
- `0x18000ee2c`
- `0x180010124`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Change_array(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  __int64 result; // rax

  v6 = *a1;
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(v6, a1[1]);
    result = std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  *a1 = a2;
  a1[1] = a2 + 16 * a3;
  a1[2] = a2 + 16 * a4;
  return result;
}

```

## disassembly

```asm
0x180010124  push    rbx
0x180010126  push    rbp
0x180010127  push    rsi
0x180010128  push    rdi
0x180010129  sub     rsp, 28h
0x18001012d  mov     rbx, rcx
0x180010130  mov     rdi, r9
0x180010133  mov     rcx, [rcx]
0x180010136  mov     rsi, r8
0x180010139  mov     rbp, rdx
0x18001013c  test    rcx, rcx
0x18001013f  jz      short loc_18001015D
0x180010141  mov     rdx, [rbx+8]
0x180010145  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,std::shared_ptr<PCLmWriter::IObject const> * const,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x18001014a  mov     rdx, [rbx+10h]
0x18001014e  sub     rdx, [rbx]
0x180010151  mov     rcx, [rbx]
0x180010154  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180010158  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001015d  shl     rsi, 4
0x180010161  add     rsi, rbp
0x180010164  mov     [rbx], rbp
0x180010167  shl     rdi, 4
0x18001016b  add     rdi, rbp
0x18001016e  mov     [rbx+8], rsi
0x180010172  mov     [rbx+10h], rdi
0x180010176  add     rsp, 28h
0x18001017a  pop     rdi
0x18001017b  pop     rsi
0x18001017c  pop     rbp
0x18001017d  pop     rbx
0x18001017e  retn
```
