# PCLmWriter::PDFFactory::CreateMemoryByteStream(void)

- ea: `0x180012880`
- end: `0x18001291b`
- name: `?CreateMemoryByteStream@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@XZ`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001f6c`
- `0x180010b28`
- `0x180011008`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall PCLmWriter::PDFFactory::CreateMemoryByteStream(__int64 a1, _OWORD *a2)
{
  __int128 v3; // xmm0
  __int64 v4; // rcx
  __int128 v6; // [rsp+28h] [rbp-20h] BYREF
  _DWORD *v7; // [rsp+60h] [rbp+18h]

  v7 = operator new(0x60u);
  v3 = 0;
  *(_OWORD *)v7 = 0;
  v7[2] = 1;
  v7[3] = 1;
  *(_QWORD *)v7 = &std::_Ref_count_obj2<PCLmWriter::MemoryByteStream>::`vftable';
  *(double *)&v3 = std::_Construct_in_place<PCLmWriter::MemoryByteStream,>(v7 + 4);
  v6 = v3;
  std::shared_ptr<PCLmWriter::MemoryByteStream>::_Set_ptr_rep_and_enable_shared<PCLmWriter::MemoryByteStream>(
    &v6,
    (__int64)(v7 + 4),
    (__int64)v7);
  v4 = v6;
  *a2 = v6;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  return a2;
}

```

## disassembly

```asm
0x180012880  mov     [rsp+arg_0], rbx
0x180012885  mov     [rsp+arg_8], rdx
0x18001288a  push    rdi
0x18001288b  sub     rsp, 40h
0x18001288f  mov     rdi, rdx
0x180012892  mov     [rsp+48h+var_28], 0
0x18001289a  mov     ecx, 60h ; '`'; Size
0x18001289f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800128a4  mov     rbx, rax
0x1800128a7  mov     [rsp+48h+arg_10], rax
0x1800128ac  xorps   xmm0, xmm0
0x1800128af  movups  xmmword ptr [rax], xmm0
0x1800128b2  mov     eax, 1
0x1800128b7  mov     [rbx+8], eax
0x1800128ba  mov     [rbx+0Ch], eax
0x1800128bd  lea     rax, ??_7?$_Ref_count_obj2@VMemoryByteStream@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::MemoryByteStream>::`vftable'
0x1800128c4  mov     [rbx], rax
0x1800128c7  lea     rcx, [rbx+10h]
0x1800128cb  call    ??$_Construct_in_place@VMemoryByteStream@PCLmWriter@@$$V@std@@YAXAEAVMemoryByteStream@PCLmWriter@@@Z; std::_Construct_in_place<PCLmWriter::MemoryByteStream,>(PCLmWriter::MemoryByteStream &)
0x1800128d0  movdqu  [rsp+48h+var_20], xmm0
0x1800128d6  mov     r8, rbx
0x1800128d9  lea     rdx, [rbx+10h]
0x1800128dd  lea     rcx, [rsp+48h+var_20]
0x1800128e2  call    ??$_Set_ptr_rep_and_enable_shared@VMemoryByteStream@PCLmWriter@@@?$shared_ptr@VMemoryByteStream@PCLmWriter@@@std@@AEAAXQEAVMemoryByteStream@PCLmWriter@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<PCLmWriter::MemoryByteStream>::_Set_ptr_rep_and_enable_shared<PCLmWriter::MemoryByteStream>(PCLmWriter::MemoryByteStream * const,std::_Ref_count_base * const)
0x1800128e7  mov     rcx, qword ptr [rsp+48h+var_20]
0x1800128ec  mov     [rdi], rcx
0x1800128ef  mov     rax, qword ptr [rsp+48h+var_20+8]
0x1800128f4  mov     [rdi+8], rax
0x1800128f8  mov     [rsp+48h+var_28], 3
0x180012900  mov     rax, [rcx]
0x180012903  mov     rax, [rax+8]
0x180012907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001290c  mov     rax, rdi
0x18001290f  mov     rbx, [rsp+48h+arg_0]
0x180012914  add     rsp, 40h
0x180012918  pop     rdi
0x180012919  retn
```
