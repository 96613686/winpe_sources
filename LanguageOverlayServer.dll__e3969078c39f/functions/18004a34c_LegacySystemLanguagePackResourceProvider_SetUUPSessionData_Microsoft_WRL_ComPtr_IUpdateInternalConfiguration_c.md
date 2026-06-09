# LegacySystemLanguagePackResourceProvider::_SetUUPSessionData(Microsoft::WRL::ComPtr<IUpdateInternalConfiguration> const &,std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &,std::vector<Microsoft::WRL::ComPtr<ICbsCapability>,std::allocator<Microsoft::WRL::ComPtr<ICbsCapability>>> const &,ulong)

- ea: `0x18004a34c`
- end: `0x18004a7ad`
- name: `?_SetUUPSessionData@LegacySystemLanguagePackResourceProvider@@CAXAEBV?$ComPtr@UIUpdateInternalConfiguration@@@WRL@Microsoft@@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$vector@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@@std@@@6@K@Z`
- size: `1121`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180048274`
- `0x1800483ec`

## callees

- `0x180003a00`
- `0x180009a74`
- `0x180012a98`
- `0x1800137bc`
- `0x180014720`
- `0x180014ed0`
- `0x1800208b8`
- `0x180033c30`
- `0x18003ff74`
- `0x18004a34c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a55f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a56f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a57f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a55f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a56f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a57f`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x18004a3e9`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x18004a3e9`
- `OLEAUT32!__imp_SysAllocString` at `0x18004a6a5`
- `OLEAUT32!__imp_SysAllocString` at `0x18004a6a5`
- `OLEAUT32!__imp_VariantInit` at `0x18004a68b`
- `OLEAUT32!__imp_VariantInit` at `0x18004a68b`
- `OLEAUT32!__imp_VariantClear` at `0x18004a70a`
- `OLEAUT32!__imp_VariantClear` at `0x18004a70a`

## string_xrefs

- `0x18004a75c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18004a74a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a771`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a786`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a79b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall LegacySystemLanguagePackResourceProvider::_SetUUPSessionData(
        __int64 *a1,
        _QWORD *a2,
        __int64 ***a3,
        unsigned int a4)
{
  _QWORD *v6; // rbx
  int v8; // r14d
  __m128i si128; // xmm1
  _QWORD *v10; // rax
  _WORD *v11; // rax
  BOOL v12; // eax
  const unsigned __int16 *v13; // r8
  int v14; // eax
  __int64 **v15; // rbx
  __int64 **v16; // rsi
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  int *v20; // rdx
  const int *v21; // rdi
  unsigned __int64 v22; // r8
  int *v23; // rdx
  __int128 *v24; // r9
  int v25; // eax
  const OLECHAR *v26; // rcx
  BSTR v27; // rax
  const char *v28; // r9
  __int64 v29; // rcx
  int v30; // eax
  int v31; // [rsp+20h] [rbp-E0h]
  int *v32; // [rsp+28h] [rbp-D8h]
  __int64 v33; // [rsp+30h] [rbp-D0h]
  VARIANTARG v34; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  int v37; // [rsp+7Ch] [rbp-84h] BYREF
  LPVOID v38; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v39; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  __int128 Src; // [rsp+98h] [rbp-68h] BYREF
  __m128i v42; // [rsp+A8h] [rbp-58h]
  OLECHAR *psz[2]; // [rsp+B8h] [rbp-48h] BYREF
  __m128i v44; // [rsp+C8h] [rbp-38h]
  int v45; // [rsp+E0h] [rbp-20h]
  int v46; // [rsp+E4h] [rbp-1Ch]
  int v47[2]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v48; // [rsp+100h] [rbp+0h]
  __int128 v49; // [rsp+108h] [rbp+8h] BYREF
  __int64 v50; // [rsp+118h] [rbp+18h]
  unsigned __int64 v51; // [rsp+120h] [rbp+20h]
  unsigned __int16 v52[264]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v6 = a2;
  v8 = 0;
  v36 = 0;
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v42 = si128;
  LOWORD(Src) = 0;
  if ( a2[3] <= 7u )
    v10 = a2;
  else
    v10 = (_QWORD *)*a2;
  if ( v10 )
  {
    v11 = a2[3] <= 7u ? a2 : (_WORD *)*a2;
    if ( *v11 )
    {
      if ( a2[3] > 7u )
        v6 = (_QWORD *)*a2;
      v12 = IsOS(0x1Du);
      v13 = L"Language.UI.Server~%ls";
      if ( !v12 )
        v13 = L"Language.UI.Client~%ls";
      v14 = StringCchPrintfW(v52, 0x104u, v13, v6);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x224,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v14,
          v31);
      if ( v42.m128i_i64[0] )
        std::wstring::operator+=(&Src, L",\n ");
      std::wstring::operator+=(&Src, L"{ \"name\":\"");
      std::wstring::operator+=(&Src, v52);
      std::wstring::operator+=(&Src, L"\" }");
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
  }
  v15 = *a3;
  v16 = a3[1];
  if ( *a3 != v16 )
  {
    do
    {
      v17 = *v15;
      if ( *v15 )
      {
        v39 = 0;
        v38 = 0;
        pv = 0;
        v36 = 0;
        v37 = 0;
        v18 = *v17;
        pv = 0;
        v38 = 0;
        v39 = 0;
        v32 = &v37;
        v19 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *, LPVOID *, LPVOID *))(v18 + 112))(v17, &v39, &v38, &pv);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3DD,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
            (const char *)(unsigned int)v19,
            (int)&v36);
        v20 = (int *)&qword_180070100;
        if ( v38 )
          v20 = (int *)v38;
        v21 = &qword_180070100;
        if ( v39 )
          v21 = (const int *)v39;
        v45 = v37;
        v46 = v36;
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
          v47,
          v20);
        v49 = 0;
        v50 = 0;
        v51 = 0;
        v22 = -1;
        do
          ++v22;
        while ( *((_WORD *)v21 + v22) );
        std::wstring::_Construct<1,unsigned short const *>((char **)&v49, v21, v22);
        v8 |= 1u;
        if ( pv )
          CoTaskMemFree(pv);
        if ( v38 )
          CoTaskMemFree(v38);
        if ( v39 )
          CoTaskMemFree(v39);
        v23 = v47;
        if ( v48 > 7 )
          v23 = *(int **)v47;
        v24 = &v49;
        if ( v51 > 7 )
          v24 = (__int128 *)v49;
        LODWORD(v33) = v45;
        LODWORD(v32) = v46;
        v25 = StringCchPrintfW(v52, 0x104u, L"%ls~%ls~%lu.%lu", v24, v23, v32, v33);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x237,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
            (const char *)(unsigned int)v25,
            v31);
        if ( v42.m128i_i64[0] )
          std::wstring::operator+=(&Src, L",\n ");
        std::wstring::operator+=(&Src, L"{ \"name\":\"");
        std::wstring::operator+=(&Src, v52);
        std::wstring::operator+=(&Src, L"\" }");
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&v49);
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)v47);
      }
      ++v15;
    }
    while ( v15 != v16 );
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  *(_OWORD *)psz = 0;
  v44 = si128;
  LOWORD(psz[0]) = 0;
  std::wstring::operator+=(psz, L"{\n \"ModuleID\" : \"FOD\",\n \"Features\": [");
  std::wstring::operator+=(psz);
  std::wstring::operator+=(psz, L"\n ]\n }");
  VariantInit(&pvarg);
  pvarg.vt = 8;
  v26 = (const OLECHAR *)psz;
  if ( v44.m128i_i64[1] > 7uLL )
    v26 = psz[0];
  v27 = SysAllocString(v26);
  pv = v27;
  v36 = v8 | 2;
  if ( !v27 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v28);
  pvarg.llVal = (LONGLONG)v27;
  v29 = *a1;
  v34 = pvarg;
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v29 + 32LL))(v29, a4, &v34);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v30,
      v31);
  VariantClear(&pvarg);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)psz);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&Src);
}

```

## disassembly

```asm
0x18004a34c  push    rbp
0x18004a34e  push    rbx
0x18004a34f  push    rsi
0x18004a350  push    rdi
0x18004a351  push    r12
0x18004a353  push    r13
0x18004a355  push    r14
0x18004a357  push    r15
0x18004a359  lea     rbp, [rsp-258h]
0x18004a361  sub     rsp, 358h
0x18004a368  mov     rax, cs:__security_cookie
0x18004a36f  xor     rax, rsp
0x18004a372  mov     [rbp+290h+var_50], rax
0x18004a379  mov     r12d, r9d
0x18004a37c  mov     rdi, r8
0x18004a37f  mov     rbx, rdx
0x18004a382  mov     r15, rcx
0x18004a385  xor     r13d, r13d
0x18004a388  mov     r14d, r13d
0x18004a38b  mov     [rsp+390h+var_318], r13d
0x18004a390  xorps   xmm0, xmm0
0x18004a393  movups  [rbp+290h+Src], xmm0
0x18004a397  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004a39f  movdqu  [rbp+290h+var_2E8], xmm1
0x18004a3a4  mov     word ptr [rbp+290h+Src], r13w
0x18004a3a9  cmp     qword ptr [rdx+18h], 7
0x18004a3ae  jbe     short loc_18004A3B5
0x18004a3b0  mov     rax, [rdx]
0x18004a3b3  jmp     short loc_18004A3B8
0x18004a3b5  mov     rax, rdx
0x18004a3b8  test    rax, rax
0x18004a3bb  jz      loc_18004A46E
0x18004a3c1  cmp     qword ptr [rdx+18h], 7
0x18004a3c6  jbe     short loc_18004A3CD
0x18004a3c8  mov     rax, [rdx]
0x18004a3cb  jmp     short loc_18004A3D0
0x18004a3cd  mov     rax, rdx
0x18004a3d0  cmp     [rax], r13w
0x18004a3d4  jz      loc_18004A46E
0x18004a3da  cmp     qword ptr [rdx+18h], 7
0x18004a3df  jbe     short loc_18004A3E4
0x18004a3e1  mov     rbx, [rdx]
0x18004a3e4  mov     ecx, 1Dh; dwOS
0x18004a3e9  call    cs:__imp_IsOS
0x18004a3ef  lea     rcx, aLanguageUiClie; "Language.UI.Client~%ls"
0x18004a3f6  lea     r8, aLanguageUiServ; "Language.UI.Server~%ls"
0x18004a3fd  test    eax, eax
0x18004a3ff  cmovz   r8, rcx; unsigned __int16 *
0x18004a403  mov     r9, rbx
0x18004a406  mov     edx, 104h; unsigned __int64
0x18004a40b  lea     rcx, [rbp+290h+var_260]; unsigned __int16 *
0x18004a40f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a414  mov     rcx, [rbp+298h]; this
0x18004a41b  test    eax, eax
0x18004a41d  js      loc_18004A76E
0x18004a423  cmp     qword ptr [rbp+290h+var_2E8], r13
0x18004a427  jz      short loc_18004A439
0x18004a429  lea     rdx, asc_180072150; ",\n "
0x18004a430  lea     rcx, [rbp+290h+Src]; Src
0x18004a434  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a439  lea     rdx, aName; "{ \"name\":\""
0x18004a440  lea     rcx, [rbp+290h+Src]; Src
0x18004a444  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a449  lea     rdx, [rbp+290h+var_260]; void *
0x18004a44d  lea     rcx, [rbp+290h+Src]; Src
0x18004a451  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a456  lea     rdx, asc_1800722C8; "\" }"
0x18004a45d  lea     rcx, [rbp+290h+Src]; Src
0x18004a461  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a466  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004a46e  mov     rbx, [rdi]
0x18004a471  mov     rsi, [rdi+8]
0x18004a475  mov     edi, 8
0x18004a47a  cmp     rbx, rsi
0x18004a47d  jz      loc_18004A648
0x18004a483  mov     rcx, [rbx]
0x18004a486  test    rcx, rcx
0x18004a489  jz      loc_18004A634
0x18004a48f  mov     [rbp+290h+var_308], r13
0x18004a493  mov     [rbp+290h+var_310], r13
0x18004a497  mov     [rbp+290h+pv], r13
0x18004a49b  mov     [rsp+390h+var_318], r13d
0x18004a4a0  mov     [rsp+390h+var_314], r13d
0x18004a4a5  mov     rax, [rcx]
0x18004a4a8  mov     [rbp+290h+pv], r13
0x18004a4ac  mov     [rbp+290h+var_310], r13
0x18004a4b0  mov     [rbp+290h+var_308], r13
0x18004a4b4  lea     rdx, [rsp+390h+var_314]
0x18004a4b9  mov     [rsp+390h+var_368], rdx
0x18004a4be  lea     rdx, [rsp+390h+var_318]
0x18004a4c3  mov     qword ptr [rsp+390h+var_370], rdx; int
0x18004a4c8  lea     r9, [rbp+290h+pv]
0x18004a4cc  lea     r8, [rbp+290h+var_310]
0x18004a4d0  lea     rdx, [rbp+290h+var_308]
0x18004a4d4  mov     rax, [rax+70h]
0x18004a4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4dd  mov     rcx, [rbp+298h]; this
0x18004a4e4  test    eax, eax
0x18004a4e6  js      loc_18004A747
0x18004a4ec  lea     rdx, qword_180070100
0x18004a4f3  mov     rax, [rbp+290h+var_310]
0x18004a4f7  test    rax, rax
0x18004a4fa  cmovnz  rdx, rax
0x18004a4fe  lea     rdi, qword_180070100
0x18004a505  mov     rax, [rbp+290h+var_308]
0x18004a509  test    rax, rax
0x18004a50c  cmovnz  rdi, rax
0x18004a510  mov     eax, [rsp+390h+var_314]
0x18004a514  mov     [rbp+290h+var_2B0], eax
0x18004a517  mov     eax, [rsp+390h+var_318]
0x18004a51b  mov     [rbp+290h+var_2AC], eax
0x18004a51e  lea     rcx, [rbp+290h+var_2A8]
0x18004a522  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(ushort const * const)
0x18004a527  nop
0x18004a528  xorps   xmm0, xmm0
0x18004a52b  movups  [rbp+290h+var_288], xmm0
0x18004a52f  mov     [rbp+290h+var_278], r13
0x18004a533  mov     [rbp+290h+var_270], r13
0x18004a537  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004a53b  inc     r8
0x18004a53e  cmp     [rdi+r8*2], r13w
0x18004a543  jnz     short loc_18004A53B
0x18004a545  mov     rdx, rdi
0x18004a548  lea     rcx, [rbp+290h+var_288]
0x18004a54c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004a551  nop
0x18004a552  or      r14d, 1
0x18004a556  mov     rcx, [rbp+290h+pv]; pv
0x18004a55a  test    rcx, rcx
0x18004a55d  jz      short loc_18004A566
0x18004a55f  call    cs:__imp_CoTaskMemFree
0x18004a565  nop
0x18004a566  mov     rcx, [rbp+290h+var_310]; pv
0x18004a56a  test    rcx, rcx
0x18004a56d  jz      short loc_18004A576
0x18004a56f  call    cs:__imp_CoTaskMemFree
0x18004a575  nop
0x18004a576  mov     rcx, [rbp+290h+var_308]; pv
0x18004a57a  test    rcx, rcx
0x18004a57d  jz      short loc_18004A586
0x18004a57f  call    cs:__imp_CoTaskMemFree
0x18004a585  nop
0x18004a586  mov     eax, [rbp+290h+var_2B0]
0x18004a589  mov     ecx, [rbp+290h+var_2AC]
0x18004a58c  lea     rdx, [rbp+290h+var_2A8]
0x18004a590  cmp     [rbp+290h+var_290], 7
0x18004a595  cmova   rdx, qword ptr [rbp+290h+var_2A8]
0x18004a59a  lea     r9, [rbp+290h+var_288]
0x18004a59e  cmp     [rbp+290h+var_270], 7
0x18004a5a3  cmova   r9, qword ptr [rbp+290h+var_288]
0x18004a5a8  mov     [rsp+390h+var_360], eax
0x18004a5ac  mov     dword ptr [rsp+390h+var_368], ecx
0x18004a5b0  mov     qword ptr [rsp+390h+var_370], rdx; int
0x18004a5b5  lea     r8, aLsLsLuLu; "%ls~%ls~%lu.%lu"
0x18004a5bc  mov     edx, 104h; unsigned __int64
0x18004a5c1  lea     rcx, [rbp+290h+var_260]; unsigned __int16 *
0x18004a5c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a5ca  mov     rcx, [rbp+298h]; this
0x18004a5d1  test    eax, eax
0x18004a5d3  js      loc_18004A798
0x18004a5d9  cmp     qword ptr [rbp+290h+var_2E8], r13
0x18004a5dd  jz      short loc_18004A5EF
0x18004a5df  lea     rdx, asc_180072150; ",\n "
0x18004a5e6  lea     rcx, [rbp+290h+Src]; Src
0x18004a5ea  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a5ef  lea     rdx, aName; "{ \"name\":\""
0x18004a5f6  lea     rcx, [rbp+290h+Src]; Src
0x18004a5fa  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a5ff  lea     rdx, [rbp+290h+var_260]; void *
0x18004a603  lea     rcx, [rbp+290h+Src]; Src
0x18004a607  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a60c  lea     rdx, asc_1800722C8; "\" }"
0x18004a613  lea     rcx, [rbp+290h+Src]; Src
0x18004a617  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a61c  nop
0x18004a61d  lea     rcx, [rbp+290h+var_288]; void *
0x18004a621  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004a626  lea     rcx, [rbp+290h+var_2A8]; void *
0x18004a62a  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004a62f  mov     edi, 8
0x18004a634  add     rbx, rdi
0x18004a637  cmp     rbx, rsi
0x18004a63a  jnz     loc_18004A483
0x18004a640  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004a648  xorps   xmm0, xmm0
0x18004a64b  movups  xmmword ptr [rbp+290h+psz], xmm0
0x18004a64f  movdqu  [rbp+290h+var_2C8], xmm1
0x18004a654  mov     word ptr [rbp+290h+psz], r13w
0x18004a659  lea     rdx, aModuleidFodFea; "{\n \"ModuleID\" : \"FOD\",\n \"Feature"...
0x18004a660  lea     rcx, [rbp+290h+psz]; Src
0x18004a664  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a669  lea     rdx, [rbp+290h+Src]
0x18004a66d  lea     rcx, [rbp+290h+psz]; Src
0x18004a671  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x18004a676  lea     rdx, asc_180072268; "\n ]\n }"
0x18004a67d  lea     rcx, [rbp+290h+psz]; Src
0x18004a681  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004a686  lea     rcx, [rsp+390h+pvarg]; pvarg
0x18004a68b  call    cs:__imp_VariantInit
0x18004a691  nop
0x18004a692  mov     word ptr [rsp+390h+pvarg], di
0x18004a697  lea     rcx, [rbp+290h+psz]
0x18004a69b  cmp     qword ptr [rbp+290h+var_2C8+8], 7
0x18004a6a0  cmova   rcx, [rbp+290h+psz]; psz
0x18004a6a5  call    cs:__imp_SysAllocString
0x18004a6ab  mov     [rbp+290h+pv], rax
0x18004a6af  or      r14d, 2
0x18004a6b3  mov     [rsp+390h+var_318], r14d
0x18004a6b8  mov     rcx, [rbp+298h]; this
0x18004a6bf  test    rax, rax
0x18004a6c2  jz      loc_18004A75C
0x18004a6c8  mov     qword ptr [rsp+390h+pvarg+8], rax
0x18004a6cd  mov     rcx, [r15]
0x18004a6d0  movups  xmm0, xmmword ptr [rsp+390h+pvarg]
0x18004a6d5  movaps  [rsp+390h+var_350], xmm0
0x18004a6da  movsd   xmm1, qword ptr [rsp+390h+pvarg+10h]
0x18004a6e0  movsd   [rsp+390h+var_340], xmm1
0x18004a6e6  mov     rax, [rcx]
0x18004a6e9  lea     r8, [rsp+390h+var_350]
0x18004a6ee  mov     edx, r12d
0x18004a6f1  mov     rax, [rax+20h]
0x18004a6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6fa  mov     rcx, [rbp+298h]; this
0x18004a701  test    eax, eax
0x18004a703  js      short loc_18004A783
0x18004a705  lea     rcx, [rsp+390h+pvarg]; pvarg
0x18004a70a  call    cs:__imp_VariantClear
0x18004a710  nop
0x18004a711  lea     rcx, [rbp+290h+psz]; void *
0x18004a715  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004a71a  nop
0x18004a71b  lea     rcx, [rbp+290h+Src]; void *
0x18004a71f  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004a724  mov     rcx, [rbp+290h+var_50]
0x18004a72b  xor     rcx, rsp; StackCookie
0x18004a72e  call    __security_check_cookie
0x18004a733  add     rsp, 358h
0x18004a73a  pop     r15
0x18004a73c  pop     r14
0x18004a73e  pop     r13
0x18004a740  pop     r12
0x18004a742  pop     rdi
0x18004a743  pop     rsi
0x18004a744  pop     rbx
0x18004a745  pop     rbp
0x18004a746  retn
0x18004a747  mov     r9d, eax; char *
0x18004a74a  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x18004a751  mov     edx, 3DDh; void *
0x18004a756  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a75c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004a763  mov     edx, 15F3h; void *
0x18004a768  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18004a76e  mov     r9d, eax; char *
0x18004a771  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x18004a778  mov     edx, 224h; void *
0x18004a77d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a783  mov     r9d, eax; char *
0x18004a786  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x18004a78d  mov     edx, 246h; void *
0x18004a792  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a798  mov     r9d, eax; char *
0x18004a79b  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x18004a7a2  mov     edx, 237h; void *
0x18004a7a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
