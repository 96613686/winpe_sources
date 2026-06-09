# PCLmWriter::PDFFactory::CreateNameObject(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,uint,uint)

- ea: `0x180012930`
- end: `0x1800129d0`
- name: `?CreateNameObject@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@$$CBVINameObject@PCLmWriter@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@II@Z`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f6c`
- `0x180010ba0`
- `0x180010ff8`

## pseudocode

```c
_OWORD *PCLmWriter::PDFFactory::CreateNameObject(__int64 a1, _OWORD *a2, __int64 a3, int a4, ...)
{
  _OWORD v7[3]; // [rsp+28h] [rbp-30h] BYREF
  _DWORD *v8; // [rsp+68h] [rbp+10h]
  int v9; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v9 = a4;
  v8 = operator new(0x48u);
  *(_OWORD *)v8 = 0;
  v8[2] = 1;
  v8[3] = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<PCLmWriter::NameObject const>::`vftable';
  std::_Construct_in_place<PCLmWriter::NameObject,std::string const &,unsigned int &,unsigned int &>(
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
0x180012930  mov     [rsp+arg_0], rbx
0x180012935  mov     [rsp+arg_18], r9d
0x18001293a  mov     [rsp+arg_8], rdx
0x18001293f  push    rsi
0x180012940  push    rdi
0x180012941  push    r14
0x180012943  sub     rsp, 40h
0x180012947  mov     rsi, r8
0x18001294a  mov     r14, rdx
0x18001294d  mov     ecx, 48h ; 'H'; Size
0x180012952  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012957  mov     rdi, rax
0x18001295a  mov     [rsp+58h+arg_8], rax
0x18001295f  xorps   xmm0, xmm0
0x180012962  movups  xmmword ptr [rax], xmm0
0x180012965  mov     eax, 1
0x18001296a  mov     [rdi+8], eax
0x18001296d  mov     [rdi+0Ch], eax
0x180012970  lea     rax, ??_7?$_Ref_count_obj2@$$CBVNameObject@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::NameObject const>::`vftable'
0x180012977  mov     [rdi], rax
0x18001297a  lea     r9, [rsp+58h+arg_20]
0x180012982  lea     r8, [rsp+58h+arg_18]
0x180012987  mov     rdx, rsi
0x18001298a  lea     rcx, [rdi+10h]
0x18001298e  call    ??$_Construct_in_place@VNameObject@PCLmWriter@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAIAEAI@std@@YAXAEAVNameObject@PCLmWriter@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEAI2@Z; std::_Construct_in_place<PCLmWriter::NameObject,std::string const &,uint &,uint &>(PCLmWriter::NameObject &,std::string const &,uint &,uint &)
0x180012993  nop
0x180012994  xorps   xmm0, xmm0
0x180012997  movdqu  [rsp+58h+var_30], xmm0
0x18001299d  mov     r8, rdi
0x1800129a0  lea     rdx, [rdi+10h]
0x1800129a4  lea     rcx, [rsp+58h+var_30]
0x1800129a9  call    ??$_Set_ptr_rep_and_enable_shared@VIntegerNumberObject@PCLmWriter@@@?$shared_ptr@$$CBVIntegerNumberObject@PCLmWriter@@@std@@AEAAXQEAVIntegerNumberObject@PCLmWriter@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(PCLmWriter::IntegerNumberObject * const,std::_Ref_count_base * const)
0x1800129ae  mov     rax, qword ptr [rsp+58h+var_30]
0x1800129b3  mov     [r14], rax
0x1800129b6  mov     rax, qword ptr [rsp+58h+var_30+8]
0x1800129bb  mov     [r14+8], rax
0x1800129bf  mov     rax, r14
0x1800129c2  mov     rbx, [rsp+58h+arg_0]
0x1800129c7  add     rsp, 40h
0x1800129cb  pop     r14
0x1800129cd  pop     rdi
0x1800129ce  pop     rsi
0x1800129cf  retn
```
