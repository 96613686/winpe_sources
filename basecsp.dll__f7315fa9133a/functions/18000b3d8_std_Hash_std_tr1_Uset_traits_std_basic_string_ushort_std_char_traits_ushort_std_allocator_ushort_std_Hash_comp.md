# std::_Hash<std::tr1::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Hash<std::tr1::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>(std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &)

- ea: `0x18000b3d8`
- end: `0x18000b473`
- name: `??0?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA@AEBV?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013fdc`

## callees

- `0x1800014dc`
- `0x1800020de`
- `0x18000b3d8`
- `0x18000b7a4`
- `0x18001818c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int16 *__fastcall std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(
        __int64 a1,
        __int16 *a2)
{
  _QWORD *v2; // rax
  const char *v3; // rdx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  word_18003C890 = *a2;
  qword_18003C8A0 = 0;
  v2 = operator new(0x38u);
  if ( !v2 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v3);
    throw (std::bad_alloc *)pExceptionObject;
  }
  qword_18003C898 = (__int64)v2;
  *v2 = v2;
  v2[1] = v2;
  xmmword_18003C8B0 = 0;
  qword_18003C8C0 = 0;
  dword_18003C8E0 = 1065353216;
  std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(
    &word_18003C890,
    8);
  return &word_18003C890;
}

```

## disassembly

```asm
0x18000b3d8  mov     [rsp+arg_10], r8
0x18000b3dd  push    rbx
0x18000b3de  sub     rsp, 40h
0x18000b3e2  lea     rbx, word_18003C890
0x18000b3e9  mov     [rsp+48h+arg_10], rbx
0x18000b3ee  movzx   eax, word ptr [rdx]
0x18000b3f1  mov     cs:word_18003C890, ax
0x18000b3f8  mov     cs:qword_18003C8A0, 0
0x18000b403  mov     ecx, 38h ; '8'; Size
0x18000b408  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b40d  test    rax, rax
0x18000b410  jz      short loc_18000B457
0x18000b412  mov     cs:qword_18003C898, rax
0x18000b419  mov     [rax], rax
0x18000b41c  mov     [rax+8], rax
0x18000b420  xorps   xmm0, xmm0
0x18000b423  movdqa  cs:xmmword_18003C8B0, xmm0
0x18000b42b  mov     cs:qword_18003C8C0, 0
0x18000b436  mov     cs:dword_18003C8E0, 3F800000h
0x18000b440  mov     edx, 8
0x18000b445  mov     rcx, rbx
0x18000b448  call    ?_Init@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAX_K@Z; std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(unsigned __int64)
0x18000b44d  nop
0x18000b44e  mov     rax, rbx
0x18000b451  add     rsp, 40h
0x18000b455  pop     rbx
0x18000b456  retn
0x18000b457  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000b45c  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18000b461  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000b468  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000b46d  call    _CxxThrowException_0
```
