# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18004b200`
- end: `0x18004b3d8`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004b1a8`

## callees

- `0x180040aa4`
- `0x180044440`
- `0x180045440`
- `0x180046300`
- `0x18004663c`
- `0x18004b200`
- `0x18004b3e0`
- `0x18004b410`
- `0x18004b42c`
- `0x1800580a8`
- `0x180066238`
- `0x18006fd5c`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004b280`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004b280`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004b2b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004b2b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004b23b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004b23b`

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
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v23 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
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
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v26, (bool *)v11);
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
    v21 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x18004b200  mov     [rsp-8+arg_10], rbx
0x18004b205  mov     [rsp-8+arg_18], rsi
0x18004b20a  push    rbp
0x18004b20b  push    rdi
0x18004b20c  push    r14
0x18004b20e  lea     rbp, [rsp-170h]
0x18004b216  sub     rsp, 270h
0x18004b21d  mov     rax, cs:__security_cookie
0x18004b224  xor     rax, rsp
0x18004b227  mov     [rbp+180h+var_20], rax
0x18004b22e  mov     r14, rdx
0x18004b231  mov     qword ptr [rdx], 0
0x18004b238  mov     rbx, rcx
0x18004b23b  call    cs:__imp_GetCurrentProcessId
0x18004b241  mov     [rsp+280h+var_258], rbx
0x18004b246  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004b24d  mov     r9d, eax
0x18004b250  mov     [rsp+280h+var_260], 130h; int
0x18004b258  mov     edx, 104h; unsigned __int64
0x18004b25d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18004b262  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18004b267  mov     r9d, 1F0001h; dwDesiredAccess
0x18004b26d  mov     [rsp+280h+hHandle], 0
0x18004b276  xor     r8d, r8d; dwFlags
0x18004b279  lea     rdx, [rsp+280h+Name]; lpName
0x18004b27e  xor     ecx, ecx; lpMutexAttributes
0x18004b280  call    cs:__imp_CreateMutexExW
0x18004b286  mov     rdx, rax
0x18004b289  lea     rcx, [rsp+280h+hHandle]
0x18004b28e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004b293  mov     rbx, [rsp+280h+hHandle]
0x18004b298  test    rbx, rbx
0x18004b29b  jnz     short loc_18004B2A9
0x18004b29d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004b2a2  mov     esi, eax
0x18004b2a4  jmp     loc_18004B382
0x18004b2a9  xor     r8d, r8d; bAlertable
0x18004b2ac  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004b2af  mov     rcx, rbx; hHandle
0x18004b2b2  call    cs:__imp_WaitForSingleObjectEx
0x18004b2b8  cmp     eax, 102h
0x18004b2bd  jz      short loc_18004B2D8
0x18004b2bf  test    eax, 0FFFFFF7Fh
0x18004b2c4  jz      short loc_18004B2D3
0x18004b2c6  mov     rcx, [rbp+188h]; this
0x18004b2cd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18004b2d3  mov     rdi, rbx
0x18004b2d6  jmp     short loc_18004B2DA
0x18004b2d8  xor     edi, edi
0x18004b2da  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18004b2df  mov     [rsp+280h+var_240], rdi
0x18004b2e4  lea     rcx, [rsp+280h+Name]; pszSrc
0x18004b2e9  mov     [rsp+280h+var_248], 0
0x18004b2f2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18004b2f7  mov     esi, eax
0x18004b2f9  test    eax, eax
0x18004b2fb  jns     short loc_18004B32F
0x18004b2fd  mov     rcx, [rbp+188h]; this
0x18004b304  mov     r9d, eax; char *
0x18004b307  mov     edx, 66h ; 'f'; void *
0x18004b30c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b311  mov     rcx, [rbp+188h]; this
0x18004b318  mov     r9d, esi; char *
0x18004b31b  mov     edx, 6Fh ; 'o'; void *
0x18004b320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b325  mov     r9d, esi
0x18004b328  mov     edx, 12Eh
0x18004b32d  jmp     short loc_18004B36C
0x18004b32f  mov     rax, [rsp+280h+var_248]
0x18004b334  lea     rcx, ds:0[rax*4]
0x18004b33c  test    rcx, rcx
0x18004b33f  jz      short loc_18004B34C
0x18004b341  mov     [r14], rcx
0x18004b344  mov     eax, [rcx]
0x18004b346  inc     eax
0x18004b348  mov     [rcx], eax
0x18004b34a  jmp     short loc_18004B395
0x18004b34c  mov     r8, r14
0x18004b34f  lea     rdx, [rsp+280h+hHandle]
0x18004b354  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18004b359  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004b35e  mov     esi, eax
0x18004b360  test    eax, eax
0x18004b362  jns     short loc_18004B390
0x18004b364  mov     r9d, eax; char *
0x18004b367  mov     edx, 137h; void *
0x18004b36c  mov     rcx, [rbp+188h]; this
0x18004b373  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b378  lea     rcx, [rsp+280h+var_240]
0x18004b37d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004b382  lea     rcx, [rsp+280h+hHandle]
0x18004b387  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004b38c  mov     eax, esi
0x18004b38e  jmp     short loc_18004B3B1
0x18004b390  mov     rbx, [rsp+280h+hHandle]
0x18004b395  test    rdi, rdi
0x18004b398  jz      short loc_18004B3A2
0x18004b39a  mov     rcx, rdi; this
0x18004b39d  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18004b3a2  test    rbx, rbx
0x18004b3a5  jz      short loc_18004B3AF
0x18004b3a7  mov     rcx, rbx; this
0x18004b3aa  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18004b3af  xor     eax, eax
0x18004b3b1  mov     rcx, [rbp+180h+var_20]
0x18004b3b8  xor     rcx, rsp; StackCookie
0x18004b3bb  call    __security_check_cookie
0x18004b3c0  lea     r11, [rsp+280h+var_10]
0x18004b3c8  mov     rbx, [r11+30h]
0x18004b3cc  mov     rsi, [r11+38h]
0x18004b3d0  mov     rsp, r11
0x18004b3d3  pop     r14
0x18004b3d5  pop     rdi
0x18004b3d6  pop     rbp
0x18004b3d7  retn
```
