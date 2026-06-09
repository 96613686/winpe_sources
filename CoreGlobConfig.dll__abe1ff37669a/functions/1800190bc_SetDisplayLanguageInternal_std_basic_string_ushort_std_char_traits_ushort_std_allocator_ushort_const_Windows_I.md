# SetDisplayLanguageInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::SET_DISPLAY_LANGUAGE_OPTIONS)

- ea: `0x1800190bc`
- end: `0x18001944c`
- name: `?SetDisplayLanguageInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4SET_DISPLAY_LANGUAGE_OPTIONS@Internal@Windows@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001fe10`
- `0x18001ff10`

## callees

- `0x180002380`
- `0x180008274`
- `0x180008294`
- `0x18000dbb0`
- `0x18000fa14`
- `0x18001220c`
- `0x180013210`
- `0x1800133d0`
- `0x1800136c8`
- `0x1800158f0`
- `0x180015a54`
- `0x180015ea8`
- `0x180016d8c`
- `0x1800190bc`
- `0x180019454`
- `0x18001d3ac`
- `0x18001d564`
- `0x18001ddf4`
- `0x18001de84`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800192b5`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800192b5`
- `ntdll!RtlPublishWnfStateData` at `0x180019395`
- `ntdll!RtlPublishWnfStateData` at `0x1800193c9`
- `ntdll!RtlPublishWnfStateData` at `0x180019395`
- `ntdll!RtlPublishWnfStateData` at `0x1800193c9`
- `KERNELBASE!NotifyRedirectedStringChange` at `0x18001934a`
- `KERNELBASE!NotifyRedirectedStringChange` at `0x18001934a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800191cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800191cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019245`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019257`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019245`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019257`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180019187`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180019187`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019165`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019165`
- `Bcp47Langs!SetPreviousUserDisplayLanguages` at `0x180019291`
- `Bcp47Langs!SetPreviousUserDisplayLanguages` at `0x180019291`

## string_xrefs

- `0x1800190ff`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001922d`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180019325`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180019358`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180019409`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall SetDisplayLanguageInternal(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  unsigned __int8 v6; // r14
  const WCHAR *v7; // rax
  LPCWCH v8; // r10
  __int64 v9; // rdx
  const WCHAR *v10; // rax
  unsigned __int16 v11; // r12
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 UserPreferredMuiLanguages; // rax
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  unsigned int v22; // r8d
  __int64 v23; // r8
  const WCHAR *v24; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  int LastError; // eax
  int v28; // eax
  unsigned int v29; // r8d
  int v30; // eax
  unsigned int v31; // r8d
  int bIgnoreCase; // [rsp+20h] [rbp-49h]
  int bIgnoreCasea; // [rsp+20h] [rbp-49h]
  _QWORD v35[3]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v36[24]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v37[32]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( !*(_QWORD *)(a1 + 16) )
  {
    v4 = 883;
LABEL_3:
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    return v5;
  }
  v6 = 0;
  if ( (a2 & 2) != 0 )
  {
    if ( (a2 & 1) == 0 )
    {
      v4 = 886;
      goto LABEL_3;
    }
    v6 = 1;
  }
  LanguageTagAsMuiForm(v37, a1);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
  if ( CompareStringOrdinal(v8, -1, v7, -1, 1) != 2 )
  {
    v9 = 896;
LABEL_45:
    v5 = -2147024809;
    v13 = 2147942487LL;
    goto LABEL_46;
  }
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v11 = LocaleNameToLCID(v10, 0);
  if ( !v11 || (v11 & 0x3FF) == 0 )
  {
    v9 = 904;
    goto LABEL_45;
  }
  v12 = PopulateInstalledLanguages(0x98u);
  v5 = v12;
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
    v9 = 909;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)v13,
      bIgnoreCasea);
    goto LABEL_47;
  }
  AcquireSRWLockShared(&stru_180032FB8);
  v14 = qword_180032FA8;
  v15 = qword_180032FA0;
  if ( qword_180032FA0 == qword_180032FA8 )
    goto LABEL_18;
  do
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                            v16,
                            *(_QWORD *)(v15 + 16),
                            v17,
                            *(_QWORD *)(a1 + 16)) )
      break;
    v15 += 32;
  }
  while ( v15 != v14 );
  if ( v15 == qword_180032FA8 )
  {
LABEL_18:
    v5 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x396,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)0x80070490LL,
      bIgnoreCasea);
    ReleaseSRWLockShared(&stru_180032FB8);
LABEL_47:
    std::wstring::_Tidy_deallocate(v37);
    return v5;
  }
  ReleaseSRWLockShared(&stru_180032FB8);
  std::vector<bond::blob>::vector<bond::blob>(v35);
  if ( v6 )
    UserPreferredMuiLanguages = GetUserPreferredMuiLanguages(v36);
  else
    UserPreferredMuiLanguages = GetSystemPreferredMuiLanguages(v36);
  std::vector<std::wstring>::operator=(v35, UserPreferredMuiLanguages);
  std::vector<std::wstring>::_Tidy(v36);
  v19 = SetPreviousUserDisplayLanguages();
  v5 = v19;
  if ( v19 < 0 )
  {
    v20 = 933;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v19,
      bIgnoreCasea);
    std::vector<std::wstring>::_Tidy(v35);
    goto LABEL_47;
  }
  if ( v35[1] == v35[0] )
  {
    std::_Xout_of_range("invalid vector subscript");
    __debugbreak();
  }
  v21 = SetStartingUserDisplayLanguageValue();
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x3AE, v22, (const char *)(unsigned int)v21, bIgnoreCasea);
  v19 = ChangeUserAndSystemMuiLanguageInternal(a1, v11, a2);
  v5 = v19;
  if ( v19 < 0 )
  {
    v20 = 944;
    goto LABEL_33;
  }
  LOBYTE(v23) = v6;
  CallNotifyUILanguageChange(a1, v35, v23);
  if ( (a2 & 1) == 0 )
  {
    v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v19 = ChangeNlsSystemLocale(v24);
    v5 = v19;
    if ( v19 < 0 )
    {
      v20 = 951;
      goto LABEL_33;
    }
  }
  if ( (unsigned int)NotifyRedirectedStringChange((unsigned int)v6 + 1) )
    LastError = 0;
  else
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x77,
                  (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
                  v26);
  if ( LastError < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x3BB, v25, (const char *)(unsigned int)LastError, bIgnoreCasea);
  v28 = RtlPublishWnfStateData(WNF_NLS_USER_UILANG_CHANGED, 0, 0, 0) | 0x10000000;
  if ( v28 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x3C3, v29, (const char *)(unsigned int)v28, 0);
  v30 = RtlPublishWnfStateData(WNF_GLOB_GLOBALIZATION_PREFERENCES_CHANGED, 0, 0, 0) | 0x10000000;
  if ( v30 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x3C5, v31, (const char *)(unsigned int)v30, 0);
  std::vector<std::wstring>::_Tidy(v35);
  std::wstring::_Tidy_deallocate(v37);
  return 0;
}

```

## disassembly

```asm
0x1800190bc  mov     [rsp-8+arg_10], rbx
0x1800190c1  push    rbp
0x1800190c2  push    rsi
0x1800190c3  push    rdi
0x1800190c4  push    r12
0x1800190c6  push    r13
0x1800190c8  push    r14
0x1800190ca  push    r15
0x1800190cc  lea     rbp, [rsp-27h]
0x1800190d1  sub     rsp, 90h
0x1800190d8  mov     rax, cs:__security_cookie
0x1800190df  xor     rax, rsp
0x1800190e2  mov     [rbp+57h+var_40], rax
0x1800190e6  mov     r15d, edx
0x1800190e9  mov     rdi, rcx
0x1800190ec  xor     r13d, r13d
0x1800190ef  cmp     [rcx+10h], r13
0x1800190f3  jnz     short loc_180019117
0x1800190f5  mov     edx, 373h; void *
0x1800190fa  mov     ebx, 80070057h
0x1800190ff  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180019106  mov     r9d, ebx; char *
0x180019109  mov     rcx, [rbp+5Fh]; this
0x18001910d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019112  jmp     loc_180019423
0x180019117  mov     r14b, r13b
0x18001911a  test    r15b, 2
0x18001911e  jz      short loc_180019130
0x180019120  test    r15b, 1
0x180019124  jnz     short loc_18001912D
0x180019126  mov     edx, 376h
0x18001912b  jmp     short loc_1800190FA
0x18001912d  mov     r14b, 1
0x180019130  mov     rdx, rdi
0x180019133  lea     rcx, [rbp+57h+var_60]
0x180019137  call    ?LanguageTagAsMuiForm@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; LanguageTagAsMuiForm(std::wstring const &)
0x18001913c  nop
0x18001913d  mov     rcx, rdi
0x180019140  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019145  mov     r10, rax
0x180019148  lea     rcx, [rbp+57h+var_60]
0x18001914c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019151  mov     r8, rax; lpString2
0x180019154  mov     [rsp+0C0h+bIgnoreCase], 1; int
0x18001915c  or      edx, 0FFFFFFFFh; cchCount1
0x18001915f  mov     r9d, edx; cchCount2
0x180019162  mov     rcx, r10; lpString1
0x180019165  call    cs:__imp_CompareStringOrdinal
0x18001916b  cmp     eax, 2
0x18001916e  jz      short loc_18001917A
0x180019170  mov     edx, 380h
0x180019175  jmp     loc_180019401
0x18001917a  mov     rcx, rdi
0x18001917d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019182  xor     edx, edx; dwFlags
0x180019184  mov     rcx, rax; lpName
0x180019187  call    cs:__imp_LocaleNameToLCID
0x18001918d  mov     r12d, eax
0x180019190  test    ax, ax
0x180019193  jz      loc_1800193FC
0x180019199  mov     eax, 3FFh
0x18001919e  test    ax, r12w
0x1800191a2  jz      loc_1800193FC
0x1800191a8  mov     ecx, 98h; dwFlags
0x1800191ad  call    ?PopulateInstalledLanguages@@YAJK@Z; PopulateInstalledLanguages(ulong)
0x1800191b2  mov     ebx, eax
0x1800191b4  test    eax, eax
0x1800191b6  jns     short loc_1800191C5
0x1800191b8  mov     r9d, eax
0x1800191bb  mov     edx, 38Dh
0x1800191c0  jmp     loc_180019409
0x1800191c5  lea     rcx, stru_180032FB8; SRWLock
0x1800191cc  call    cs:__imp_AcquireSRWLockShared
0x1800191d2  mov     rsi, cs:qword_180032FA8
0x1800191d9  mov     rbx, cs:qword_180032FA0
0x1800191e0  cmp     rbx, rsi
0x1800191e3  jz      short loc_180019221
0x1800191e5  mov     rcx, rdi
0x1800191e8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800191ed  mov     r8, rax
0x1800191f0  mov     rcx, rbx
0x1800191f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800191f8  mov     r9, [rdi+10h]
0x1800191fc  mov     rdx, [rbx+10h]
0x180019200  mov     rcx, rax
0x180019203  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180019208  test    al, al
0x18001920a  jnz     short loc_180019215
0x18001920c  add     rbx, 20h ; ' '
0x180019210  cmp     rbx, rsi
0x180019213  jnz     short loc_1800191E5
0x180019215  mov     rsi, cs:qword_180032FA8
0x18001921c  cmp     rbx, rsi
0x18001921f  jnz     short loc_180019250
0x180019221  mov     rcx, [rbp+5Fh]; this
0x180019225  mov     ebx, 80070490h
0x18001922a  mov     r9d, ebx; char *
0x18001922d  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180019234  mov     edx, 396h; void *
0x180019239  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001923e  lea     rcx, stru_180032FB8; SRWLock
0x180019245  call    cs:__imp_ReleaseSRWLockShared
0x18001924b  jmp     loc_18001941A
0x180019250  lea     rcx, stru_180032FB8; SRWLock
0x180019257  call    cs:__imp_ReleaseSRWLockShared
0x18001925d  lea     rcx, [rbp+57h+var_90]
0x180019261  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x180019266  nop
0x180019267  lea     rcx, [rbp+57h+var_78]
0x18001926b  test    r14b, r14b
0x18001926e  jz      short loc_180019277
0x180019270  call    ?GetUserPreferredMuiLanguages@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; GetUserPreferredMuiLanguages(void)
0x180019275  jmp     short loc_18001927C
0x180019277  call    ?GetSystemPreferredMuiLanguages@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; GetSystemPreferredMuiLanguages(void)
0x18001927c  mov     rdx, rax
0x18001927f  lea     rcx, [rbp+57h+var_90]
0x180019283  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x180019288  lea     rcx, [rbp+57h+var_78]
0x18001928c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180019291  call    cs:__imp_SetPreviousUserDisplayLanguages
0x180019297  mov     ebx, eax
0x180019299  test    eax, eax
0x18001929b  jns     short loc_1800192A4
0x18001929d  mov     edx, 3A5h
0x1800192a2  jmp     short loc_180019322
0x1800192a4  mov     rcx, [rbp+57h+var_90]
0x1800192a8  cmp     [rbp+57h+var_88], rcx
0x1800192ac  jnz     short loc_1800192BC
0x1800192ae  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x1800192b5  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800192bb  int     3; Trap to Debugger
0x1800192bc  call    ?SetStartingUserDisplayLanguageValue@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SetStartingUserDisplayLanguageValue(std::wstring const &)
0x1800192c1  mov     rcx, [rbp+5Fh]; this
0x1800192c5  test    eax, eax
0x1800192c7  jns     short loc_1800192D6
0x1800192c9  mov     r9d, eax; char *
0x1800192cc  mov     edx, 3AEh; void *
0x1800192d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800192d6  mov     r8d, r15d
0x1800192d9  movzx   edx, r12w
0x1800192dd  mov     rcx, rdi
0x1800192e0  call    ?ChangeUserAndSystemMuiLanguageInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GW4SET_DISPLAY_LANGUAGE_OPTIONS@Internal@Windows@@@Z; ChangeUserAndSystemMuiLanguageInternal(std::wstring const &,ushort,Windows::Internal::SET_DISPLAY_LANGUAGE_OPTIONS)
0x1800192e5  mov     ebx, eax
0x1800192e7  test    eax, eax
0x1800192e9  jns     short loc_1800192F2
0x1800192eb  mov     edx, 3B0h
0x1800192f0  jmp     short loc_180019322
0x1800192f2  mov     r8b, r14b
0x1800192f5  lea     rdx, [rbp+57h+var_90]
0x1800192f9  mov     rcx, rdi
0x1800192fc  call    ?CallNotifyUILanguageChange@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@_N@Z; CallNotifyUILanguageChange(std::wstring const &,std::vector<std::wstring> const &,bool)
0x180019301  test    r15b, 1
0x180019305  jnz     short loc_180019344
0x180019307  mov     rcx, rdi
0x18001930a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001930f  mov     rcx, rax; lpName
0x180019312  call    ?ChangeNlsSystemLocale@@YAJPEBG@Z; ChangeNlsSystemLocale(ushort const *)
0x180019317  mov     ebx, eax
0x180019319  test    eax, eax
0x18001931b  jns     short loc_180019344
0x18001931d  mov     edx, 3B7h; void *
0x180019322  mov     r9d, eax; char *
0x180019325  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001932c  mov     rcx, [rbp+5Fh]; this
0x180019330  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019335  nop
0x180019336  lea     rcx, [rbp+57h+var_90]
0x18001933a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001933f  jmp     loc_18001941A
0x180019344  movzx   ecx, r14b
0x180019348  inc     ecx
0x18001934a  call    cs:__imp_NotifyRedirectedStringChange
0x180019350  test    eax, eax
0x180019352  jnz     short loc_180019369
0x180019354  mov     rcx, [rbp+5Fh]; this
0x180019358  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001935f  lea     edx, [rax+77h]; void *
0x180019362  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019367  jmp     short loc_18001936C
0x180019369  mov     eax, r13d
0x18001936c  mov     rcx, [rbp+5Fh]; this
0x180019370  test    eax, eax
0x180019372  jns     short loc_180019381
0x180019374  mov     r9d, eax; char *
0x180019377  mov     edx, 3BBh; void *
0x18001937c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019381  mov     qword ptr [rsp+0C0h+bIgnoreCase], r13; int
0x180019386  xor     r9d, r9d
0x180019389  xor     r8d, r8d
0x18001938c  xor     edx, edx
0x18001938e  mov     rcx, cs:WNF_NLS_USER_UILANG_CHANGED
0x180019395  call    cs:__imp_RtlPublishWnfStateData
0x18001939b  mov     ebx, 10000000h
0x1800193a0  or      eax, ebx
0x1800193a2  mov     rcx, [rbp+5Fh]; this
0x1800193a6  jge     short loc_1800193B5
0x1800193a8  mov     r9d, eax; char *
0x1800193ab  mov     edx, 3C3h; void *
0x1800193b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800193b5  mov     qword ptr [rsp+0C0h+bIgnoreCase], r13; int
0x1800193ba  xor     r9d, r9d
0x1800193bd  xor     r8d, r8d
0x1800193c0  xor     edx, edx
0x1800193c2  mov     rcx, cs:WNF_GLOB_GLOBALIZATION_PREFERENCES_CHANGED
0x1800193c9  call    cs:__imp_RtlPublishWnfStateData
0x1800193cf  or      eax, ebx
0x1800193d1  mov     rcx, [rbp+5Fh]; this
0x1800193d5  jge     short loc_1800193E5
0x1800193d7  mov     r9d, eax; char *
0x1800193da  mov     edx, 3C5h; void *
0x1800193df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800193e4  nop
0x1800193e5  lea     rcx, [rbp+57h+var_90]
0x1800193e9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800193ee  nop
0x1800193ef  lea     rcx, [rbp+57h+var_60]
0x1800193f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800193f8  xor     eax, eax
0x1800193fa  jmp     short loc_180019425
0x1800193fc  mov     edx, 388h; void *
0x180019401  mov     ebx, 80070057h
0x180019406  mov     r9d, ebx; char *
0x180019409  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180019410  mov     rcx, [rbp+5Fh]; this
0x180019414  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019419  nop
0x18001941a  lea     rcx, [rbp+57h+var_60]
0x18001941e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019423  mov     eax, ebx
0x180019425  mov     rcx, [rbp+57h+var_40]
0x180019429  xor     rcx, rsp; StackCookie
0x18001942c  call    __security_check_cookie
0x180019431  mov     rbx, [rsp+0C0h+arg_10]
0x180019439  add     rsp, 90h
0x180019440  pop     r15
0x180019442  pop     r14
0x180019444  pop     r13
0x180019446  pop     r12
0x180019448  pop     rdi
0x180019449  pop     rsi
0x18001944a  pop     rbp
0x18001944b  retn
```
