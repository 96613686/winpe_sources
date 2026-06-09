# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180027378`
- end: `0x180027529`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `433`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800279a8`

## callees

- `0x1800050f0`
- `0x180010484`
- `0x1800104a0`
- `0x180011ea8`
- `0x1800152d4`
- `0x180015bac`
- `0x180015f0c`
- `0x180016830`
- `0x1800169a0`
- `0x180027378`
- `0x180027d34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800273f6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800273f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800273b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800273b0`

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
  void *v7; // rdx
  int Pointer; // eax
  void *v10; // rdx
  _DWORD *v11; // rcx
  void *v12; // rdx
  int v13; // eax
  void *v14; // rdx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[8]; // [rsp+38h] [rbp-C8h] BYREF
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
  if ( !v15 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v15,
      v7);
    return LastErrorFailHr;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v15,
    v16);
  v17 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
  LastErrorFailHr = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v15,
      v10);
    return LastErrorFailHr;
  }
  v11 = v17;
  if ( v17 )
  {
    *a2 = v17;
    ++*v11;
  }
  else
  {
    v13 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v15,
        v14);
      return LastErrorFailHr;
    }
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v12);
  return 0;
}

```

## disassembly

```asm
0x180027378  mov     [rsp-8+arg_10], rbx
0x18002737d  mov     [rsp-8+arg_18], rdi
0x180027382  push    rbp
0x180027383  lea     rbp, [rsp-170h]
0x18002738b  sub     rsp, 270h
0x180027392  mov     rax, cs:__security_cookie
0x180027399  xor     rax, rsp
0x18002739c  mov     [rbp+170h+var_10], rax
0x1800273a3  mov     rdi, rdx
0x1800273a6  mov     rbx, rcx
0x1800273a9  mov     qword ptr [rdx], 0
0x1800273b0  call    cs:__imp_GetCurrentProcessId
0x1800273b6  mov     r9d, eax
0x1800273b9  mov     [rsp+270h+var_248], rbx
0x1800273be  mov     [rsp+270h+var_250], 130h; int
0x1800273c6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800273cd  mov     edx, 104h; unsigned __int64
0x1800273d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800273d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800273dc  nop
0x1800273dd  mov     [rsp+270h+var_240], 0
0x1800273e6  mov     r9d, 1F0001h; dwDesiredAccess
0x1800273ec  xor     r8d, r8d; dwFlags
0x1800273ef  lea     rdx, [rsp+270h+Name]; lpName
0x1800273f4  xor     ecx, ecx; lpMutexAttributes
0x1800273f6  call    cs:__imp_CreateMutexExW
0x1800273fc  mov     rdx, rax
0x1800273ff  lea     rcx, [rsp+270h+var_240]
0x180027404  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180027409  cmp     [rsp+270h+var_240], 0
0x18002740f  jnz     short loc_18002742A
0x180027411  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180027416  mov     ebx, eax
0x180027418  lea     rcx, [rsp+270h+var_240]
0x18002741d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027422  nop
0x180027423  mov     eax, ebx
0x180027425  jmp     loc_1800274B6
0x18002742a  lea     rdx, [rsp+270h+var_238]
0x18002742f  lea     rcx, [rsp+270h+var_240]
0x180027434  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180027439  mov     [rsp+270h+var_230], 0
0x180027442  lea     rdx, [rsp+270h+var_230]; void **
0x180027447  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002744c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180027451  mov     ebx, eax
0x180027453  test    eax, eax
0x180027455  jns     short loc_18002748B
0x180027457  mov     rcx, [rbp+178h]; this
0x18002745e  mov     r9d, eax; char *
0x180027461  lea     r8, aWil; "wil"
0x180027468  mov     edx, 12Eh; void *
0x18002746d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027472  nop
0x180027473  lea     rcx, [rsp+270h+var_238]
0x180027478  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002747d  nop
0x18002747e  lea     rcx, [rsp+270h+var_240]
0x180027483  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027488  nop
0x180027489  jmp     short loc_180027423
0x18002748b  mov     rcx, [rsp+270h+var_230]
0x180027490  test    rcx, rcx
0x180027493  jz      short loc_1800274DA
0x180027495  mov     [rdi], rcx
0x180027498  mov     eax, [rcx]
0x18002749a  inc     eax
0x18002749c  mov     [rcx], eax
0x18002749e  lea     rcx, [rsp+270h+var_238]
0x1800274a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800274a8  nop
0x1800274a9  lea     rcx, [rsp+270h+var_240]
0x1800274ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800274b3  nop
0x1800274b4  xor     eax, eax
0x1800274b6  mov     rcx, [rbp+170h+var_10]
0x1800274bd  xor     rcx, rsp; StackCookie
0x1800274c0  call    __security_check_cookie
0x1800274c5  lea     r11, [rsp+270h+var_s0]
0x1800274cd  mov     rbx, [r11+20h]
0x1800274d1  mov     rdi, [r11+28h]
0x1800274d5  mov     rsp, r11
0x1800274d8  pop     rbp
0x1800274d9  retn
0x1800274da  mov     r8, rdi
0x1800274dd  lea     rdx, [rsp+270h+var_240]
0x1800274e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800274e7  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800274ec  mov     ebx, eax
0x1800274ee  test    eax, eax
0x1800274f0  jns     short loc_18002749E
0x1800274f2  mov     rcx, [rbp+178h]; this
0x1800274f9  mov     r9d, eax; char *
0x1800274fc  lea     r8, aWil; "wil"
0x180027503  mov     edx, 137h; void *
0x180027508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002750d  nop
0x18002750e  lea     rcx, [rsp+270h+var_238]
0x180027513  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027518  nop
0x180027519  lea     rcx, [rsp+270h+var_240]
0x18002751e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027523  nop
0x180027524  jmp     loc_180027423
```
