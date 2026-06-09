# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000d8f0`
- end: `0x14000da97`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400117c4`

## callees

- `0x14000d8f0`
- `0x14000dc50`
- `0x14000dc6c`
- `0x14000dfe0`
- `0x14000e034`
- `0x14000e058`
- `0x14000e160`
- `0x14000e1c0`
- `0x14000ec5c`
- `0x14000f6a0`
- `0x140012ad4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000d925`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000d925`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000d96a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000d96a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  int Pointer; // eax
  unsigned int v9; // edi
  void *v10; // rdx
  _DWORD *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rdx
  void *v15; // rdx
  wil::details *v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v18; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v16 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v16,
    Mutex);
  v6 = v16;
  if ( !v16 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v16,
    v17);
  v18 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v18);
  v9 = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    wil::details::CloseHandle(v6, v10);
    return v9;
  }
  v11 = v18;
  if ( v18 )
  {
    *a2 = v18;
    ++*v11;
LABEL_12:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    if ( v6 )
      wil::details::CloseHandle(v6, v15);
    return 0;
  }
  v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v6 = v16;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v12, 304);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
  if ( v16 )
    wil::details::CloseHandle(v16, v14);
  return v13;
}

```

## disassembly

```asm
0x14000d8f0  mov     [rsp-8+arg_10], rbx
0x14000d8f5  push    rbp
0x14000d8f6  push    rsi
0x14000d8f7  push    rdi
0x14000d8f8  lea     rbp, [rsp-170h]
0x14000d900  sub     rsp, 270h
0x14000d907  mov     rax, cs:__security_cookie
0x14000d90e  xor     rax, rsp
0x14000d911  mov     [rbp+180h+var_20], rax
0x14000d918  mov     rsi, rdx
0x14000d91b  mov     qword ptr [rdx], 0
0x14000d922  mov     rbx, rcx
0x14000d925  call    cs:__imp_GetCurrentProcessId
0x14000d92b  mov     [rsp+280h+var_258], rbx
0x14000d930  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000d937  mov     r9d, eax
0x14000d93a  mov     [rsp+280h+var_260], 130h; int
0x14000d942  mov     edx, 104h; unsigned __int64
0x14000d947  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000d94c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d951  mov     r9d, 1F0001h; dwDesiredAccess
0x14000d957  mov     [rsp+280h+var_250], 0
0x14000d960  xor     r8d, r8d; dwFlags
0x14000d963  lea     rdx, [rsp+280h+Name]; lpName
0x14000d968  xor     ecx, ecx; lpMutexAttributes
0x14000d96a  call    cs:__imp_CreateMutexExW
0x14000d970  mov     rdx, rax
0x14000d973  lea     rcx, [rsp+280h+var_250]
0x14000d978  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000d97d  mov     rbx, [rsp+280h+var_250]
0x14000d982  test    rbx, rbx
0x14000d985  jnz     short loc_14000D991
0x14000d987  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000d98c  jmp     loc_14000DA75
0x14000d991  lea     rdx, [rsp+280h+var_248]
0x14000d996  lea     rcx, [rsp+280h+var_250]
0x14000d99b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000d9a0  lea     rdx, [rsp+280h+var_240]; void **
0x14000d9a5  mov     [rsp+280h+var_240], 0
0x14000d9ae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000d9b3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14000d9b8  mov     edi, eax
0x14000d9ba  test    eax, eax
0x14000d9bc  jns     short loc_14000D9F2
0x14000d9be  mov     rcx, [rbp+188h]; this
0x14000d9c5  lea     r8, aWil; "wil"
0x14000d9cc  mov     r9d, eax; char *
0x14000d9cf  mov     edx, 12Eh; void *
0x14000d9d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d9d9  lea     rcx, [rsp+280h+var_248]
0x14000d9de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000d9e3  mov     rcx, rbx; this
0x14000d9e6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000d9eb  mov     eax, edi
0x14000d9ed  jmp     loc_14000DA75
0x14000d9f2  mov     rcx, [rsp+280h+var_240]
0x14000d9f7  test    rcx, rcx
0x14000d9fa  jz      short loc_14000DA07
0x14000d9fc  mov     [rsi], rcx
0x14000d9ff  mov     eax, [rcx]
0x14000da01  inc     eax
0x14000da03  mov     [rcx], eax
0x14000da05  jmp     short loc_14000DA5C
0x14000da07  mov     r8, rsi
0x14000da0a  lea     rdx, [rsp+280h+var_250]
0x14000da0f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000da14  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000da19  mov     ebx, eax
0x14000da1b  test    eax, eax
0x14000da1d  jns     short loc_14000DA57
0x14000da1f  mov     rcx, [rbp+188h]; this
0x14000da26  lea     r8, aWil; "wil"
0x14000da2d  mov     r9d, eax; char *
0x14000da30  mov     edx, 137h; void *
0x14000da35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000da3a  lea     rcx, [rsp+280h+var_248]
0x14000da3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000da44  mov     rcx, [rsp+280h+var_250]; this
0x14000da49  test    rcx, rcx
0x14000da4c  jz      short loc_14000DA53
0x14000da4e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000da53  mov     eax, ebx
0x14000da55  jmp     short loc_14000DA75
0x14000da57  mov     rbx, [rsp+280h+var_250]
0x14000da5c  lea     rcx, [rsp+280h+var_248]
0x14000da61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000da66  test    rbx, rbx
0x14000da69  jz      short loc_14000DA73
0x14000da6b  mov     rcx, rbx; this
0x14000da6e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000da73  xor     eax, eax
0x14000da75  mov     rcx, [rbp+180h+var_20]
0x14000da7c  xor     rcx, rsp; StackCookie
0x14000da7f  call    __security_check_cookie
0x14000da84  mov     rbx, [rsp+280h+arg_10]
0x14000da8c  add     rsp, 270h
0x14000da93  pop     rdi
0x14000da94  pop     rsi
0x14000da95  pop     rbp
0x14000da96  retn
```
