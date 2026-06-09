# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004e5c`
- end: `0x180004fcf`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006250`

## callees

- `0x18000473c`
- `0x18000475c`
- `0x180004e5c`
- `0x180006080`
- `0x18000703c`
- `0x1800087ec`
- `0x180008f60`
- `0x180009368`
- `0x180009e24`
- `0x18000a614`
- `0x180028860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004edf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004edf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e94`

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
0x180004e5c  mov     [rsp-8+arg_10], rbx
0x180004e61  mov     [rsp-8+arg_18], rdi
0x180004e66  push    rbp
0x180004e67  lea     rbp, [rsp-170h]
0x180004e6f  sub     rsp, 270h
0x180004e76  mov     rax, cs:__security_cookie
0x180004e7d  xor     rax, rsp
0x180004e80  mov     [rbp+170h+var_10], rax
0x180004e87  mov     rdi, rdx
0x180004e8a  mov     qword ptr [rdx], 0
0x180004e91  mov     rbx, rcx
0x180004e94  call    cs:__imp_GetCurrentProcessId
0x180004e9b  nop     dword ptr [rax+rax+00h]
0x180004ea0  mov     [rsp+270h+var_248], rbx
0x180004ea5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004eac  mov     r9d, eax
0x180004eaf  mov     [rsp+270h+var_250], 130h; int
0x180004eb7  mov     edx, 104h; unsigned __int64
0x180004ebc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004ec1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004ec6  mov     r9d, 1F0001h; dwDesiredAccess
0x180004ecc  mov     [rsp+270h+var_240], 0
0x180004ed5  xor     r8d, r8d; dwFlags
0x180004ed8  lea     rdx, [rsp+270h+Name]; lpName
0x180004edd  xor     ecx, ecx; lpMutexAttributes
0x180004edf  call    cs:__imp_CreateMutexExW
0x180004ee6  nop     dword ptr [rax+rax+00h]
0x180004eeb  mov     rdx, rax
0x180004eee  lea     rcx, [rsp+270h+var_240]
0x180004ef3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004ef8  cmp     [rsp+270h+var_240], 0
0x180004efe  jnz     short loc_180004F09
0x180004f00  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004f05  mov     ebx, eax
0x180004f07  jmp     short loc_180004F7C
0x180004f09  lea     rdx, [rsp+270h+var_238]
0x180004f0e  lea     rcx, [rsp+270h+var_240]
0x180004f13  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004f18  lea     rdx, [rsp+270h+var_230]; void **
0x180004f1d  mov     [rsp+270h+var_230], 0
0x180004f26  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004f2b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004f30  mov     ebx, eax
0x180004f32  test    eax, eax
0x180004f34  jns     short loc_180004F5D
0x180004f36  mov     edx, 12Eh; void *
0x180004f3b  mov     rcx, [rbp+178h]; this
0x180004f42  lea     r8, aWil; "wil"
0x180004f49  mov     r9d, eax; char *
0x180004f4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f51  lea     rcx, [rsp+270h+var_238]
0x180004f56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f5b  jmp     short loc_180004F7C
0x180004f5d  mov     rcx, [rsp+270h+var_230]
0x180004f62  test    rcx, rcx
0x180004f65  jz      short loc_180004FAD
0x180004f67  mov     [rdi], rcx
0x180004f6a  mov     eax, [rcx]
0x180004f6c  inc     eax
0x180004f6e  mov     [rcx], eax
0x180004f70  lea     rcx, [rsp+270h+var_238]
0x180004f75  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f7a  xor     ebx, ebx
0x180004f7c  lea     rcx, [rsp+270h+var_240]
0x180004f81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f86  mov     eax, ebx
0x180004f88  mov     rcx, [rbp+170h+var_10]
0x180004f8f  xor     rcx, rsp; StackCookie
0x180004f92  call    __security_check_cookie
0x180004f97  lea     r11, [rsp+270h+var_s0]
0x180004f9f  mov     rbx, [r11+20h]
0x180004fa3  mov     rdi, [r11+28h]
0x180004fa7  mov     rsp, r11
0x180004faa  pop     rbp
0x180004fab  retn
0x180004fad  mov     r8, rdi
0x180004fb0  lea     rdx, [rsp+270h+var_240]
0x180004fb5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004fba  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004fbf  mov     ebx, eax
0x180004fc1  test    eax, eax
0x180004fc3  jns     short loc_180004F70
0x180004fc5  mov     edx, 137h
0x180004fca  jmp     loc_180004F3B
```
