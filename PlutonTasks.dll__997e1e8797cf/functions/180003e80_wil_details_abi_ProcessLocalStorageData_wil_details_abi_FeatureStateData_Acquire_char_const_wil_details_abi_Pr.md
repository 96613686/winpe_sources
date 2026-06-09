# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003e80`
- end: `0x180003fdf`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800048d0`

## callees

- `0x180001e00`
- `0x18000373c`
- `0x180003758`
- `0x180003e80`
- `0x180005098`
- `0x180005e74`
- `0x1800074cc`
- `0x180007d1c`
- `0x180008210`
- `0x180008a14`
- `0x180008de8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003efd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003efd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003eb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003eb8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rdx
  _DWORD *v13; // rcx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v16; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( v15 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v15,
      &v16);
    v17 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v12);
      goto LABEL_9;
    }
    v13 = v17;
    if ( v17 )
    {
      *a2 = v17;
      ++*v13;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v16,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180003e80  mov     [rsp-8+arg_10], rbx
0x180003e85  mov     [rsp-8+arg_18], rdi
0x180003e8a  push    rbp
0x180003e8b  lea     rbp, [rsp-170h]
0x180003e93  sub     rsp, 270h
0x180003e9a  mov     rax, cs:__security_cookie
0x180003ea1  xor     rax, rsp
0x180003ea4  mov     [rbp+170h+var_10], rax
0x180003eab  mov     rdi, rdx
0x180003eae  mov     qword ptr [rdx], 0
0x180003eb5  mov     rbx, rcx
0x180003eb8  call    cs:__imp_GetCurrentProcessId
0x180003ebe  mov     [rsp+270h+var_248], rbx
0x180003ec3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003eca  mov     r9d, eax
0x180003ecd  mov     [rsp+270h+var_250], 130h; int
0x180003ed5  mov     edx, 104h; unsigned __int64
0x180003eda  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003edf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003ee4  mov     r9d, 1F0001h; dwDesiredAccess
0x180003eea  mov     [rsp+270h+var_240], 0
0x180003ef3  xor     r8d, r8d; dwFlags
0x180003ef6  lea     rdx, [rsp+270h+Name]; lpName
0x180003efb  xor     ecx, ecx; lpMutexAttributes
0x180003efd  call    cs:__imp_CreateMutexExW
0x180003f03  mov     rdx, rax
0x180003f06  lea     rcx, [rsp+270h+var_240]
0x180003f0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003f10  cmp     [rsp+270h+var_240], 0
0x180003f16  jnz     short loc_180003F21
0x180003f18  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003f1d  mov     ebx, eax
0x180003f1f  jmp     short loc_180003F8D
0x180003f21  lea     rdx, [rsp+270h+var_238]
0x180003f26  lea     rcx, [rsp+270h+var_240]
0x180003f2b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003f30  lea     rdx, [rsp+270h+var_230]; void **
0x180003f35  mov     [rsp+270h+var_230], 0
0x180003f3e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003f43  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180003f48  mov     ebx, eax
0x180003f4a  test    eax, eax
0x180003f4c  jns     short loc_180003F6E
0x180003f4e  mov     edx, 12Eh; void *
0x180003f53  mov     rcx, [rbp+178h]; this
0x180003f5a  mov     r9d, eax; char *
0x180003f5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f62  lea     rcx, [rsp+270h+var_238]
0x180003f67  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003f6c  jmp     short loc_180003F8D
0x180003f6e  mov     rcx, [rsp+270h+var_230]
0x180003f73  test    rcx, rcx
0x180003f76  jz      short loc_180003FBD
0x180003f78  mov     [rdi], rcx
0x180003f7b  mov     eax, [rcx]
0x180003f7d  inc     eax
0x180003f7f  mov     [rcx], eax
0x180003f81  lea     rcx, [rsp+270h+var_238]
0x180003f86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003f8b  xor     ebx, ebx
0x180003f8d  lea     rcx, [rsp+270h+var_240]
0x180003f92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003f97  mov     eax, ebx
0x180003f99  mov     rcx, [rbp+170h+var_10]
0x180003fa0  xor     rcx, rsp; StackCookie
0x180003fa3  call    __security_check_cookie
0x180003fa8  lea     r11, [rsp+270h+var_s0]
0x180003fb0  mov     rbx, [r11+20h]
0x180003fb4  mov     rdi, [r11+28h]
0x180003fb8  mov     rsp, r11
0x180003fbb  pop     rbp
0x180003fbc  retn
0x180003fbd  mov     r8, rdi
0x180003fc0  lea     rdx, [rsp+270h+var_240]
0x180003fc5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003fca  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003fcf  mov     ebx, eax
0x180003fd1  test    eax, eax
0x180003fd3  jns     short loc_180003F81
0x180003fd5  mov     edx, 137h
0x180003fda  jmp     loc_180003F53
```
