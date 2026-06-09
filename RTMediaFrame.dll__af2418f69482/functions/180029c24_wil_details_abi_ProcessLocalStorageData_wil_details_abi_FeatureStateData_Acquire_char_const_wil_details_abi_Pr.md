# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180029c24`
- end: `0x180029d8a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002c070`

## callees

- `0x180020c48`
- `0x180025dac`
- `0x180026920`
- `0x180029488`
- `0x1800294a4`
- `0x180029c24`
- `0x18002ce5c`
- `0x18002f814`
- `0x18002fcac`
- `0x1800305f4`
- `0x180030920`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029c5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029c5c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029ca1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029ca1`

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
0x180029c24  mov     [rsp-8+arg_10], rbx
0x180029c29  mov     [rsp-8+arg_18], rdi
0x180029c2e  push    rbp
0x180029c2f  lea     rbp, [rsp-170h]
0x180029c37  sub     rsp, 270h
0x180029c3e  mov     rax, cs:__security_cookie
0x180029c45  xor     rax, rsp
0x180029c48  mov     [rbp+170h+var_10], rax
0x180029c4f  mov     rdi, rdx
0x180029c52  mov     qword ptr [rdx], 0
0x180029c59  mov     rbx, rcx
0x180029c5c  call    cs:__imp_GetCurrentProcessId
0x180029c62  mov     [rsp+270h+var_248], rbx
0x180029c67  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180029c6e  mov     r9d, eax
0x180029c71  mov     [rsp+270h+var_250], 130h; int
0x180029c79  mov     edx, 104h; unsigned __int64
0x180029c7e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180029c83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029c88  mov     r9d, 1F0001h; dwDesiredAccess
0x180029c8e  mov     [rsp+270h+var_240], 0
0x180029c97  xor     r8d, r8d; dwFlags
0x180029c9a  lea     rdx, [rsp+270h+Name]; lpName
0x180029c9f  xor     ecx, ecx; lpMutexAttributes
0x180029ca1  call    cs:__imp_CreateMutexExW
0x180029ca7  mov     rdx, rax
0x180029caa  lea     rcx, [rsp+270h+var_240]
0x180029caf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180029cb4  cmp     [rsp+270h+var_240], 0
0x180029cba  jnz     short loc_180029CC5
0x180029cbc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180029cc1  mov     ebx, eax
0x180029cc3  jmp     short loc_180029D38
0x180029cc5  lea     rdx, [rsp+270h+var_238]
0x180029cca  lea     rcx, [rsp+270h+var_240]
0x180029ccf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180029cd4  lea     rdx, [rsp+270h+var_230]; void **
0x180029cd9  mov     [rsp+270h+var_230], 0
0x180029ce2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180029ce7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180029cec  mov     ebx, eax
0x180029cee  test    eax, eax
0x180029cf0  jns     short loc_180029D19
0x180029cf2  mov     edx, 12Eh; void *
0x180029cf7  mov     rcx, [rbp+178h]; this
0x180029cfe  lea     r8, aWil; "wil"
0x180029d05  mov     r9d, eax; char *
0x180029d08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d0d  lea     rcx, [rsp+270h+var_238]
0x180029d12  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029d17  jmp     short loc_180029D38
0x180029d19  mov     rcx, [rsp+270h+var_230]
0x180029d1e  test    rcx, rcx
0x180029d21  jz      short loc_180029D68
0x180029d23  mov     [rdi], rcx
0x180029d26  mov     eax, [rcx]
0x180029d28  inc     eax
0x180029d2a  mov     [rcx], eax
0x180029d2c  lea     rcx, [rsp+270h+var_238]
0x180029d31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029d36  xor     ebx, ebx
0x180029d38  lea     rcx, [rsp+270h+var_240]
0x180029d3d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029d42  mov     eax, ebx
0x180029d44  mov     rcx, [rbp+170h+var_10]
0x180029d4b  xor     rcx, rsp; StackCookie
0x180029d4e  call    __security_check_cookie
0x180029d53  lea     r11, [rsp+270h+var_s0]
0x180029d5b  mov     rbx, [r11+20h]
0x180029d5f  mov     rdi, [r11+28h]
0x180029d63  mov     rsp, r11
0x180029d66  pop     rbp
0x180029d67  retn
0x180029d68  mov     r8, rdi
0x180029d6b  lea     rdx, [rsp+270h+var_240]
0x180029d70  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180029d75  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180029d7a  mov     ebx, eax
0x180029d7c  test    eax, eax
0x180029d7e  jns     short loc_180029D2C
0x180029d80  mov     edx, 137h
0x180029d85  jmp     loc_180029CF7
```
