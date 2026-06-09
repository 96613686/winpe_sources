# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180095bb4`
- end: `0x180095d1c`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180097144`

## callees

- `0x1800049e0`
- `0x18003e1c4`
- `0x18008278c`
- `0x180093830`
- `0x1800956d8`
- `0x180095bb4`
- `0x180097110`
- `0x180097568`
- `0x1800987fc`
- `0x1800990f0`
- `0x180099ac4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180095bec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180095bec`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180095c31`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180095c31`

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
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
    v13 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x180095bb4  mov     [rsp-8+arg_10], rbx
0x180095bb9  mov     [rsp-8+arg_18], rdi
0x180095bbe  push    rbp
0x180095bbf  lea     rbp, [rsp-170h]
0x180095bc7  sub     rsp, 270h
0x180095bce  mov     rax, cs:__security_cookie
0x180095bd5  xor     rax, rsp
0x180095bd8  mov     [rbp+170h+var_10], rax
0x180095bdf  mov     rdi, rdx
0x180095be2  mov     qword ptr [rdx], 0
0x180095be9  mov     rbx, rcx
0x180095bec  call    cs:__imp_GetCurrentProcessId
0x180095bf2  mov     [rsp+270h+var_248], rbx
0x180095bf7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180095bfe  mov     r9d, eax
0x180095c01  mov     [rsp+270h+var_250], 130h; int
0x180095c09  mov     edx, 104h; unsigned __int64
0x180095c0e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180095c13  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180095c18  mov     r9d, 1F0001h; dwDesiredAccess
0x180095c1e  mov     [rsp+270h+var_240], 0
0x180095c27  xor     r8d, r8d; dwFlags
0x180095c2a  lea     rdx, [rsp+270h+Name]; lpName
0x180095c2f  xor     ecx, ecx; lpMutexAttributes
0x180095c31  call    cs:__imp_CreateMutexExW
0x180095c37  mov     rdx, rax
0x180095c3a  lea     rcx, [rsp+270h+var_240]
0x180095c3f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180095c44  cmp     [rsp+270h+var_240], 0
0x180095c4a  jnz     short loc_180095C55
0x180095c4c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180095c51  mov     ebx, eax
0x180095c53  jmp     short loc_180095CCA
0x180095c55  lea     rdx, [rsp+270h+var_238]
0x180095c5a  mov     [rsp+270h+var_238], 0
0x180095c63  lea     rcx, [rsp+270h+var_240]
0x180095c68  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180095c6d  lea     rdx, [rsp+270h+var_230]; void **
0x180095c72  mov     [rsp+270h+var_230], 0
0x180095c7b  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180095c80  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180095c85  mov     ebx, eax
0x180095c87  test    eax, eax
0x180095c89  jns     short loc_180095CAB
0x180095c8b  mov     edx, 12Eh; void *
0x180095c90  mov     rcx, [rbp+178h]; this
0x180095c97  mov     r9d, eax; char *
0x180095c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095c9f  lea     rcx, [rsp+270h+var_238]
0x180095ca4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180095ca9  jmp     short loc_180095CCA
0x180095cab  mov     rcx, [rsp+270h+var_230]
0x180095cb0  test    rcx, rcx
0x180095cb3  jz      short loc_180095CFA
0x180095cb5  mov     [rdi], rcx
0x180095cb8  mov     eax, [rcx]
0x180095cba  inc     eax
0x180095cbc  mov     [rcx], eax
0x180095cbe  lea     rcx, [rsp+270h+var_238]
0x180095cc3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180095cc8  xor     ebx, ebx
0x180095cca  lea     rcx, [rsp+270h+var_240]
0x180095ccf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180095cd4  mov     eax, ebx
0x180095cd6  mov     rcx, [rbp+170h+var_10]
0x180095cdd  xor     rcx, rsp; StackCookie
0x180095ce0  call    __security_check_cookie
0x180095ce5  lea     r11, [rsp+270h+var_s0]
0x180095ced  mov     rbx, [r11+20h]
0x180095cf1  mov     rdi, [r11+28h]
0x180095cf5  mov     rsp, r11
0x180095cf8  pop     rbp
0x180095cf9  retn
0x180095cfa  mov     r8, rdi
0x180095cfd  lea     rdx, [rsp+270h+var_240]
0x180095d02  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180095d07  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180095d0c  mov     ebx, eax
0x180095d0e  test    eax, eax
0x180095d10  jns     short loc_180095CBE
0x180095d12  mov     edx, 137h
0x180095d17  jmp     loc_180095C90
```
