# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180029de4`
- end: `0x180029f43`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002ad94`

## callees

- `0x180023d68`
- `0x1800249f0`
- `0x180029be8`
- `0x180029c04`
- `0x180029de4`
- `0x18002b5e0`
- `0x18002c3ac`
- `0x18002c8c8`
- `0x18002ccc0`
- `0x18002d4a4`
- `0x18002d5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029e61`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029e61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029e1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029e1c`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180029de4  mov     [rsp-8+arg_10], rbx
0x180029de9  mov     [rsp-8+arg_18], rdi
0x180029dee  push    rbp
0x180029def  lea     rbp, [rsp-170h]
0x180029df7  sub     rsp, 270h
0x180029dfe  mov     rax, cs:__security_cookie
0x180029e05  xor     rax, rsp
0x180029e08  mov     [rbp+170h+var_10], rax
0x180029e0f  mov     rdi, rdx
0x180029e12  mov     qword ptr [rdx], 0
0x180029e19  mov     rbx, rcx
0x180029e1c  call    cs:__imp_GetCurrentProcessId
0x180029e22  mov     [rsp+270h+var_248], rbx
0x180029e27  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180029e2e  mov     r9d, eax
0x180029e31  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180029e39  mov     edx, 104h; unsigned __int64
0x180029e3e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029e43  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180029e48  mov     r9d, 1F0001h; dwDesiredAccess
0x180029e4e  mov     [rsp+270h+var_240], 0
0x180029e57  xor     r8d, r8d; dwFlags
0x180029e5a  lea     rdx, [rsp+270h+Name]; lpName
0x180029e5f  xor     ecx, ecx; lpMutexAttributes
0x180029e61  call    cs:__imp_CreateMutexExW
0x180029e67  mov     rdx, rax
0x180029e6a  lea     rcx, [rsp+270h+var_240]
0x180029e6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180029e74  cmp     [rsp+270h+var_240], 0
0x180029e7a  jnz     short loc_180029E85
0x180029e7c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180029e81  mov     ebx, eax
0x180029e83  jmp     short loc_180029EF1
0x180029e85  lea     rdx, [rsp+270h+var_238]
0x180029e8a  lea     rcx, [rsp+270h+var_240]
0x180029e8f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180029e94  lea     rdx, [rsp+270h+var_230]; void **
0x180029e99  mov     [rsp+270h+var_230], 0
0x180029ea2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029ea7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180029eac  mov     ebx, eax
0x180029eae  test    eax, eax
0x180029eb0  jns     short loc_180029ED2
0x180029eb2  mov     edx, 12Eh; void *
0x180029eb7  mov     rcx, [rbp+178h]; this
0x180029ebe  mov     r9d, eax; char *
0x180029ec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029ec6  lea     rcx, [rsp+270h+var_238]
0x180029ecb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029ed0  jmp     short loc_180029EF1
0x180029ed2  mov     rcx, [rsp+270h+var_230]
0x180029ed7  test    rcx, rcx
0x180029eda  jz      short loc_180029F21
0x180029edc  mov     [rdi], rcx
0x180029edf  mov     eax, [rcx]
0x180029ee1  inc     eax
0x180029ee3  mov     [rcx], eax
0x180029ee5  lea     rcx, [rsp+270h+var_238]
0x180029eea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029eef  xor     ebx, ebx
0x180029ef1  lea     rcx, [rsp+270h+var_240]
0x180029ef6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029efb  mov     eax, ebx
0x180029efd  mov     rcx, [rbp+170h+var_10]
0x180029f04  xor     rcx, rsp; StackCookie
0x180029f07  call    __security_check_cookie
0x180029f0c  lea     r11, [rsp+270h+var_s0]
0x180029f14  mov     rbx, [r11+20h]
0x180029f18  mov     rdi, [r11+28h]
0x180029f1c  mov     rsp, r11
0x180029f1f  pop     rbp
0x180029f20  retn
0x180029f21  mov     r8, rdi
0x180029f24  lea     rdx, [rsp+270h+var_240]
0x180029f29  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029f2e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180029f33  mov     ebx, eax
0x180029f35  test    eax, eax
0x180029f37  jns     short loc_180029EE5
0x180029f39  mov     edx, 137h
0x180029f3e  jmp     loc_180029EB7
```
