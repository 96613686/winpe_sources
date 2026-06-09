# AgentAccountRegistry::Initialize(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>)

- ea: `0x180060218`
- end: `0x180060756`
- name: `?Initialize@AgentAccountRegistry@@QEAAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1342`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180062ba8`

## callees

- `0x180002520`
- `0x1800029cc`
- `0x180002ee8`
- `0x180003070`
- `0x1800075e4`
- `0x18000e4ec`
- `0x18001045c`
- `0x180011e18`
- `0x180014c04`
- `0x18001e820`
- `0x18001eb90`
- `0x18001f998`
- `0x18001fa68`
- `0x18002030c`
- `0x18002083c`
- `0x18002193c`
- `0x180030214`
- `0x18003b734`
- `0x18003b968`
- `0x18003d690`
- `0x18003dce4`
- `0x18003de88`
- `0x18003e03c`
- `0x180060218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060292`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800602a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800602a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060269`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060269`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006029d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006065d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006067b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800606e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006029d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006065d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006067b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800606e9`

## string_xrefs

- `0x18006072c`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18006071a`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180060744`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
LSTATUS __fastcall AgentAccountRegistry::Initialize(__int64 a1, HKEY *a2)
{
  int v3; // edi
  int v4; // ebx
  const char *v5; // r9
  HKEY v6; // r15
  HKEY v7; // r14
  DWORD LastError; // ebx
  HKEY v9; // rdx
  int child_key_count; // eax
  float v11; // xmm0_4
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  float v14; // xmm0_4
  float v15; // xmm0_4
  unsigned __int64 v16; // rcx
  int v17; // eax
  const char *v18; // r9
  int v19; // r15d
  char *v20; // r12
  char **v21; // r8
  const WCHAR *v22; // r8
  int v23; // edi
  __int128 *v24; // rcx
  int v25; // edi
  __int128 *v26; // r9
  char **v27; // r8
  char **v28; // r8
  HKEY *v29; // rbx
  void *v30; // rax
  HKEY v31; // rbx
  __int64 v32; // rax
  __int64 v33; // r14
  LSTATUS result; // eax
  int v35; // [rsp+28h] [rbp-E0h]
  HKEY v36; // [rsp+38h] [rbp-D0h] BYREF
  HKEY *v37; // [rsp+40h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A8h]
  __int64 v41; // [rsp+68h] [rbp-A0h]
  HKEY v42; // [rsp+70h] [rbp-98h]
  __int64 v43; // [rsp+78h] [rbp-90h]
  __int64 v44; // [rsp+80h] [rbp-88h]
  HKEY *v45; // [rsp+88h] [rbp-80h]
  void *v46; // [rsp+90h] [rbp-78h]
  _BYTE v47[16]; // [rsp+98h] [rbp-70h] BYREF
  char *Src[3]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int64 v49; // [rsp+C0h] [rbp-48h]
  char *v50; // [rsp+C8h] [rbp-40h]
  int v51; // [rsp+D0h] [rbp-38h]
  __int128 v52; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v53; // [rsp+F0h] [rbp-18h]
  __int128 v54; // [rsp+100h] [rbp-8h] BYREF
  __int64 v55; // [rsp+110h] [rbp+8h]
  __int64 v56; // [rsp+118h] [rbp+10h]
  __int64 v57; // [rsp+120h] [rbp+18h]
  int v58; // [rsp+128h] [rbp+20h]
  int v59; // [rsp+12Ch] [rbp+24h]
  __int64 v60; // [rsp+130h] [rbp+28h]
  __int128 v61; // [rsp+138h] [rbp+30h] BYREF
  __int64 v62; // [rsp+148h] [rbp+40h]
  __int64 v63; // [rsp+150h] [rbp+48h]
  char *v64[5]; // [rsp+158h] [rbp+50h] BYREF
  int v65; // [rsp+180h] [rbp+78h]
  char *v66[7]; // [rsp+198h] [rbp+90h] BYREF
  char *v67[7]; // [rsp+1D0h] [rbp+C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  v45 = a2;
  v3 = 0;
  LODWORD(v36) = 0;
  v4 = dword_1800B9160;
  if ( v4 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15D,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v5);
  if ( &g_agentAccountRegistry != a2 )
  {
    v6 = *a2;
    v7 = g_agentAccountRegistry;
    if ( g_agentAccountRegistry )
    {
      LastError = GetLastError();
      RegCloseKey(v7);
      SetLastError(LastError);
    }
    g_agentAccountRegistry = v6;
    *a2 = 0;
  }
  wil::reg::set_value_string(
    (wil::reg *)g_agentAccountRegistry,
    (HKEY)&stru_1800A3588,
    L"IsoEnvUsers_2025_Preview",
    (const wchar_t *)v5);
  child_key_count = wil::reg::get_child_key_count((wil::reg *)g_agentAccountRegistry, v9);
  v11 = o_ceilf_0((float)child_key_count / *(float *)&dword_1800B9468);
  v12 = 0;
  if ( v11 >= 9.223372e18 )
  {
    v11 = v11 - 9.223372e18;
    if ( v11 < 9.223372e18 )
      v12 = 0x8000000000000000uLL;
  }
  v13 = v12 + (unsigned int)(int)v11;
  if ( qword_1800B9478 < 0 )
    v14 = (float)(qword_1800B9478 & 1 | (unsigned int)((unsigned __int64)qword_1800B9478 >> 1))
        + (float)(qword_1800B9478 & 1 | (unsigned int)((unsigned __int64)qword_1800B9478 >> 1));
  else
    v14 = (float)(int)qword_1800B9478;
  v15 = o_ceilf_0(v14 / *(float *)&dword_1800B9468);
  v16 = 0;
  if ( v15 >= 9.223372e18 )
  {
    v15 = v15 - 9.223372e18;
    if ( v15 < 9.223372e18 )
      v16 = 0x8000000000000000uLL;
  }
  if ( v16 + (unsigned int)(int)v15 >= v13 )
    v13 = v16 + (unsigned int)(int)v15;
  if ( v13 > qword_1800B94A0 )
    std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OwningUserRegistry>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>>,0>>::_Forced_rehash(
      &dword_1800B9468,
      v13);
  hKey = (HKEY)&v54;
  v59 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 7;
  LOWORD(v54) = 0;
  v57 = 0;
  v58 = -1;
  v60 = 0;
  v37 = hKey_8;
  *(_OWORD *)hKey_8 = 0;
  v40 = 0;
  v41 = 7;
  LOWORD(hKey_8[0]) = 0;
  v42 = g_agentAccountRegistry;
  LODWORD(v43) = -1;
  v44 = 0;
  if ( g_agentAccountRegistry )
  {
    LODWORD(v43) = 0;
    v17 = wil::reg::key_iterator_data<std::wstring>::enumerate_current_index(hKey_8);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6EE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        (const char *)(unsigned int)v17,
        v35);
  }
  wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(v66, hKey_8, &v54);
  wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(
    Src,
    v66);
  wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(
    v64,
    v67);
  v19 = v65;
  v20 = v64[4];
  while ( v51 != -1 && v19 != -1 && v50 != v20 || v51 != v19 )
  {
    if ( v51 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6FF,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        v18);
    v21 = Src;
    if ( v49 > 7 )
      v21 = (char **)Src[0];
    Log(4u, L"Populating for existing key %s", v21);
    v22 = (const WCHAR *)Src;
    if ( v49 > 7 )
      v22 = (const WCHAR *)Src[0];
    v36 = g_agentAccountRegistry;
    wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(
      &v36,
      (__int64)hKey_8,
      v22,
      (const WCHAR *)&stru_18009E3F8,
      0x10000006u);
    v23 = v3 | 4;
    LODWORD(v36) = v23;
    if ( (_BYTE)v42 )
    {
      v24 = (__int128 *)std::wstring::wstring((__int64)&v54, (__int64)hKey_8);
      v25 = v23 | 1;
    }
    else
    {
      v61 = 0;
      v62 = 0;
      v63 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v61, L"(unknown)", 9u);
      v24 = &v61;
      v25 = v23 | 2;
    }
    v52 = 0;
    v53 = 0u;
    v52 = *v24;
    v53 = v24[1];
    *((_QWORD *)v24 + 2) = 0;
    *((_QWORD *)v24 + 3) = 7;
    *(_WORD *)v24 = 0;
    if ( (v25 & 2) != 0 )
    {
      v25 &= ~2u;
      std::wstring::~wstring((char **)&v61);
    }
    if ( (v25 & 1) != 0 )
    {
      v25 &= ~1u;
      std::wstring::~wstring((char **)&v54);
    }
    v26 = &v52;
    if ( *((_QWORD *)&v53 + 1) > 7u )
      v26 = (__int128 *)v52;
    v27 = Src;
    if ( v49 > 7 )
      v27 = (char **)Src[0];
    Log(4u, L"Found UserName for %s: %s", v27, v26);
    v28 = Src;
    if ( v49 > 7 )
      v28 = (char **)Src[0];
    v29 = (HKEY *)wil::reg::create_unique_key(&hKey, g_agentAccountRegistry, v28);
    v30 = operator new(0xA8u);
    v46 = v30;
    v37 = (HKEY *)*v29;
    *v29 = 0;
    v31 = (HKEY)OwningUserRegistry::OwningUserRegistry((__int64)v30, (HKEY *)&v37, (__int64)&v52);
    v36 = v31;
    v3 = v25 | 8;
    v32 = std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OwningUserRegistry>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>>,0>>::_Try_emplace<std::wstring const &,>(
            (float *)&dword_1800B9468,
            (__int64)v47,
            Src);
    v33 = *(_QWORD *)(*(_QWORD *)v32 + 48LL);
    *(_QWORD *)(*(_QWORD *)v32 + 48LL) = v31;
    if ( v33 )
    {
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>((char **)(v33 + 128));
      std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v33 + 112);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>((char **)(v33 + 64));
      std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v33 + 48);
      std::wstring::~wstring((char **)(v33 + 8));
      if ( *(_QWORD *)v33 )
        RegCloseKey(*(HKEY *)v33);
      operator delete((void *)v33, (const struct std::nothrow_t *)0xA8);
    }
    if ( hKey )
      RegCloseKey(hKey);
    std::wstring::~wstring((char **)&v52);
    if ( (_BYTE)v42 )
      std::wstring::~wstring((char **)hKey_8);
    wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::operator++(Src);
  }
  std::wstring::~wstring(v64);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v67);
  result = std::wstring::~wstring(v66);
  if ( *a2 )
    return RegCloseKey(*a2);
  return result;
}

```

## disassembly

```asm
0x180060218  mov     rax, rsp
0x18006021b  push    rbp
0x18006021c  push    rbx
0x18006021d  push    rsi
0x18006021e  push    rdi
0x18006021f  push    r12
0x180060221  push    r13
0x180060223  push    r14
0x180060225  push    r15
0x180060227  lea     rbp, [rax-168h]
0x18006022e  sub     rsp, 228h
0x180060235  movaps  xmmword ptr [rax-58h], xmm6
0x180060239  mov     rax, cs:__security_cookie
0x180060240  xor     rax, rsp
0x180060243  mov     [rbp+160h+var_60], rax
0x18006024a  mov     rsi, rdx
0x18006024d  mov     [rbp+160h+var_1E0], rdx
0x180060251  xor     r13d, r13d
0x180060254  mov     edi, r13d
0x180060257  mov     dword ptr [rsp+260h+var_230], r13d
0x18006025c  mov     ebx, cs:dword_1800B9160
0x180060262  mov     r14, [rbp+168h]
0x180060269  call    cs:__imp_GetCurrentThreadId
0x18006026f  cmp     ebx, eax
0x180060271  jnz     loc_18006072C
0x180060277  lea     rax, ?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; AgentAccountRegistry g_agentAccountRegistry
0x18006027e  cmp     rax, rsi
0x180060281  jz      short loc_1800602B5
0x180060283  mov     r15, [rsi]
0x180060286  mov     r14, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; AgentAccountRegistry g_agentAccountRegistry
0x18006028d  test    r14, r14
0x180060290  jz      short loc_1800602AB
0x180060292  call    cs:__imp_GetLastError
0x180060298  mov     ebx, eax
0x18006029a  mov     rcx, r14; hKey
0x18006029d  call    cs:__imp_RegCloseKey
0x1800602a3  mov     ecx, ebx; dwErrCode
0x1800602a5  call    cs:__imp_SetLastError
0x1800602ab  mov     cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A, r15; AgentAccountRegistry g_agentAccountRegistry
0x1800602b2  mov     [rsi], r13
0x1800602b5  lea     r8, aIsoenvusers202; "IsoEnvUsers_2025_Preview"
0x1800602bc  lea     rdx, stru_1800A3588; HKEY
0x1800602c3  mov     rcx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; this
0x1800602ca  call    ?set_value_string@reg@wil@@YAXPEAUHKEY__@@PEB_W1@Z; wil::reg::set_value_string(HKEY__ *,wchar_t const *,wchar_t const *)
0x1800602cf  mov     rcx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; this
0x1800602d6  call    ?get_child_key_count@reg@wil@@YAIPEAUHKEY__@@@Z; wil::reg::get_child_key_count(HKEY__ *)
0x1800602db  mov     eax, eax
0x1800602dd  xorps   xmm0, xmm0
0x1800602e0  cvtsi2ss xmm0, rax
0x1800602e5  divss   xmm0, cs:dword_1800B9468; X
0x1800602ed  call    _o_ceilf_0
0x1800602f2  xor     eax, eax
0x1800602f4  mov     r14, 8000000000000000h
0x1800602fe  movss   xmm6, cs:__real@5f000000
0x180060306  comiss  xmm0, xmm6
0x180060309  jb      short loc_180060317
0x18006030b  subss   xmm0, xmm6
0x18006030f  comiss  xmm0, xmm6
0x180060312  jnb     short loc_180060317
0x180060314  mov     rax, r14
0x180060317  cvttss2si rbx, xmm0
0x18006031c  add     rbx, rax
0x18006031f  mov     rcx, cs:qword_1800B9478
0x180060326  xorps   xmm0, xmm0
0x180060329  test    rcx, rcx
0x18006032c  js      short loc_180060335
0x18006032e  cvtsi2ss xmm0, rcx
0x180060333  jmp     short loc_18006034A
0x180060335  mov     rax, rcx
0x180060338  shr     rax, 1
0x18006033b  and     ecx, 1
0x18006033e  or      rax, rcx
0x180060341  cvtsi2ss xmm0, rax
0x180060346  addss   xmm0, xmm0
0x18006034a  divss   xmm0, cs:dword_1800B9468; X
0x180060352  call    _o_ceilf_0
0x180060357  xor     ecx, ecx
0x180060359  comiss  xmm0, xmm6
0x18006035c  jb      short loc_18006036A
0x18006035e  subss   xmm0, xmm6
0x180060362  comiss  xmm0, xmm6
0x180060365  jnb     short loc_18006036A
0x180060367  mov     rcx, r14
0x18006036a  cvttss2si rax, xmm0
0x18006036f  add     rax, rcx
0x180060372  cmp     rax, rbx
0x180060375  cmovnb  rbx, rax
0x180060379  cmp     rbx, cs:qword_1800B94A0
0x180060380  jbe     short loc_180060391
0x180060382  mov     rdx, rbx
0x180060385  lea     rcx, dword_1800B9468
0x18006038c  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OwningUserRegistry>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>>,0>>::_Forced_rehash(unsigned __int64)
0x180060391  lea     rax, [rbp+160h+var_168]
0x180060395  mov     [rsp+260h+hKey], rax
0x18006039a  mov     [rbp+160h+var_13C], r13d
0x18006039e  xorps   xmm0, xmm0
0x1800603a1  movups  [rbp+160h+var_168], xmm0
0x1800603a5  mov     [rbp+160h+var_158], r13
0x1800603a9  mov     r14d, 7
0x1800603af  mov     [rbp+160h+var_150], r14
0x1800603b3  mov     word ptr [rbp+160h+var_168], r13w
0x1800603b8  mov     [rbp+160h+var_148], r13
0x1800603bc  or      ebx, 0FFFFFFFFh
0x1800603bf  mov     [rbp+160h+var_140], ebx
0x1800603c2  mov     [rbp+160h+var_138], r13
0x1800603c6  lea     rax, [rsp+260h+hKey+8]
0x1800603cb  mov     [rsp+260h+var_228], rax
0x1800603d0  mov     rcx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; AgentAccountRegistry g_agentAccountRegistry
0x1800603d7  movups  xmmword ptr [rsp+260h+hKey+8], xmm0
0x1800603dc  mov     [rsp+260h+var_208], r13
0x1800603e1  mov     [rsp+260h+var_200], r14
0x1800603e6  mov     word ptr [rsp+260h+hKey+8], r13w
0x1800603ec  mov     [rsp+260h+var_1F8], rcx
0x1800603f1  mov     dword ptr [rsp+260h+var_1F0], ebx
0x1800603f5  mov     [rsp+260h+var_1E8], r13
0x1800603fa  test    rcx, rcx
0x1800603fd  jz      short loc_18006041D
0x1800603ff  mov     dword ptr [rsp+260h+var_1F0], r13d
0x180060404  lea     rcx, [rsp+260h+hKey+8]; Src
0x180060409  call    ?enumerate_current_index@?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<std::wstring>::enumerate_current_index(void)
0x18006040e  mov     rcx, [rbp+168h]; this
0x180060415  test    eax, eax
0x180060417  js      loc_180060741
0x18006041d  lea     r8, [rbp+160h+var_168]
0x180060421  lea     rdx, [rsp+260h+hKey+8]
0x180060426  lea     rcx, [rbp+160h+var_D0]
0x18006042d  call    ??$make_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@@wil@@YA?AV?$pointer_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@@details@0@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@0@0@Z; wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>,wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>)
0x180060432  nop
0x180060433  lea     rdx, [rbp+160h+var_D0]
0x18006043a  lea     rcx, [rbp+160h+Src]
0x18006043e  call    ??0?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>> const &)
0x180060443  nop
0x180060444  lea     rdx, [rbp+160h+var_98]
0x18006044b  lea     rcx, [rbp+160h+var_110]
0x18006044f  call    ??0?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>> const &)
0x180060454  nop
0x180060455  mov     r15d, [rbp+160h+var_E8]
0x180060459  mov     r12, [rbp+160h+var_F0]
0x18006045d  mov     eax, [rbp+160h+var_198]
0x180060460  cmp     eax, ebx
0x180060462  jz      short loc_18006046F
0x180060464  cmp     r15d, ebx
0x180060467  jz      short loc_18006046F
0x180060469  cmp     [rbp+160h+var_1A0], r12
0x18006046d  jnz     short loc_180060478
0x18006046f  cmp     eax, r15d
0x180060472  jz      loc_1800606B4
0x180060478  cmp     eax, ebx
0x18006047a  setz    al
0x18006047d  mov     rcx, [rbp+168h]; this
0x180060484  test    al, al
0x180060486  jnz     loc_18006071A
0x18006048c  lea     r8, [rbp+160h+Src]
0x180060490  cmp     [rbp+160h+var_1A8], r14
0x180060494  cmova   r8, [rbp+160h+Src]
0x180060499  lea     rdx, aPopulatingForE; "Populating for existing key %s"
0x1800604a0  mov     ecx, 4; unsigned __int8
0x1800604a5  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800604aa  lea     r8, [rbp+160h+Src]
0x1800604ae  cmp     [rbp+160h+var_1A8], r14
0x1800604b2  cmova   r8, [rbp+160h+Src]
0x1800604b7  mov     rax, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; AgentAccountRegistry g_agentAccountRegistry
0x1800604be  mov     [rsp+260h+var_230], rax
0x1800604c3  mov     dword ptr [rsp+20h], 10000006h
0x1800604cb  lea     r9, stru_18009E3F8
0x1800604d2  lea     rdx, [rsp+260h+hKey+8]
0x1800604d7  lea     rcx, [rsp+260h+var_230]
0x1800604dc  call    ??$try_get_value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEB_W0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(wchar_t const *,wchar_t const *,ulong)
0x1800604e1  or      edi, 4
0x1800604e4  mov     dword ptr [rsp+260h+var_230], edi
0x1800604e8  cmp     byte ptr [rsp+260h+var_1F8], r13b
0x1800604ed  jz      short loc_180060505
0x1800604ef  lea     rdx, [rsp+260h+hKey+8]
0x1800604f4  lea     rcx, [rbp+160h+var_168]
0x1800604f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800604fd  mov     rcx, rax
0x180060500  or      edi, 1
0x180060503  jmp     short loc_180060531
0x180060505  xorps   xmm0, xmm0
0x180060508  movups  [rbp+160h+var_130], xmm0
0x18006050c  mov     [rbp+160h+var_120], r13
0x180060510  mov     [rbp+160h+var_118], r13
0x180060514  mov     r8d, 9
0x18006051a  lea     rdx, aUnknown; "(unknown)"
0x180060521  lea     rcx, [rbp+160h+var_130]
0x180060525  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006052a  lea     rcx, [rbp+160h+var_130]
0x18006052e  or      edi, 2
0x180060531  xorps   xmm0, xmm0
0x180060534  movups  [rbp+160h+var_188], xmm0
0x180060538  mov     qword ptr [rbp+160h+var_178], r13
0x18006053c  mov     qword ptr [rbp+160h+var_178+8], r13
0x180060540  movups  xmm0, xmmword ptr [rcx]
0x180060543  movups  [rbp+160h+var_188], xmm0
0x180060547  movups  xmm1, xmmword ptr [rcx+10h]
0x18006054b  movups  [rbp+160h+var_178], xmm1
0x18006054f  mov     [rcx+10h], r13
0x180060553  mov     [rcx+18h], r14
0x180060557  mov     [rcx], r13w
0x18006055b  test    dil, 2
0x18006055f  jz      short loc_18006056E
0x180060561  and     edi, 0FFFFFFFDh
0x180060564  lea     rcx, [rbp+160h+var_130]
0x180060568  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006056d  nop
0x18006056e  test    dil, 1
0x180060572  jz      short loc_180060580
0x180060574  and     edi, 0FFFFFFFEh
0x180060577  lea     rcx, [rbp+160h+var_168]
0x18006057b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060580  lea     r9, [rbp+160h+var_188]
0x180060584  cmp     qword ptr [rbp+160h+var_178+8], r14
0x180060588  cmova   r9, qword ptr [rbp+160h+var_188]
0x18006058d  lea     r8, [rbp+160h+Src]
0x180060591  cmp     [rbp+160h+var_1A8], r14
0x180060595  cmova   r8, [rbp+160h+Src]
0x18006059a  lea     rdx, aFoundUsernameF; "Found UserName for %s: %s"
0x1800605a1  mov     ecx, 4; unsigned __int8
0x1800605a6  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800605ab  lea     r8, [rbp+160h+Src]
0x1800605af  cmp     [rbp+160h+var_1A8], r14
0x1800605b3  cmova   r8, [rbp+160h+Src]
0x1800605b8  mov     rdx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; AgentAccountRegistry g_agentAccountRegistry
0x1800605bf  lea     rcx, [rsp+260h+hKey]
0x1800605c4  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x1800605c9  mov     rbx, rax
0x1800605cc  mov     ecx, 0A8h; Size
0x1800605d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800605d6  mov     [rbp+160h+var_1D8], rax
0x1800605da  mov     rcx, [rbx]
0x1800605dd  mov     [rsp+260h+var_228], rcx
0x1800605e2  mov     [rbx], r13
0x1800605e5  lea     r8, [rbp+160h+var_188]
0x1800605e9  lea     rdx, [rsp+260h+var_228]
0x1800605ee  mov     rcx, rax
0x1800605f1  call    ??0OwningUserRegistry@@QEAA@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OwningUserRegistry::OwningUserRegistry(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>,std::wstring const &)
0x1800605f6  mov     rbx, rax
0x1800605f9  mov     [rsp+260h+var_230], rax
0x1800605fe  or      edi, 8
0x180060601  lea     r8, [rbp+160h+Src]
0x180060605  lea     rdx, [rbp+160h+var_1D0]
0x180060609  lea     rcx, dword_1800B9468
0x180060610  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OwningUserRegistry>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180060615  mov     rcx, [rax]
0x180060618  mov     r14, [rcx+30h]
0x18006061c  mov     [rcx+30h], rbx
0x180060620  test    r14, r14
0x180060623  jz      short loc_180060671
0x180060625  lea     rcx, [r14+80h]
0x18006062c  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>(void)
0x180060631  lea     rcx, [r14+70h]
0x180060635  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(void)
0x18006063a  lea     rcx, [r14+40h]
0x18006063e  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>(void)
0x180060643  lea     rcx, [r14+30h]
0x180060647  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(void)
0x18006064c  lea     rcx, [r14+8]
0x180060650  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060655  mov     rcx, [r14]; hKey
0x180060658  test    rcx, rcx
0x18006065b  jz      short loc_180060663
0x18006065d  call    cs:__imp_RegCloseKey
0x180060663  mov     edx, 0A8h; struct std::nothrow_t *
0x180060668  mov     rcx, r14; void *
0x18006066b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060670  nop
0x180060671  mov     rcx, [rsp+260h+hKey]; hKey
0x180060676  test    rcx, rcx
0x180060679  jz      short loc_180060682
0x18006067b  call    cs:__imp_RegCloseKey
0x180060681  nop
0x180060682  lea     rcx, [rbp+160h+var_188]
0x180060686  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006068b  nop
0x18006068c  cmp     byte ptr [rsp+260h+var_1F8], r13b
0x180060691  jz      short loc_18006069D
0x180060693  lea     rcx, [rsp+260h+hKey+8]
0x180060698  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006069d  lea     rcx, [rbp+160h+Src]; Src
0x1800606a1  call    ??E?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAAAEAV012@XZ; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::operator++(void)
0x1800606a6  or      ebx, 0FFFFFFFFh
0x1800606a9  mov     r14d, 7
0x1800606af  jmp     loc_18006045D
0x1800606b4  lea     rcx, [rbp+160h+var_110]
0x1800606b8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800606bd  nop
0x1800606be  lea     rcx, [rbp+160h+Src]
0x1800606c2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800606c7  nop
0x1800606c8  lea     rcx, [rbp+160h+var_98]
0x1800606cf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800606d4  lea     rcx, [rbp+160h+var_D0]
0x1800606db  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800606e0  nop
0x1800606e1  mov     rcx, [rsi]; hKey
0x1800606e4  test    rcx, rcx
0x1800606e7  jz      short loc_1800606EF
0x1800606e9  call    cs:__imp_RegCloseKey
0x1800606ef  mov     rcx, [rbp+160h+var_60]
0x1800606f6  xor     rcx, rsp; StackCookie
  ... truncated ...
```
