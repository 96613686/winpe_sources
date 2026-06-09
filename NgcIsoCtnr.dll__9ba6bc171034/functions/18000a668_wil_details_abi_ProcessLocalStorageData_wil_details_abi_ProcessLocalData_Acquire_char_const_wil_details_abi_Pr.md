# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a668`
- end: `0x18000a7ce`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b77c`

## callees

- `0x180007670`
- `0x18000a1e0`
- `0x18000a1fc`
- `0x18000a668`
- `0x18000b408`
- `0x18000c194`
- `0x18000d62c`
- `0x18000ddc8`
- `0x18000e23c`
- `0x18000eb84`
- `0x18000eeb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a6e5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a6e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a6a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a6a0`

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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18000a668  mov     [rsp-8+arg_10], rbx
0x18000a66d  mov     [rsp-8+arg_18], rdi
0x18000a672  push    rbp
0x18000a673  lea     rbp, [rsp-170h]
0x18000a67b  sub     rsp, 270h
0x18000a682  mov     rax, cs:__security_cookie
0x18000a689  xor     rax, rsp
0x18000a68c  mov     [rbp+170h+var_10], rax
0x18000a693  mov     rdi, rdx
0x18000a696  mov     qword ptr [rdx], 0
0x18000a69d  mov     rbx, rcx
0x18000a6a0  call    cs:__imp_GetCurrentProcessId
0x18000a6a6  mov     [rsp+270h+var_248], rbx
0x18000a6ab  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a6b2  mov     r9d, eax
0x18000a6b5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000a6bd  mov     edx, 104h; unsigned __int64
0x18000a6c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a6c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a6cc  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a6d2  mov     [rsp+270h+var_240], 0
0x18000a6db  xor     r8d, r8d; dwFlags
0x18000a6de  lea     rdx, [rsp+270h+Name]; lpName
0x18000a6e3  xor     ecx, ecx; lpMutexAttributes
0x18000a6e5  call    cs:__imp_CreateMutexExW
0x18000a6eb  mov     rdx, rax
0x18000a6ee  lea     rcx, [rsp+270h+var_240]
0x18000a6f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a6f8  cmp     [rsp+270h+var_240], 0
0x18000a6fe  jnz     short loc_18000A709
0x18000a700  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a705  mov     ebx, eax
0x18000a707  jmp     short loc_18000A77C
0x18000a709  lea     rdx, [rsp+270h+var_238]
0x18000a70e  lea     rcx, [rsp+270h+var_240]
0x18000a713  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a718  lea     rdx, [rsp+270h+var_230]; void **
0x18000a71d  mov     [rsp+270h+var_230], 0
0x18000a726  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a72b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a730  mov     ebx, eax
0x18000a732  test    eax, eax
0x18000a734  jns     short loc_18000A75D
0x18000a736  mov     edx, 12Eh; void *
0x18000a73b  mov     rcx, [rbp+178h]; this
0x18000a742  lea     r8, aWil; "wil"
0x18000a749  mov     r9d, eax; char *
0x18000a74c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a751  lea     rcx, [rsp+270h+var_238]
0x18000a756  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a75b  jmp     short loc_18000A77C
0x18000a75d  mov     rcx, [rsp+270h+var_230]
0x18000a762  test    rcx, rcx
0x18000a765  jz      short loc_18000A7AC
0x18000a767  mov     [rdi], rcx
0x18000a76a  mov     eax, [rcx]
0x18000a76c  inc     eax
0x18000a76e  mov     [rcx], eax
0x18000a770  lea     rcx, [rsp+270h+var_238]
0x18000a775  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a77a  xor     ebx, ebx
0x18000a77c  lea     rcx, [rsp+270h+var_240]
0x18000a781  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a786  mov     eax, ebx
0x18000a788  mov     rcx, [rbp+170h+var_10]
0x18000a78f  xor     rcx, rsp; StackCookie
0x18000a792  call    __security_check_cookie
0x18000a797  lea     r11, [rsp+270h+var_s0]
0x18000a79f  mov     rbx, [r11+20h]
0x18000a7a3  mov     rdi, [r11+28h]
0x18000a7a7  mov     rsp, r11
0x18000a7aa  pop     rbp
0x18000a7ab  retn
0x18000a7ac  mov     r8, rdi
0x18000a7af  lea     rdx, [rsp+270h+var_240]
0x18000a7b4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a7b9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a7be  mov     ebx, eax
0x18000a7c0  test    eax, eax
0x18000a7c2  jns     short loc_18000A770
0x18000a7c4  mov     edx, 137h
0x18000a7c9  jmp     loc_18000A73B
```
