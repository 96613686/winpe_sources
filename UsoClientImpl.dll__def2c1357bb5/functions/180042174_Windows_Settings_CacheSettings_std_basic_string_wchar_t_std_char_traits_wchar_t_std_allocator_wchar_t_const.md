# Windows::Settings::CacheSettings(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180042174`
- end: `0x180042b21`
- name: `?CacheSettings@Settings@Windows@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z`
- size: `2477`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003ef00`

## callees

- `0x180009380`
- `0x1800093fc`
- `0x180030280`
- `0x180032dec`
- `0x1800333f8`
- `0x1800338a4`
- `0x180033b00`
- `0x180033f14`
- `0x180034304`
- `0x180036b10`
- `0x18003a204`
- `0x180040a9c`
- `0x180042174`
- `0x180042c60`
- `0x18004363c`
- `0x1800439a4`
- `0x1800448c4`
- `0x18004573c`
- `0x180045864`
- `0x180045874`
- `0x180045884`
- `0x180048220`
- `0x18004bde4`
- `0x18004fc3c`
- `0x180056500`
- `0x18005c5e0`
- `0x18005c660`
- `0x18005ca20`

## string_xrefs

- `0x180042b0e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
_QWORD *__fastcall Windows::Settings::CacheSettings(__int64 a1, _QWORD *a2, __int64 a3)
{
  int v4; // esi
  _QWORD *v5; // rax
  __int64 *v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rdi
  int v9; // eax
  __int64 *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  void **v13; // rax
  int v14; // esi
  __int128 *v15; // rcx
  __int64 v16; // rax
  _QWORD *v17; // rax
  __int64 traits_2_unsigned_short; // rax
  const char *v19; // r9
  __int64 v20; // r11
  __int64 v21; // rax
  __int64 v22; // r8
  _QWORD *v24; // rcx
  __int64 v25; // r10
  void (__fastcall *v26)(__int64, void **, __int128 *, _OWORD *, _QWORD *); // r11
  __int64 v27; // rax
  __int64 v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // r10
  void (__fastcall *v31)(__int64, __int128 *, _OWORD *, void **, _QWORD *); // r11
  __int64 v32; // rax
  __int64 v33; // rax
  _QWORD *v34; // rdx
  __int64 v35; // rax
  int v36; // esi
  __int64 v37; // rax
  _WORD *v38; // r9
  unsigned int v39; // r8d
  void **v40; // rdx
  __int64 v41; // rax
  const void *v42; // r9
  void *v43; // rdx
  __int64 v44; // rbx
  __int64 v45; // [rsp+48h] [rbp-300h] BYREF
  __int128 v46; // [rsp+50h] [rbp-2F8h] BYREF
  void *Src[2]; // [rsp+60h] [rbp-2E8h] BYREF
  __int64 v48; // [rsp+70h] [rbp-2D8h]
  unsigned __int64 v49; // [rsp+78h] [rbp-2D0h]
  __int64 v50; // [rsp+80h] [rbp-2C8h]
  __int64 v51; // [rsp+88h] [rbp-2C0h]
  _QWORD *v52; // [rsp+90h] [rbp-2B8h]
  _OWORD v53[2]; // [rsp+A0h] [rbp-2A8h] BYREF
  __int128 v54; // [rsp+C0h] [rbp-288h]
  __int128 v55; // [rsp+D0h] [rbp-278h]
  __int128 v56; // [rsp+E0h] [rbp-268h]
  _QWORD v57[2]; // [rsp+F0h] [rbp-258h] BYREF
  __int128 v58; // [rsp+100h] [rbp-248h]
  __int128 v59; // [rsp+110h] [rbp-238h]
  __int128 v60; // [rsp+120h] [rbp-228h]
  __int128 v61; // [rsp+130h] [rbp-218h]
  __int128 v62; // [rsp+140h] [rbp-208h]
  __int128 v63; // [rsp+150h] [rbp-1F8h]
  _QWORD v64[2]; // [rsp+160h] [rbp-1E8h] BYREF
  __int64 v65; // [rsp+170h] [rbp-1D8h]
  unsigned __int64 v66; // [rsp+178h] [rbp-1D0h]
  __int128 v67; // [rsp+180h] [rbp-1C8h] BYREF
  __int64 v68; // [rsp+190h] [rbp-1B8h]
  unsigned __int64 v69; // [rsp+198h] [rbp-1B0h]
  _QWORD v70[4]; // [rsp+1A0h] [rbp-1A8h] BYREF
  char v71; // [rsp+1C0h] [rbp-188h]
  int v72; // [rsp+1CCh] [rbp-17Ch]
  _OWORD v73[16]; // [rsp+1D0h] [rbp-178h] BYREF
  _QWORD v74[4]; // [rsp+2D0h] [rbp-78h] BYREF
  char v75; // [rsp+2F0h] [rbp-58h]
  _BYTE v76[6]; // [rsp+2FAh] [rbp-4Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  v52 = a2;
  v45 = 0;
  web::json::value::parse(&v45, a3);
  memset(v73, 0, 0xF8u);
  *(_QWORD *)&v73[0] = &std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbtable'{for `std::wistream'};
  *(_QWORD *)&v73[1] = &std::wostringstream::`vbtable';
  memset(&v73[10], 0, 20);
  *((_QWORD *)&v73[11] + 1) = 0;
  memset(&v73[12], 0, 50);
  *((_QWORD *)&v73[9] + 1) = &std::wios::`vftable';
  v4 = 0x800000;
  std::wiostream::basic_iostream<wchar_t>(v73, (char *)&v73[1] + 8);
  *(_QWORD *)((char *)v73 + *(int *)(*(_QWORD *)&v73[0] + 4LL)) = &std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable';
  *(int *)((char *)&v72 + *(int *)(*(_QWORD *)&v73[0] + 4LL)) = *(_DWORD *)(*(_QWORD *)&v73[0] + 4LL) - 152;
  std::wstreambuf::wstreambuf((char *)&v73[1] + 8);
  *((_QWORD *)&v73[1] + 1) = &std::wstringbuf::`vftable';
  *(_QWORD *)&v73[8] = 0;
  DWORD2(v73[8]) = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v67);
  v5 = (_QWORD *)web::json::value::at(&v45, &v67);
  v6 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 168LL))(*v5);
  std::wstring::~wstring(&v67);
  v7 = *v6;
  v8 = v6[1];
  v51 = v8;
  while ( 1 )
  {
    v50 = v7;
    if ( v7 == v8 )
      break;
    std::wstring::wstring(v64, v7);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 32) + 88LL))(*(_QWORD *)(v7 + 32));
    v10 = *(__int64 **)(v7 + 32);
    v11 = *v10;
    if ( v9 == 2 )
    {
      v12 = (*(__int64 (**)(void))(v11 + 176))();
      v13 = (void **)std::wstring::wstring(v53, v12);
      v14 = v4 | 1;
    }
    else
    {
      (*(void (__fastcall **)(__int64 *, void **, __int64))(v11 + 80))(v10, Src, v11);
      v13 = Src;
      v14 = v4 | 0x400002;
    }
    std::wstring::wstring(&v67, v13);
    if ( (v14 & 2) != 0 )
    {
      v14 &= ~2u;
      std::wstring::~wstring(Src);
    }
    if ( (v14 & 1) != 0 )
    {
      v14 &= ~1u;
      std::wstring::~wstring(v53);
    }
    v15 = &v67;
    if ( v69 > 7 )
      v15 = (__int128 *)v67;
    *(_QWORD *)&v54 = v15;
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    *((_QWORD *)&v54 + 1) = v16;
    v46 = v54;
    Windows::Settings::GetValue(v15, v70, &v46);
    v17 = v64;
    if ( v66 > 7 )
      v17 = (_QWORD *)v64[0];
    *(_QWORD *)&v55 = v17;
    *((_QWORD *)&v55 + 1) = v65;
    traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                L"CLEARSETTINGS",
                                &dword_18008CB14,
                                0);
    if ( traits_2_unsigned_short == v20 || (v21 = (traits_2_unsigned_short - (__int64)L"CLEARSETTINGS") >> 1, v21 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v19);
    *(_QWORD *)&v56 = L"CLEARSETTINGS";
    *((_QWORD *)&v56 + 1) = v21;
    v46 = v55;
    v53[0] = v56;
    if ( (unsigned __int8)Strings::iequals(v53, &v46) )
    {
      if ( v71 )
        std::_Throw_bad_variant_access();
      v22 = v70[0];
      if ( LODWORD(v70[0]) == 1 )
      {
        *(_OWORD *)a2 = 0;
        a2[2] = 0;
        a2[3] = 0;
        std::wstring::_Construct<1,wchar_t const *>(a2);
        if ( v71 != -1 && v71 && v71 != 1 )
          std::wstring::~wstring(v70);
        std::wstring::~wstring(&v67);
        std::wstring::~wstring(v64);
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>((char *)&v73[9] + 8);
        *((_QWORD *)&v73[9] + 1) = &std::wios::`vftable';
        std::ios_base::~ios_base((std::ios_base *)((char *)&v73[9] + 8));
        if ( v45 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 192LL))(v45, 1);
        return a2;
      }
    }
    else
    {
      v22 = v70[0];
    }
    v57[0] = a1;
    v57[1] = v64;
    if ( v71 == -1 )
      std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_void__Windows::Settings::CacheSettings_::_7_::_lambda_1__std::variant_unsigned_int_unsigned___int64_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______const___1_();
    if ( v71 )
    {
      if ( v71 != 1 )
      {
        std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_3___::_Dispatch2_void__Windows::Settings::CacheSettings_::_7_::_lambda_1__std::variant_unsigned_int_unsigned___int64_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______const___0_(
          v57,
          v70);
        goto LABEL_51;
      }
      v24 = v64;
      if ( v66 > 7 )
        v24 = (_QWORD *)v64[0];
      v25 = *(_QWORD *)(a1 + 88);
      v26 = *(void (__fastcall **)(__int64, void **, __int128 *, _OWORD *, _QWORD *))(*(_QWORD *)v25 + 64LL);
      v74[0] = v22;
      v75 = 1;
      *(_QWORD *)&v58 = v24;
      *((_QWORD *)&v58 + 1) = v65;
      v27 = -1;
      do
        ++v27;
      while ( Windows::Settings::c_settingsRegistryRoot[v27] );
      *(_QWORD *)&v59 = Windows::Settings::c_settingsRegistryRoot;
      *((_QWORD *)&v59 + 1) = v27;
      *(_QWORD *)&v60 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v28 = -1;
      do
        ++v28;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v28] );
      *((_QWORD *)&v60 + 1) = v28;
      v53[0] = v58;
      v46 = v59;
      *(_OWORD *)Src = v60;
      v26(v25, Src, &v46, v53, v74);
    }
    else
    {
      v29 = v64;
      if ( v66 > 7 )
        v29 = (_QWORD *)v64[0];
      v30 = *(_QWORD *)(a1 + 88);
      v31 = *(void (__fastcall **)(__int64, __int128 *, _OWORD *, void **, _QWORD *))(*(_QWORD *)v30 + 64LL);
      LODWORD(v74[0]) = v22;
      v75 = 0;
      *(_QWORD *)&v61 = v29;
      *((_QWORD *)&v61 + 1) = v65;
      v32 = -1;
      do
        ++v32;
      while ( Windows::Settings::c_settingsRegistryRoot[v32] );
      *(_QWORD *)&v62 = Windows::Settings::c_settingsRegistryRoot;
      *((_QWORD *)&v62 + 1) = v32;
      *(_QWORD *)&v63 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v33 = -1;
      do
        ++v33;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v33] );
      *((_QWORD *)&v63 + 1) = v33;
      *(_OWORD *)Src = v61;
      v53[0] = v62;
      v46 = v63;
      v31(v30, &v46, v53, Src, v74);
    }
    if ( v75 != -1 && v75 && v75 != 1 )
      std::wstring::~wstring(v74);
LABEL_51:
    v34 = v64;
    if ( v66 > 7 )
      v34 = (_QWORD *)v64[0];
    v35 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&v73[1], v34, v65);
    *(_QWORD *)&v46 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v35, ":");
    if ( v71 == -1 )
      ____Dispatch2_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__overloaded_V_lambda_1___1__to_wstring_Registry_Windows__SA_AV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEBV__variant_I_KV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___6__Z_V_lambda_2___1__234_SA_AV56_0_Z___AEBV__variant_I_KV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__00____Variant_dispatcher_U__integer_sequence__K_0A__std___std__SA_AV__basic_string__WU__char_traits__W_std__V__allocator__W_2__1___QEAU__overloaded_V_lambda_1___1__to_wstring_Registry_Windows__SA_AV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEBV__variant_I_KV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___6__Z_V_lambda_2___1__234_SA_AV56_0_Z___AEBV__variant_I_KV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___1__Z(v71 + 1LL);
    if ( v71 )
    {
      if ( v71 == 1 )
      {
        v37 = std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v76, v70[0]);
        std::wstring::wstring(Src, v37, v76);
        v36 = v14 | 0x7C100;
      }
      else
      {
        std::wstring::wstring(Src, v70);
        v36 = v14 | 0x380100;
      }
    }
    else
    {
      v38 = v76;
      v39 = v70[0];
      do
      {
        *--v38 = v39 % 0xA + 48;
        v39 /= 0xAu;
      }
      while ( v39 );
      std::wstring::wstring(Src, v38, v76);
      v36 = v14 | 0x3F00;
    }
    v4 = v36 | 0xE0;
    v40 = Src;
    if ( v49 > 7 )
      v40 = (void **)Src[0];
    v41 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v46, v40, v48);
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v41, ",");
    std::wstring::~wstring(Src);
    if ( v71 != -1 && v71 && v71 != 1 )
      std::wstring::~wstring(v70);
    std::wstring::~wstring(&v67);
    std::wstring::~wstring(v64);
    v7 += 40;
  }
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  std::wstringbuf::_Get_buffer_view((char *)&v73[1] + 8, Src);
  v42 = Src[0];
  if ( Src[0] )
  {
    v43 = Src[1];
    if ( Src[1] > (void *)7 )
    {
      ____Reallocate_for_V_lambda_1___1__assign___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__assign_01_QEAAAEAV01_QEB_W0_Z_PEB_W_Z(a2);
    }
    else
    {
      a2[2] = Src[1];
      v44 = 2LL * (_QWORD)v43;
      memmove(a2, v42, 2LL * (_QWORD)v43);
      *(_WORD *)((char *)a2 + v44) = 0;
    }
  }
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>((char *)&v73[9] + 8);
  *((_QWORD *)&v73[9] + 1) = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)((char *)&v73[9] + 8));
  if ( v45 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 192LL))(v45, 1);
  return a2;
}

```

## disassembly

```asm
0x180042174  mov     [rsp+arg_0], rcx
0x180042179  push    rbx
0x18004217a  push    rsi
0x18004217b  push    rdi
0x18004217c  push    r12
0x18004217e  push    r13
0x180042180  push    r14
0x180042182  push    r15
0x180042184  sub     rsp, 310h
0x18004218b  mov     rax, cs:__security_cookie
0x180042192  xor     rax, rsp
0x180042195  mov     [rsp+348h+var_48], rax
0x18004219d  mov     r15, rdx
0x1800421a0  mov     [rsp+348h+var_2B8], rdx
0x1800421a8  xor     r14d, r14d
0x1800421ab  mov     [rsp+348h+var_308], r14d
0x1800421b0  mov     [rsp+348h+var_300], r14
0x1800421b5  mov     rdx, r8
0x1800421b8  lea     rcx, [rsp+348h+var_300]
0x1800421bd  call    ?parse@value@json@web@@SA?AV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::parse(std::wstring const &)
0x1800421c2  nop
0x1800421c3  xor     edx, edx; Val
0x1800421c5  mov     r8d, 0F8h; Size
0x1800421cb  lea     rcx, [rsp+348h+var_178]; void *
0x1800421d3  call    memset
0x1800421d8  lea     rax, ??_8?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@7B?$basic_istream@_WU?$char_traits@_W@std@@@1@@; const std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbtable'{for `std::wistream'}
0x1800421df  mov     [rsp+348h+var_178], rax
0x1800421e7  lea     rax, ??_8?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@7B@; const std::wostringstream::`vbtable'
0x1800421ee  mov     [rsp+348h+var_168], rax
0x1800421f6  mov     [rsp+348h+var_D8], r14
0x1800421fe  mov     [rsp+348h+var_D0], r14
0x180042206  mov     [rsp+348h+var_C8], r14d
0x18004220e  mov     [rsp+348h+var_C0], r14
0x180042216  xorps   xmm0, xmm0
0x180042219  movdqa  [rsp+348h+var_B8], xmm0
0x180042222  xorps   xmm1, xmm1
0x180042225  movdqa  [rsp+348h+var_A8], xmm1
0x18004222e  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x180042235  mov     [rsp+348h+var_E0], rax
0x18004223d  movdqa  [rsp+348h+var_98], xmm0
0x180042246  mov     [rsp+348h+var_88], r14w
0x18004224f  mov     esi, 800000h
0x180042254  mov     [rsp+348h+var_308], esi
0x180042258  lea     rdx, [rsp+348h+var_160]
0x180042260  lea     rcx, [rsp+348h+var_178]
0x180042268  call    ??0?$basic_iostream@_WU?$char_traits@_W@std@@@std@@QEAA@PEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@1@@Z; std::wiostream::basic_iostream<wchar_t>(std::wstreambuf *)
0x18004226d  nop
0x18004226e  mov     rax, [rsp+348h+var_178]
0x180042276  movsxd  rcx, dword ptr [rax+4]
0x18004227a  lea     rax, ??_7?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable'
0x180042281  mov     [rsp+rcx+348h+var_178], rax
0x180042289  mov     rax, [rsp+348h+var_178]
0x180042291  movsxd  rcx, dword ptr [rax+4]
0x180042295  lea     edx, [rcx-98h]
0x18004229b  mov     [rsp+rcx+348h+var_17C], edx
0x1800422a2  lea     rcx, [rsp+348h+var_160]
0x1800422aa  call    ??0?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAA@XZ; std::wstreambuf::wstreambuf(void)
0x1800422af  lea     rax, ??_7?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::wstringbuf::`vftable'
0x1800422b6  mov     [rsp+348h+var_160], rax
0x1800422be  mov     [rsp+348h+var_F8], r14
0x1800422c6  mov     [rsp+348h+var_F0], r14d
0x1800422ce  xorps   xmm0, xmm0
0x1800422d1  movups  [rsp+348h+var_1C8], xmm0
0x1800422d9  mov     [rsp+348h+var_1B8], r14
0x1800422e1  mov     [rsp+348h+var_1B0], r14
0x1800422e9  lea     r8d, [r14+8]
0x1800422ed  lea     rdx, aSettings; "settings"
0x1800422f4  lea     rcx, [rsp+348h+var_1C8]
0x1800422fc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180042301  nop
0x180042302  lea     rdx, [rsp+348h+var_1C8]
0x18004230a  lea     rcx, [rsp+348h+var_300]
0x18004230f  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180042314  mov     rcx, [rax]
0x180042317  mov     rax, [rcx]
0x18004231a  mov     rax, [rax+0A8h]
0x180042321  call    _guard_dispatch_icall
0x180042326  mov     rdi, rax
0x180042329  lea     rcx, [rsp+348h+var_1C8]; void *
0x180042331  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042336  mov     rbx, [rdi]
0x180042339  mov     rdi, [rdi+8]
0x18004233d  mov     [rsp+348h+var_2C0], rdi
0x180042345  or      r12, 0FFFFFFFFFFFFFFFFh
0x180042349  lea     r13, aClearsettings; "CLEARSETTINGS"
0x180042350  mov     [rsp+348h+var_2C8], rbx
0x180042358  cmp     rbx, rdi
0x18004235b  jz      loc_180042A20
0x180042361  mov     rdx, rbx
0x180042364  lea     rcx, [rsp+348h+var_1E8]
0x18004236c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180042371  nop
0x180042372  mov     rcx, [rbx+20h]
0x180042376  mov     rax, [rcx]
0x180042379  mov     rax, [rax+58h]
0x18004237d  call    _guard_dispatch_icall
0x180042382  mov     rcx, [rbx+20h]
0x180042386  mov     r8, [rcx]
0x180042389  cmp     eax, 2
0x18004238c  jnz     short loc_1800423B0
0x18004238e  mov     rax, [r8+0B0h]
0x180042395  call    _guard_dispatch_icall
0x18004239a  mov     rdx, rax
0x18004239d  lea     rcx, [rsp+348h+var_2A8]
0x1800423a5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800423aa  nop
0x1800423ab  or      esi, 1
0x1800423ae  jmp     short loc_1800423CA
0x1800423b0  lea     rdx, [rsp+348h+Src]
0x1800423b5  mov     rax, [r8+50h]
0x1800423b9  call    _guard_dispatch_icall
0x1800423be  bts     esi, 16h
0x1800423c2  lea     rax, [rsp+348h+Src]
0x1800423c7  or      esi, 2
0x1800423ca  mov     [rsp+348h+var_308], esi
0x1800423ce  mov     rdx, rax
0x1800423d1  lea     rcx, [rsp+348h+var_1C8]
0x1800423d9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800423de  nop
0x1800423df  test    sil, 2
0x1800423e3  jz      short loc_1800423F7
0x1800423e5  and     esi, 0FFFFFFFDh
0x1800423e8  mov     [rsp+348h+var_308], esi
0x1800423ec  lea     rcx, [rsp+348h+Src]; void *
0x1800423f1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800423f6  nop
0x1800423f7  test    sil, 1
0x1800423fb  jz      short loc_180042412
0x1800423fd  and     esi, 0FFFFFFFEh
0x180042400  mov     [rsp+348h+var_308], esi
0x180042404  lea     rcx, [rsp+348h+var_2A8]; void *
0x18004240c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042411  nop
0x180042412  lea     rcx, [rsp+348h+var_1C8]
0x18004241a  cmp     [rsp+348h+var_1B0], 7
0x180042423  cmova   rcx, qword ptr [rsp+348h+var_1C8]
0x18004242c  mov     qword ptr [rsp+348h+var_288], rcx
0x180042434  mov     rax, r12
0x180042437  inc     rax
0x18004243a  cmp     [rcx+rax*2], r14w
0x18004243f  jnz     short loc_180042437
0x180042441  mov     qword ptr [rsp+348h+var_288+8], rax
0x180042449  movaps  xmm0, [rsp+348h+var_288]
0x180042451  movdqa  [rsp+348h+var_2F8], xmm0
0x180042457  lea     r8, [rsp+348h+var_2F8]
0x18004245c  lea     rdx, [rsp+348h+var_1A8]
0x180042464  call    ?GetValue@Settings@Windows@@AEAA?AV?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::Settings::GetValue(wil::basic_zstring_view<wchar_t>)
0x180042469  nop
0x18004246a  lea     rax, [rsp+348h+var_1E8]
0x180042472  cmp     [rsp+348h+var_1D0], 7
0x18004247b  cmova   rax, [rsp+348h+var_1E8]
0x180042484  mov     qword ptr [rsp+348h+var_278], rax
0x18004248c  mov     rax, [rsp+348h+var_1D8]
0x180042494  mov     qword ptr [rsp+348h+var_278+8], rax
0x18004249c  xor     r8d, r8d
0x18004249f  lea     r11, dword_18008CB14
0x1800424a6  mov     rdx, r11
0x1800424a9  mov     rcx, r13
0x1800424ac  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800424b1  cmp     rax, r11
0x1800424b4  jz      loc_180042B06
0x1800424ba  sub     rax, r13
0x1800424bd  sar     rax, 1
0x1800424c0  cmp     rax, r12
0x1800424c3  jz      loc_180042B06
0x1800424c9  mov     qword ptr [rsp+348h+var_268], r13
0x1800424d1  mov     qword ptr [rsp+348h+var_268+8], rax
0x1800424d9  movups  xmm0, [rsp+348h+var_278]
0x1800424e1  movdqu  [rsp+348h+var_2F8], xmm0
0x1800424e7  movaps  xmm1, [rsp+348h+var_268]
0x1800424ef  movdqa  [rsp+348h+var_2A8], xmm1
0x1800424f8  lea     rdx, [rsp+348h+var_2F8]
0x1800424fd  lea     rcx, [rsp+348h+var_2A8]
0x180042505  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18004250a  test    al, al
0x18004250c  mov     al, [rsp+348h+var_188]
0x180042513  jz      loc_1800425EF
0x180042519  test    al, al
0x18004251b  jnz     loc_180042AF6
0x180042521  mov     r8, [rsp+348h+var_1A8]
0x180042529  cmp     r8d, 1
0x18004252d  jnz     loc_1800425F7
0x180042533  xorps   xmm0, xmm0
0x180042536  movups  xmmword ptr [r15], xmm0
0x18004253a  mov     [r15+10h], r14
0x18004253e  mov     [r15+18h], r14
0x180042542  mov     r8d, 0Dh
0x180042548  mov     rdx, r13
0x18004254b  mov     rcx, r15
0x18004254e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180042553  or      esi, 4
0x180042556  mov     [rsp+348h+var_308], esi
0x18004255a  movsx   rax, [rsp+348h+var_188]
0x180042563  add     rax, 1
0x180042567  jz      short loc_180042583
0x180042569  sub     rax, 1
0x18004256d  jz      short loc_180042583
0x18004256f  cmp     rax, 1
0x180042573  jz      short loc_180042583
0x180042575  lea     rcx, [rsp+348h+var_1A8]; void *
0x18004257d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042582  nop
0x180042583  lea     rcx, [rsp+348h+var_1C8]; void *
0x18004258b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042590  nop
0x180042591  lea     rcx, [rsp+348h+var_1E8]; void *
0x180042599  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004259e  nop
0x18004259f  lea     rcx, [rsp+348h+var_E0]
0x1800425a7  call    ??1?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x1800425ac  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x1800425b3  mov     [rsp+348h+var_E0], rax
0x1800425bb  lea     rcx, [rsp+348h+var_E0]; this
0x1800425c3  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x1800425c8  nop
0x1800425c9  mov     rcx, [rsp+348h+var_300]
0x1800425ce  test    rcx, rcx
0x1800425d1  jz      short loc_1800425E7
0x1800425d3  mov     r8, [rcx]
0x1800425d6  mov     edx, 1
0x1800425db  mov     rax, [r8+0C0h]
0x1800425e2  call    _guard_dispatch_icall
0x1800425e7  mov     rax, r15
0x1800425ea  jmp     loc_180042AD3
0x1800425ef  mov     r8, [rsp+348h+var_1A8]
0x1800425f7  mov     rdx, [rsp+348h+arg_0]
0x1800425ff  mov     [rsp+348h+var_258], rdx
0x180042607  lea     rcx, [rsp+348h+var_1E8]
0x18004260f  mov     [rsp+348h+var_250], rcx
0x180042617  movsx   rax, al
0x18004261b  add     rax, 1
0x18004261f  jz      loc_180042B01
0x180042625  sub     rax, 1
0x180042629  jz      loc_180042741
0x18004262f  cmp     rax, 1
0x180042633  jz      short loc_18004264F
0x180042635  lea     rdx, [rsp+348h+var_1A8]
0x18004263d  lea     rcx, [rsp+348h+var_258]
0x180042645  call    std___Variant_dispatcher_std__integer_sequence_unsigned___int64_3______Dispatch2_void__Windows__Settings__CacheSettings____7____lambda_1__std__variant_unsigned_int_unsigned___int64_std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t______const___0_
0x18004264a  jmp     loc_180042856
0x18004264f  lea     rcx, [rsp+348h+var_1E8]
0x180042657  cmp     [rsp+348h+var_1D0], 7
0x180042660  cmova   rcx, [rsp+348h+var_1E8]
0x180042669  mov     r10, [rdx+58h]
0x18004266d  mov     rax, [r10]
0x180042670  mov     r11, [rax+40h]
0x180042674  mov     [rsp+348h+var_78], r8
0x18004267c  mov     [rsp+348h+var_58], 1
0x180042684  mov     qword ptr [rsp+348h+var_248], rcx
0x18004268c  mov     rax, [rsp+348h+var_1D8]
0x180042694  mov     qword ptr [rsp+348h+var_248+8], rax
0x18004269c  mov     rcx, cs:?c_settingsRegistryRoot@Settings@Windows@@0QEB_WEB; wchar_t const * const Windows::Settings::c_settingsRegistryRoot
0x1800426a3  mov     rax, r12
0x1800426a6  inc     rax
0x1800426a9  cmp     [rcx+rax*2], r14w
0x1800426ae  jnz     short loc_1800426A6
0x1800426b0  mov     qword ptr [rsp+348h+var_238], rcx
0x1800426b8  mov     qword ptr [rsp+348h+var_238+8], rax
0x1800426c0  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x1800426c7  mov     qword ptr [rsp+348h+var_228], rcx
0x1800426cf  mov     rax, r12
0x1800426d2  inc     rax
0x1800426d5  cmp     [rcx+rax*2], r14w
0x1800426da  jnz     short loc_1800426D2
0x1800426dc  mov     qword ptr [rsp+348h+var_228+8], rax
0x1800426e4  movups  xmm0, [rsp+348h+var_248]
0x1800426ec  movdqu  [rsp+348h+var_2A8], xmm0
0x1800426f5  movups  xmm1, [rsp+348h+var_238]
0x1800426fd  movdqu  [rsp+348h+var_2F8], xmm1
0x180042703  movaps  xmm0, [rsp+348h+var_228]
0x18004270b  movdqa  xmmword ptr [rsp+348h+Src], xmm0
0x180042711  lea     rax, [rsp+348h+var_78]
0x180042719  mov     [rsp+348h+var_328], rax
0x18004271e  lea     r9, [rsp+348h+var_2A8]
0x180042726  lea     r8, [rsp+348h+var_2F8]
0x18004272b  lea     rdx, [rsp+348h+Src]
0x180042730  mov     rcx, r10
0x180042733  mov     rax, r11
0x180042736  call    _guard_dispatch_icall
0x18004273b  nop
0x18004273c  jmp     loc_18004282E
0x180042741  lea     rcx, [rsp+348h+var_1E8]
0x180042749  cmp     [rsp+348h+var_1D0], 7
0x180042752  cmova   rcx, [rsp+348h+var_1E8]
0x18004275b  mov     r10, [rdx+58h]
0x18004275f  mov     rax, [r10]
0x180042762  mov     r11, [rax+40h]
0x180042766  mov     dword ptr [rsp+348h+var_78], r8d
0x18004276e  mov     [rsp+348h+var_58], r14b
0x180042776  mov     qword ptr [rsp+348h+var_218], rcx
0x18004277e  mov     rax, [rsp+348h+var_1D8]
0x180042786  mov     qword ptr [rsp+348h+var_218+8], rax
0x18004278e  mov     rcx, cs:?c_settingsRegistryRoot@Settings@Windows@@0QEB_WEB; wchar_t const * const Windows::Settings::c_settingsRegistryRoot
0x180042795  mov     rax, r12
0x180042798  inc     rax
0x18004279b  cmp     [rcx+rax*2], r14w
0x1800427a0  jnz     short loc_180042798
0x1800427a2  mov     qword ptr [rsp+348h+var_208], rcx
0x1800427aa  mov     qword ptr [rsp+348h+var_208+8], rax
0x1800427b2  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
  ... truncated ...
```
