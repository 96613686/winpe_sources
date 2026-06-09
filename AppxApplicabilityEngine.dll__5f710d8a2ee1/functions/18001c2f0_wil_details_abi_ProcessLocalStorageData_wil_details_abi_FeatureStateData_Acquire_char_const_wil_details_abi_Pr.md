# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001c2f0`
- end: `0x18001c4aa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001c80c`

## callees

- `0x180009bf8`
- `0x180010818`
- `0x18001433c`
- `0x180014358`
- `0x18001577c`
- `0x180015dac`
- `0x1800160cc`
- `0x1800161d0`
- `0x18001c2f0`
- `0x18001ca9c`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c377`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c377`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c331`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  _DWORD *v9; // rcx
  int v10; // eax
  __int64 v11; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+40h] [rbp-C8h] BYREF
  void *v13[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v13[1] = (void *)-2LL;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( !v11 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
    return LastErrorFailHr;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v11,
    &v12);
  v13[0] = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, v13);
  LastErrorFailHr = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
    return LastErrorFailHr;
  }
  v9 = v13[0];
  if ( v13[0] )
  {
    *a2 = v13[0];
    ++*v9;
  }
  else
  {
    v10 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v10,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
      return LastErrorFailHr;
    }
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return 0;
}

```

## disassembly

```asm
0x18001c2f0  mov     rax, rsp
0x18001c2f3  push    rbp
0x18001c2f4  lea     rbp, [rax-178h]
0x18001c2fb  sub     rsp, 270h
0x18001c302  mov     qword ptr [rsp+270h+var_228], 0FFFFFFFFFFFFFFFEh
0x18001c30b  mov     [rax+18h], rbx
0x18001c30f  mov     [rax+20h], rdi
0x18001c313  mov     rax, cs:__security_cookie
0x18001c31a  xor     rax, rsp
0x18001c31d  mov     [rbp+170h+var_10], rax
0x18001c324  mov     rdi, rdx
0x18001c327  mov     rbx, rcx
0x18001c32a  mov     qword ptr [rdx], 0
0x18001c331  call    cs:__imp_GetCurrentProcessId
0x18001c337  mov     r9d, eax
0x18001c33a  mov     [rsp+270h+var_248], rbx
0x18001c33f  mov     [rsp+270h+var_250], 130h; int
0x18001c347  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001c34e  mov     edx, 104h; unsigned __int64
0x18001c353  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001c358  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c35d  nop
0x18001c35e  mov     [rsp+270h+var_240], 0
0x18001c367  mov     r9d, 1F0001h; dwDesiredAccess
0x18001c36d  xor     r8d, r8d; dwFlags
0x18001c370  lea     rdx, [rsp+270h+Name]; lpName
0x18001c375  xor     ecx, ecx; lpMutexAttributes
0x18001c377  call    cs:__imp_CreateMutexExW
0x18001c37d  mov     rdx, rax
0x18001c380  lea     rcx, [rsp+270h+var_240]
0x18001c385  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001c38a  cmp     [rsp+270h+var_240], 0
0x18001c390  jnz     short loc_18001C3AB
0x18001c392  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c397  mov     ebx, eax
0x18001c399  lea     rcx, [rsp+270h+var_240]
0x18001c39e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c3a3  nop
0x18001c3a4  mov     eax, ebx
0x18001c3a6  jmp     loc_18001C437
0x18001c3ab  lea     rdx, [rsp+270h+var_238]
0x18001c3b0  lea     rcx, [rsp+270h+var_240]
0x18001c3b5  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001c3ba  mov     [rsp+270h+var_230], 0
0x18001c3c3  lea     rdx, [rsp+270h+var_230]; void **
0x18001c3c8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001c3cd  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001c3d2  mov     ebx, eax
0x18001c3d4  test    eax, eax
0x18001c3d6  jns     short loc_18001C40C
0x18001c3d8  mov     rcx, [rbp+178h]; this
0x18001c3df  mov     r9d, eax; char *
0x18001c3e2  lea     r8, aWil; "wil"
0x18001c3e9  mov     edx, 12Eh; void *
0x18001c3ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c3f3  nop
0x18001c3f4  lea     rcx, [rsp+270h+var_238]
0x18001c3f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c3fe  nop
0x18001c3ff  lea     rcx, [rsp+270h+var_240]
0x18001c404  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c409  nop
0x18001c40a  jmp     short loc_18001C3A4
0x18001c40c  mov     rcx, [rsp+270h+var_230]
0x18001c411  test    rcx, rcx
0x18001c414  jz      short loc_18001C45B
0x18001c416  mov     [rdi], rcx
0x18001c419  mov     eax, [rcx]
0x18001c41b  inc     eax
0x18001c41d  mov     [rcx], eax
0x18001c41f  lea     rcx, [rsp+270h+var_238]
0x18001c424  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c429  nop
0x18001c42a  lea     rcx, [rsp+270h+var_240]
0x18001c42f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c434  nop
0x18001c435  xor     eax, eax
0x18001c437  mov     rcx, [rbp+170h+var_10]
0x18001c43e  xor     rcx, rsp; StackCookie
0x18001c441  call    __security_check_cookie
0x18001c446  lea     r11, [rsp+270h+var_s0]
0x18001c44e  mov     rbx, [r11+20h]
0x18001c452  mov     rdi, [r11+28h]
0x18001c456  mov     rsp, r11
0x18001c459  pop     rbp
0x18001c45a  retn
0x18001c45b  mov     r8, rdi
0x18001c45e  lea     rdx, [rsp+270h+var_240]
0x18001c463  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001c468  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001c46d  mov     ebx, eax
0x18001c46f  test    eax, eax
0x18001c471  jns     short loc_18001C41F
0x18001c473  mov     rcx, [rbp+178h]; this
0x18001c47a  mov     r9d, eax; char *
0x18001c47d  lea     r8, aWil; "wil"
0x18001c484  mov     edx, 137h; void *
0x18001c489  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c48e  nop
0x18001c48f  lea     rcx, [rsp+270h+var_238]
0x18001c494  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c499  nop
0x18001c49a  lea     rcx, [rsp+270h+var_240]
0x18001c49f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c4a4  nop
0x18001c4a5  jmp     loc_18001C3A4
```
