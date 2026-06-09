# std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(PCLmWriter::PDFImageData *,PCLmWriter::PDFImageData * const,std::allocator<PCLmWriter::PDFImageData> &)

- ea: `0x18000edf4`
- end: `0x18000ee25`
- name: `??$_Destroy_range@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@YAXPEAUPDFImageData@PCLmWriter@@QEAU12@AEAV?$allocator@UPDFImageData@PCLmWriter@@@0@@Z`
- size: `49`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f728`
- `0x180016bd0`
- `0x180016d64`
- `0x180017350`
- `0x180017620`

## callees

- `0x18000edf4`
- `0x180010718`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = std::string::_Tidy_deallocate(v3);
      v3 += 72;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x18000edf4  cmp     rcx, rdx
0x18000edf7  jz      short locret_18000EE24
0x18000edf9  mov     [rsp+arg_0], rbx
0x18000edfe  push    rdi
0x18000edff  sub     rsp, 20h
0x18000ee03  mov     rdi, rdx
0x18000ee06  mov     rbx, rcx
0x18000ee09  mov     rcx, rbx
0x18000ee0c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18000ee11  add     rbx, 48h ; 'H'
0x18000ee15  cmp     rbx, rdi
0x18000ee18  jnz     short loc_18000EE09
0x18000ee1a  mov     rbx, [rsp+28h+arg_0]
0x18000ee1f  add     rsp, 20h
0x18000ee23  pop     rdi
0x18000ee24  retn
```
