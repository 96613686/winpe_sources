# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180029f4c`
- end: `0x18002a0ab`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002a3c4`

## callees

- `0x180023d68`
- `0x1800249f0`
- `0x180029be8`
- `0x180029c04`
- `0x180029f4c`
- `0x18002b704`
- `0x18002c3ac`
- `0x18002c8c8`
- `0x18002ccc0`
- `0x18002d4a4`
- `0x18002d5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029fc9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029fc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029f84`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x180029f4c  mov     [rsp-8+arg_10], rbx
0x180029f51  mov     [rsp-8+arg_18], rdi
0x180029f56  push    rbp
0x180029f57  lea     rbp, [rsp-170h]
0x180029f5f  sub     rsp, 270h
0x180029f66  mov     rax, cs:__security_cookie
0x180029f6d  xor     rax, rsp
0x180029f70  mov     [rbp+170h+var_10], rax
0x180029f77  mov     rdi, rdx
0x180029f7a  mov     qword ptr [rdx], 0
0x180029f81  mov     rbx, rcx
0x180029f84  call    cs:__imp_GetCurrentProcessId
0x180029f8a  mov     [rsp+270h+var_248], rbx
0x180029f8f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180029f96  mov     r9d, eax
0x180029f99  mov     [rsp+270h+var_250], 130h; int
0x180029fa1  mov     edx, 104h; unsigned __int64
0x180029fa6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029fab  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180029fb0  mov     r9d, 1F0001h; dwDesiredAccess
0x180029fb6  mov     [rsp+270h+var_240], 0
0x180029fbf  xor     r8d, r8d; dwFlags
0x180029fc2  lea     rdx, [rsp+270h+Name]; lpName
0x180029fc7  xor     ecx, ecx; lpMutexAttributes
0x180029fc9  call    cs:__imp_CreateMutexExW
0x180029fcf  mov     rdx, rax
0x180029fd2  lea     rcx, [rsp+270h+var_240]
0x180029fd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180029fdc  cmp     [rsp+270h+var_240], 0
0x180029fe2  jnz     short loc_180029FED
0x180029fe4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180029fe9  mov     ebx, eax
0x180029feb  jmp     short loc_18002A059
0x180029fed  lea     rdx, [rsp+270h+var_238]
0x180029ff2  lea     rcx, [rsp+270h+var_240]
0x180029ff7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180029ffc  lea     rdx, [rsp+270h+var_230]; void **
0x18002a001  mov     [rsp+270h+var_230], 0
0x18002a00a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18002a00f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18002a014  mov     ebx, eax
0x18002a016  test    eax, eax
0x18002a018  jns     short loc_18002A03A
0x18002a01a  mov     edx, 12Eh; void *
0x18002a01f  mov     rcx, [rbp+178h]; this
0x18002a026  mov     r9d, eax; char *
0x18002a029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a02e  lea     rcx, [rsp+270h+var_238]
0x18002a033  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a038  jmp     short loc_18002A059
0x18002a03a  mov     rcx, [rsp+270h+var_230]
0x18002a03f  test    rcx, rcx
0x18002a042  jz      short loc_18002A089
0x18002a044  mov     [rdi], rcx
0x18002a047  mov     eax, [rcx]
0x18002a049  inc     eax
0x18002a04b  mov     [rcx], eax
0x18002a04d  lea     rcx, [rsp+270h+var_238]
0x18002a052  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a057  xor     ebx, ebx
0x18002a059  lea     rcx, [rsp+270h+var_240]
0x18002a05e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a063  mov     eax, ebx
0x18002a065  mov     rcx, [rbp+170h+var_10]
0x18002a06c  xor     rcx, rsp; StackCookie
0x18002a06f  call    __security_check_cookie
0x18002a074  lea     r11, [rsp+270h+var_s0]
0x18002a07c  mov     rbx, [r11+20h]
0x18002a080  mov     rdi, [r11+28h]
0x18002a084  mov     rsp, r11
0x18002a087  pop     rbp
0x18002a088  retn
0x18002a089  mov     r8, rdi
0x18002a08c  lea     rdx, [rsp+270h+var_240]
0x18002a091  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18002a096  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002a09b  mov     ebx, eax
0x18002a09d  test    eax, eax
0x18002a09f  jns     short loc_18002A04D
0x18002a0a1  mov     edx, 137h
0x18002a0a6  jmp     loc_18002A01F
```
