# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180036b44`
- end: `0x180036d02`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180037360`

## callees

- `0x180006f60`
- `0x180009004`
- `0x180009024`
- `0x180009dcc`
- `0x18000b014`
- `0x18000b5dc`
- `0x18000b878`
- `0x18000be08`
- `0x18000c354`
- `0x180036b44`
- `0x1800376d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180036bc8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180036bc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036b7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036b7c`

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
0x180036b44  mov     [rsp-8+arg_10], rbx
0x180036b49  mov     [rsp-8+arg_18], rdi
0x180036b4e  push    rbp
0x180036b4f  lea     rbp, [rsp-170h]
0x180036b57  sub     rsp, 270h
0x180036b5e  mov     rax, cs:__security_cookie
0x180036b65  xor     rax, rsp
0x180036b68  mov     [rbp+170h+var_10], rax
0x180036b6f  mov     rdi, rdx
0x180036b72  mov     rbx, rcx
0x180036b75  mov     qword ptr [rdx], 0
0x180036b7c  call    cs:__imp_GetCurrentProcessId
0x180036b83  nop     dword ptr [rax+rax+00h]
0x180036b88  mov     r9d, eax
0x180036b8b  mov     [rsp+270h+var_248], rbx
0x180036b90  mov     [rsp+270h+var_250], 130h; int
0x180036b98  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180036b9f  mov     edx, 104h; unsigned __int64
0x180036ba4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180036ba9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036bae  nop
0x180036baf  mov     [rsp+270h+var_240], 0
0x180036bb8  mov     r9d, 1F0001h; dwDesiredAccess
0x180036bbe  xor     r8d, r8d; dwFlags
0x180036bc1  lea     rdx, [rsp+270h+Name]; lpName
0x180036bc6  xor     ecx, ecx; lpMutexAttributes
0x180036bc8  call    cs:__imp_CreateMutexExW
0x180036bcf  nop     dword ptr [rax+rax+00h]
0x180036bd4  mov     rdx, rax
0x180036bd7  lea     rcx, [rsp+270h+var_240]
0x180036bdc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180036be1  cmp     [rsp+270h+var_240], 0
0x180036be7  jnz     short loc_180036C02
0x180036be9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180036bee  mov     ebx, eax
0x180036bf0  lea     rcx, [rsp+270h+var_240]
0x180036bf5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036bfa  nop
0x180036bfb  mov     eax, ebx
0x180036bfd  jmp     loc_180036C8E
0x180036c02  lea     rdx, [rsp+270h+var_238]
0x180036c07  lea     rcx, [rsp+270h+var_240]
0x180036c0c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180036c11  mov     [rsp+270h+var_230], 0
0x180036c1a  lea     rdx, [rsp+270h+var_230]; void **
0x180036c1f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180036c24  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180036c29  mov     ebx, eax
0x180036c2b  test    eax, eax
0x180036c2d  jns     short loc_180036C63
0x180036c2f  mov     rcx, [rbp+178h]; this
0x180036c36  mov     r9d, eax; char *
0x180036c39  lea     r8, aWil; "wil"
0x180036c40  mov     edx, 12Eh; void *
0x180036c45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036c4a  nop
0x180036c4b  lea     rcx, [rsp+270h+var_238]
0x180036c50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036c55  nop
0x180036c56  lea     rcx, [rsp+270h+var_240]
0x180036c5b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036c60  nop
0x180036c61  jmp     short loc_180036BFB
0x180036c63  mov     rcx, [rsp+270h+var_230]
0x180036c68  test    rcx, rcx
0x180036c6b  jz      short loc_180036CB3
0x180036c6d  mov     [rdi], rcx
0x180036c70  mov     eax, [rcx]
0x180036c72  inc     eax
0x180036c74  mov     [rcx], eax
0x180036c76  lea     rcx, [rsp+270h+var_238]
0x180036c7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036c80  nop
0x180036c81  lea     rcx, [rsp+270h+var_240]
0x180036c86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036c8b  nop
0x180036c8c  xor     eax, eax
0x180036c8e  mov     rcx, [rbp+170h+var_10]
0x180036c95  xor     rcx, rsp; StackCookie
0x180036c98  call    __security_check_cookie
0x180036c9d  lea     r11, [rsp+270h+var_s0]
0x180036ca5  mov     rbx, [r11+20h]
0x180036ca9  mov     rdi, [r11+28h]
0x180036cad  mov     rsp, r11
0x180036cb0  pop     rbp
0x180036cb1  retn
0x180036cb3  mov     r8, rdi
0x180036cb6  lea     rdx, [rsp+270h+var_240]
0x180036cbb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180036cc0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180036cc5  mov     ebx, eax
0x180036cc7  test    eax, eax
0x180036cc9  jns     short loc_180036C76
0x180036ccb  mov     rcx, [rbp+178h]; this
0x180036cd2  mov     r9d, eax; char *
0x180036cd5  lea     r8, aWil; "wil"
0x180036cdc  mov     edx, 137h; void *
0x180036ce1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036ce6  nop
0x180036ce7  lea     rcx, [rsp+270h+var_238]
0x180036cec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036cf1  nop
0x180036cf2  lea     rcx, [rsp+270h+var_240]
0x180036cf7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036cfc  nop
0x180036cfd  jmp     loc_180036BFB
```
