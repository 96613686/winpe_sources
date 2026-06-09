# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003d34`
- end: `0x140003e9a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140004858`

## callees

- `0x140002310`
- `0x140003cb4`
- `0x140003cd0`
- `0x140003d34`
- `0x1400045b8`
- `0x140004fb8`
- `0x1400053c0`
- `0x140005798`
- `0x140005904`
- `0x140005cf4`
- `0x140005da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003db1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003db1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003d6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003d6c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140003d34  mov     [rsp-8+arg_10], rbx
0x140003d39  mov     [rsp-8+arg_18], rdi
0x140003d3e  push    rbp
0x140003d3f  lea     rbp, [rsp-170h]
0x140003d47  sub     rsp, 270h
0x140003d4e  mov     rax, cs:__security_cookie
0x140003d55  xor     rax, rsp
0x140003d58  mov     [rbp+170h+var_10], rax
0x140003d5f  mov     rdi, rdx
0x140003d62  mov     qword ptr [rdx], 0
0x140003d69  mov     rbx, rcx
0x140003d6c  call    cs:__imp_GetCurrentProcessId
0x140003d72  mov     [rsp+270h+var_248], rbx
0x140003d77  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003d7e  mov     r9d, eax
0x140003d81  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140003d89  mov     edx, 104h; unsigned __int64
0x140003d8e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140003d93  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140003d98  mov     r9d, 1F0001h; dwDesiredAccess
0x140003d9e  mov     [rsp+270h+var_240], 0
0x140003da7  xor     r8d, r8d; dwFlags
0x140003daa  lea     rdx, [rsp+270h+Name]; lpName
0x140003daf  xor     ecx, ecx; lpMutexAttributes
0x140003db1  call    cs:__imp_CreateMutexExW
0x140003db7  mov     rdx, rax
0x140003dba  lea     rcx, [rsp+270h+var_240]
0x140003dbf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140003dc4  cmp     [rsp+270h+var_240], 0
0x140003dca  jnz     short loc_140003DD5
0x140003dcc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003dd1  mov     ebx, eax
0x140003dd3  jmp     short loc_140003E48
0x140003dd5  lea     rdx, [rsp+270h+var_238]
0x140003dda  lea     rcx, [rsp+270h+var_240]
0x140003ddf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140003de4  lea     rdx, [rsp+270h+var_230]; void **
0x140003de9  mov     [rsp+270h+var_230], 0
0x140003df2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140003df7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x140003dfc  mov     ebx, eax
0x140003dfe  test    eax, eax
0x140003e00  jns     short loc_140003E29
0x140003e02  mov     edx, 12Eh; void *
0x140003e07  mov     rcx, [rbp+178h]; this
0x140003e0e  lea     r8, aWil; "wil"
0x140003e15  mov     r9d, eax; char *
0x140003e18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e1d  lea     rcx, [rsp+270h+var_238]
0x140003e22  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003e27  jmp     short loc_140003E48
0x140003e29  mov     rcx, [rsp+270h+var_230]
0x140003e2e  test    rcx, rcx
0x140003e31  jz      short loc_140003E78
0x140003e33  mov     [rdi], rcx
0x140003e36  mov     eax, [rcx]
0x140003e38  inc     eax
0x140003e3a  mov     [rcx], eax
0x140003e3c  lea     rcx, [rsp+270h+var_238]
0x140003e41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003e46  xor     ebx, ebx
0x140003e48  lea     rcx, [rsp+270h+var_240]
0x140003e4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003e52  mov     eax, ebx
0x140003e54  mov     rcx, [rbp+170h+var_10]
0x140003e5b  xor     rcx, rsp; StackCookie
0x140003e5e  call    __security_check_cookie
0x140003e63  lea     r11, [rsp+270h+var_s0]
0x140003e6b  mov     rbx, [r11+20h]
0x140003e6f  mov     rdi, [r11+28h]
0x140003e73  mov     rsp, r11
0x140003e76  pop     rbp
0x140003e77  retn
0x140003e78  mov     r8, rdi
0x140003e7b  lea     rdx, [rsp+270h+var_240]
0x140003e80  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140003e85  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140003e8a  mov     ebx, eax
0x140003e8c  test    eax, eax
0x140003e8e  jns     short loc_140003E3C
0x140003e90  mov     edx, 137h
0x140003e95  jmp     loc_140003E07
```
