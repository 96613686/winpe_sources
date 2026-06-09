# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140006ccc`
- end: `0x140006e32`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140007660`

## callees

- `0x1400023e0`
- `0x140003da4`
- `0x140003dc0`
- `0x1400046a8`
- `0x1400054b0`
- `0x140005844`
- `0x140005a04`
- `0x140005df4`
- `0x140005ea0`
- `0x140006ccc`
- `0x140007d68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006d49`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006d04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006d04`

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
0x140006ccc  mov     [rsp-8+arg_10], rbx
0x140006cd1  mov     [rsp-8+arg_18], rdi
0x140006cd6  push    rbp
0x140006cd7  lea     rbp, [rsp-170h]
0x140006cdf  sub     rsp, 270h
0x140006ce6  mov     rax, cs:__security_cookie
0x140006ced  xor     rax, rsp
0x140006cf0  mov     [rbp+170h+var_10], rax
0x140006cf7  mov     rdi, rdx
0x140006cfa  mov     qword ptr [rdx], 0
0x140006d01  mov     rbx, rcx
0x140006d04  call    cs:__imp_GetCurrentProcessId
0x140006d0a  mov     [rsp+270h+var_248], rbx
0x140006d0f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140006d16  mov     r9d, eax
0x140006d19  mov     [rsp+270h+var_250], 130h; int
0x140006d21  mov     edx, 104h; unsigned __int64
0x140006d26  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140006d2b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140006d30  mov     r9d, 1F0001h; dwDesiredAccess
0x140006d36  mov     [rsp+270h+var_240], 0
0x140006d3f  xor     r8d, r8d; dwFlags
0x140006d42  lea     rdx, [rsp+270h+Name]; lpName
0x140006d47  xor     ecx, ecx; lpMutexAttributes
0x140006d49  call    cs:__imp_CreateMutexExW
0x140006d4f  mov     rdx, rax
0x140006d52  lea     rcx, [rsp+270h+var_240]
0x140006d57  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140006d5c  cmp     [rsp+270h+var_240], 0
0x140006d62  jnz     short loc_140006D6D
0x140006d64  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006d69  mov     ebx, eax
0x140006d6b  jmp     short loc_140006DE0
0x140006d6d  lea     rdx, [rsp+270h+var_238]
0x140006d72  lea     rcx, [rsp+270h+var_240]
0x140006d77  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140006d7c  lea     rdx, [rsp+270h+var_230]; void **
0x140006d81  mov     [rsp+270h+var_230], 0
0x140006d8a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140006d8f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x140006d94  mov     ebx, eax
0x140006d96  test    eax, eax
0x140006d98  jns     short loc_140006DC1
0x140006d9a  mov     edx, 12Eh; void *
0x140006d9f  mov     rcx, [rbp+178h]; this
0x140006da6  lea     r8, aWil; "wil"
0x140006dad  mov     r9d, eax; char *
0x140006db0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006db5  lea     rcx, [rsp+270h+var_238]
0x140006dba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006dbf  jmp     short loc_140006DE0
0x140006dc1  mov     rcx, [rsp+270h+var_230]
0x140006dc6  test    rcx, rcx
0x140006dc9  jz      short loc_140006E10
0x140006dcb  mov     [rdi], rcx
0x140006dce  mov     eax, [rcx]
0x140006dd0  inc     eax
0x140006dd2  mov     [rcx], eax
0x140006dd4  lea     rcx, [rsp+270h+var_238]
0x140006dd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006dde  xor     ebx, ebx
0x140006de0  lea     rcx, [rsp+270h+var_240]
0x140006de5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006dea  mov     eax, ebx
0x140006dec  mov     rcx, [rbp+170h+var_10]
0x140006df3  xor     rcx, rsp; StackCookie
0x140006df6  call    __security_check_cookie
0x140006dfb  lea     r11, [rsp+270h+var_s0]
0x140006e03  mov     rbx, [r11+20h]
0x140006e07  mov     rdi, [r11+28h]
0x140006e0b  mov     rsp, r11
0x140006e0e  pop     rbp
0x140006e0f  retn
0x140006e10  mov     r8, rdi
0x140006e13  lea     rdx, [rsp+270h+var_240]
0x140006e18  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140006e1d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140006e22  mov     ebx, eax
0x140006e24  test    eax, eax
0x140006e26  jns     short loc_140006DD4
0x140006e28  mov     edx, 137h
0x140006e2d  jmp     loc_140006D9F
```
