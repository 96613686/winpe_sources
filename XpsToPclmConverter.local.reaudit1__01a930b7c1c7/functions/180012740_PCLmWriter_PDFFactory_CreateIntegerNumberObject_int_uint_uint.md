# PCLmWriter::PDFFactory::CreateIntegerNumberObject(int,uint,uint)

- ea: `0x180012740`
- end: `0x1800127c9`
- name: `?CreateIntegerNumberObject@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@std@@HII@Z`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f6c`
- `0x180010afc`
- `0x180010ff8`

## pseudocode

```c
_OWORD *PCLmWriter::PDFFactory::CreateIntegerNumberObject(__int64 a1, _OWORD *a2, int a3, int a4, ...)
{
  __int128 v5; // xmm0
  __int64 v6; // rcx
  __int64 v7; // r11
  __int128 v9; // [rsp+28h] [rbp-20h] BYREF
  _DWORD *v10; // [rsp+58h] [rbp+10h]
  int v11; // [rsp+60h] [rbp+18h] BYREF
  int v12; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  v12 = a4;
  v11 = a3;
  v10 = operator new(0x30u);
  v5 = 0;
  *(_OWORD *)v10 = 0;
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = &std::_Ref_count_obj2<PCLmWriter::IntegerNumberObject const>::`vftable';
  *(double *)&v5 = std::_Construct_in_place<PCLmWriter::IntegerNumberObject,int const &,unsigned int &,unsigned int &>(
                     v10 + 4,
                     &v11,
                     &v12,
                     va);
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
0x180012740  mov     [rsp+arg_18], r9d
0x180012745  mov     [rsp+arg_10], r8d
0x18001274a  push    rbx
0x18001274b  sub     rsp, 40h
0x18001274f  mov     ecx, 30h ; '0'; Size
0x180012754  mov     rbx, rdx
0x180012757  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001275c  mov     r11, rax
0x18001275f  mov     [rsp+48h+arg_8], rax
0x180012764  xorps   xmm0, xmm0
0x180012767  lea     r9, [rsp+48h+arg_20]
0x18001276c  lea     r8, [rsp+48h+arg_18]
0x180012771  movups  xmmword ptr [rax], xmm0
0x180012774  mov     eax, 1
0x180012779  lea     rcx, [r11+10h]
0x18001277d  mov     [r11+8], eax
0x180012781  lea     rdx, [rsp+48h+arg_10]
0x180012786  mov     [r11+0Ch], eax
0x18001278a  lea     rax, ??_7?$_Ref_count_obj2@$$CBVIntegerNumberObject@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::IntegerNumberObject const>::`vftable'
0x180012791  mov     [r11], rax
0x180012794  call    ??$_Construct_in_place@VIntegerNumberObject@PCLmWriter@@AEBHAEAIAEAI@std@@YAXAEAVIntegerNumberObject@PCLmWriter@@AEBHAEAI2@Z; std::_Construct_in_place<PCLmWriter::IntegerNumberObject,int const &,uint &,uint &>(PCLmWriter::IntegerNumberObject &,int const &,uint &,uint &)
0x180012799  mov     rdx, rcx
0x18001279c  mov     r8, r11
0x18001279f  lea     rcx, [rsp+48h+var_20]
0x1800127a4  movdqu  [rsp+48h+var_20], xmm0
0x1800127aa  call    ??$_Set_ptr_rep_and_enable_shared@VIntegerNumberObject@PCLmWriter@@@?$shared_ptr@$$CBVIntegerNumberObject@PCLmWriter@@@std@@AEAAXQEAVIntegerNumberObject@PCLmWriter@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(PCLmWriter::IntegerNumberObject * const,std::_Ref_count_base * const)
0x1800127af  mov     rax, qword ptr [rsp+48h+var_20]
0x1800127b4  mov     [rbx], rax
0x1800127b7  mov     rax, qword ptr [rsp+48h+var_20+8]
0x1800127bc  mov     [rbx+8], rax
0x1800127c0  mov     rax, rbx
0x1800127c3  add     rsp, 40h
0x1800127c7  pop     rbx
0x1800127c8  retn
```
