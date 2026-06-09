# CDeploymentSession::RequestContainsFiles(IDeploymentDownloadRequest *,std::set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WstringCaseInsensitiveCompare,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &)

- ea: `0x180089fd4`
- end: `0x18008a2e4`
- name: `?RequestContainsFiles@CDeploymentSession@@QEAA_NPEAUIDeploymentDownloadRequest@@AEBV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180095f2c`

## callees

- `0x1800059d0`
- `0x18001efc8`
- `0x18003c418`
- `0x180077664`
- `0x180089fd4`
- `0x180094d0c`
- `0x18009f0b0`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a14f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a1f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a14f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a1f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a164`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a206`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a164`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a206`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008a0d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008a0d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a0b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a0c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a223`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a0c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a223`

## string_xrefs

- `0x18008a266`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18008a27b`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18008a293`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18008a2a8`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18008a2bd`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18008a2d2`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall CDeploymentSession::RequestContainsFiles(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v5; // rax
  int v6; // eax
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, LPVOID *); // r15
  void *v13; // rsi
  DWORD LastError; // ebx
  int v15; // eax
  int v16; // eax
  char v17; // al
  __int64 v18; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v21; // rax
  __int64 v22; // [rsp+20h] [rbp-40h] BYREF
  __int64 v23[2]; // [rsp+28h] [rbp-38h] BYREF
  unsigned int v24; // [rsp+38h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  __int64 v26; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v27; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v23[1] = -2;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20F8,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)0x80004003LL,
      v22);
  v24 = 0;
  v5 = *a2;
  v27 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD **))(v5 + 40))(a2, &v27);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20FB,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v6,
      v22);
  v7 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *))(*v27 + 24LL))(v27, &v24);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20FC,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v7,
      v22);
  v8 = 0;
  if ( v24 )
  {
    while ( 1 )
    {
      v26 = 0;
      pv = 0;
      v22 = 0;
      v9 = *v27;
      v26 = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *))(v9 + 32))(v27, v8, &v26);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2103,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v10,
          v22);
      v11 = v26;
      v12 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v26 + 40LL);
      v13 = pv;
      if ( pv )
      {
        LastError = GetLastError();
        CoTaskMemFree(v13);
        SetLastError(LastError);
      }
      pv = 0;
      v15 = v12(v11, &pv);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2104,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v15,
          v22);
      _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v22);
      v16 = CMiscHelpersT<CEmptyType>::CombinePath(*(_QWORD *)(a1 + 488), (__int64)pv, 0);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2106,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v16,
          v22);
      v23[0] = v22;
      v17 = std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::contains<wchar_t *>(
              a3,
              v23);
      v18 = v22;
      if ( v17 )
        break;
      if ( v22 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v18 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      if ( pv )
        CoTaskMemFree(pv);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( ++v8 >= v24 )
        goto LABEL_18;
    }
    if ( v22 )
    {
      v21 = GetProcessHeap();
      HeapFree(v21, 0, (LPVOID)(v18 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v27 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v27 + 16LL))(v27, *v27);
    return 1;
  }
  else
  {
LABEL_18:
    if ( v27 )
      (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
    return 0;
  }
}

```

## disassembly

```asm
0x180089fd4  mov     rax, rsp
0x180089fd7  push    rbp
0x180089fd8  push    rsi
0x180089fd9  push    rdi
0x180089fda  push    r12
0x180089fdc  push    r13
0x180089fde  push    r14
0x180089fe0  push    r15
0x180089fe2  mov     rbp, rsp
0x180089fe5  sub     rsp, 60h
0x180089fe9  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x180089ff1  mov     [rax+20h], rbx
0x180089ff5  mov     rax, cs:__security_cookie
0x180089ffc  xor     rax, rsp
0x180089fff  mov     [rbp+var_8], rax
0x18008a003  mov     r12, r8
0x18008a006  mov     r9, rdx
0x18008a009  mov     r13, rcx
0x18008a00c  mov     rcx, [rbp+38h]; this
0x18008a010  xor     esi, esi
0x18008a012  test    rdx, rdx
0x18008a015  jz      loc_18008A28D
0x18008a01b  mov     [rbp+var_28], esi
0x18008a01e  mov     rax, [rdx]
0x18008a021  mov     [rbp+var_10], rsi
0x18008a025  lea     rdx, [rbp+var_10]
0x18008a029  mov     rcx, r9
0x18008a02c  mov     rax, [rax+28h]
0x18008a030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a035  mov     rcx, [rbp+38h]; this
0x18008a039  test    eax, eax
0x18008a03b  js      loc_18008A2A5
0x18008a041  mov     rcx, [rbp+var_10]
0x18008a045  mov     rax, [rcx]
0x18008a048  lea     rdx, [rbp+var_28]
0x18008a04c  mov     rax, [rax+18h]
0x18008a050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a055  mov     rcx, [rbp+38h]; this
0x18008a059  test    eax, eax
0x18008a05b  js      loc_18008A2BA
0x18008a061  mov     edi, esi
0x18008a063  cmp     [rbp+var_28], esi
0x18008a066  jbe     loc_18008A1AF
0x18008a06c  mov     [rbp+var_18], rsi
0x18008a070  mov     [rbp+pv], rsi
0x18008a074  mov     [rbp+var_40], rsi
0x18008a078  mov     rcx, [rbp+var_10]
0x18008a07c  mov     rax, [rcx]
0x18008a07f  mov     [rbp+var_18], rsi
0x18008a083  lea     r8, [rbp+var_18]
0x18008a087  mov     edx, edi
0x18008a089  mov     rax, [rax+20h]
0x18008a08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a092  mov     rcx, [rbp+38h]; this
0x18008a096  test    eax, eax
0x18008a098  js      loc_18008A278
0x18008a09e  mov     r14, [rbp+var_18]
0x18008a0a2  mov     rax, [r14]
0x18008a0a5  mov     r15, [rax+28h]
0x18008a0a9  mov     rsi, [rbp+pv]
0x18008a0ad  test    rsi, rsi
0x18008a0b0  jz      short loc_18008A0DD
0x18008a0b2  call    cs:__imp_GetLastError
0x18008a0b9  nop     dword ptr [rax+rax+00h]
0x18008a0be  mov     ebx, eax
0x18008a0c0  mov     rcx, rsi; pv
0x18008a0c3  call    cs:__imp_CoTaskMemFree
0x18008a0ca  nop     dword ptr [rax+rax+00h]
0x18008a0cf  mov     ecx, ebx; dwErrCode
0x18008a0d1  call    cs:__imp_SetLastError
0x18008a0d8  nop     dword ptr [rax+rax+00h]
0x18008a0dd  xor     esi, esi
0x18008a0df  mov     [rbp+pv], rsi
0x18008a0e3  lea     rdx, [rbp+pv]
0x18008a0e7  mov     rcx, r14
0x18008a0ea  mov     rax, r15
0x18008a0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a0f2  mov     rcx, [rbp+38h]; this
0x18008a0f6  test    eax, eax
0x18008a0f8  js      loc_18008A263
0x18008a0fe  lea     rcx, [rbp+var_40]
0x18008a102  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x18008a107  mov     r9, rax
0x18008a10a  xor     r8d, r8d
0x18008a10d  mov     rdx, [rbp+pv]
0x18008a111  mov     rcx, [r13+1E8h]
0x18008a118  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18008a11d  mov     rcx, [rbp+38h]; this
0x18008a121  test    eax, eax
0x18008a123  js      loc_18008A2CF
0x18008a129  mov     rax, [rbp+var_40]
0x18008a12d  mov     [rbp+var_38], rax
0x18008a131  lea     rdx, [rbp+var_38]
0x18008a135  mov     rcx, r12
0x18008a138  call    ??$contains@PEA_W@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEBA_NAEBQEA_W@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::contains<wchar_t *>(wchar_t * const &)
0x18008a13d  nop
0x18008a13e  mov     rbx, [rbp+var_40]
0x18008a142  test    al, al
0x18008a144  jnz     loc_18008A1EC
0x18008a14a  test    rbx, rbx
0x18008a14d  jz      short loc_18008A178
0x18008a14f  call    cs:__imp_GetProcessHeap
0x18008a156  nop     dword ptr [rax+rax+00h]
0x18008a15b  mov     rcx, rax; hHeap
0x18008a15e  lea     r8, [rbx-4]; lpMem
0x18008a162  xor     edx, edx; dwFlags
0x18008a164  call    cs:__imp_HeapFree
0x18008a16b  nop     dword ptr [rax+rax+00h]
0x18008a170  xor     ecx, ecx
0x18008a172  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18008a177  nop
0x18008a178  mov     rcx, [rbp+pv]; pv
0x18008a17c  test    rcx, rcx
0x18008a17f  jz      short loc_18008A18E
0x18008a181  call    cs:__imp_CoTaskMemFree
0x18008a188  nop     dword ptr [rax+rax+00h]
0x18008a18d  nop
0x18008a18e  mov     rcx, [rbp+var_18]
0x18008a192  test    rcx, rcx
0x18008a195  jz      short loc_18008A1A4
0x18008a197  mov     rax, [rcx]
0x18008a19a  mov     rax, [rax+10h]
0x18008a19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a1a3  nop
0x18008a1a4  inc     edi
0x18008a1a6  cmp     edi, [rbp+var_28]
0x18008a1a9  jb      loc_18008A06C
0x18008a1af  mov     rcx, [rbp+var_10]
0x18008a1b3  test    rcx, rcx
0x18008a1b6  jz      short loc_18008A1C5
0x18008a1b8  mov     rax, [rcx]
0x18008a1bb  mov     rax, [rax+10h]
0x18008a1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a1c4  nop
0x18008a1c5  xor     al, al
0x18008a1c7  mov     rcx, [rbp+var_8]
0x18008a1cb  xor     rcx, rsp; StackCookie
0x18008a1ce  call    __security_check_cookie
0x18008a1d3  mov     rbx, [rsp+60h+arg_18]
0x18008a1db  add     rsp, 60h
0x18008a1df  pop     r15
0x18008a1e1  pop     r14
0x18008a1e3  pop     r13
0x18008a1e5  pop     r12
0x18008a1e7  pop     rdi
0x18008a1e8  pop     rsi
0x18008a1e9  pop     rbp
0x18008a1ea  retn
0x18008a1ec  test    rbx, rbx
0x18008a1ef  jz      short loc_18008A21A
0x18008a1f1  call    cs:__imp_GetProcessHeap
0x18008a1f8  nop     dword ptr [rax+rax+00h]
0x18008a1fd  mov     rcx, rax; hHeap
0x18008a200  lea     r8, [rbx-4]; lpMem
0x18008a204  xor     edx, edx; dwFlags
0x18008a206  call    cs:__imp_HeapFree
0x18008a20d  nop     dword ptr [rax+rax+00h]
0x18008a212  xor     ecx, ecx
0x18008a214  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18008a219  nop
0x18008a21a  mov     rcx, [rbp+pv]; pv
0x18008a21e  test    rcx, rcx
0x18008a221  jz      short loc_18008A230
0x18008a223  call    cs:__imp_CoTaskMemFree
0x18008a22a  nop     dword ptr [rax+rax+00h]
0x18008a22f  nop
0x18008a230  mov     rcx, [rbp+var_18]
0x18008a234  test    rcx, rcx
0x18008a237  jz      short loc_18008A246
0x18008a239  mov     rax, [rcx]
0x18008a23c  mov     rax, [rax+10h]
0x18008a240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a245  nop
0x18008a246  mov     rcx, [rbp+var_10]
0x18008a24a  test    rcx, rcx
0x18008a24d  jz      short loc_18008A25C
0x18008a24f  mov     rdx, [rcx]
0x18008a252  mov     rax, [rdx+10h]
0x18008a256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a25b  nop
0x18008a25c  mov     al, 1
0x18008a25e  jmp     loc_18008A1C7
0x18008a263  mov     r9d, eax; char *
0x18008a266  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18008a26d  mov     edx, 2104h; void *
0x18008a272  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a278  mov     r9d, eax; char *
0x18008a27b  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18008a282  mov     edx, 2103h; void *
0x18008a287  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a28d  mov     r9d, 80004003h; char *
0x18008a293  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18008a29a  mov     edx, 20F8h; void *
0x18008a29f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a2a5  mov     r9d, eax; char *
0x18008a2a8  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18008a2af  mov     edx, 20FBh; void *
0x18008a2b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a2ba  mov     r9d, eax; char *
0x18008a2bd  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18008a2c4  mov     edx, 20FCh; void *
0x18008a2c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a2cf  mov     r9d, eax; char *
0x18008a2d2  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18008a2d9  mov     edx, 2106h; void *
0x18008a2de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
