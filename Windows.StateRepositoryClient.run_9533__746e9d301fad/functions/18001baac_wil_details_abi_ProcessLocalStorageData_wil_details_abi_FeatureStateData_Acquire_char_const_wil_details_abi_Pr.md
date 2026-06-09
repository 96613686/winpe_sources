# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001baac`
- end: `0x18001bc5d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001becc`

## callees

- `0x180002980`
- `0x180005340`
- `0x18000535c`
- `0x1800062d8`
- `0x1800075e4`
- `0x180007bb8`
- `0x180007e78`
- `0x180008300`
- `0x1800084bc`
- `0x18001baac`
- `0x18001c244`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001bb2a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001bb2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bae4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bae4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  _DWORD *v9; // rcx
  int v10; // eax
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
  if ( !v11 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
    return LastErrorFailHr;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v11,
    v12);
  v13 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
  LastErrorFailHr = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
    return LastErrorFailHr;
  }
  v9 = v13;
  if ( v13 )
  {
    *a2 = v13;
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
      return LastErrorFailHr;
    }
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return 0;
}

```

## disassembly

```asm
0x18001baac  mov     [rsp-8+arg_10], rbx
0x18001bab1  mov     [rsp-8+arg_18], rdi
0x18001bab6  push    rbp
0x18001bab7  lea     rbp, [rsp-170h]
0x18001babf  sub     rsp, 270h
0x18001bac6  mov     rax, cs:__security_cookie
0x18001bacd  xor     rax, rsp
0x18001bad0  mov     [rbp+170h+var_10], rax
0x18001bad7  mov     rdi, rdx
0x18001bada  mov     rbx, rcx
0x18001badd  mov     qword ptr [rdx], 0
0x18001bae4  call    cs:__imp_GetCurrentProcessId
0x18001baea  mov     r9d, eax
0x18001baed  mov     [rsp+270h+var_248], rbx
0x18001baf2  mov     [rsp+270h+var_250], 130h; int
0x18001bafa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001bb01  mov     edx, 104h; unsigned __int64
0x18001bb06  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001bb0b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001bb10  nop
0x18001bb11  mov     [rsp+270h+var_240], 0
0x18001bb1a  mov     r9d, 1F0001h; dwDesiredAccess
0x18001bb20  xor     r8d, r8d; dwFlags
0x18001bb23  lea     rdx, [rsp+270h+Name]; lpName
0x18001bb28  xor     ecx, ecx; lpMutexAttributes
0x18001bb2a  call    cs:__imp_CreateMutexExW
0x18001bb30  mov     rdx, rax
0x18001bb33  lea     rcx, [rsp+270h+var_240]
0x18001bb38  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001bb3d  cmp     [rsp+270h+var_240], 0
0x18001bb43  jnz     short loc_18001BB5E
0x18001bb45  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001bb4a  mov     ebx, eax
0x18001bb4c  lea     rcx, [rsp+270h+var_240]
0x18001bb51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bb56  nop
0x18001bb57  mov     eax, ebx
0x18001bb59  jmp     loc_18001BBEA
0x18001bb5e  lea     rdx, [rsp+270h+var_238]
0x18001bb63  lea     rcx, [rsp+270h+var_240]
0x18001bb68  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001bb6d  mov     [rsp+270h+var_230], 0
0x18001bb76  lea     rdx, [rsp+270h+var_230]; void **
0x18001bb7b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001bb80  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001bb85  mov     ebx, eax
0x18001bb87  test    eax, eax
0x18001bb89  jns     short loc_18001BBBF
0x18001bb8b  mov     rcx, [rbp+178h]; this
0x18001bb92  mov     r9d, eax; char *
0x18001bb95  lea     r8, aWil; "wil"
0x18001bb9c  mov     edx, 12Eh; void *
0x18001bba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bba6  nop
0x18001bba7  lea     rcx, [rsp+270h+var_238]
0x18001bbac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bbb1  nop
0x18001bbb2  lea     rcx, [rsp+270h+var_240]
0x18001bbb7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bbbc  nop
0x18001bbbd  jmp     short loc_18001BB57
0x18001bbbf  mov     rcx, [rsp+270h+var_230]
0x18001bbc4  test    rcx, rcx
0x18001bbc7  jz      short loc_18001BC0E
0x18001bbc9  mov     [rdi], rcx
0x18001bbcc  mov     eax, [rcx]
0x18001bbce  inc     eax
0x18001bbd0  mov     [rcx], eax
0x18001bbd2  lea     rcx, [rsp+270h+var_238]
0x18001bbd7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bbdc  nop
0x18001bbdd  lea     rcx, [rsp+270h+var_240]
0x18001bbe2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bbe7  nop
0x18001bbe8  xor     eax, eax
0x18001bbea  mov     rcx, [rbp+170h+var_10]
0x18001bbf1  xor     rcx, rsp; StackCookie
0x18001bbf4  call    __security_check_cookie
0x18001bbf9  lea     r11, [rsp+270h+var_s0]
0x18001bc01  mov     rbx, [r11+20h]
0x18001bc05  mov     rdi, [r11+28h]
0x18001bc09  mov     rsp, r11
0x18001bc0c  pop     rbp
0x18001bc0d  retn
0x18001bc0e  mov     r8, rdi
0x18001bc11  lea     rdx, [rsp+270h+var_240]
0x18001bc16  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001bc1b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001bc20  mov     ebx, eax
0x18001bc22  test    eax, eax
0x18001bc24  jns     short loc_18001BBD2
0x18001bc26  mov     rcx, [rbp+178h]; this
0x18001bc2d  mov     r9d, eax; char *
0x18001bc30  lea     r8, aWil; "wil"
0x18001bc37  mov     edx, 137h; void *
0x18001bc3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc41  nop
0x18001bc42  lea     rcx, [rsp+270h+var_238]
0x18001bc47  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bc4c  nop
0x18001bc4d  lea     rcx, [rsp+270h+var_240]
0x18001bc52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bc57  nop
0x18001bc58  jmp     loc_18001BB57
```
