# PCLmWriter::PDFFactory::CreateRealNumberObject(double,uint,uint)

- ea: `0x1800129e0`
- end: `0x180012a6d`
- name: `?CreateRealNumberObject@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@$$CBVIRealNumberObject@PCLmWriter@@@std@@NII@Z`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f6c`
- `0x180010bd8`
- `0x180010ff8`

## pseudocode

```c
_OWORD *PCLmWriter::PDFFactory::CreateRealNumberObject(__int64 a1, _OWORD *a2, double a3, int a4, ...)
{
  __int64 v5; // rcx
  __int64 v6; // r10
  __int128 v8; // [rsp+28h] [rbp-20h] BYREF
  _DWORD *v9; // [rsp+58h] [rbp+10h]
  double v10; // [rsp+60h] [rbp+18h] BYREF
  int v11; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  v11 = a4;
  v10 = a3;
  v9 = operator new(0x30u);
  *(_OWORD *)v9 = 0;
  v9[2] = 1;
  v9[3] = 1;
  *(_QWORD *)v9 = &std::_Ref_count_obj2<PCLmWriter::RealNumberObject const>::`vftable';
  std::_Construct_in_place<PCLmWriter::RealNumberObject,double const &,unsigned int &,unsigned int &>(
    v9 + 4,
    &v10,
    &v11,
    va);
  v8 = 0;
  std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(
    &v8,
    v5,
    v6);
  *a2 = v8;
  return a2;
}

```

## disassembly

```asm
0x1800129e0  mov     [rsp+arg_18], r9d
0x1800129e5  movsd   [rsp+arg_10], xmm2
0x1800129eb  push    rbx
0x1800129ec  sub     rsp, 40h
0x1800129f0  mov     ecx, 30h ; '0'; Size
0x1800129f5  mov     rbx, rdx
0x1800129f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800129fd  mov     r10, rax
0x180012a00  mov     [rsp+48h+arg_8], rax
0x180012a05  xorps   xmm0, xmm0
0x180012a08  lea     r9, [rsp+48h+arg_20]
0x180012a0d  lea     r8, [rsp+48h+arg_18]
0x180012a12  movups  xmmword ptr [rax], xmm0
0x180012a15  mov     eax, 1
0x180012a1a  lea     rcx, [r10+10h]
0x180012a1e  mov     [r10+8], eax
0x180012a22  lea     rdx, [rsp+48h+arg_10]
0x180012a27  mov     [r10+0Ch], eax
0x180012a2b  lea     rax, ??_7?$_Ref_count_obj2@$$CBVRealNumberObject@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::RealNumberObject const>::`vftable'
0x180012a32  mov     [r10], rax
0x180012a35  call    ??$_Construct_in_place@VRealNumberObject@PCLmWriter@@AEBNAEAIAEAI@std@@YAXAEAVRealNumberObject@PCLmWriter@@AEBNAEAI2@Z; std::_Construct_in_place<PCLmWriter::RealNumberObject,double const &,uint &,uint &>(PCLmWriter::RealNumberObject &,double const &,uint &,uint &)
0x180012a3a  mov     rdx, rcx
0x180012a3d  xorps   xmm1, xmm1
0x180012a40  lea     rcx, [rsp+48h+var_20]
0x180012a45  mov     r8, r10
0x180012a48  movdqu  [rsp+48h+var_20], xmm1
0x180012a4e  call    ??$_Set_ptr_rep_and_enable_shared@VIntegerNumberObject@PCLmWriter@@@?$shared_ptr@$$CBVIntegerNumberObject@PCLmWriter@@@std@@AEAAXQEAVIntegerNumberObject@PCLmWriter@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(PCLmWriter::IntegerNumberObject * const,std::_Ref_count_base * const)
0x180012a53  mov     rax, qword ptr [rsp+48h+var_20]
0x180012a58  mov     [rbx], rax
0x180012a5b  mov     rax, qword ptr [rsp+48h+var_20+8]
0x180012a60  mov     [rbx+8], rax
0x180012a64  mov     rax, rbx
0x180012a67  add     rsp, 40h
0x180012a6b  pop     rbx
0x180012a6c  retn
```
