# PCLmWriter::PDFFactory::CreateIndirectObject(uint,uint)

- ea: `0x1800126b0`
- end: `0x180012734`
- name: `?CreateIndirectObject@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@$$CBVIIndirectObject@PCLmWriter@@@std@@II@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f6c`
- `0x180010ad0`
- `0x180010ff8`

## pseudocode

```c
_OWORD *__fastcall PCLmWriter::PDFFactory::CreateIndirectObject(__int64 a1, _OWORD *a2, int a3, int a4)
{
  __int128 v5; // xmm0
  __int64 v6; // rcx
  __int64 v7; // r9
  __int128 v9; // [rsp+28h] [rbp-20h] BYREF
  _DWORD *v10; // [rsp+58h] [rbp+10h]
  int v11; // [rsp+60h] [rbp+18h] BYREF
  int v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = a4;
  v11 = a3;
  v10 = operator new(0x30u);
  v5 = 0;
  *(_OWORD *)v10 = 0;
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = &std::_Ref_count_obj2<PCLmWriter::IndirectObject const>::`vftable';
  *(double *)&v5 = std::_Construct_in_place<PCLmWriter::IndirectObject,unsigned int const &,unsigned int const &>(
                     v10 + 4,
                     &v11,
                     &v12);
  v9 = v5;
  std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(
    &v9,
    v6,
    v7);
  *a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x1800126b0  mov     [rsp+arg_18], r9d
0x1800126b5  mov     [rsp+arg_10], r8d
0x1800126ba  push    rbx
0x1800126bb  sub     rsp, 40h
0x1800126bf  mov     ecx, 30h ; '0'; Size
0x1800126c4  mov     rbx, rdx
0x1800126c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800126cc  mov     r9, rax
0x1800126cf  mov     [rsp+48h+arg_8], rax
0x1800126d4  xorps   xmm0, xmm0
0x1800126d7  lea     r8, [rsp+48h+arg_18]
0x1800126dc  lea     rdx, [rsp+48h+arg_10]
0x1800126e1  movups  xmmword ptr [rax], xmm0
0x1800126e4  mov     eax, 1
0x1800126e9  lea     rcx, [r9+10h]
0x1800126ed  mov     [r9+8], eax
0x1800126f1  mov     [r9+0Ch], eax
0x1800126f5  lea     rax, ??_7?$_Ref_count_obj2@$$CBVIndirectObject@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::IndirectObject const>::`vftable'
0x1800126fc  mov     [r9], rax
0x1800126ff  call    ??$_Construct_in_place@VIndirectObject@PCLmWriter@@AEBIAEBI@std@@YAXAEAVIndirectObject@PCLmWriter@@AEBI1@Z; std::_Construct_in_place<PCLmWriter::IndirectObject,uint const &,uint const &>(PCLmWriter::IndirectObject &,uint const &,uint const &)
0x180012704  mov     rdx, rcx
0x180012707  mov     r8, r9
0x18001270a  lea     rcx, [rsp+48h+var_20]
0x18001270f  movdqu  [rsp+48h+var_20], xmm0
0x180012715  call    ??$_Set_ptr_rep_and_enable_shared@VIntegerNumberObject@PCLmWriter@@@?$shared_ptr@$$CBVIntegerNumberObject@PCLmWriter@@@std@@AEAAXQEAVIntegerNumberObject@PCLmWriter@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(PCLmWriter::IntegerNumberObject * const,std::_Ref_count_base * const)
0x18001271a  mov     rax, qword ptr [rsp+48h+var_20]
0x18001271f  mov     [rbx], rax
0x180012722  mov     rax, qword ptr [rsp+48h+var_20+8]
0x180012727  mov     [rbx+8], rax
0x18001272b  mov     rax, rbx
0x18001272e  add     rsp, 40h
0x180012732  pop     rbx
0x180012733  retn
```
