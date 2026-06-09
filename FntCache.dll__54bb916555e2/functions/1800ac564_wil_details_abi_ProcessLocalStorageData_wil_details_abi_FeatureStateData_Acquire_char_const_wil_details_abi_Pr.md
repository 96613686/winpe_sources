# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800ac564`
- end: `0x1800ac6ca`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ac8d4`

## callees

- `0x1800a868c`
- `0x1800aa650`
- `0x1800ac1a4`
- `0x1800ac1c0`
- `0x1800ac564`
- `0x1800adb18`
- `0x1800ae75c`
- `0x1800aed7c`
- `0x1800af1d8`
- `0x1800af8c4`
- `0x1800afa50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ac59c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ac59c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800ac5e1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800ac5e1`

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
0x1800ac564  mov     [rsp-8+arg_10], rbx
0x1800ac569  mov     [rsp-8+arg_18], rdi
0x1800ac56e  push    rbp
0x1800ac56f  lea     rbp, [rsp-170h]
0x1800ac577  sub     rsp, 270h
0x1800ac57e  mov     rax, cs:__security_cookie
0x1800ac585  xor     rax, rsp
0x1800ac588  mov     [rbp+170h+var_10], rax
0x1800ac58f  mov     rdi, rdx
0x1800ac592  mov     qword ptr [rdx], 0
0x1800ac599  mov     rbx, rcx
0x1800ac59c  call    cs:__imp_GetCurrentProcessId
0x1800ac5a2  mov     [rsp+270h+var_248], rbx
0x1800ac5a7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800ac5ae  mov     r9d, eax
0x1800ac5b1  mov     [rsp+270h+var_250], 130h; int
0x1800ac5b9  mov     edx, 104h; unsigned __int64
0x1800ac5be  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800ac5c3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ac5c8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800ac5ce  mov     [rsp+270h+var_240], 0
0x1800ac5d7  xor     r8d, r8d; dwFlags
0x1800ac5da  lea     rdx, [rsp+270h+Name]; lpName
0x1800ac5df  xor     ecx, ecx; lpMutexAttributes
0x1800ac5e1  call    cs:__imp_CreateMutexExW
0x1800ac5e7  mov     rdx, rax
0x1800ac5ea  lea     rcx, [rsp+270h+var_240]
0x1800ac5ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800ac5f4  cmp     [rsp+270h+var_240], 0
0x1800ac5fa  jnz     short loc_1800AC605
0x1800ac5fc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800ac601  mov     ebx, eax
0x1800ac603  jmp     short loc_1800AC678
0x1800ac605  lea     rdx, [rsp+270h+var_238]
0x1800ac60a  lea     rcx, [rsp+270h+var_240]
0x1800ac60f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800ac614  lea     rdx, [rsp+270h+var_230]; void **
0x1800ac619  mov     [rsp+270h+var_230], 0
0x1800ac622  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800ac627  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800ac62c  mov     ebx, eax
0x1800ac62e  test    eax, eax
0x1800ac630  jns     short loc_1800AC659
0x1800ac632  mov     edx, 12Eh; void *
0x1800ac637  mov     rcx, [rbp+178h]; this
0x1800ac63e  lea     r8, aWil; "wil"
0x1800ac645  mov     r9d, eax; char *
0x1800ac648  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac64d  lea     rcx, [rsp+270h+var_238]
0x1800ac652  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ac657  jmp     short loc_1800AC678
0x1800ac659  mov     rcx, [rsp+270h+var_230]
0x1800ac65e  test    rcx, rcx
0x1800ac661  jz      short loc_1800AC6A8
0x1800ac663  mov     [rdi], rcx
0x1800ac666  mov     eax, [rcx]
0x1800ac668  inc     eax
0x1800ac66a  mov     [rcx], eax
0x1800ac66c  lea     rcx, [rsp+270h+var_238]
0x1800ac671  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ac676  xor     ebx, ebx
0x1800ac678  lea     rcx, [rsp+270h+var_240]
0x1800ac67d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ac682  mov     eax, ebx
0x1800ac684  mov     rcx, [rbp+170h+var_10]
0x1800ac68b  xor     rcx, rsp; StackCookie
0x1800ac68e  call    __security_check_cookie
0x1800ac693  lea     r11, [rsp+270h+var_s0]
0x1800ac69b  mov     rbx, [r11+20h]
0x1800ac69f  mov     rdi, [r11+28h]
0x1800ac6a3  mov     rsp, r11
0x1800ac6a6  pop     rbp
0x1800ac6a7  retn
0x1800ac6a8  mov     r8, rdi
0x1800ac6ab  lea     rdx, [rsp+270h+var_240]
0x1800ac6b0  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800ac6b5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800ac6ba  mov     ebx, eax
0x1800ac6bc  test    eax, eax
0x1800ac6be  jns     short loc_1800AC66C
0x1800ac6c0  mov     edx, 137h
0x1800ac6c5  jmp     loc_1800AC637
```
