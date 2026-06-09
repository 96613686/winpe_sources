# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000c510`
- end: `0x18000c676`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d714`

## callees

- `0x18000bd24`
- `0x18000bd40`
- `0x18000c510`
- `0x18000fb98`
- `0x180014738`
- `0x1800166cc`
- `0x180016f24`
- `0x1800174c0`
- `0x180018810`
- `0x180018f64`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c58d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c58d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c548`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c548`

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
0x18000c510  mov     [rsp-8+arg_10], rbx
0x18000c515  mov     [rsp-8+arg_18], rdi
0x18000c51a  push    rbp
0x18000c51b  lea     rbp, [rsp-170h]
0x18000c523  sub     rsp, 270h
0x18000c52a  mov     rax, cs:__security_cookie
0x18000c531  xor     rax, rsp
0x18000c534  mov     [rbp+170h+var_10], rax
0x18000c53b  mov     rdi, rdx
0x18000c53e  mov     qword ptr [rdx], 0
0x18000c545  mov     rbx, rcx
0x18000c548  call    cs:__imp_GetCurrentProcessId
0x18000c54e  mov     [rsp+270h+var_248], rbx
0x18000c553  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c55a  mov     r9d, eax
0x18000c55d  mov     [rsp+270h+var_250], 130h; int
0x18000c565  mov     edx, 104h; unsigned __int64
0x18000c56a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c56f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c574  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c57a  mov     [rsp+270h+var_240], 0
0x18000c583  xor     r8d, r8d; dwFlags
0x18000c586  lea     rdx, [rsp+270h+Name]; lpName
0x18000c58b  xor     ecx, ecx; lpMutexAttributes
0x18000c58d  call    cs:__imp_CreateMutexExW
0x18000c593  mov     rdx, rax
0x18000c596  lea     rcx, [rsp+270h+var_240]
0x18000c59b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c5a0  cmp     [rsp+270h+var_240], 0
0x18000c5a6  jnz     short loc_18000C5B1
0x18000c5a8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c5ad  mov     ebx, eax
0x18000c5af  jmp     short loc_18000C624
0x18000c5b1  lea     rdx, [rsp+270h+var_238]
0x18000c5b6  lea     rcx, [rsp+270h+var_240]
0x18000c5bb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000c5c0  lea     rdx, [rsp+270h+var_230]; void **
0x18000c5c5  mov     [rsp+270h+var_230], 0
0x18000c5ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c5d3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000c5d8  mov     ebx, eax
0x18000c5da  test    eax, eax
0x18000c5dc  jns     short loc_18000C605
0x18000c5de  mov     edx, 12Eh; void *
0x18000c5e3  mov     rcx, [rbp+178h]; this
0x18000c5ea  lea     r8, aWil; "wil"
0x18000c5f1  mov     r9d, eax; char *
0x18000c5f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c5f9  lea     rcx, [rsp+270h+var_238]
0x18000c5fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c603  jmp     short loc_18000C624
0x18000c605  mov     rcx, [rsp+270h+var_230]
0x18000c60a  test    rcx, rcx
0x18000c60d  jz      short loc_18000C654
0x18000c60f  mov     [rdi], rcx
0x18000c612  mov     eax, [rcx]
0x18000c614  inc     eax
0x18000c616  mov     [rcx], eax
0x18000c618  lea     rcx, [rsp+270h+var_238]
0x18000c61d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c622  xor     ebx, ebx
0x18000c624  lea     rcx, [rsp+270h+var_240]
0x18000c629  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c62e  mov     eax, ebx
0x18000c630  mov     rcx, [rbp+170h+var_10]
0x18000c637  xor     rcx, rsp; StackCookie
0x18000c63a  call    __security_check_cookie
0x18000c63f  lea     r11, [rsp+270h+var_s0]
0x18000c647  mov     rbx, [r11+20h]
0x18000c64b  mov     rdi, [r11+28h]
0x18000c64f  mov     rsp, r11
0x18000c652  pop     rbp
0x18000c653  retn
0x18000c654  mov     r8, rdi
0x18000c657  lea     rdx, [rsp+270h+var_240]
0x18000c65c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c661  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000c666  mov     ebx, eax
0x18000c668  test    eax, eax
0x18000c66a  jns     short loc_18000C618
0x18000c66c  mov     edx, 137h
0x18000c671  jmp     loc_18000C5E3
```
