# ApplicabilityContextInternal::Create(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000e8dc`
- end: `0x18000eab9`
- name: `?Create@ApplicabilityContextInternal@@SA?AV?$unique_ptr@VApplicabilityContextInternal@@U?$default_delete@VApplicabilityContextInternal@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `477`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000e840`

## callees

- `0x180009f34`
- `0x18000a90c`
- `0x18000d6f4`
- `0x18000e8dc`
- `0x18000eac0`
- `0x18000ef28`
- `0x18000f068`
- `0x18000f0f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall ApplicabilityContextInternal::Create(__int64 *a1, _QWORD *a2)
{
  _QWORD *v4; // rcx
  int v5; // eax
  int v6; // eax
  int v8; // [rsp+20h] [rbp-79h]
  _OWORD v9[2]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v10; // [rsp+68h] [rbp-31h]
  __int64 v11; // [rsp+70h] [rbp-29h]
  char v12; // [rsp+78h] [rbp-21h]
  __int128 v13; // [rsp+80h] [rbp-19h]
  char v14; // [rsp+90h] [rbp-9h]
  __int64 v15; // [rsp+98h] [rbp-1h]
  __int64 v16; // [rsp+A0h] [rbp+7h]
  char v17; // [rsp+A8h] [rbp+Fh]
  __int64 v18; // [rsp+B0h] [rbp+17h]
  _BYTE v19[56]; // [rsp+B8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  _QWORD *v21; // [rsp+108h] [rbp+6Fh] BYREF
  _QWORD *v22; // [rsp+110h] [rbp+77h] BYREF

  v18 = -2;
  ApplicabilityContextInternal::Create(a1);
  if ( a2[3] < 8u )
  {
    v21 = a2;
    v4 = a2;
  }
  else
  {
    v21 = (_QWORD *)*a2;
    v4 = v21;
  }
  v22 = (_QWORD *)((char *)v4 + 2 * a2[2]);
  CollectionImplementationBase::Deserialize(
    (void (__fastcall ***)(_QWORD, _BYTE *))(*(_QWORD *)(*a1 + 8) + 8LL),
    &v21,
    &v22);
  memset(v9, 0, sizeof(v9));
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v5 = std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(
         v19,
         L",");
  if ( !(unsigned __int8)std::tr1::_Regex_search<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>>,unsigned short,std::tr1::regex_traits<unsigned short>,std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>(
                           (_DWORD)v21,
                           (_DWORD)v22,
                           (unsigned int)v9,
                           v5) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\applicabilitycontext.cpp",
      (const char *)0x80070057LL,
      v8);
  std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(v19);
  v21 = (_QWORD *)v13;
  CollectionImplementationBase::Deserialize(
    (void (__fastcall ***)(_QWORD, _BYTE *))(*(_QWORD *)(*a1 + 16) + 8LL),
    &v21,
    &v22);
  v6 = std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(
         v19,
         L",");
  if ( !(unsigned __int8)std::tr1::_Regex_search<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>>,unsigned short,std::tr1::regex_traits<unsigned short>,std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>(
                           (_DWORD)v21,
                           (_DWORD)v22,
                           (unsigned int)v9,
                           v6) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\applicabilitycontext.cpp",
      (const char *)0x80070057LL,
      v8);
  std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(v19);
  v21 = (_QWORD *)v13;
  CollectionImplementationBase::Deserialize(
    (void (__fastcall ***)(_QWORD, _BYTE *))(*(_QWORD *)(*a1 + 24) + 8LL),
    &v21,
    &v22);
  if ( v21 != v22 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\applicabilitycontext.cpp",
      (const char *)0x80070057LL,
      v8);
  std::vector<enum DX_FEATURE_LEVEL>::~vector<enum DX_FEATURE_LEVEL>((char *)v9 + 8);
  return a1;
}

```

## disassembly

```asm
0x18000e8dc  mov     [rsp-8+arg_0], rcx
0x18000e8e1  push    rbp
0x18000e8e2  push    rbx
0x18000e8e3  push    rdi
0x18000e8e4  lea     rbp, [rsp-47h]
0x18000e8e9  sub     rsp, 0E0h
0x18000e8f0  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x18000e8f8  mov     rbx, rdx
0x18000e8fb  mov     rdi, rcx
0x18000e8fe  mov     [rbp+57h+var_C0], 0
0x18000e905  call    ?Create@ApplicabilityContextInternal@@SA?AV?$unique_ptr@VApplicabilityContextInternal@@U?$default_delete@VApplicabilityContextInternal@@@std@@@std@@XZ; ApplicabilityContextInternal::Create(void)
0x18000e90a  mov     [rbp+57h+var_C0], 1
0x18000e911  cmp     qword ptr [rbx+18h], 8
0x18000e916  jb      short loc_18000E924
0x18000e918  mov     rax, [rbx]
0x18000e91b  mov     [rbp+57h+arg_8], rax
0x18000e91f  mov     rcx, rax
0x18000e922  jmp     short loc_18000E92B
0x18000e924  mov     [rbp+57h+arg_8], rbx
0x18000e928  mov     rcx, rbx
0x18000e92b  mov     rax, [rbx+10h]
0x18000e92f  lea     rcx, [rcx+rax*2]
0x18000e933  mov     [rbp+57h+arg_10], rcx
0x18000e937  mov     rax, [rdi]
0x18000e93a  mov     rcx, [rax+8]
0x18000e93e  add     rcx, 8
0x18000e942  lea     r8, [rbp+57h+arg_10]
0x18000e946  lea     rdx, [rbp+57h+arg_8]
0x18000e94a  call    ?Deserialize@CollectionImplementationBase@@QEAAXPEAV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; CollectionImplementationBase::Deserialize(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)
0x18000e94f  xorps   xmm0, xmm0
0x18000e952  movdqa  [rbp+57h+var_B0], xmm0
0x18000e957  xorps   xmm1, xmm1
0x18000e95a  movdqa  [rbp+57h+var_A0], xmm1
0x18000e95f  mov     [rbp+57h+var_88], 0
0x18000e967  mov     [rbp+57h+var_80], 0
0x18000e96f  mov     [rbp+57h+var_78], 0
0x18000e973  movdqa  [rbp+57h+var_70], xmm0
0x18000e978  mov     [rbp+57h+var_60], 0
0x18000e97c  mov     [rbp+57h+var_58], 0
0x18000e984  mov     [rbp+57h+var_50], 0
0x18000e98c  mov     [rbp+57h+var_48], 0
0x18000e990  lea     rdx, asc_18002E714; ","
0x18000e997  lea     rcx, [rbp+57h+var_38]
0x18000e99b  call    ??0?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@PEBGW4syntax_option_type@regex_constants@12@@Z; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::basic_regex<ushort,std::tr1::regex_traits<ushort>>(ushort const *,std::tr1::regex_constants::syntax_option_type)
0x18000e9a0  nop
0x18000e9a1  mov     rcx, [rbp+57h+arg_8]
0x18000e9a5  mov     [rsp+0F0h+var_C8], rcx
0x18000e9aa  mov     r9, rax
0x18000e9ad  lea     r8, [rbp+57h+var_B0]
0x18000e9b1  mov     rdx, [rbp+57h+arg_10]
0x18000e9b5  call    ??$_Regex_search@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@GV?$regex_traits@G@tr1@2@V12@@tr1@std@@YA_NV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0PEAV?$match_results@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@@01@AEBV?$basic_regex@GV?$regex_traits@G@tr1@std@@@01@W4match_flag_type@regex_constants@01@0@Z; std::tr1::_Regex_search<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,ushort,std::tr1::regex_traits<ushort>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::tr1::match_results<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>> const &,std::tr1::regex_constants::match_flag_type,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>)
0x18000e9ba  mov     rcx, [rbp+5Fh]; this
0x18000e9be  test    al, al
0x18000e9c0  jnz     short loc_18000E9DA
0x18000e9c2  mov     r9d, 80070057h; char *
0x18000e9c8  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000e9cf  mov     edx, 11Ah; void *
0x18000e9d4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e9da  lea     rcx, [rbp+57h+var_38]
0x18000e9de  call    ??1?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::~basic_regex<ushort,std::tr1::regex_traits<ushort>>(void)
0x18000e9e3  mov     rax, qword ptr [rbp+57h+var_70]
0x18000e9e7  mov     [rbp+57h+arg_8], rax
0x18000e9eb  mov     rax, [rdi]
0x18000e9ee  mov     rcx, [rax+10h]
0x18000e9f2  add     rcx, 8
0x18000e9f6  lea     r8, [rbp+57h+arg_10]
0x18000e9fa  lea     rdx, [rbp+57h+arg_8]
0x18000e9fe  call    ?Deserialize@CollectionImplementationBase@@QEAAXPEAV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; CollectionImplementationBase::Deserialize(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)
0x18000ea03  lea     rdx, asc_18002E714; ","
0x18000ea0a  lea     rcx, [rbp+57h+var_38]
0x18000ea0e  call    ??0?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@PEBGW4syntax_option_type@regex_constants@12@@Z; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::basic_regex<ushort,std::tr1::regex_traits<ushort>>(ushort const *,std::tr1::regex_constants::syntax_option_type)
0x18000ea13  nop
0x18000ea14  mov     rcx, [rbp+57h+arg_8]
0x18000ea18  mov     [rsp+0F0h+var_C8], rcx
0x18000ea1d  mov     r9, rax
0x18000ea20  lea     r8, [rbp+57h+var_B0]
0x18000ea24  mov     rdx, [rbp+57h+arg_10]
0x18000ea28  call    ??$_Regex_search@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@GV?$regex_traits@G@tr1@2@V12@@tr1@std@@YA_NV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0PEAV?$match_results@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@@01@AEBV?$basic_regex@GV?$regex_traits@G@tr1@std@@@01@W4match_flag_type@regex_constants@01@0@Z; std::tr1::_Regex_search<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,ushort,std::tr1::regex_traits<ushort>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::tr1::match_results<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>> const &,std::tr1::regex_constants::match_flag_type,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>)
0x18000ea2d  mov     rcx, [rbp+5Fh]; this
0x18000ea31  test    al, al
0x18000ea33  jnz     short loc_18000EA4D
0x18000ea35  mov     r9d, 80070057h; char *
0x18000ea3b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000ea42  mov     edx, 120h; void *
0x18000ea47  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ea4d  lea     rcx, [rbp+57h+var_38]
0x18000ea51  call    ??1?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::~basic_regex<ushort,std::tr1::regex_traits<ushort>>(void)
0x18000ea56  mov     rax, qword ptr [rbp+57h+var_70]
0x18000ea5a  mov     [rbp+57h+arg_8], rax
0x18000ea5e  mov     rax, [rdi]
0x18000ea61  mov     rcx, [rax+18h]
0x18000ea65  add     rcx, 8
0x18000ea69  lea     r8, [rbp+57h+arg_10]
0x18000ea6d  lea     rdx, [rbp+57h+arg_8]
0x18000ea71  call    ?Deserialize@CollectionImplementationBase@@QEAAXPEAV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; CollectionImplementationBase::Deserialize(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)
0x18000ea76  mov     rax, [rbp+57h+arg_10]
0x18000ea7a  cmp     [rbp+57h+arg_8], rax
0x18000ea7e  setz    al
0x18000ea81  mov     rcx, [rbp+5Fh]; this
0x18000ea85  test    al, al
0x18000ea87  jnz     short loc_18000EAA1
0x18000ea89  mov     r9d, 80070057h; char *
0x18000ea8f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000ea96  mov     edx, 126h; void *
0x18000ea9b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000eaa1  lea     rcx, [rbp+57h+var_B0+8]
0x18000eaa5  call    ??1?$vector@W4DX_FEATURE_LEVEL@@V?$allocator@W4DX_FEATURE_LEVEL@@@std@@@std@@QEAA@XZ; std::vector<DX_FEATURE_LEVEL>::~vector<DX_FEATURE_LEVEL>(void)
0x18000eaaa  mov     rax, rdi
0x18000eaad  add     rsp, 0E0h
0x18000eab4  pop     rdi
0x18000eab5  pop     rbx
0x18000eab6  pop     rbp
0x18000eab7  retn
```
