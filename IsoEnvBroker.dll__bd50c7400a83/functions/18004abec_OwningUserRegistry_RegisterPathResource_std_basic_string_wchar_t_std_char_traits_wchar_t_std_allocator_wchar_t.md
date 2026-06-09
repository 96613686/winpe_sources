# OwningUserRegistry::RegisterPathResource(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18004abec`
- end: `0x18004b284`
- name: `?RegisterPathResource@OwningUserRegistry@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00@Z`
- size: `1688`
- prototype: `void __fastcall(__int128 *, wchar_t *, wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004b28c`

## callees

- `0x180002520`
- `0x1800075e4`
- `0x18000e4ec`
- `0x18001045c`
- `0x180011e18`
- `0x18001e820`
- `0x18001eb90`
- `0x18001fa68`
- `0x18002193c`
- `0x180030214`
- `0x18003dce4`
- `0x18003e03c`
- `0x180048bd0`
- `0x18004abec`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18004aeaf`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18004aeaf`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004aec6`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004aec6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004af86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004af86`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18004ae98`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18004ae98`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004ae58`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004ae58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ac54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ac54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004af11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004af11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b004`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b04c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b05d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b0a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b1e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b1fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b20b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b21f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b004`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b04c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b05d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b0a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b1e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b1fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b20b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b21f`

## string_xrefs

- `0x18004b248`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18004b260`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18004b272`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18004acc2`: `RegisteredPaths`
- `0x18004afd0`: `Path already registered for Agent %s, App Identity %s: %s (skipping duplicate)`
- `0x18004b1ca`: `Registered path resource for Agent %s, App Identity %s: %s`

## pseudocode

```c
void __fastcall OwningUserRegistry::RegisterPathResource(__int128 *a1, wchar_t *a2, wchar_t *a3, wchar_t *a4)
{
  wchar_t *v5; // r14
  wchar_t *v6; // r15
  wchar_t *v7; // rsi
  int v8; // ebx
  const char *v9; // r9
  wchar_t *v10; // rbx
  wchar_t *v11; // r8
  wchar_t *v12; // r8
  int v13; // eax
  unsigned int v14; // r13d
  const char *v15; // r9
  _DWORD *v16; // rax
  const wchar_t *v17; // rbx
  unsigned int v18; // eax
  const WCHAR *v19; // rdx
  char v20; // al
  const wchar_t *v21; // rdx
  __int128 *v22; // rcx
  const wchar_t *v23; // r9
  const wchar_t *v24; // r8
  int phkResult; // [rsp+20h] [rbp-248h]
  _QWORD *v27; // [rsp+40h] [rbp-228h]
  HKEY hKey; // [rsp+50h] [rbp-218h] BYREF
  __int128 *p_Src; // [rsp+58h] [rbp-210h]
  HKEY v31; // [rsp+60h] [rbp-208h] BYREF
  _QWORD *v32; // [rsp+68h] [rbp-200h]
  HKEY v33; // [rsp+70h] [rbp-1F8h] BYREF
  HKEY v34; // [rsp+78h] [rbp-1F0h] BYREF
  HKEY v35; // [rsp+80h] [rbp-1E8h] BYREF
  wchar_t *EndPtr[8]; // [rsp+88h] [rbp-1E0h] BYREF
  HKEY v37; // [rsp+C8h] [rbp-1A0h] BYREF
  __int128 Src; // [rsp+D0h] [rbp-198h] BYREF
  __int64 v39; // [rsp+E0h] [rbp-188h]
  unsigned __int64 v40; // [rsp+E8h] [rbp-180h]
  HKEY v41; // [rsp+F0h] [rbp-178h]
  int v42; // [rsp+F8h] [rbp-170h]
  __int64 v43; // [rsp+100h] [rbp-168h]
  wchar_t *String[3]; // [rsp+118h] [rbp-150h] BYREF
  unsigned __int64 v45; // [rsp+130h] [rbp-138h]
  __int64 v46; // [rsp+138h] [rbp-130h]
  int v47; // [rsp+140h] [rbp-128h]
  __int128 v48; // [rsp+150h] [rbp-118h] BYREF
  __int64 v49; // [rsp+160h] [rbp-108h]
  __int64 v50; // [rsp+168h] [rbp-100h]
  __int64 v51; // [rsp+170h] [rbp-F8h]
  __int64 v52; // [rsp+178h] [rbp-F0h]
  __int64 v53; // [rsp+180h] [rbp-E8h]
  _BYTE v54[56]; // [rsp+190h] [rbp-D8h] BYREF
  _BYTE v55[56]; // [rsp+1C8h] [rbp-A0h] BYREF
  _BYTE v56[32]; // [rsp+200h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  p_Src = a1;
  EndPtr[2] = a4;
  EndPtr[3] = a3;
  EndPtr[4] = a2;
  v5 = a2;
  v6 = a3;
  v7 = a4;
  v8 = dword_1800B9160;
  if ( v8 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v9);
  v32 = v5 + 12;
  v10 = v5;
  if ( *((_QWORD *)v5 + 3) <= 7u )
    v11 = v5;
  else
    v11 = *(wchar_t **)v5;
  wil::reg::create_unique_key(&v35, *(_QWORD *)p_Src, v11);
  v27 = v6 + 12;
  if ( *((_QWORD *)v6 + 3) <= 7u )
    v12 = v6;
  else
    v12 = *(wchar_t **)a3;
  wil::reg::create_unique_key(&v34, v35, v12);
  wil::reg::create_unique_key(&hKey, v34, L"RegisteredPaths");
  v33 = (HKEY)&v48;
  v48 = 0;
  v49 = 0;
  v50 = 7;
  LOWORD(v48) = 0;
  v51 = 0;
  v52 = 0xFFFFFFFFLL;
  v53 = 0;
  p_Src = &Src;
  Src = 0;
  v39 = 0;
  v40 = 7;
  LOWORD(Src) = 0;
  v41 = hKey;
  v42 = -1;
  v43 = 0;
  if ( hKey )
  {
    v42 = 0;
    v13 = wil::reg::key_iterator_data<std::wstring>::enumerate_current_index(&Src);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6EE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        (const char *)(unsigned int)v13,
        phkResult);
  }
  EndPtr[1] = v5 + 12;
  p_Src = (__int128 *)(v6 + 12);
  v14 = 1;
  wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(v54, &Src, &v48);
  wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(
    String,
    v54);
  wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(
    &v48,
    v55);
  while ( v47 != -1 && (_DWORD)v52 != -1 && v46 != v51 || v47 != (_DWORD)v52 )
  {
    if ( v47 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6FF,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        v15);
    v16 = (_DWORD *)_o__errno(retaddr, v52);
    v33 = (HKEY)v16;
    v17 = (const wchar_t *)String;
    if ( v45 > 7 )
      v17 = String[0];
    EndPtr[0] = 0;
    *v16 = 0;
    v18 = wcstoul(v17, EndPtr, 10);
    if ( v17 == EndPtr[0] )
      std::_Xinvalid_argument("invalid stoul argument");
    if ( *(_DWORD *)v33 == 34 )
      std::_Xout_of_range("stoul argument out of range");
    if ( v18 >= v14 )
      v14 = v18 + 1;
    v31 = 0;
    v19 = (const WCHAR *)String;
    if ( v45 > 7 )
      v19 = String[0];
    if ( !RegOpenKeyExW(hKey, v19, 0, 0x20019u, &v31) )
    {
      v33 = v31;
      wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(
        &v33,
        &Src,
        0,
        &stru_1800A0760,
        268435462);
      v20 = (char)v41;
      if ( (_BYTE)v41 )
      {
        v21 = v7;
        if ( *((_QWORD *)v7 + 3) > 7u )
          v21 = *(const wchar_t **)a4;
        v22 = &Src;
        if ( v40 > 7 )
          v22 = (__int128 *)Src;
        if ( !(unsigned int)_o__wcsicmp(v22, v21) )
        {
          if ( *((_QWORD *)v7 + 3) > 7u )
            v7 = *(wchar_t **)a4;
          if ( *v27 > 7u )
            v6 = *(wchar_t **)a3;
          if ( *v32 > 7u )
            v5 = *(wchar_t **)a2;
          Log(4u, L"Path already registered for Agent %s, App Identity %s: %s (skipping duplicate)", v5, v6, v7);
          if ( (_BYTE)v41 )
            std::wstring::~wstring(&Src);
          if ( v31 )
            RegCloseKey(v31);
          std::wstring::~wstring(&v48);
          std::wstring::~wstring(String);
          std::wstring::~wstring(v55);
          std::wstring::~wstring(v54);
          if ( hKey )
            RegCloseKey(hKey);
          if ( v34 )
            RegCloseKey(v34);
          if ( v35 )
            RegCloseKey(v35);
          return;
        }
        v20 = (char)v41;
      }
      if ( v20 )
        std::wstring::~wstring(&Src);
    }
    if ( v31 )
      RegCloseKey(v31);
    v10 = a2;
    wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::operator++(String);
  }
  std::wstring::~wstring(&v48);
  std::wstring::~wstring(String);
  std::wstring::~wstring(v55);
  std::wstring::~wstring(v54);
  swprintf_s<16>(v56, L"%04u", v14);
  wil::reg::create_unique_key(&v37, hKey, v56);
  v24 = v7;
  if ( *((_QWORD *)v7 + 3) > 7u )
    v24 = *(const wchar_t **)a4;
  wil::reg::set_value_string((wil::reg *)v37, (HKEY)&stru_1800A0760, v24, v23);
  if ( *((_QWORD *)v7 + 3) > 7u )
    v7 = *(wchar_t **)a4;
  if ( *v27 > 7u )
    v6 = *(wchar_t **)a3;
  if ( *v32 > 7u )
    v5 = *(wchar_t **)v10;
  Log(4u, L"Registered path resource for Agent %s, App Identity %s: %s", v5, v6, v7);
  if ( v37 )
    RegCloseKey(v37);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v34 )
    RegCloseKey(v34);
  if ( v35 )
    RegCloseKey(v35);
}

```

## disassembly

```asm
0x18004abec  push    rbx
0x18004abee  push    rsi
0x18004abef  push    rdi
0x18004abf0  push    r12
0x18004abf2  push    r13
0x18004abf4  push    r14
0x18004abf6  push    r15
0x18004abf8  sub     rsp, 230h
0x18004abff  mov     rax, cs:__security_cookie
0x18004ac06  xor     rax, rsp
0x18004ac09  mov     [rsp+268h+var_48], rax
0x18004ac11  mov     r12, r9
0x18004ac14  mov     [rsp+268h+var_220], r8
0x18004ac19  mov     [rsp+268h+var_230], rdx
0x18004ac1e  mov     [rsp+268h+var_210], rcx
0x18004ac23  mov     [rsp+268h+var_1D0], r9
0x18004ac2b  mov     [rsp+268h+var_1C8], r8
0x18004ac33  mov     [rsp+268h+var_1C0], rdx
0x18004ac3b  mov     r14, rdx
0x18004ac3e  mov     r15, r8
0x18004ac41  mov     rsi, r9
0x18004ac44  xor     edi, edi
0x18004ac46  mov     ebx, cs:dword_1800B9160
0x18004ac4c  mov     r13, [rsp+268h]
0x18004ac54  call    cs:__imp_GetCurrentThreadId
0x18004ac5a  cmp     ebx, eax
0x18004ac5c  jnz     loc_18004B248
0x18004ac62  lea     r13, [r14+18h]
0x18004ac66  mov     [rsp+268h+var_200], r13
0x18004ac6b  mov     rbx, r14
0x18004ac6e  cmp     qword ptr [r13+0], 7
0x18004ac73  jbe     short loc_18004AC7A
0x18004ac75  mov     r8, [r14]
0x18004ac78  jmp     short loc_18004AC7D
0x18004ac7a  mov     r8, r14
0x18004ac7d  mov     rdx, [rsp+268h+var_210]
0x18004ac82  mov     rdx, [rdx]
0x18004ac85  lea     rcx, [rsp+268h+var_1E8]
0x18004ac8d  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x18004ac92  nop
0x18004ac93  lea     rax, [r15+18h]
0x18004ac97  mov     [rsp+268h+var_228], rax
0x18004ac9c  cmp     qword ptr [rax], 7
0x18004aca0  jbe     short loc_18004ACAC
0x18004aca2  mov     r8, [rsp+268h+var_220]
0x18004aca7  mov     r8, [r8]
0x18004acaa  jmp     short loc_18004ACAF
0x18004acac  mov     r8, r15
0x18004acaf  mov     rdx, [rsp+268h+var_1E8]
0x18004acb7  lea     rcx, [rsp+268h+var_1F0]
0x18004acbc  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x18004acc1  nop
0x18004acc2  lea     r8, aRegisteredpath; "RegisteredPaths"
0x18004acc9  mov     rdx, [rsp+268h+var_1F0]
0x18004acce  lea     rcx, [rsp+268h+hKey]
0x18004acd3  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x18004acd8  nop
0x18004acd9  lea     rax, [rsp+268h+var_118]
0x18004ace1  mov     [rsp+268h+var_1F8], rax
0x18004ace6  mov     dword ptr [rsp+268h+var_F0+4], edi
0x18004aced  xorps   xmm0, xmm0
0x18004acf0  movups  [rsp+268h+var_118], xmm0
0x18004acf8  mov     [rsp+268h+var_108], rdi
0x18004ad00  mov     [rsp+268h+var_100], 7
0x18004ad0c  mov     word ptr [rsp+268h+var_118], di
0x18004ad14  mov     [rsp+268h+var_F8], rdi
0x18004ad1c  or      ecx, 0FFFFFFFFh
0x18004ad1f  mov     dword ptr [rsp+268h+var_F0], ecx
0x18004ad26  mov     [rsp+268h+var_E8], rdi
0x18004ad2e  lea     rax, [rsp+268h+Src]
0x18004ad36  mov     [rsp+268h+var_210], rax
0x18004ad3b  mov     rax, [rsp+268h+hKey]
0x18004ad40  movups  [rsp+268h+Src], xmm0
0x18004ad48  mov     [rsp+268h+var_188], rdi
0x18004ad50  mov     [rsp+268h+var_180], 7
0x18004ad5c  mov     word ptr [rsp+268h+Src], di
0x18004ad64  mov     [rsp+268h+var_178], rax
0x18004ad6c  mov     [rsp+268h+var_170], ecx
0x18004ad73  mov     [rsp+268h+var_168], rdi
0x18004ad7b  test    rax, rax
0x18004ad7e  jz      short loc_18004ADA4
0x18004ad80  mov     [rsp+268h+var_170], edi
0x18004ad87  lea     rcx, [rsp+268h+Src]; Src
0x18004ad8f  call    ?enumerate_current_index@?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<std::wstring>::enumerate_current_index(void)
0x18004ad94  mov     rcx, [rsp+268h]; this
0x18004ad9c  test    eax, eax
0x18004ad9e  js      loc_18004B25D
0x18004ada4  mov     [rsp+268h+var_1D8], r13
0x18004adac  mov     rax, [rsp+268h+var_228]
0x18004adb1  mov     [rsp+268h+var_210], rax
0x18004adb6  mov     r13d, 1
0x18004adbc  mov     [rsp+268h+var_238], r13d
0x18004adc1  lea     r8, [rsp+268h+var_118]
0x18004adc9  lea     rdx, [rsp+268h+Src]
0x18004add1  lea     rcx, [rsp+268h+var_D8]
0x18004add9  call    ??$make_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@@wil@@YA?AV?$pointer_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@@details@0@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@0@0@Z; wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>,wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>)
0x18004adde  nop
0x18004addf  lea     rdx, [rsp+268h+var_D8]
0x18004ade7  lea     rcx, [rsp+268h+String]
0x18004adef  call    ??0?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>> const &)
0x18004adf4  nop
0x18004adf5  lea     rdx, [rsp+268h+var_A0]
0x18004adfd  lea     rcx, [rsp+268h+var_118]
0x18004ae05  call    ??0?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>> const &)
0x18004ae0a  nop
0x18004ae0b  mov     ecx, [rsp+268h+var_128]
0x18004ae12  or      r8d, 0FFFFFFFFh
0x18004ae16  mov     rdx, [rsp+268h+var_F0]
0x18004ae1e  cmp     ecx, r8d
0x18004ae21  jz      short loc_18004AE3A
0x18004ae23  cmp     edx, r8d
0x18004ae26  jz      short loc_18004AE3A
0x18004ae28  mov     rax, [rsp+268h+var_F8]
0x18004ae30  cmp     [rsp+268h+var_130], rax
0x18004ae38  jnz     short loc_18004AE42
0x18004ae3a  cmp     ecx, edx
0x18004ae3c  jz      loc_18004B109
0x18004ae42  cmp     ecx, r8d
0x18004ae45  setz    al
0x18004ae48  mov     rcx, [rsp+268h]; this
0x18004ae50  test    al, al
0x18004ae52  jnz     loc_18004B272
0x18004ae58  call    cs:__imp__o__errno
0x18004ae5e  mov     [rsp+268h+var_1F8], rax
0x18004ae63  lea     rbx, [rsp+268h+String]
0x18004ae6b  cmp     [rsp+268h+var_138], 7
0x18004ae74  cmova   rbx, [rsp+268h+String]
0x18004ae7d  mov     [rsp+268h+EndPtr], rdi
0x18004ae85  mov     [rax], edi
0x18004ae87  mov     r8d, 0Ah; Radix
0x18004ae8d  lea     rdx, [rsp+268h+EndPtr]; EndPtr
0x18004ae95  mov     rcx, rbx; String
0x18004ae98  call    cs:__imp_wcstoul
0x18004ae9e  cmp     rbx, [rsp+268h+EndPtr]
0x18004aea6  jnz     short loc_18004AEB5
0x18004aea8  lea     rcx, aInvalidStoulAr; "invalid stoul argument"
0x18004aeaf  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x18004aeb5  mov     rcx, [rsp+268h+var_1F8]
0x18004aeba  cmp     dword ptr [rcx], 22h ; '"'
0x18004aebd  jnz     short loc_18004AECC
0x18004aebf  lea     rcx, aStoulArgumentO; "stoul argument out of range"
0x18004aec6  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18004aecc  cmp     eax, r13d
0x18004aecf  jb      short loc_18004AEDA
0x18004aed1  lea     r13d, [rax+1]
0x18004aed5  mov     [rsp+268h+var_238], r13d
0x18004aeda  mov     [rsp+268h+var_208], rdi
0x18004aedf  lea     rdx, [rsp+268h+String]
0x18004aee7  cmp     [rsp+268h+var_138], 7
0x18004aef0  cmova   rdx, [rsp+268h+String]; lpSubKey
0x18004aef9  lea     rax, [rsp+268h+var_208]
0x18004aefe  mov     qword ptr [rsp+268h+phkResult], rax; phkResult
0x18004af03  mov     r9d, 20019h; samDesired
0x18004af09  xor     r8d, r8d; ulOptions
0x18004af0c  mov     rcx, [rsp+268h+hKey]; hKey
0x18004af11  call    cs:__imp_RegOpenKeyExW
0x18004af17  test    eax, eax
0x18004af19  jnz     loc_18004B096
0x18004af1f  mov     rax, [rsp+268h+var_208]
0x18004af24  mov     [rsp+268h+var_1F8], rax
0x18004af29  mov     [rsp+268h+phkResult], 10000006h
0x18004af31  lea     r9, stru_1800A0760
0x18004af38  xor     r8d, r8d
0x18004af3b  lea     rdx, [rsp+268h+Src]
0x18004af43  lea     rcx, [rsp+268h+var_1F8]
0x18004af48  call    ??$try_get_value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEB_W0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(wchar_t const *,wchar_t const *,ulong)
0x18004af4d  nop
0x18004af4e  mov     rax, [rsp+268h+var_178]
0x18004af56  test    al, al
0x18004af58  jz      loc_18004B084
0x18004af5e  mov     rdx, rsi
0x18004af61  cmp     qword ptr [rsi+18h], 7
0x18004af66  jbe     short loc_18004AF6C
0x18004af68  mov     rdx, [r12]
0x18004af6c  lea     rcx, [rsp+268h+Src]
0x18004af74  cmp     [rsp+268h+var_180], 7
0x18004af7d  cmova   rcx, qword ptr [rsp+268h+Src]
0x18004af86  call    cs:__imp__o__wcsicmp
0x18004af8c  test    eax, eax
0x18004af8e  jnz     loc_18004B07C
0x18004af94  cmp     qword ptr [rsi+18h], 7
0x18004af99  jbe     short loc_18004AF9F
0x18004af9b  mov     rsi, [r12]
0x18004af9f  mov     rax, [rsp+268h+var_228]
0x18004afa4  cmp     qword ptr [rax], 7
0x18004afa8  jbe     short loc_18004AFB2
0x18004afaa  mov     rax, [rsp+268h+var_220]
0x18004afaf  mov     r15, [rax]
0x18004afb2  mov     rax, [rsp+268h+var_200]
0x18004afb7  cmp     qword ptr [rax], 7
0x18004afbb  jbe     short loc_18004AFC5
0x18004afbd  mov     r14, [rsp+268h+var_230]
0x18004afc2  mov     r14, [r14]
0x18004afc5  mov     qword ptr [rsp+268h+phkResult], rsi
0x18004afca  mov     r9, r15
0x18004afcd  mov     r8, r14
0x18004afd0  lea     rdx, aPathAlreadyReg; "Path already registered for Agent %s, A"...
0x18004afd7  mov     ecx, 4; unsigned __int8
0x18004afdc  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004afe1  nop
0x18004afe2  cmp     byte ptr [rsp+268h+var_178], dil
0x18004afea  jz      short loc_18004AFFA
0x18004afec  lea     rcx, [rsp+268h+Src]
0x18004aff4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004aff9  nop
0x18004affa  mov     rcx, [rsp+268h+var_208]; hKey
0x18004afff  test    rcx, rcx
0x18004b002  jz      short loc_18004B00B
0x18004b004  call    cs:__imp_RegCloseKey
0x18004b00a  nop
0x18004b00b  lea     rcx, [rsp+268h+var_118]
0x18004b013  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b018  nop
0x18004b019  lea     rcx, [rsp+268h+String]
0x18004b021  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b026  nop
0x18004b027  lea     rcx, [rsp+268h+var_A0]
0x18004b02f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b034  lea     rcx, [rsp+268h+var_D8]
0x18004b03c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b041  nop
0x18004b042  mov     rcx, [rsp+268h+hKey]; hKey
0x18004b047  test    rcx, rcx
0x18004b04a  jz      short loc_18004B053
0x18004b04c  call    cs:__imp_RegCloseKey
0x18004b052  nop
0x18004b053  mov     rcx, [rsp+268h+var_1F0]; hKey
0x18004b058  test    rcx, rcx
0x18004b05b  jz      short loc_18004B064
0x18004b05d  call    cs:__imp_RegCloseKey
0x18004b063  nop
0x18004b064  mov     rcx, [rsp+268h+var_1E8]; hKey
0x18004b06c  test    rcx, rcx
0x18004b06f  jz      short loc_18004B077
0x18004b071  call    cs:__imp_RegCloseKey
0x18004b077  jmp     loc_18004B225
0x18004b07c  mov     rax, [rsp+268h+var_178]
0x18004b084  test    al, al
0x18004b086  jz      short loc_18004B096
0x18004b088  lea     rcx, [rsp+268h+Src]
0x18004b090  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b095  nop
0x18004b096  mov     rcx, [rsp+268h+var_208]; hKey
0x18004b09b  test    rcx, rcx
0x18004b09e  jz      short loc_18004B0A7
0x18004b0a0  call    cs:__imp_RegCloseKey
0x18004b0a6  nop
0x18004b0a7  mov     rbx, [rsp+268h+var_230]
0x18004b0ac  jmp     short loc_18004B0F7
0x18004b0ae  mov     rax, [rsp+268h+var_1D8]
0x18004b0b6  mov     [rsp+268h+var_200], rax
0x18004b0bb  mov     rax, [rsp+268h+var_210]
0x18004b0c0  mov     [rsp+268h+var_228], rax
0x18004b0c5  mov     r12, [rsp+268h+var_1D0]
0x18004b0cd  mov     rax, [rsp+268h+var_1C8]
0x18004b0d5  mov     rbx, [rsp+268h+var_1C0]
0x18004b0dd  mov     rsi, r12
0x18004b0e0  mov     r15, rax
0x18004b0e3  mov     r14, rbx
0x18004b0e6  mov     [rsp+268h+var_230], rbx
0x18004b0eb  mov     [rsp+268h+var_220], rax
0x18004b0f0  mov     r13d, [rsp+268h+var_238]
0x18004b0f5  xor     edi, edi
0x18004b0f7  lea     rcx, [rsp+268h+String]; Src
0x18004b0ff  call    ??E?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAAAEAV012@XZ; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::operator++(void)
0x18004b104  jmp     loc_18004AE0B
0x18004b109  lea     rcx, [rsp+268h+var_118]
0x18004b111  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b116  nop
0x18004b117  lea     rcx, [rsp+268h+String]
0x18004b11f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b124  nop
0x18004b125  lea     rcx, [rsp+268h+var_A0]
0x18004b12d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b132  lea     rcx, [rsp+268h+var_D8]
0x18004b13a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b13f  mov     r8d, r13d
0x18004b142  lea     rdx, a04u; "%04u"
0x18004b149  lea     rcx, [rsp+268h+var_68]
0x18004b151  call    ??$swprintf_s@$0BA@@@YAHAEAY0BA@_WPEB_WZZ; swprintf_s<16>(wchar_t (&)[16],wchar_t const *,...)
0x18004b156  lea     r8, [rsp+268h+var_68]
0x18004b15e  mov     rdx, [rsp+268h+hKey]
0x18004b163  lea     rcx, [rsp+268h+var_1A0]
0x18004b16b  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x18004b170  nop
0x18004b171  mov     r8, rsi
0x18004b174  cmp     qword ptr [rsi+18h], 7
0x18004b179  jbe     short loc_18004B17F
0x18004b17b  mov     r8, [r12]; wchar_t *
0x18004b17f  lea     rdx, stru_1800A0760; HKEY
0x18004b186  mov     rcx, [rsp+268h+var_1A0]; this
0x18004b18e  call    ?set_value_string@reg@wil@@YAXPEAUHKEY__@@PEB_W1@Z; wil::reg::set_value_string(HKEY__ *,wchar_t const *,wchar_t const *)
0x18004b193  cmp     qword ptr [rsi+18h], 7
0x18004b198  jbe     short loc_18004B19E
0x18004b19a  mov     rsi, [r12]
0x18004b19e  mov     rax, [rsp+268h+var_228]
0x18004b1a3  cmp     qword ptr [rax], 7
0x18004b1a7  jbe     short loc_18004B1B1
0x18004b1a9  mov     rax, [rsp+268h+var_220]
0x18004b1ae  mov     r15, [rax]
  ... truncated ...
```
