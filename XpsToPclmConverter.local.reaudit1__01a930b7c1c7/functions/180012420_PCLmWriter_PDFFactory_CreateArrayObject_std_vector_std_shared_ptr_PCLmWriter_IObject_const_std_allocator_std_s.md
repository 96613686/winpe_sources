# PCLmWriter::PDFFactory::CreateArrayObject(std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>> const &,uint,uint)

- ea: `0x180012420`
- end: `0x1800124c0`
- name: `?CreateArrayObject@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@$$CBVIArrayObject@PCLmWriter@@@std@@AEBV?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@4@II@Z`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f6c`
- `0x180010984`
- `0x180010ff8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *PCLmWriter::PDFFactory::CreateArrayObject(__int64 a1, _OWORD *a2, __int64 a3, int a4, ...)
{
  _OWORD v7[3]; // [rsp+28h] [rbp-30h] BYREF
  _DWORD *v8; // [rsp+68h] [rbp+10h]
  int v9; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v9 = a4;
  v8 = operator new(0x40u);
  *(_OWORD *)v8 = 0;
  v8[2] = 1;
  v8[3] = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<PCLmWriter::ArrayObject const>::`vftable';
  std::_Construct_in_place<PCLmWriter::ArrayObject,std::vector<std::shared_ptr<PCLmWriter::IObject const>> const &,unsigned int &,unsigned int &>(
    v8 + 4,
    a3,
    &v9,
    va);
  v7[0] = 0;
  std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(
    v7,
    (__int64)(v8 + 4),
    (__int64)v8);
  *a2 = v7[0];
  return a2;
}

```

## disassembly

```asm
0x180012420  mov     [rsp+arg_0], rbx
0x180012425  mov     [rsp+arg_18], r9d
0x18001242a  mov     [rsp+arg_8], rdx
0x18001242f  push    rsi
0x180012430  push    rdi
0x180012431  push    r14
0x180012433  sub     rsp, 40h
0x180012437  mov     rsi, r8
0x18001243a  mov     r14, rdx
0x18001243d  mov     ecx, 40h ; '@'; Size
0x180012442  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012447  mov     rdi, rax
0x18001244a  mov     [rsp+58h+arg_8], rax
0x18001244f  xorps   xmm0, xmm0
0x180012452  movups  xmmword ptr [rax], xmm0
0x180012455  mov     eax, 1
0x18001245a  mov     [rdi+8], eax
0x18001245d  mov     [rdi+0Ch], eax
0x180012460  lea     rax, ??_7?$_Ref_count_obj2@$$CBVArrayObject@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::ArrayObject const>::`vftable'
0x180012467  mov     [rdi], rax
0x18001246a  lea     r9, [rsp+58h+arg_20]
0x180012472  lea     r8, [rsp+58h+arg_18]
0x180012477  mov     rdx, rsi
0x18001247a  lea     rcx, [rdi+10h]
0x18001247e  call    ??$_Construct_in_place@VArrayObject@PCLmWriter@@AEBV?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAIAEAI@std@@YAXAEAVArrayObject@PCLmWriter@@AEBV?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@0@AEAI2@Z; std::_Construct_in_place<PCLmWriter::ArrayObject,std::vector<std::shared_ptr<PCLmWriter::IObject const>> const &,uint &,uint &>(PCLmWriter::ArrayObject &,std::vector<std::shared_ptr<PCLmWriter::IObject const>> const &,uint &,uint &)
0x180012483  nop
0x180012484  xorps   xmm0, xmm0
0x180012487  movdqu  [rsp+58h+var_30], xmm0
0x18001248d  mov     r8, rdi
0x180012490  lea     rdx, [rdi+10h]
0x180012494  lea     rcx, [rsp+58h+var_30]
0x180012499  call    ??$_Set_ptr_rep_and_enable_shared@VIntegerNumberObject@PCLmWriter@@@?$shared_ptr@$$CBVIntegerNumberObject@PCLmWriter@@@std@@AEAAXQEAVIntegerNumberObject@PCLmWriter@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(PCLmWriter::IntegerNumberObject * const,std::_Ref_count_base * const)
0x18001249e  mov     rax, qword ptr [rsp+58h+var_30]
0x1800124a3  mov     [r14], rax
0x1800124a6  mov     rax, qword ptr [rsp+58h+var_30+8]
0x1800124ab  mov     [r14+8], rax
0x1800124af  mov     rax, r14
0x1800124b2  mov     rbx, [rsp+58h+arg_0]
0x1800124b7  add     rsp, 40h
0x1800124bb  pop     r14
0x1800124bd  pop     rdi
0x1800124be  pop     rsi
0x1800124bf  retn
```
