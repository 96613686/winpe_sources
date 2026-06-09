# CollectionImplementationBase::Deserialize(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000eac0`
- end: `0x18000ef1f`
- name: `?Deserialize@CollectionImplementationBase@@QEAAXPEAV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18000e8dc`

## callees

- `0x180004080`
- `0x180009028`
- `0x18000a90c`
- `0x18000d6f4`
- `0x18000eac0`
- `0x18000ef28`
- `0x18000f068`
- `0x18000f0f8`
- `0x18000f11c`
- `0x18000f478`
- `0x180016d0c`
- `0x180017e38`
- `0x1800180f4`
- `0x18001bab0`
- `0x1800227c0`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CollectionImplementationBase::Deserialize(
        void (__fastcall ***a1)(_QWORD, _BYTE *),
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rdx
  int v7; // eax
  char v8; // r15
  __int64 v9; // rdx
  __int64 v10; // rdx
  int v11; // eax
  char v12; // bl
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  void (__fastcall *v15)(_QWORD, _BYTE *); // rbx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  int v19; // eax
  char v20; // bl
  __int64 v21; // rdx
  int v22; // eax
  char v23; // bl
  void *v24; // rdx
  unsigned int v25; // r8d
  _QWORD *v26; // rcx
  void (__fastcall *v27)(_QWORD, _BYTE *); // rbx
  _QWORD *v28; // rcx
  int v29; // eax
  int v31; // [rsp+20h] [rbp-E0h]
  _BYTE v32[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v34; // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  char v37; // [rsp+88h] [rbp-78h]
  __int128 v38; // [rsp+90h] [rbp-70h]
  char v39; // [rsp+A0h] [rbp-60h]
  _QWORD v40[2]; // [rsp+A8h] [rbp-58h] BYREF
  char v41; // [rsp+B8h] [rbp-48h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  _BYTE v43[40]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v44[40]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v42 = -2;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40[0] = 0;
  v40[1] = 0;
  v41 = 0;
  v6 = std::operator+<unsigned short>(v43, a1 + 1, L":\\[");
  v7 = std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(
         v32,
         v6);
  if ( !(unsigned __int8)std::tr1::_Regex_search<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>>,unsigned short,std::tr1::regex_traits<unsigned short>,std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>(
                           *a2,
                           *a3,
                           (unsigned int)&v33,
                           v7) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\applicabilitycontext.cpp",
      (const char *)0x80070057LL,
      v31);
  std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(v32);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v43);
  *a2 = v38;
  v8 = 0;
  std::operator+<unsigned short>(v43, v9, a1 + 6);
  v10 = std::operator+<unsigned short>(v44);
  v11 = std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(
          v32,
          v10);
  v12 = std::tr1::_Regex_search<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>>,unsigned short,std::tr1::regex_traits<unsigned short>,std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>(
          *a2,
          *a3,
          (unsigned int)&v33,
          v11);
  std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(v32);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v44);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v43);
  if ( v12 )
  {
    do
    {
      v8 = 1;
      v14 = v40;
      if ( (unsigned __int64)(((_QWORD)v34 - *((_QWORD *)&v33 + 1)) / 24LL) > 1 )
        v14 = (_QWORD *)(*((_QWORD *)&v33 + 1) + 24LL);
      std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>::str(
        v14,
        v43);
      CollectionImplementationBase::CheckValidity(a1, v43);
      std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v43);
      v15 = **a1;
      v16 = v40;
      if ( (unsigned __int64)(((_QWORD)v34 - *((_QWORD *)&v33 + 1)) / 24LL) > 1 )
        v16 = (_QWORD *)(*((_QWORD *)&v33 + 1) + 24LL);
      std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>::str(
        v16,
        v43);
      v15(a1, v43);
      std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v43);
      *a2 = v38;
      std::operator+<unsigned short>(v43, v17, a1 + 6);
      v18 = std::operator+<unsigned short>(v44);
      v19 = std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(
              v32,
              v18);
      v20 = std::tr1::_Regex_search<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>>,unsigned short,std::tr1::regex_traits<unsigned short>,std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>(
              *a2,
              *a3,
              (unsigned int)&v33,
              v19);
      std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(v32);
      std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v44);
      std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v43);
    }
    while ( v20 );
  }
  std::operator+<unsigned short>(v44, v13, a1 + 6);
  v21 = std::operator+<unsigned short>(v43);
  v22 = std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(
          v32,
          v21);
  v23 = std::tr1::_Regex_search<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>>,unsigned short,std::tr1::regex_traits<unsigned short>,std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>(
          *a2,
          *a3,
          (unsigned int)&v33,
          v22);
  std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(v32);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v43);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v44);
  if ( v23 )
  {
    v26 = v40;
    if ( (unsigned __int64)(((_QWORD)v34 - *((_QWORD *)&v33 + 1)) / 24LL) > 1 )
      v26 = (_QWORD *)(*((_QWORD *)&v33 + 1) + 24LL);
    std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>::str(
      v26,
      v43);
    CollectionImplementationBase::CheckValidity(a1, v43);
    std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v43);
    v27 = **a1;
    v28 = v40;
    if ( (unsigned __int64)(((_QWORD)v34 - *((_QWORD *)&v33 + 1)) / 24LL) > 1 )
      v28 = (_QWORD *)(*((_QWORD *)&v33 + 1) + 24LL);
    std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>::str(
      v28,
      v43);
    v27(a1, v43);
    std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v43);
    *a2 = v38;
  }
  else if ( v8 )
  {
    wil::details::in1diag3::Throw_Hr(retaddr, v24, v25, (const char *)0x80070057LL, v31);
  }
  v29 = std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(
          v32,
          L"\\]");
  if ( !(unsigned __int8)std::tr1::_Regex_search<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>>,unsigned short,std::tr1::regex_traits<unsigned short>,std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>(
                           *a2,
                           *a3,
                           (unsigned int)&v33,
                           v29) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\applicabilitycontext.cpp",
      (const char *)0x80070057LL,
      v31);
  std::tr1::basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::tr1::regex_traits<unsigned short>>(v32);
  *a2 = v38;
  return std::vector<enum DX_FEATURE_LEVEL>::~vector<enum DX_FEATURE_LEVEL>((char *)&v33 + 8);
}

```

## disassembly

```asm
0x18000eac0  push    rbp
0x18000eac2  push    rbx
0x18000eac3  push    rsi
0x18000eac4  push    rdi
0x18000eac5  push    r12
0x18000eac7  push    r14
0x18000eac9  push    r15
0x18000eacb  lea     rbp, [rsp-30h]
0x18000ead0  sub     rsp, 130h
0x18000ead7  mov     [rbp+60h+var_98], 0FFFFFFFFFFFFFFFEh
0x18000eadf  mov     rax, cs:__security_cookie
0x18000eae6  xor     rax, rsp
0x18000eae9  mov     [rbp+60h+var_40], rax
0x18000eaed  mov     r14, r8
0x18000eaf0  mov     rdi, rdx
0x18000eaf3  mov     rsi, rcx
0x18000eaf6  xorps   xmm0, xmm0
0x18000eaf9  movdqa  [rsp+160h+var_110], xmm0
0x18000eaff  xorps   xmm1, xmm1
0x18000eb02  movdqa  [rsp+160h+var_100], xmm1
0x18000eb08  mov     [rsp+160h+var_E8], 0
0x18000eb11  mov     [rbp+60h+var_E0], 0
0x18000eb19  mov     [rbp+60h+var_D8], 0
0x18000eb1d  movdqa  [rbp+60h+var_D0], xmm0
0x18000eb22  mov     [rbp+60h+var_C0], 0
0x18000eb26  mov     [rbp+60h+var_B8], 0
0x18000eb2e  mov     [rbp+60h+var_B0], 0
0x18000eb36  mov     [rbp+60h+var_A8], 0
0x18000eb3a  lea     rdx, [rcx+8]
0x18000eb3e  lea     r8, asc_18002E718; ":\\["
0x18000eb45  lea     rcx, [rbp+60h+var_90]
0x18000eb49  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18000eb4e  nop
0x18000eb4f  mov     rdx, rax
0x18000eb52  lea     rcx, [rsp+160h+var_130]
0x18000eb57  call    ??$?0U?$char_traits@G@std@@V?$allocator@G@1@@?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4syntax_option_type@regex_constants@12@@Z; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::basic_regex<ushort,std::tr1::regex_traits<ushort>>(std::wstring const &,std::tr1::regex_constants::syntax_option_type)
0x18000eb5c  nop
0x18000eb5d  mov     rcx, [rdi]
0x18000eb60  mov     [rsp+160h+var_138], rcx
0x18000eb65  mov     r9, rax
0x18000eb68  lea     r8, [rsp+160h+var_110]
0x18000eb6d  mov     rdx, [r14]
0x18000eb70  call    ??$_Regex_search@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@GV?$regex_traits@G@tr1@2@V12@@tr1@std@@YA_NV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0PEAV?$match_results@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@@01@AEBV?$basic_regex@GV?$regex_traits@G@tr1@std@@@01@W4match_flag_type@regex_constants@01@0@Z; std::tr1::_Regex_search<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,ushort,std::tr1::regex_traits<ushort>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::tr1::match_results<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>> const &,std::tr1::regex_constants::match_flag_type,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>)
0x18000eb75  mov     rcx, [rbp+68h]; this
0x18000eb79  test    al, al
0x18000eb7b  jnz     short loc_18000EB95
0x18000eb7d  mov     r9d, 80070057h; char *
0x18000eb83  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000eb8a  mov     edx, 45h ; 'E'; void *
0x18000eb8f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000eb95  lea     rcx, [rsp+160h+var_130]
0x18000eb9a  call    ??1?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::~basic_regex<ushort,std::tr1::regex_traits<ushort>>(void)
0x18000eb9f  nop
0x18000eba0  lea     rcx, [rbp+60h+var_90]
0x18000eba4  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000eba9  mov     rax, qword ptr [rbp+60h+var_D0]
0x18000ebad  mov     [rdi], rax
0x18000ebb0  xor     r15b, r15b
0x18000ebb3  lea     r12, [rsi+30h]
0x18000ebb7  mov     r8, r12
0x18000ebba  lea     rcx, [rbp+60h+var_90]
0x18000ebbe  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x18000ebc3  nop
0x18000ebc4  lea     r8, asc_18002EE68; "),"
0x18000ebcb  mov     rdx, rax
0x18000ebce  lea     rcx, [rbp+60h+var_68]; void *
0x18000ebd2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18000ebd7  nop
0x18000ebd8  mov     rdx, rax
0x18000ebdb  lea     rcx, [rsp+160h+var_130]
0x18000ebe0  call    ??$?0U?$char_traits@G@std@@V?$allocator@G@1@@?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4syntax_option_type@regex_constants@12@@Z; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::basic_regex<ushort,std::tr1::regex_traits<ushort>>(std::wstring const &,std::tr1::regex_constants::syntax_option_type)
0x18000ebe5  nop
0x18000ebe6  mov     rcx, [rdi]
0x18000ebe9  mov     [rsp+160h+var_138], rcx
0x18000ebee  mov     r9, rax
0x18000ebf1  lea     r8, [rsp+160h+var_110]
0x18000ebf6  mov     rdx, [r14]
0x18000ebf9  call    ??$_Regex_search@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@GV?$regex_traits@G@tr1@2@V12@@tr1@std@@YA_NV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0PEAV?$match_results@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@@01@AEBV?$basic_regex@GV?$regex_traits@G@tr1@std@@@01@W4match_flag_type@regex_constants@01@0@Z; std::tr1::_Regex_search<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,ushort,std::tr1::regex_traits<ushort>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::tr1::match_results<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>> const &,std::tr1::regex_constants::match_flag_type,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>)
0x18000ebfe  mov     bl, al
0x18000ec00  lea     rcx, [rsp+160h+var_130]
0x18000ec05  call    ??1?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::~basic_regex<ushort,std::tr1::regex_traits<ushort>>(void)
0x18000ec0a  nop
0x18000ec0b  lea     rcx, [rbp+60h+var_68]
0x18000ec0f  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000ec14  nop
0x18000ec15  lea     rcx, [rbp+60h+var_90]
0x18000ec19  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000ec1e  mov     rax, 2AAAAAAAAAAAAAABh
0x18000ec28  test    bl, bl
0x18000ec2a  jz      loc_18000ED60
0x18000ec30  jmp     short loc_18000EC3C
0x18000ec32  mov     rax, 2AAAAAAAAAAAAAABh
0x18000ec3c  mov     r15b, 1
0x18000ec3f  mov     r8, qword ptr [rsp+160h+var_110+8]
0x18000ec44  mov     rcx, qword ptr [rsp+160h+var_100]
0x18000ec49  sub     rcx, r8
0x18000ec4c  imul    rcx
0x18000ec4f  sar     rdx, 2
0x18000ec53  mov     rax, rdx
0x18000ec56  shr     rax, 3Fh
0x18000ec5a  add     rdx, rax
0x18000ec5d  cmp     rdx, 1
0x18000ec61  lea     rcx, [rbp+60h+var_B8]
0x18000ec65  jbe     short loc_18000EC6B
0x18000ec67  lea     rcx, [r8+18h]
0x18000ec6b  lea     rdx, [rbp+60h+var_90]
0x18000ec6f  call    ?str@?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::str(void)
0x18000ec74  nop
0x18000ec75  lea     rdx, [rbp+60h+var_90]
0x18000ec79  mov     rcx, rsi
0x18000ec7c  call    ?CheckValidity@CollectionImplementationBase@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CollectionImplementationBase::CheckValidity(std::wstring const &)
0x18000ec81  nop
0x18000ec82  lea     rcx, [rbp+60h+var_90]
0x18000ec86  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000ec8b  mov     rax, [rsi]
0x18000ec8e  mov     rbx, [rax]
0x18000ec91  mov     r8, qword ptr [rsp+160h+var_110+8]
0x18000ec96  mov     rcx, qword ptr [rsp+160h+var_100]
0x18000ec9b  sub     rcx, r8
0x18000ec9e  mov     rax, 2AAAAAAAAAAAAAABh
0x18000eca8  imul    rcx
0x18000ecab  sar     rdx, 2
0x18000ecaf  mov     rax, rdx
0x18000ecb2  shr     rax, 3Fh
0x18000ecb6  add     rdx, rax
0x18000ecb9  cmp     rdx, 1
0x18000ecbd  lea     rcx, [rbp+60h+var_B8]
0x18000ecc1  jbe     short loc_18000ECC7
0x18000ecc3  lea     rcx, [r8+18h]
0x18000ecc7  lea     rdx, [rbp+60h+var_90]
0x18000eccb  call    ?str@?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::str(void)
0x18000ecd0  nop
0x18000ecd1  lea     rdx, [rbp+60h+var_90]
0x18000ecd5  mov     rcx, rsi
0x18000ecd8  mov     rax, rbx
0x18000ecdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ece0  nop
0x18000ece1  lea     rcx, [rbp+60h+var_90]
0x18000ece5  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000ecea  mov     rax, qword ptr [rbp+60h+var_D0]
0x18000ecee  mov     [rdi], rax
0x18000ecf1  mov     r8, r12
0x18000ecf4  lea     rcx, [rbp+60h+var_90]
0x18000ecf8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x18000ecfd  nop
0x18000ecfe  lea     r8, asc_18002EE68; "),"
0x18000ed05  mov     rdx, rax
0x18000ed08  lea     rcx, [rbp+60h+var_68]; void *
0x18000ed0c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18000ed11  nop
0x18000ed12  mov     rdx, rax
0x18000ed15  lea     rcx, [rsp+160h+var_130]
0x18000ed1a  call    ??$?0U?$char_traits@G@std@@V?$allocator@G@1@@?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4syntax_option_type@regex_constants@12@@Z; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::basic_regex<ushort,std::tr1::regex_traits<ushort>>(std::wstring const &,std::tr1::regex_constants::syntax_option_type)
0x18000ed1f  nop
0x18000ed20  mov     rcx, [rdi]
0x18000ed23  mov     [rsp+160h+var_138], rcx
0x18000ed28  mov     r9, rax
0x18000ed2b  lea     r8, [rsp+160h+var_110]
0x18000ed30  mov     rdx, [r14]
0x18000ed33  call    ??$_Regex_search@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@GV?$regex_traits@G@tr1@2@V12@@tr1@std@@YA_NV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0PEAV?$match_results@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@@01@AEBV?$basic_regex@GV?$regex_traits@G@tr1@std@@@01@W4match_flag_type@regex_constants@01@0@Z; std::tr1::_Regex_search<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,ushort,std::tr1::regex_traits<ushort>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::tr1::match_results<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>> const &,std::tr1::regex_constants::match_flag_type,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>)
0x18000ed38  mov     bl, al
0x18000ed3a  lea     rcx, [rsp+160h+var_130]
0x18000ed3f  call    ??1?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::~basic_regex<ushort,std::tr1::regex_traits<ushort>>(void)
0x18000ed44  nop
0x18000ed45  lea     rcx, [rbp+60h+var_68]
0x18000ed49  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000ed4e  nop
0x18000ed4f  lea     rcx, [rbp+60h+var_90]
0x18000ed53  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000ed58  test    bl, bl
0x18000ed5a  jnz     loc_18000EC32
0x18000ed60  mov     r8, r12
0x18000ed63  lea     rcx, [rbp+60h+var_68]
0x18000ed67  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x18000ed6c  nop
0x18000ed6d  lea     r8, asc_18002EE74; ")"
0x18000ed74  mov     rdx, rax
0x18000ed77  lea     rcx, [rbp+60h+var_90]; void *
0x18000ed7b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18000ed80  nop
0x18000ed81  mov     rdx, rax
0x18000ed84  lea     rcx, [rsp+160h+var_130]
0x18000ed89  call    ??$?0U?$char_traits@G@std@@V?$allocator@G@1@@?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4syntax_option_type@regex_constants@12@@Z; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::basic_regex<ushort,std::tr1::regex_traits<ushort>>(std::wstring const &,std::tr1::regex_constants::syntax_option_type)
0x18000ed8e  nop
0x18000ed8f  mov     rcx, [rdi]
0x18000ed92  mov     [rsp+160h+var_138], rcx
0x18000ed97  mov     r9, rax
0x18000ed9a  lea     r8, [rsp+160h+var_110]
0x18000ed9f  mov     rdx, [r14]
0x18000eda2  call    ??$_Regex_search@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@GV?$regex_traits@G@tr1@2@V12@@tr1@std@@YA_NV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0PEAV?$match_results@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@@01@AEBV?$basic_regex@GV?$regex_traits@G@tr1@std@@@01@W4match_flag_type@regex_constants@01@0@Z; std::tr1::_Regex_search<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,ushort,std::tr1::regex_traits<ushort>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::tr1::match_results<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>> const &,std::tr1::regex_constants::match_flag_type,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>)
0x18000eda7  mov     bl, al
0x18000eda9  lea     rcx, [rsp+160h+var_130]
0x18000edae  call    ??1?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::~basic_regex<ushort,std::tr1::regex_traits<ushort>>(void)
0x18000edb3  nop
0x18000edb4  lea     rcx, [rbp+60h+var_90]
0x18000edb8  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000edbd  nop
0x18000edbe  lea     rcx, [rbp+60h+var_68]
0x18000edc2  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000edc7  test    bl, bl
0x18000edc9  jz      loc_18000EED1
0x18000edcf  mov     r8, qword ptr [rsp+160h+var_110+8]
0x18000edd4  mov     rcx, qword ptr [rsp+160h+var_100]
0x18000edd9  sub     rcx, r8
0x18000eddc  mov     r15, 2AAAAAAAAAAAAAABh
0x18000ede6  mov     rax, r15
0x18000ede9  imul    rcx
0x18000edec  sar     rdx, 2
0x18000edf0  mov     rax, rdx
0x18000edf3  shr     rax, 3Fh
0x18000edf7  add     rdx, rax
0x18000edfa  cmp     rdx, 1
0x18000edfe  lea     rcx, [rbp+60h+var_B8]
0x18000ee02  jbe     short loc_18000EE08
0x18000ee04  lea     rcx, [r8+18h]
0x18000ee08  lea     rdx, [rbp+60h+var_90]
0x18000ee0c  call    ?str@?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::str(void)
0x18000ee11  nop
0x18000ee12  lea     rdx, [rbp+60h+var_90]
0x18000ee16  mov     rcx, rsi
0x18000ee19  call    ?CheckValidity@CollectionImplementationBase@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CollectionImplementationBase::CheckValidity(std::wstring const &)
0x18000ee1e  nop
0x18000ee1f  lea     rcx, [rbp+60h+var_90]
0x18000ee23  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000ee28  mov     rcx, [rsi]
0x18000ee2b  mov     rbx, [rcx]
0x18000ee2e  mov     r8, qword ptr [rsp+160h+var_110+8]
0x18000ee33  mov     rcx, qword ptr [rsp+160h+var_100]
0x18000ee38  sub     rcx, r8
0x18000ee3b  mov     rax, r15
0x18000ee3e  imul    rcx
0x18000ee41  sar     rdx, 2
0x18000ee45  mov     rax, rdx
0x18000ee48  shr     rax, 3Fh
0x18000ee4c  add     rdx, rax
0x18000ee4f  cmp     rdx, 1
0x18000ee53  lea     rcx, [rbp+60h+var_B8]
0x18000ee57  jbe     short loc_18000EE5D
0x18000ee59  lea     rcx, [r8+18h]
0x18000ee5d  lea     rdx, [rbp+60h+var_90]
0x18000ee61  call    ?str@?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::str(void)
0x18000ee66  nop
0x18000ee67  lea     rdx, [rbp+60h+var_90]
0x18000ee6b  mov     rcx, rsi
0x18000ee6e  mov     rax, rbx
0x18000ee71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee76  nop
0x18000ee77  lea     rcx, [rbp+60h+var_90]
0x18000ee7b  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000ee80  mov     rax, qword ptr [rbp+60h+var_D0]
0x18000ee84  mov     [rdi], rax
0x18000ee87  lea     rdx, asc_18002E720; "\\]"
0x18000ee8e  lea     rcx, [rsp+160h+var_130]
0x18000ee93  call    ??0?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@PEBGW4syntax_option_type@regex_constants@12@@Z; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::basic_regex<ushort,std::tr1::regex_traits<ushort>>(ushort const *,std::tr1::regex_constants::syntax_option_type)
0x18000ee98  nop
0x18000ee99  mov     rcx, [rdi]
0x18000ee9c  mov     [rsp+160h+var_138], rcx
0x18000eea1  mov     r9, rax
0x18000eea4  lea     r8, [rsp+160h+var_110]
0x18000eea9  mov     rdx, [r14]
0x18000eeac  call    ??$_Regex_search@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@GV?$regex_traits@G@tr1@2@V12@@tr1@std@@YA_NV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0PEAV?$match_results@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@tr1@std@@@2@@01@AEBV?$basic_regex@GV?$regex_traits@G@tr1@std@@@01@W4match_flag_type@regex_constants@01@0@Z; std::tr1::_Regex_search<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,ushort,std::tr1::regex_traits<ushort>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::tr1::match_results<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::tr1::sub_match<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *,std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>> const &,std::tr1::regex_constants::match_flag_type,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>)
0x18000eeb1  mov     rcx, [rbp+68h]; this
0x18000eeb5  test    al, al
0x18000eeb7  jnz     short loc_18000EEE6
0x18000eeb9  mov     r9d, 80070057h; char *
0x18000eebf  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000eec6  mov     edx, 5Fh ; '_'; void *
0x18000eecb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000eed1  test    r15b, r15b
0x18000eed4  jz      short loc_18000EE87
0x18000eed6  mov     rcx, [rbp+68h]; this
0x18000eeda  mov     r9d, 80070057h; char *
0x18000eee0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000eee6  lea     rcx, [rsp+160h+var_130]
0x18000eeeb  call    ??1?$basic_regex@GV?$regex_traits@G@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::basic_regex<ushort,std::tr1::regex_traits<ushort>>::~basic_regex<ushort,std::tr1::regex_traits<ushort>>(void)
0x18000eef0  mov     rax, qword ptr [rbp+60h+var_D0]
0x18000eef4  mov     [rdi], rax
0x18000eef7  lea     rcx, [rsp+160h+var_110+8]
0x18000eefc  call    ??1?$vector@W4DX_FEATURE_LEVEL@@V?$allocator@W4DX_FEATURE_LEVEL@@@std@@@std@@QEAA@XZ; std::vector<DX_FEATURE_LEVEL>::~vector<DX_FEATURE_LEVEL>(void)
0x18000ef01  mov     rcx, [rbp+60h+var_40]
0x18000ef05  xor     rcx, rsp; StackCookie
0x18000ef08  call    __security_check_cookie
0x18000ef0d  add     rsp, 130h
0x18000ef14  pop     r15
0x18000ef16  pop     r14
0x18000ef18  pop     r12
0x18000ef1a  pop     rdi
0x18000ef1b  pop     rsi
0x18000ef1c  pop     rbx
0x18000ef1d  pop     rbp
0x18000ef1e  retn
```
