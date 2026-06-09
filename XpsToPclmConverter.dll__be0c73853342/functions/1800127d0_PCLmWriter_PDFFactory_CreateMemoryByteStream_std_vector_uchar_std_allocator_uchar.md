# PCLmWriter::PDFFactory::CreateMemoryByteStream(std::vector<uchar,std::allocator<uchar>> &&)

- ea: `0x1800127d0`
- end: `0x18001287a`
- name: `?CreateMemoryByteStream@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@$$QEAV?$vector@EV?$allocator@E@std@@@4@@Z`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001f6c`
- `0x180010b34`
- `0x180011008`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall PCLmWriter::PDFFactory::CreateMemoryByteStream(__int64 a1, _OWORD *a2, __int64 a3)
{
  __int128 v5; // xmm0
  __int64 v6; // rcx
  __int128 v8; // [rsp+28h] [rbp-20h] BYREF
  _DWORD *v9; // [rsp+68h] [rbp+20h]

  v9 = operator new(0x60u);
  v5 = 0;
  *(_OWORD *)v9 = 0;
  v9[2] = 1;
  v9[3] = 1;
  *(_QWORD *)v9 = &std::_Ref_count_obj2<PCLmWriter::MemoryByteStream>::`vftable';
  *(double *)&v5 = std::_Construct_in_place<PCLmWriter::MemoryByteStream,std::vector<unsigned char>>(v9 + 4, a3);
  v8 = v5;
  std::shared_ptr<PCLmWriter::MemoryByteStream>::_Set_ptr_rep_and_enable_shared<PCLmWriter::MemoryByteStream>(
    &v8,
    (__int64)(v9 + 4),
    (__int64)v9);
  v6 = v8;
  *a2 = v8;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  return a2;
}

```

## disassembly

```asm
0x1800127d0  mov     rax, rsp
0x1800127d3  mov     [rax+8], rbx
0x1800127d7  mov     [rax+18h], rsi
0x1800127db  mov     [rax+10h], rdx
0x1800127df  push    rdi
0x1800127e0  sub     rsp, 40h
0x1800127e4  mov     rdi, r8
0x1800127e7  mov     rsi, rdx
0x1800127ea  mov     dword ptr [rax-28h], 0
0x1800127f1  mov     ecx, 60h ; '`'; Size
0x1800127f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800127fb  mov     rbx, rax
0x1800127fe  mov     [rsp+48h+arg_18], rax
0x180012803  xorps   xmm0, xmm0
0x180012806  movups  xmmword ptr [rax], xmm0
0x180012809  mov     eax, 1
0x18001280e  mov     [rbx+8], eax
0x180012811  mov     [rbx+0Ch], eax
0x180012814  lea     rax, ??_7?$_Ref_count_obj2@VMemoryByteStream@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::MemoryByteStream>::`vftable'
0x18001281b  mov     [rbx], rax
0x18001281e  mov     rdx, rdi
0x180012821  lea     rcx, [rbx+10h]
0x180012825  call    ??$_Construct_in_place@VMemoryByteStream@PCLmWriter@@V?$vector@EV?$allocator@E@std@@@std@@@std@@YAXAEAVMemoryByteStream@PCLmWriter@@$$QEAV?$vector@EV?$allocator@E@std@@@0@@Z; std::_Construct_in_place<PCLmWriter::MemoryByteStream,std::vector<uchar>>(PCLmWriter::MemoryByteStream &,std::vector<uchar> &&)
0x18001282a  movdqu  [rsp+48h+var_20], xmm0
0x180012830  mov     r8, rbx
0x180012833  lea     rdx, [rbx+10h]
0x180012837  lea     rcx, [rsp+48h+var_20]
0x18001283c  call    ??$_Set_ptr_rep_and_enable_shared@VMemoryByteStream@PCLmWriter@@@?$shared_ptr@VMemoryByteStream@PCLmWriter@@@std@@AEAAXQEAVMemoryByteStream@PCLmWriter@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<PCLmWriter::MemoryByteStream>::_Set_ptr_rep_and_enable_shared<PCLmWriter::MemoryByteStream>(PCLmWriter::MemoryByteStream * const,std::_Ref_count_base * const)
0x180012841  mov     rcx, qword ptr [rsp+48h+var_20]
0x180012846  mov     [rsi], rcx
0x180012849  mov     rax, qword ptr [rsp+48h+var_20+8]
0x18001284e  mov     [rsi+8], rax
0x180012852  mov     [rsp+48h+var_28], 3
0x18001285a  mov     rax, [rcx]
0x18001285d  mov     rax, [rax+8]
0x180012861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012866  mov     rax, rsi
0x180012869  mov     rbx, [rsp+48h+arg_0]
0x18001286e  mov     rsi, [rsp+48h+arg_10]
0x180012873  add     rsp, 40h
0x180012877  pop     rdi
0x180012878  retn
```
