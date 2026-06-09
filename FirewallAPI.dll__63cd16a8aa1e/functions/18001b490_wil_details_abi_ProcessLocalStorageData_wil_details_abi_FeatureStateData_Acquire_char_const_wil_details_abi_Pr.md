# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001b490`
- end: `0x18001b668`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003c594`

## callees

- `0x18001b490`
- `0x18001b670`
- `0x18001b68c`
- `0x18001b6b8`
- `0x180023228`
- `0x1800232a0`
- `0x1800232d4`
- `0x1800234c8`
- `0x180023540`
- `0x18002355c`
- `0x1800277b0`
- `0x18003b29c`
- `0x18003cc3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b542`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b542`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001b510`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001b510`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b4cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b4cb`

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
0x18001b490  mov     [rsp-8+arg_10], rbx
0x18001b495  mov     [rsp-8+arg_18], rsi
0x18001b49a  push    rbp
0x18001b49b  push    rdi
0x18001b49c  push    r14
0x18001b49e  lea     rbp, [rsp-170h]
0x18001b4a6  sub     rsp, 270h
0x18001b4ad  mov     rax, cs:__security_cookie
0x18001b4b4  xor     rax, rsp
0x18001b4b7  mov     [rbp+180h+var_20], rax
0x18001b4be  mov     r14, rdx
0x18001b4c1  mov     qword ptr [rdx], 0
0x18001b4c8  mov     rbx, rcx
0x18001b4cb  call    cs:__imp_GetCurrentProcessId
0x18001b4d1  mov     [rsp+280h+var_258], rbx
0x18001b4d6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001b4dd  mov     r9d, eax
0x18001b4e0  mov     [rsp+280h+var_260], 130h; int
0x18001b4e8  mov     edx, 104h; cchDest
0x18001b4ed  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18001b4f2  call    StringCchPrintfW
0x18001b4f7  mov     r9d, 1F0001h; dwDesiredAccess
0x18001b4fd  mov     [rsp+280h+hHandle], 0
0x18001b506  xor     r8d, r8d; dwFlags
0x18001b509  lea     rdx, [rsp+280h+pszDest]; lpName
0x18001b50e  xor     ecx, ecx; lpMutexAttributes
0x18001b510  call    cs:__imp_CreateMutexExW
0x18001b516  mov     rdx, rax
0x18001b519  lea     rcx, [rsp+280h+hHandle]
0x18001b51e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001b523  mov     rbx, [rsp+280h+hHandle]
0x18001b528  test    rbx, rbx
0x18001b52b  jnz     short loc_18001B539
0x18001b52d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001b532  mov     esi, eax
0x18001b534  jmp     loc_18001B612
0x18001b539  xor     r8d, r8d; bAlertable
0x18001b53c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b53f  mov     rcx, rbx; hHandle
0x18001b542  call    cs:__imp_WaitForSingleObjectEx
0x18001b548  cmp     eax, 102h
0x18001b54d  jz      short loc_18001B568
0x18001b54f  test    eax, 0FFFFFF7Fh
0x18001b554  jz      short loc_18001B563
0x18001b556  mov     rcx, [rbp+188h]; this
0x18001b55d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001b563  mov     rdi, rbx
0x18001b566  jmp     short loc_18001B56A
0x18001b568  xor     edi, edi
0x18001b56a  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18001b56f  mov     [rsp+280h+var_240], rdi
0x18001b574  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18001b579  mov     [rsp+280h+var_248], 0
0x18001b582  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001b587  mov     esi, eax
0x18001b589  test    eax, eax
0x18001b58b  jns     short loc_18001B5BF
0x18001b58d  mov     rcx, [rbp+188h]; this
0x18001b594  mov     r9d, eax; char *
0x18001b597  mov     edx, 66h ; 'f'; void *
0x18001b59c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b5a1  mov     rcx, [rbp+188h]; this
0x18001b5a8  mov     r9d, esi; char *
0x18001b5ab  mov     edx, 6Fh ; 'o'; void *
0x18001b5b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b5b5  mov     r9d, esi
0x18001b5b8  mov     edx, 12Eh
0x18001b5bd  jmp     short loc_18001B5FC
0x18001b5bf  mov     rax, [rsp+280h+var_248]
0x18001b5c4  lea     rcx, ds:0[rax*4]
0x18001b5cc  test    rcx, rcx
0x18001b5cf  jz      short loc_18001B5DC
0x18001b5d1  mov     [r14], rcx
0x18001b5d4  mov     eax, [rcx]
0x18001b5d6  inc     eax
0x18001b5d8  mov     [rcx], eax
0x18001b5da  jmp     short loc_18001B625
0x18001b5dc  mov     r8, r14
0x18001b5df  lea     rdx, [rsp+280h+hHandle]
0x18001b5e4  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18001b5e9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001b5ee  mov     esi, eax
0x18001b5f0  test    eax, eax
0x18001b5f2  jns     short loc_18001B620
0x18001b5f4  mov     r9d, eax; char *
0x18001b5f7  mov     edx, 137h; void *
0x18001b5fc  mov     rcx, [rbp+188h]; this
0x18001b603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b608  lea     rcx, [rsp+280h+var_240]
0x18001b60d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b612  lea     rcx, [rsp+280h+hHandle]
0x18001b617  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b61c  mov     eax, esi
0x18001b61e  jmp     short loc_18001B641
0x18001b620  mov     rbx, [rsp+280h+hHandle]
0x18001b625  test    rdi, rdi
0x18001b628  jz      short loc_18001B632
0x18001b62a  mov     rcx, rdi; this
0x18001b62d  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001b632  test    rbx, rbx
0x18001b635  jz      short loc_18001B63F
0x18001b637  mov     rcx, rbx; this
0x18001b63a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001b63f  xor     eax, eax
0x18001b641  mov     rcx, [rbp+180h+var_20]
0x18001b648  xor     rcx, rsp; StackCookie
0x18001b64b  call    __security_check_cookie
0x18001b650  lea     r11, [rsp+280h+var_10]
0x18001b658  mov     rbx, [r11+30h]
0x18001b65c  mov     rsi, [r11+38h]
0x18001b660  mov     rsp, r11
0x18001b663  pop     r14
0x18001b665  pop     rdi
0x18001b666  pop     rbp
0x18001b667  retn
```
