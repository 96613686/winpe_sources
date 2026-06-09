# PCLmWriter::PDFFactory::CreateDictionaryObject(std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>> const &,uint,uint)

- ea: `0x180012580`
- end: `0x180012620`
- name: `?CreateDictionaryObject@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@std@@AEBV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@4@II@Z`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f6c`
- `0x180010a50`
- `0x180010ff8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *PCLmWriter::PDFFactory::CreateDictionaryObject(__int64 a1, _OWORD *a2, __int64 a3, int a4, ...)
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
  *(_QWORD *)v8 = &std::_Ref_count_obj2<PCLmWriter::DictionaryObject const>::`vftable';
  std::_Construct_in_place<PCLmWriter::DictionaryObject,std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>> const &,unsigned int &,unsigned int &>(
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
0x180012580  mov     [rsp+arg_0], rbx
0x180012585  mov     [rsp+arg_18], r9d
0x18001258a  mov     [rsp+arg_8], rdx
0x18001258f  push    rsi
0x180012590  push    rdi
0x180012591  push    r14
0x180012593  sub     rsp, 40h
0x180012597  mov     rsi, r8
0x18001259a  mov     r14, rdx
0x18001259d  mov     ecx, 48h ; 'H'; Size
0x1800125a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800125a7  mov     rdi, rax
0x1800125aa  mov     [rsp+58h+arg_8], rax
0x1800125af  xorps   xmm0, xmm0
0x1800125b2  movups  xmmword ptr [rax], xmm0
0x1800125b5  mov     eax, 1
0x1800125ba  mov     [rdi+8], eax
0x1800125bd  mov     [rdi+0Ch], eax
0x1800125c0  lea     rax, ??_7?$_Ref_count_obj2@$$CBVDictionaryObject@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::DictionaryObject const>::`vftable'
0x1800125c7  mov     [rdi], rax
0x1800125ca  lea     r9, [rsp+58h+arg_20]
0x1800125d2  lea     r8, [rsp+58h+arg_18]
0x1800125d7  mov     rdx, rsi
0x1800125da  lea     rcx, [rdi+10h]
0x1800125de  call    ??$_Construct_in_place@VDictionaryObject@PCLmWriter@@AEBV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAIAEAI@std@@YAXAEAVDictionaryObject@PCLmWriter@@AEBV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@0@AEAI2@Z; std::_Construct_in_place<PCLmWriter::DictionaryObject,std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>> const &,uint &,uint &>(PCLmWriter::DictionaryObject &,std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>> const &,uint &,uint &)
0x1800125e3  nop
0x1800125e4  xorps   xmm0, xmm0
0x1800125e7  movdqu  [rsp+58h+var_30], xmm0
0x1800125ed  mov     r8, rdi
0x1800125f0  lea     rdx, [rdi+10h]
0x1800125f4  lea     rcx, [rsp+58h+var_30]
0x1800125f9  call    ??$_Set_ptr_rep_and_enable_shared@VIntegerNumberObject@PCLmWriter@@@?$shared_ptr@$$CBVIntegerNumberObject@PCLmWriter@@@std@@AEAAXQEAVIntegerNumberObject@PCLmWriter@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<PCLmWriter::IntegerNumberObject const>::_Set_ptr_rep_and_enable_shared<PCLmWriter::IntegerNumberObject>(PCLmWriter::IntegerNumberObject * const,std::_Ref_count_base * const)
0x1800125fe  mov     rax, qword ptr [rsp+58h+var_30]
0x180012603  mov     [r14], rax
0x180012606  mov     rax, qword ptr [rsp+58h+var_30+8]
0x18001260b  mov     [r14+8], rax
0x18001260f  mov     rax, r14
0x180012612  mov     rbx, [rsp+58h+arg_0]
0x180012617  add     rsp, 40h
0x18001261b  pop     r14
0x18001261d  pop     rdi
0x18001261e  pop     rsi
0x18001261f  retn
```
