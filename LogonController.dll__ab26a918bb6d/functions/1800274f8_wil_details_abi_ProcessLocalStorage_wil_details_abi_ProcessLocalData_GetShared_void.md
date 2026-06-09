# wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)

- ea: `0x1800274f8`
- end: `0x180027702`
- name: `?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800274a0`

## callees

- `0x180004b70`
- `0x180026f14`
- `0x1800274f8`
- `0x180027850`
- `0x180027c8c`
- `0x18002a8b0`
- `0x18005d488`
- `0x18005d718`
- `0x18005f4c0`
- `0x1800652ec`
- `0x18006c000`
- `0x18006ff90`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180027573`
- `KERNEL32!CreateMutexExW` at `0x180027573`
- `KERNEL32!GetCurrentProcessId` at `0x180027537`
- `KERNEL32!GetCurrentProcessId` at `0x180027537`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800275d1`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800275d1`

## string_xrefs

- `0x1800276b7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared()
{
  __int64 v0; // rsi
  _DWORD *v1; // rdi
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v4; // rcx
  wil::details *v5; // rbx
  DWORD v7; // eax
  bool v8; // dl
  char *v9; // r9
  wil::details *v10; // r14
  int ValueInternal; // eax
  void *v12; // rdx
  unsigned int v13; // edi
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // eax
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  wil::details *v19; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v21; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v22; // [rsp+48h] [rbp-B8h]
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v0 = wil::details_abi::g_pProcessLocalData;
  if ( *(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
  v1 = 0;
  v22 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v17 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v19 = Mutex;
  v5 = Mutex;
  if ( !Mutex )
  {
    if ( (int)wil::details::GetLastErrorFailHr(v4) < 0 )
      return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
    goto LABEL_4;
  }
  v7 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v10 = 0;
  }
  else
  {
    if ( (v7 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    v10 = v5;
  }
  v21 = v10;
  v20 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, (bool *)v9);
  v13 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v13, v18);
    v14 = v13;
    v15 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v15, (unsigned int)"wil", (const char *)v14, v17);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
  }
  v1 = (_DWORD *)(4 * v20);
  if ( 4 * v20 )
  {
    ++*v1;
  }
  else
  {
    v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    if ( v16 < 0 )
    {
      v14 = (unsigned int)v16;
      v15 = 311;
      goto LABEL_11;
    }
    v1 = v22;
    v5 = v19;
  }
  if ( v10 )
    wil::details::ReleaseMutex(v10, v12);
  if ( v5 )
    wil::details::CloseHandle(v5, v12);
LABEL_4:
  if ( !*(_QWORD *)(v0 + 8) )
    *(_QWORD *)(v0 + 8) = v1;
  return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
}

```

## disassembly

```asm
0x1800274f8  push    rbp
0x1800274fa  push    rbx
0x1800274fb  push    rsi
0x1800274fc  push    rdi
0x1800274fd  push    r14
0x1800274ff  lea     rbp, [rsp-170h]
0x180027507  sub     rsp, 270h
0x18002750e  mov     rax, cs:__security_cookie
0x180027515  xor     rax, rsp
0x180027518  mov     [rbp+190h+var_30], rax
0x18002751f  mov     rsi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180027526  cmp     qword ptr [rsi+8], 0
0x18002752b  jnz     short loc_18002759A
0x18002752d  mov     rbx, [rsi]
0x180027530  xor     edi, edi
0x180027532  mov     [rsp+290h+var_248], rdi
0x180027537  call    cs:__imp_GetCurrentProcessId
0x18002753d  mov     [rsp+290h+var_268], rbx
0x180027542  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180027549  mov     r9d, eax
0x18002754c  mov     [rsp+290h+var_270], 78h ; 'x'; int
0x180027554  mov     edx, 104h; unsigned __int64
0x180027559  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18002755e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027563  mov     r9d, 1F0001h; dwDesiredAccess
0x180027569  lea     rdx, [rsp+290h+Name]; lpName
0x18002756e  xor     r8d, r8d; dwFlags
0x180027571  xor     ecx, ecx; lpMutexAttributes
0x180027573  call    cs:__imp_CreateMutexExW
0x180027579  mov     [rsp+290h+var_260], rax
0x18002757e  mov     rbx, rax
0x180027581  test    rax, rax
0x180027584  jnz     short loc_1800275C8
0x180027586  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002758b  test    eax, eax
0x18002758d  js      short loc_18002759A
0x18002758f  cmp     qword ptr [rsi+8], 0
0x180027594  jnz     short loc_18002759A
0x180027596  mov     [rsi+8], rdi
0x18002759a  mov     rax, [rsi+8]
0x18002759e  lea     rcx, [rax+20h]
0x1800275a2  neg     rax
0x1800275a5  sbb     rax, rax
0x1800275a8  and     rax, rcx
0x1800275ab  mov     rcx, [rbp+190h+var_30]
0x1800275b2  xor     rcx, rsp; StackCookie
0x1800275b5  call    __security_check_cookie
0x1800275ba  add     rsp, 270h
0x1800275c1  pop     r14
0x1800275c3  pop     rdi
0x1800275c4  pop     rsi
0x1800275c5  pop     rbx
0x1800275c6  pop     rbp
0x1800275c7  retn
0x1800275c8  xor     r8d, r8d; bAlertable
0x1800275cb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800275ce  mov     rcx, rbx; hHandle
0x1800275d1  call    cs:__imp_WaitForSingleObjectEx
0x1800275d7  cmp     eax, 102h
0x1800275dc  jnz     loc_1800276A9
0x1800275e2  xor     r14d, r14d
0x1800275e5  lea     r8, [rsp+290h+var_258]; unsigned __int64 *
0x1800275ea  mov     [rsp+290h+var_250], r14
0x1800275ef  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x1800275f4  mov     [rsp+290h+var_258], rdi
0x1800275f9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800275fe  mov     edi, eax
0x180027600  test    eax, eax
0x180027602  jns     short loc_18002766E
0x180027604  mov     rcx, [rbp+198h]; this
0x18002760b  lea     r8, aWil; "wil"
0x180027612  mov     r9d, eax; char *
0x180027615  mov     edx, 66h ; 'f'; void *
0x18002761a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002761f  mov     rcx, [rbp+198h]; this
0x180027626  lea     r8, aWil; "wil"
0x18002762d  mov     r9d, edi; char *
0x180027630  mov     edx, 6Fh ; 'o'; void *
0x180027635  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002763a  mov     r9d, edi; char *
0x18002763d  mov     edx, 12Eh; void *
0x180027642  mov     rcx, [rbp+198h]; this
0x180027649  lea     r8, aWil; "wil"
0x180027650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027655  lea     rcx, [rsp+290h+var_250]
0x18002765a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002765f  lea     rcx, [rsp+290h+var_260]
0x180027664  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027669  jmp     loc_18002759A
0x18002766e  mov     rax, [rsp+290h+var_258]
0x180027673  lea     rdi, ds:0[rax*4]
0x18002767b  test    rdi, rdi
0x18002767e  jz      short loc_1800276D1
0x180027680  mov     eax, [rdi]
0x180027682  inc     eax
0x180027684  mov     [rdi], eax
0x180027686  test    r14, r14
0x180027689  jz      short loc_180027693
0x18002768b  mov     rcx, r14; this
0x18002768e  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180027693  test    rbx, rbx
0x180027696  jz      loc_18002758F
0x18002769c  mov     rcx, rbx; this
0x18002769f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800276a4  jmp     loc_18002758F
0x1800276a9  test    eax, 0FFFFFF7Fh
0x1800276ae  jz      short loc_1800276C9
0x1800276b0  mov     rcx, [rbp+198h]; this
0x1800276b7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800276be  mov     edx, 0E01h; void *
0x1800276c3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800276c9  mov     r14, rbx
0x1800276cc  jmp     loc_1800275E5
0x1800276d1  lea     r8, [rsp+290h+var_248]
0x1800276d6  lea     rdx, [rsp+290h+var_260]
0x1800276db  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x1800276e0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800276e5  test    eax, eax
0x1800276e7  jns     short loc_1800276F6
0x1800276e9  mov     r9d, eax
0x1800276ec  mov     edx, 137h
0x1800276f1  jmp     loc_180027642
0x1800276f6  mov     rdi, [rsp+290h+var_248]
0x1800276fb  mov     rbx, [rsp+290h+var_260]
0x180027700  jmp     short loc_180027686
```
