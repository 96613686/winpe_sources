# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180136c40`
- end: `0x180136d9f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801370a0`

## callees

- `0x18011b44c`
- `0x180128ca4`
- `0x180134b70`
- `0x180136788`
- `0x1801367a4`
- `0x180136c40`
- `0x1801388bc`
- `0x18013984c`
- `0x18013a2d8`
- `0x18013aaf4`
- `0x18013ac74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180136cbd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180136cbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180136c78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180136c78`

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
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180136c40  mov     [rsp-8+arg_10], rbx
0x180136c45  mov     [rsp-8+arg_18], rdi
0x180136c4a  push    rbp
0x180136c4b  lea     rbp, [rsp-170h]
0x180136c53  sub     rsp, 270h
0x180136c5a  mov     rax, cs:__security_cookie
0x180136c61  xor     rax, rsp
0x180136c64  mov     [rbp+170h+var_10], rax
0x180136c6b  mov     rdi, rdx
0x180136c6e  mov     qword ptr [rdx], 0
0x180136c75  mov     rbx, rcx
0x180136c78  call    cs:__imp_GetCurrentProcessId
0x180136c7e  mov     [rsp+270h+var_248], rbx
0x180136c83  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180136c8a  mov     r9d, eax
0x180136c8d  mov     [rsp+270h+var_250], 130h; int
0x180136c95  mov     edx, 104h; unsigned __int64
0x180136c9a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180136c9f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180136ca4  mov     r9d, 1F0001h; dwDesiredAccess
0x180136caa  mov     [rsp+270h+var_240], 0
0x180136cb3  xor     r8d, r8d; dwFlags
0x180136cb6  lea     rdx, [rsp+270h+Name]; lpName
0x180136cbb  xor     ecx, ecx; lpMutexAttributes
0x180136cbd  call    cs:__imp_CreateMutexExW
0x180136cc3  mov     rdx, rax
0x180136cc6  lea     rcx, [rsp+270h+var_240]
0x180136ccb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180136cd0  cmp     [rsp+270h+var_240], 0
0x180136cd6  jnz     short loc_180136CE1
0x180136cd8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180136cdd  mov     ebx, eax
0x180136cdf  jmp     short loc_180136D4D
0x180136ce1  lea     rdx, [rsp+270h+var_238]
0x180136ce6  lea     rcx, [rsp+270h+var_240]
0x180136ceb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180136cf0  lea     rdx, [rsp+270h+var_230]; void **
0x180136cf5  mov     [rsp+270h+var_230], 0
0x180136cfe  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180136d03  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180136d08  mov     ebx, eax
0x180136d0a  test    eax, eax
0x180136d0c  jns     short loc_180136D2E
0x180136d0e  mov     edx, 12Eh; void *
0x180136d13  mov     rcx, [rbp+178h]; this
0x180136d1a  mov     r9d, eax; char *
0x180136d1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180136d22  lea     rcx, [rsp+270h+var_238]
0x180136d27  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180136d2c  jmp     short loc_180136D4D
0x180136d2e  mov     rcx, [rsp+270h+var_230]
0x180136d33  test    rcx, rcx
0x180136d36  jz      short loc_180136D7D
0x180136d38  mov     [rdi], rcx
0x180136d3b  mov     eax, [rcx]
0x180136d3d  inc     eax
0x180136d3f  mov     [rcx], eax
0x180136d41  lea     rcx, [rsp+270h+var_238]
0x180136d46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180136d4b  xor     ebx, ebx
0x180136d4d  lea     rcx, [rsp+270h+var_240]
0x180136d52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180136d57  mov     eax, ebx
0x180136d59  mov     rcx, [rbp+170h+var_10]
0x180136d60  xor     rcx, rsp; StackCookie
0x180136d63  call    __security_check_cookie
0x180136d68  lea     r11, [rsp+270h+var_s0]
0x180136d70  mov     rbx, [r11+20h]
0x180136d74  mov     rdi, [r11+28h]
0x180136d78  mov     rsp, r11
0x180136d7b  pop     rbp
0x180136d7c  retn
0x180136d7d  mov     r8, rdi
0x180136d80  lea     rdx, [rsp+270h+var_240]
0x180136d85  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180136d8a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180136d8f  mov     ebx, eax
0x180136d91  test    eax, eax
0x180136d93  jns     short loc_180136D41
0x180136d95  mov     edx, 137h
0x180136d9a  jmp     loc_180136D13
```
