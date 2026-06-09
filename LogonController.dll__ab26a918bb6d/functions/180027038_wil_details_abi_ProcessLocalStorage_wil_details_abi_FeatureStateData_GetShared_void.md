# wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)

- ea: `0x180027038`
- end: `0x180027258`
- name: `?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180063c40`

## callees

- `0x180004b70`
- `0x180026f14`
- `0x180027038`
- `0x180027850`
- `0x180027c8c`
- `0x18002a8b0`
- `0x18005d488`
- `0x18005d718`
- `0x18005f4c0`
- `0x1800652ec`
- `0x18006c000`
- `0x18007dbd4`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800270b6`
- `KERNEL32!CreateMutexExW` at `0x1800270b6`
- `KERNEL32!GetCurrentProcessId` at `0x18002707a`
- `KERNEL32!GetCurrentProcessId` at `0x18002707a`
- `KERNEL32!WaitForSingleObjectEx` at `0x18002711e`
- `KERNEL32!WaitForSingleObjectEx` at `0x18002711e`

## string_xrefs

- `0x180027204`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(__int64 a1)
{
  _DWORD *v2; // rdi
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // r14
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // edi
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  wil::details *v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v22; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v23; // [rsp+48h] [rbp-B8h]
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  if ( *(_QWORD *)(a1 + 8) )
    return (*(_QWORD *)(a1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(a1 + 8) != 0);
  v2 = 0;
  v23 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v20 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    if ( (int)wil::details::GetLastErrorFailHr(v5) < 0 )
      return (*(_QWORD *)(a1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(a1 + 8) != 0);
    goto LABEL_4;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v22 = v11;
  v21 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v21, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v19);
    v15 = v14;
    v16 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v16, (unsigned int)"wil", (const char *)v15, v18);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    return (*(_QWORD *)(a1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(a1 + 8) != 0);
  }
  v2 = (_DWORD *)(4 * v21);
  if ( 4 * v21 )
  {
    ++*v2;
  }
  else
  {
    v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    if ( v17 < 0 )
    {
      v15 = (unsigned int)v17;
      v16 = 311;
      goto LABEL_11;
    }
    v2 = v23;
    v6 = v20;
  }
  if ( v11 )
    wil::details::ReleaseMutex(v11, v13);
  if ( v6 )
    wil::details::CloseHandle(v6, v13);
LABEL_4:
  if ( !*(_QWORD *)(a1 + 8) )
    *(_QWORD *)(a1 + 8) = v2;
  return (*(_QWORD *)(a1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(a1 + 8) != 0);
}

```

## disassembly

```asm
0x180027038  mov     [rsp-8+arg_8], rbx
0x18002703d  mov     [rsp-8+arg_10], rsi
0x180027042  push    rbp
0x180027043  push    rdi
0x180027044  push    r14
0x180027046  lea     rbp, [rsp-170h]
0x18002704e  sub     rsp, 270h
0x180027055  mov     rax, cs:__security_cookie
0x18002705c  xor     rax, rsp
0x18002705f  mov     [rbp+180h+var_20], rax
0x180027066  cmp     qword ptr [rcx+8], 0
0x18002706b  mov     rsi, rcx
0x18002706e  jnz     short loc_1800270DD
0x180027070  mov     rbx, [rcx]
0x180027073  xor     edi, edi
0x180027075  mov     [rsp+280h+var_238], rdi
0x18002707a  call    cs:__imp_GetCurrentProcessId
0x180027080  mov     [rsp+280h+var_258], rbx
0x180027085  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002708c  mov     r9d, eax
0x18002708f  mov     [rsp+280h+var_260], 130h; int
0x180027097  mov     edx, 104h; unsigned __int64
0x18002709c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800270a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800270a6  mov     r9d, 1F0001h; dwDesiredAccess
0x1800270ac  lea     rdx, [rsp+280h+Name]; lpName
0x1800270b1  xor     r8d, r8d; dwFlags
0x1800270b4  xor     ecx, ecx; lpMutexAttributes
0x1800270b6  call    cs:__imp_CreateMutexExW
0x1800270bc  mov     [rsp+280h+var_250], rax
0x1800270c1  mov     rbx, rax
0x1800270c4  test    rax, rax
0x1800270c7  jnz     short loc_180027115
0x1800270c9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800270ce  test    eax, eax
0x1800270d0  js      short loc_1800270DD
0x1800270d2  cmp     qword ptr [rsi+8], 0
0x1800270d7  jz      loc_18002724F
0x1800270dd  mov     rax, [rsi+8]
0x1800270e1  lea     rcx, [rax+20h]
0x1800270e5  neg     rax
0x1800270e8  sbb     rax, rax
0x1800270eb  and     rax, rcx
0x1800270ee  mov     rcx, [rbp+180h+var_20]
0x1800270f5  xor     rcx, rsp; StackCookie
0x1800270f8  call    __security_check_cookie
0x1800270fd  lea     r11, [rsp+280h+var_10]
0x180027105  mov     rbx, [r11+28h]
0x180027109  mov     rsi, [r11+30h]
0x18002710d  mov     rsp, r11
0x180027110  pop     r14
0x180027112  pop     rdi
0x180027113  pop     rbp
0x180027114  retn
0x180027115  xor     r8d, r8d; bAlertable
0x180027118  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002711b  mov     rcx, rbx; hHandle
0x18002711e  call    cs:__imp_WaitForSingleObjectEx
0x180027124  cmp     eax, 102h
0x180027129  jnz     loc_1800271F6
0x18002712f  xor     r14d, r14d
0x180027132  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180027137  mov     [rsp+280h+var_240], r14
0x18002713c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180027141  mov     [rsp+280h+var_248], rdi
0x180027146  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18002714b  mov     edi, eax
0x18002714d  test    eax, eax
0x18002714f  jns     short loc_1800271BB
0x180027151  mov     rcx, [rbp+188h]; this
0x180027158  lea     r8, aWil; "wil"
0x18002715f  mov     r9d, eax; char *
0x180027162  mov     edx, 66h ; 'f'; void *
0x180027167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002716c  mov     rcx, [rbp+188h]; this
0x180027173  lea     r8, aWil; "wil"
0x18002717a  mov     r9d, edi; char *
0x18002717d  mov     edx, 6Fh ; 'o'; void *
0x180027182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027187  mov     r9d, edi; char *
0x18002718a  mov     edx, 12Eh; void *
0x18002718f  mov     rcx, [rbp+188h]; this
0x180027196  lea     r8, aWil; "wil"
0x18002719d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800271a2  lea     rcx, [rsp+280h+var_240]
0x1800271a7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800271ac  lea     rcx, [rsp+280h+var_250]
0x1800271b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800271b6  jmp     loc_1800270DD
0x1800271bb  mov     rax, [rsp+280h+var_248]
0x1800271c0  lea     rdi, ds:0[rax*4]
0x1800271c8  test    rdi, rdi
0x1800271cb  jz      short loc_18002721E
0x1800271cd  mov     eax, [rdi]
0x1800271cf  inc     eax
0x1800271d1  mov     [rdi], eax
0x1800271d3  test    r14, r14
0x1800271d6  jz      short loc_1800271E0
0x1800271d8  mov     rcx, r14; this
0x1800271db  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800271e0  test    rbx, rbx
0x1800271e3  jz      loc_1800270D2
0x1800271e9  mov     rcx, rbx; this
0x1800271ec  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800271f1  jmp     loc_1800270D2
0x1800271f6  test    eax, 0FFFFFF7Fh
0x1800271fb  jz      short loc_180027216
0x1800271fd  mov     rcx, [rbp+188h]; this
0x180027204  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002720b  mov     edx, 0E01h; void *
0x180027210  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180027216  mov     r14, rbx
0x180027219  jmp     loc_180027132
0x18002721e  lea     r8, [rsp+280h+var_238]
0x180027223  lea     rdx, [rsp+280h+var_250]
0x180027228  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002722d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180027232  test    eax, eax
0x180027234  jns     short loc_180027243
0x180027236  mov     r9d, eax
0x180027239  mov     edx, 137h
0x18002723e  jmp     loc_18002718F
0x180027243  mov     rdi, [rsp+280h+var_238]
0x180027248  mov     rbx, [rsp+280h+var_250]
0x18002724d  jmp     short loc_1800271D3
0x18002724f  mov     [rsi+8], rdi
0x180027253  jmp     loc_1800270DD
```
