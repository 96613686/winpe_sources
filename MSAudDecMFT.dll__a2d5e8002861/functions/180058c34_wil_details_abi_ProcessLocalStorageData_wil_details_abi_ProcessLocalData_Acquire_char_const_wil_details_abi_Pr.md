# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180058c34`
- end: `0x180058dd9`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005b4c4`

## callees

- `0x18004caf4`
- `0x18004d320`
- `0x180056188`
- `0x180058b14`
- `0x180058b34`
- `0x180058c34`
- `0x18005ba74`
- `0x18005c408`
- `0x18005c7a4`
- `0x18005cd00`
- `0x18005ce40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180058c6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180058c6c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180058cb7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180058cb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180058c34  mov     [rsp-8+arg_10], rbx
0x180058c39  mov     [rsp-8+arg_18], rdi
0x180058c3e  push    rbp
0x180058c3f  lea     rbp, [rsp-170h]
0x180058c47  sub     rsp, 270h
0x180058c4e  mov     rax, cs:__security_cookie
0x180058c55  xor     rax, rsp
0x180058c58  mov     [rbp+170h+var_10], rax
0x180058c5f  mov     rdi, rdx
0x180058c62  mov     rbx, rcx
0x180058c65  mov     qword ptr [rdx], 0
0x180058c6c  call    cs:__imp_GetCurrentProcessId
0x180058c73  nop     dword ptr [rax+rax+00h]
0x180058c78  mov     r9d, eax
0x180058c7b  mov     [rsp+270h+var_248], rbx
0x180058c80  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180058c88  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180058c8f  mov     edx, 104h; unsigned __int64
0x180058c94  lea     rcx, [rsp+270h+Name]; Buffer
0x180058c99  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058c9e  mov     [rsp+270h+var_240], 0
0x180058ca7  mov     r9d, 1F0001h; dwDesiredAccess
0x180058cad  xor     r8d, r8d; dwFlags
0x180058cb0  lea     rdx, [rsp+270h+Name]; lpName
0x180058cb5  xor     ecx, ecx; lpMutexAttributes
0x180058cb7  call    cs:__imp_CreateMutexExW
0x180058cbe  nop     dword ptr [rax+rax+00h]
0x180058cc3  mov     rdx, rax
0x180058cc6  lea     rcx, [rsp+270h+var_240]
0x180058ccb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180058cd0  cmp     [rsp+270h+var_240], 0
0x180058cd6  jnz     short loc_180058CE4
0x180058cd8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180058cdd  mov     ebx, eax
0x180058cdf  jmp     loc_180058D82
0x180058ce4  lea     rdx, [rsp+270h+var_238]
0x180058ce9  lea     rcx, [rsp+270h+var_240]
0x180058cee  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180058cf3  nop
0x180058cf4  mov     [rsp+270h+var_230], 0
0x180058cfd  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180058d02  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180058d07  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180058d0c  mov     ebx, eax
0x180058d0e  test    eax, eax
0x180058d10  jns     short loc_180058D5B
0x180058d12  mov     rcx, [rbp+178h]; this
0x180058d19  mov     r9d, eax; char *
0x180058d1c  mov     edx, 66h ; 'f'; void *
0x180058d21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058d26  mov     rcx, [rbp+178h]; this
0x180058d2d  mov     r9d, ebx; char *
0x180058d30  mov     edx, 6Fh ; 'o'; void *
0x180058d35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058d3a  mov     r9d, ebx; char *
0x180058d3d  mov     edx, 12Eh; void *
0x180058d42  mov     rcx, [rbp+178h]; this
0x180058d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058d4e  nop
0x180058d4f  lea     rcx, [rsp+270h+var_238]
0x180058d54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058d59  jmp     short loc_180058D82
0x180058d5b  mov     rax, [rsp+270h+var_230]
0x180058d60  lea     rcx, ds:0[rax*4]
0x180058d68  test    rcx, rcx
0x180058d6b  jz      short loc_180058DB3
0x180058d6d  mov     [rdi], rcx
0x180058d70  mov     eax, [rcx]
0x180058d72  inc     eax
0x180058d74  mov     [rcx], eax
0x180058d76  lea     rcx, [rsp+270h+var_238]
0x180058d7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058d80  xor     ebx, ebx
0x180058d82  lea     rcx, [rsp+270h+var_240]
0x180058d87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058d8c  mov     eax, ebx
0x180058d8e  mov     rcx, [rbp+170h+var_10]
0x180058d95  xor     rcx, rsp; StackCookie
0x180058d98  call    __security_check_cookie
0x180058d9d  lea     r11, [rsp+270h+var_s0]
0x180058da5  mov     rbx, [r11+20h]
0x180058da9  mov     rdi, [r11+28h]
0x180058dad  mov     rsp, r11
0x180058db0  pop     rbp
0x180058db1  retn
0x180058db3  mov     r8, rdi
0x180058db6  lea     rdx, [rsp+270h+var_240]
0x180058dbb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180058dc0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180058dc5  mov     ebx, eax
0x180058dc7  test    eax, eax
0x180058dc9  jns     short loc_180058D76
0x180058dcb  mov     r9d, eax
0x180058dce  mov     edx, 137h
0x180058dd3  jmp     loc_180058D42
```
