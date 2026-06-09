# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000f7ec`
- end: `0x18000f952`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000ff34`

## callees

- `0x180003980`
- `0x180008d0c`
- `0x180008d28`
- `0x180009608`
- `0x18000a3c0`
- `0x18000a7c0`
- `0x18000a918`
- `0x18000ada0`
- `0x18000ae58`
- `0x18000f7ec`
- `0x1800102d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f869`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f824`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f824`

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
0x18000f7ec  mov     [rsp-8+arg_10], rbx
0x18000f7f1  mov     [rsp-8+arg_18], rdi
0x18000f7f6  push    rbp
0x18000f7f7  lea     rbp, [rsp-170h]
0x18000f7ff  sub     rsp, 270h
0x18000f806  mov     rax, cs:__security_cookie
0x18000f80d  xor     rax, rsp
0x18000f810  mov     [rbp+170h+var_10], rax
0x18000f817  mov     rdi, rdx
0x18000f81a  mov     qword ptr [rdx], 0
0x18000f821  mov     rbx, rcx
0x18000f824  call    cs:__imp_GetCurrentProcessId
0x18000f82a  mov     [rsp+270h+var_248], rbx
0x18000f82f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000f836  mov     r9d, eax
0x18000f839  mov     [rsp+270h+var_250], 130h; int
0x18000f841  mov     edx, 104h; unsigned __int64
0x18000f846  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f84b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f850  mov     r9d, 1F0001h; dwDesiredAccess
0x18000f856  mov     [rsp+270h+var_240], 0
0x18000f85f  xor     r8d, r8d; dwFlags
0x18000f862  lea     rdx, [rsp+270h+Name]; lpName
0x18000f867  xor     ecx, ecx; lpMutexAttributes
0x18000f869  call    cs:__imp_CreateMutexExW
0x18000f86f  mov     rdx, rax
0x18000f872  lea     rcx, [rsp+270h+var_240]
0x18000f877  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f87c  cmp     [rsp+270h+var_240], 0
0x18000f882  jnz     short loc_18000F88D
0x18000f884  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f889  mov     ebx, eax
0x18000f88b  jmp     short loc_18000F900
0x18000f88d  lea     rdx, [rsp+270h+var_238]
0x18000f892  lea     rcx, [rsp+270h+var_240]
0x18000f897  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000f89c  lea     rdx, [rsp+270h+var_230]; void **
0x18000f8a1  mov     [rsp+270h+var_230], 0
0x18000f8aa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f8af  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000f8b4  mov     ebx, eax
0x18000f8b6  test    eax, eax
0x18000f8b8  jns     short loc_18000F8E1
0x18000f8ba  mov     edx, 12Eh; void *
0x18000f8bf  mov     rcx, [rbp+178h]; this
0x18000f8c6  lea     r8, aWil; "wil"
0x18000f8cd  mov     r9d, eax; char *
0x18000f8d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f8d5  lea     rcx, [rsp+270h+var_238]
0x18000f8da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f8df  jmp     short loc_18000F900
0x18000f8e1  mov     rcx, [rsp+270h+var_230]
0x18000f8e6  test    rcx, rcx
0x18000f8e9  jz      short loc_18000F930
0x18000f8eb  mov     [rdi], rcx
0x18000f8ee  mov     eax, [rcx]
0x18000f8f0  inc     eax
0x18000f8f2  mov     [rcx], eax
0x18000f8f4  lea     rcx, [rsp+270h+var_238]
0x18000f8f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f8fe  xor     ebx, ebx
0x18000f900  lea     rcx, [rsp+270h+var_240]
0x18000f905  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f90a  mov     eax, ebx
0x18000f90c  mov     rcx, [rbp+170h+var_10]
0x18000f913  xor     rcx, rsp; StackCookie
0x18000f916  call    __security_check_cookie
0x18000f91b  lea     r11, [rsp+270h+var_s0]
0x18000f923  mov     rbx, [r11+20h]
0x18000f927  mov     rdi, [r11+28h]
0x18000f92b  mov     rsp, r11
0x18000f92e  pop     rbp
0x18000f92f  retn
0x18000f930  mov     r8, rdi
0x18000f933  lea     rdx, [rsp+270h+var_240]
0x18000f938  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f93d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000f942  mov     ebx, eax
0x18000f944  test    eax, eax
0x18000f946  jns     short loc_18000F8F4
0x18000f948  mov     edx, 137h
0x18000f94d  jmp     loc_18000F8BF
```
