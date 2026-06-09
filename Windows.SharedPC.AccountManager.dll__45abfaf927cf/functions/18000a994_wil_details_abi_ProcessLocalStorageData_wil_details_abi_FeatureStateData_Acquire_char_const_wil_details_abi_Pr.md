# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a994`
- end: `0x18000aafa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000afb4`

## callees

- `0x180003530`
- `0x1800057ac`
- `0x180007248`
- `0x180007264`
- `0x180007dd8`
- `0x180008a38`
- `0x180008ed0`
- `0x180009564`
- `0x180009664`
- `0x18000a994`
- `0x18000b2bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a9cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a9cc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000aa11`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000aa11`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000a994  mov     [rsp-8+arg_10], rbx
0x18000a999  mov     [rsp-8+arg_18], rdi
0x18000a99e  push    rbp
0x18000a99f  lea     rbp, [rsp-170h]
0x18000a9a7  sub     rsp, 270h
0x18000a9ae  mov     rax, cs:__security_cookie
0x18000a9b5  xor     rax, rsp
0x18000a9b8  mov     [rbp+170h+var_10], rax
0x18000a9bf  mov     rdi, rdx
0x18000a9c2  mov     qword ptr [rdx], 0
0x18000a9c9  mov     rbx, rcx
0x18000a9cc  call    cs:__imp_GetCurrentProcessId
0x18000a9d2  mov     [rsp+270h+var_248], rbx
0x18000a9d7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a9de  mov     r9d, eax
0x18000a9e1  mov     [rsp+270h+var_250], 130h; int
0x18000a9e9  mov     edx, 104h; unsigned __int64
0x18000a9ee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a9f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a9f8  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a9fe  mov     [rsp+270h+var_240], 0
0x18000aa07  xor     r8d, r8d; dwFlags
0x18000aa0a  lea     rdx, [rsp+270h+Name]; lpName
0x18000aa0f  xor     ecx, ecx; lpMutexAttributes
0x18000aa11  call    cs:__imp_CreateMutexExW
0x18000aa17  mov     rdx, rax
0x18000aa1a  lea     rcx, [rsp+270h+var_240]
0x18000aa1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000aa24  cmp     [rsp+270h+var_240], 0
0x18000aa2a  jnz     short loc_18000AA35
0x18000aa2c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000aa31  mov     ebx, eax
0x18000aa33  jmp     short loc_18000AAA8
0x18000aa35  lea     rdx, [rsp+270h+var_238]
0x18000aa3a  lea     rcx, [rsp+270h+var_240]
0x18000aa3f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000aa44  lea     rdx, [rsp+270h+var_230]; void **
0x18000aa49  mov     [rsp+270h+var_230], 0
0x18000aa52  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000aa57  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000aa5c  mov     ebx, eax
0x18000aa5e  test    eax, eax
0x18000aa60  jns     short loc_18000AA89
0x18000aa62  mov     edx, 12Eh; void *
0x18000aa67  mov     rcx, [rbp+178h]; this
0x18000aa6e  lea     r8, aWil; "wil"
0x18000aa75  mov     r9d, eax; char *
0x18000aa78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa7d  lea     rcx, [rsp+270h+var_238]
0x18000aa82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000aa87  jmp     short loc_18000AAA8
0x18000aa89  mov     rcx, [rsp+270h+var_230]
0x18000aa8e  test    rcx, rcx
0x18000aa91  jz      short loc_18000AAD8
0x18000aa93  mov     [rdi], rcx
0x18000aa96  mov     eax, [rcx]
0x18000aa98  inc     eax
0x18000aa9a  mov     [rcx], eax
0x18000aa9c  lea     rcx, [rsp+270h+var_238]
0x18000aaa1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000aaa6  xor     ebx, ebx
0x18000aaa8  lea     rcx, [rsp+270h+var_240]
0x18000aaad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000aab2  mov     eax, ebx
0x18000aab4  mov     rcx, [rbp+170h+var_10]
0x18000aabb  xor     rcx, rsp; StackCookie
0x18000aabe  call    __security_check_cookie
0x18000aac3  lea     r11, [rsp+270h+var_s0]
0x18000aacb  mov     rbx, [r11+20h]
0x18000aacf  mov     rdi, [r11+28h]
0x18000aad3  mov     rsp, r11
0x18000aad6  pop     rbp
0x18000aad7  retn
0x18000aad8  mov     r8, rdi
0x18000aadb  lea     rdx, [rsp+270h+var_240]
0x18000aae0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000aae5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000aaea  mov     ebx, eax
0x18000aaec  test    eax, eax
0x18000aaee  jns     short loc_18000AA9C
0x18000aaf0  mov     edx, 137h
0x18000aaf5  jmp     loc_18000AA67
```
