# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000bab0`
- end: `0x18000bc16`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000cbc4`

## callees

- `0x180009190`
- `0x18000b5ac`
- `0x18000b5c8`
- `0x18000bab0`
- `0x18000c8a8`
- `0x18000d600`
- `0x18000eacc`
- `0x18000f208`
- `0x18000f74c`
- `0x180010094`
- `0x1800103c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bb2d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bb2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bae8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bae8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  HANDLE v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
      &v12);
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
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x18000bab0  mov     [rsp-8+arg_10], rbx
0x18000bab5  mov     [rsp-8+arg_18], rdi
0x18000baba  push    rbp
0x18000babb  lea     rbp, [rsp-170h]
0x18000bac3  sub     rsp, 270h
0x18000baca  mov     rax, cs:__security_cookie
0x18000bad1  xor     rax, rsp
0x18000bad4  mov     [rbp+170h+var_10], rax
0x18000badb  mov     rdi, rdx
0x18000bade  mov     qword ptr [rdx], 0
0x18000bae5  mov     rbx, rcx
0x18000bae8  call    cs:__imp_GetCurrentProcessId
0x18000baee  mov     [rsp+270h+var_248], rbx
0x18000baf3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000bafa  mov     r9d, eax
0x18000bafd  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000bb05  mov     edx, 104h; unsigned __int64
0x18000bb0a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000bb0f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bb14  mov     r9d, 1F0001h; dwDesiredAccess
0x18000bb1a  mov     [rsp+270h+var_240], 0
0x18000bb23  xor     r8d, r8d; dwFlags
0x18000bb26  lea     rdx, [rsp+270h+Name]; lpName
0x18000bb2b  xor     ecx, ecx; lpMutexAttributes
0x18000bb2d  call    cs:__imp_CreateMutexExW
0x18000bb33  mov     rdx, rax
0x18000bb36  lea     rcx, [rsp+270h+var_240]
0x18000bb3b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000bb40  cmp     [rsp+270h+var_240], 0
0x18000bb46  jnz     short loc_18000BB51
0x18000bb48  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bb4d  mov     ebx, eax
0x18000bb4f  jmp     short loc_18000BBC4
0x18000bb51  lea     rdx, [rsp+270h+var_238]
0x18000bb56  lea     rcx, [rsp+270h+var_240]
0x18000bb5b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000bb60  lea     rdx, [rsp+270h+var_230]; void **
0x18000bb65  mov     [rsp+270h+var_230], 0
0x18000bb6e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000bb73  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000bb78  mov     ebx, eax
0x18000bb7a  test    eax, eax
0x18000bb7c  jns     short loc_18000BBA5
0x18000bb7e  mov     edx, 12Eh; void *
0x18000bb83  mov     rcx, [rbp+178h]; this
0x18000bb8a  lea     r8, aWil; "wil"
0x18000bb91  mov     r9d, eax; char *
0x18000bb94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb99  lea     rcx, [rsp+270h+var_238]
0x18000bb9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bba3  jmp     short loc_18000BBC4
0x18000bba5  mov     rcx, [rsp+270h+var_230]
0x18000bbaa  test    rcx, rcx
0x18000bbad  jz      short loc_18000BBF4
0x18000bbaf  mov     [rdi], rcx
0x18000bbb2  mov     eax, [rcx]
0x18000bbb4  inc     eax
0x18000bbb6  mov     [rcx], eax
0x18000bbb8  lea     rcx, [rsp+270h+var_238]
0x18000bbbd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bbc2  xor     ebx, ebx
0x18000bbc4  lea     rcx, [rsp+270h+var_240]
0x18000bbc9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bbce  mov     eax, ebx
0x18000bbd0  mov     rcx, [rbp+170h+var_10]
0x18000bbd7  xor     rcx, rsp; StackCookie
0x18000bbda  call    __security_check_cookie
0x18000bbdf  lea     r11, [rsp+270h+var_s0]
0x18000bbe7  mov     rbx, [r11+20h]
0x18000bbeb  mov     rdi, [r11+28h]
0x18000bbef  mov     rsp, r11
0x18000bbf2  pop     rbp
0x18000bbf3  retn
0x18000bbf4  mov     r8, rdi
0x18000bbf7  lea     rdx, [rsp+270h+var_240]
0x18000bbfc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000bc01  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000bc06  mov     ebx, eax
0x18000bc08  test    eax, eax
0x18000bc0a  jns     short loc_18000BBB8
0x18000bc0c  mov     edx, 137h
0x18000bc11  jmp     loc_18000BB83
```
