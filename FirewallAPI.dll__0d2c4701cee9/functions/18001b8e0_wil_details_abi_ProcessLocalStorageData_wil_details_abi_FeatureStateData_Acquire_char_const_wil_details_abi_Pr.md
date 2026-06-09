# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001b8e0`
- end: `0x18001bacb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003f408`

## callees

- `0x18001b8e0`
- `0x18001bad4`
- `0x18001baf4`
- `0x18001bb24`
- `0x180024cb0`
- `0x180024d2c`
- `0x180024d60`
- `0x180024f5c`
- `0x180024fe0`
- `0x180025000`
- `0x1800294b0`
- `0x18003dfd8`
- `0x18003fac4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b99e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b99e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001b966`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001b966`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b91b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b91b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  unsigned int LastErrorFailHr; // esi
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  _DWORD *v20; // rcx
  int v21; // eax
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v27; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v23 = 304;
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = (wil::details *)hHandle;
  if ( !hHandle )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_15:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v27 = v12;
  v26 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(pszDest, (bool)v9, &v26, (bool *)v11);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v15, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)LastErrorFailHr, v24);
    v18 = LastErrorFailHr;
    v19 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v19, v17, (const char *)v18, v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
    goto LABEL_15;
  }
  v20 = (_DWORD *)(4 * v26);
  if ( 4 * v26 )
  {
    *a2 = v20;
    ++*v20;
  }
  else
  {
    v21 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(pszDest);
    LastErrorFailHr = v21;
    if ( v21 < 0 )
    {
      v18 = (unsigned int)v21;
      v19 = 311;
      goto LABEL_14;
    }
    v6 = (wil::details *)hHandle;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x18001b8e0  mov     [rsp-8+arg_10], rbx
0x18001b8e5  mov     [rsp-8+arg_18], rsi
0x18001b8ea  push    rbp
0x18001b8eb  push    rdi
0x18001b8ec  push    r14
0x18001b8ee  lea     rbp, [rsp-170h]
0x18001b8f6  sub     rsp, 270h
0x18001b8fd  mov     rax, cs:__security_cookie
0x18001b904  xor     rax, rsp
0x18001b907  mov     [rbp+180h+var_20], rax
0x18001b90e  mov     r14, rdx
0x18001b911  mov     qword ptr [rdx], 0
0x18001b918  mov     rbx, rcx
0x18001b91b  call    cs:__imp_GetCurrentProcessId
0x18001b922  nop     dword ptr [rax+rax+00h]
0x18001b927  mov     [rsp+280h+var_258], rbx
0x18001b92c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001b933  mov     r9d, eax
0x18001b936  mov     [rsp+280h+var_260], 130h; int
0x18001b93e  mov     edx, 104h; cchDest
0x18001b943  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18001b948  call    StringCchPrintfW
0x18001b94d  mov     r9d, 1F0001h; dwDesiredAccess
0x18001b953  mov     [rsp+280h+hHandle], 0
0x18001b95c  xor     r8d, r8d; dwFlags
0x18001b95f  lea     rdx, [rsp+280h+pszDest]; lpName
0x18001b964  xor     ecx, ecx; lpMutexAttributes
0x18001b966  call    cs:__imp_CreateMutexExW
0x18001b96d  nop     dword ptr [rax+rax+00h]
0x18001b972  mov     rdx, rax
0x18001b975  lea     rcx, [rsp+280h+hHandle]
0x18001b97a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001b97f  mov     rbx, [rsp+280h+hHandle]
0x18001b984  test    rbx, rbx
0x18001b987  jnz     short loc_18001B995
0x18001b989  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001b98e  mov     esi, eax
0x18001b990  jmp     loc_18001BA74
0x18001b995  xor     r8d, r8d; bAlertable
0x18001b998  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b99b  mov     rcx, rbx; hHandle
0x18001b99e  call    cs:__imp_WaitForSingleObjectEx
0x18001b9a5  nop     dword ptr [rax+rax+00h]
0x18001b9aa  cmp     eax, 102h
0x18001b9af  jz      short loc_18001B9CA
0x18001b9b1  test    eax, 0FFFFFF7Fh
0x18001b9b6  jz      short loc_18001B9C5
0x18001b9b8  mov     rcx, [rbp+188h]; this
0x18001b9bf  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001b9c5  mov     rdi, rbx
0x18001b9c8  jmp     short loc_18001B9CC
0x18001b9ca  xor     edi, edi
0x18001b9cc  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18001b9d1  mov     [rsp+280h+var_240], rdi
0x18001b9d6  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18001b9db  mov     [rsp+280h+var_248], 0
0x18001b9e4  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001b9e9  mov     esi, eax
0x18001b9eb  test    eax, eax
0x18001b9ed  jns     short loc_18001BA21
0x18001b9ef  mov     rcx, [rbp+188h]; this
0x18001b9f6  mov     r9d, eax; char *
0x18001b9f9  mov     edx, 66h ; 'f'; void *
0x18001b9fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba03  mov     rcx, [rbp+188h]; this
0x18001ba0a  mov     r9d, esi; char *
0x18001ba0d  mov     edx, 6Fh ; 'o'; void *
0x18001ba12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba17  mov     r9d, esi
0x18001ba1a  mov     edx, 12Eh
0x18001ba1f  jmp     short loc_18001BA5E
0x18001ba21  mov     rax, [rsp+280h+var_248]
0x18001ba26  lea     rcx, ds:0[rax*4]
0x18001ba2e  test    rcx, rcx
0x18001ba31  jz      short loc_18001BA3E
0x18001ba33  mov     [r14], rcx
0x18001ba36  mov     eax, [rcx]
0x18001ba38  inc     eax
0x18001ba3a  mov     [rcx], eax
0x18001ba3c  jmp     short loc_18001BA87
0x18001ba3e  mov     r8, r14
0x18001ba41  lea     rdx, [rsp+280h+hHandle]
0x18001ba46  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18001ba4b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001ba50  mov     esi, eax
0x18001ba52  test    eax, eax
0x18001ba54  jns     short loc_18001BA82
0x18001ba56  mov     r9d, eax; char *
0x18001ba59  mov     edx, 137h; void *
0x18001ba5e  mov     rcx, [rbp+188h]; this
0x18001ba65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba6a  lea     rcx, [rsp+280h+var_240]
0x18001ba6f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ba74  lea     rcx, [rsp+280h+hHandle]
0x18001ba79  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ba7e  mov     eax, esi
0x18001ba80  jmp     short loc_18001BAA3
0x18001ba82  mov     rbx, [rsp+280h+hHandle]
0x18001ba87  test    rdi, rdi
0x18001ba8a  jz      short loc_18001BA94
0x18001ba8c  mov     rcx, rdi; this
0x18001ba8f  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001ba94  test    rbx, rbx
0x18001ba97  jz      short loc_18001BAA1
0x18001ba99  mov     rcx, rbx; this
0x18001ba9c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001baa1  xor     eax, eax
0x18001baa3  mov     rcx, [rbp+180h+var_20]
0x18001baaa  xor     rcx, rsp; StackCookie
0x18001baad  call    __security_check_cookie
0x18001bab2  lea     r11, [rsp+280h+var_10]
0x18001baba  mov     rbx, [r11+30h]
0x18001babe  mov     rsi, [r11+38h]
0x18001bac2  mov     rsp, r11
0x18001bac5  pop     r14
0x18001bac7  pop     rdi
0x18001bac8  pop     rbp
0x18001bac9  retn
```
