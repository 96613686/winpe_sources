# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003e28`
- end: `0x140003f8e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140004b28`

## callees

- `0x140003c68`
- `0x140003c84`
- `0x140003e28`
- `0x140004888`
- `0x140005270`
- `0x1400056a4`
- `0x140005c3c`
- `0x140005db0`
- `0x1400064e4`
- `0x14000690c`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140003ea5`
- `KERNEL32!CreateMutexExW` at `0x140003ea5`
- `KERNEL32!GetCurrentProcessId` at `0x140003e60`
- `KERNEL32!GetCurrentProcessId` at `0x140003e60`

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
0x140003e28  mov     [rsp-8+arg_10], rbx
0x140003e2d  mov     [rsp-8+arg_18], rdi
0x140003e32  push    rbp
0x140003e33  lea     rbp, [rsp-170h]
0x140003e3b  sub     rsp, 270h
0x140003e42  mov     rax, cs:__security_cookie
0x140003e49  xor     rax, rsp
0x140003e4c  mov     [rbp+170h+var_10], rax
0x140003e53  mov     rdi, rdx
0x140003e56  mov     qword ptr [rdx], 0
0x140003e5d  mov     rbx, rcx
0x140003e60  call    cs:__imp_GetCurrentProcessId
0x140003e66  mov     [rsp+270h+var_248], rbx
0x140003e6b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003e72  mov     r9d, eax
0x140003e75  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140003e7d  mov     edx, 104h; unsigned __int64
0x140003e82  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003e87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003e8c  mov     r9d, 1F0001h; dwDesiredAccess
0x140003e92  mov     [rsp+270h+var_240], 0
0x140003e9b  xor     r8d, r8d; dwFlags
0x140003e9e  lea     rdx, [rsp+270h+Name]; lpName
0x140003ea3  xor     ecx, ecx; lpMutexAttributes
0x140003ea5  call    cs:__imp_CreateMutexExW
0x140003eab  mov     rdx, rax
0x140003eae  lea     rcx, [rsp+270h+var_240]
0x140003eb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140003eb8  cmp     [rsp+270h+var_240], 0
0x140003ebe  jnz     short loc_140003EC9
0x140003ec0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003ec5  mov     ebx, eax
0x140003ec7  jmp     short loc_140003F3C
0x140003ec9  lea     rdx, [rsp+270h+var_238]
0x140003ece  lea     rcx, [rsp+270h+var_240]
0x140003ed3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140003ed8  lea     rdx, [rsp+270h+var_230]; void **
0x140003edd  mov     [rsp+270h+var_230], 0
0x140003ee6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003eeb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140003ef0  mov     ebx, eax
0x140003ef2  test    eax, eax
0x140003ef4  jns     short loc_140003F1D
0x140003ef6  mov     edx, 12Eh; void *
0x140003efb  mov     rcx, [rbp+178h]; this
0x140003f02  lea     r8, aWil; "wil"
0x140003f09  mov     r9d, eax; char *
0x140003f0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f11  lea     rcx, [rsp+270h+var_238]
0x140003f16  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003f1b  jmp     short loc_140003F3C
0x140003f1d  mov     rcx, [rsp+270h+var_230]
0x140003f22  test    rcx, rcx
0x140003f25  jz      short loc_140003F6C
0x140003f27  mov     [rdi], rcx
0x140003f2a  mov     eax, [rcx]
0x140003f2c  inc     eax
0x140003f2e  mov     [rcx], eax
0x140003f30  lea     rcx, [rsp+270h+var_238]
0x140003f35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003f3a  xor     ebx, ebx
0x140003f3c  lea     rcx, [rsp+270h+var_240]
0x140003f41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003f46  mov     eax, ebx
0x140003f48  mov     rcx, [rbp+170h+var_10]
0x140003f4f  xor     rcx, rsp; StackCookie
0x140003f52  call    __security_check_cookie
0x140003f57  lea     r11, [rsp+270h+var_s0]
0x140003f5f  mov     rbx, [r11+20h]
0x140003f63  mov     rdi, [r11+28h]
0x140003f67  mov     rsp, r11
0x140003f6a  pop     rbp
0x140003f6b  retn
0x140003f6c  mov     r8, rdi
0x140003f6f  lea     rdx, [rsp+270h+var_240]
0x140003f74  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003f79  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140003f7e  mov     ebx, eax
0x140003f80  test    eax, eax
0x140003f82  jns     short loc_140003F30
0x140003f84  mov     edx, 137h
0x140003f89  jmp     loc_140003EFB
```
