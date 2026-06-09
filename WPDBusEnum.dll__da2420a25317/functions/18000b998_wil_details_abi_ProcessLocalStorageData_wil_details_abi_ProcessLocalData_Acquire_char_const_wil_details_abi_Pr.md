# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000b998`
- end: `0x18000bb2d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c490`

## callees

- `0x180001730`
- `0x18000908c`
- `0x1800097d0`
- `0x18000b870`
- `0x18000b88c`
- `0x18000b998`
- `0x18000c9ac`
- `0x18000ce54`
- `0x18000d4b8`
- `0x18000d878`
- `0x18000d9e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ba15`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ba15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b9d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b9d0`

## pseudocode

```c
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
0x18000b998  mov     [rsp-8+arg_10], rbx
0x18000b99d  mov     [rsp-8+arg_18], rdi
0x18000b9a2  push    rbp
0x18000b9a3  lea     rbp, [rsp-170h]
0x18000b9ab  sub     rsp, 270h
0x18000b9b2  mov     rax, cs:__security_cookie
0x18000b9b9  xor     rax, rsp
0x18000b9bc  mov     [rbp+170h+var_10], rax
0x18000b9c3  mov     rdi, rdx
0x18000b9c6  mov     qword ptr [rdx], 0
0x18000b9cd  mov     rbx, rcx
0x18000b9d0  call    cs:__imp_GetCurrentProcessId
0x18000b9d6  mov     [rsp+270h+var_248], rbx
0x18000b9db  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b9e2  mov     r9d, eax
0x18000b9e5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000b9ed  mov     edx, 104h; unsigned __int64
0x18000b9f2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b9f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b9fc  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ba02  mov     [rsp+270h+var_240], 0
0x18000ba0b  xor     r8d, r8d; dwFlags
0x18000ba0e  lea     rdx, [rsp+270h+Name]; lpName
0x18000ba13  xor     ecx, ecx; lpMutexAttributes
0x18000ba15  call    cs:__imp_CreateMutexExW
0x18000ba1b  mov     rdx, rax
0x18000ba1e  lea     rcx, [rsp+270h+var_240]
0x18000ba23  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ba28  cmp     [rsp+270h+var_240], 0
0x18000ba2e  jnz     short loc_18000BA3C
0x18000ba30  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ba35  mov     ebx, eax
0x18000ba37  jmp     loc_18000BAD8
0x18000ba3c  lea     rdx, [rsp+270h+var_238]
0x18000ba41  lea     rcx, [rsp+270h+var_240]
0x18000ba46  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000ba4b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000ba50  mov     [rsp+270h+var_230], 0
0x18000ba59  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000ba5e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000ba63  mov     ebx, eax
0x18000ba65  test    eax, eax
0x18000ba67  jns     short loc_18000BAB1
0x18000ba69  mov     rcx, [rbp+178h]; this
0x18000ba70  mov     r9d, eax; char *
0x18000ba73  mov     edx, 66h ; 'f'; void *
0x18000ba78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba7d  mov     rcx, [rbp+178h]; this
0x18000ba84  mov     r9d, ebx; char *
0x18000ba87  mov     edx, 6Fh ; 'o'; void *
0x18000ba8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba91  mov     r9d, ebx; char *
0x18000ba94  mov     edx, 12Eh; void *
0x18000ba99  mov     rcx, [rbp+178h]; this
0x18000baa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000baa5  lea     rcx, [rsp+270h+var_238]
0x18000baaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000baaf  jmp     short loc_18000BAD8
0x18000bab1  mov     rax, [rsp+270h+var_230]
0x18000bab6  lea     rcx, ds:0[rax*4]
0x18000babe  test    rcx, rcx
0x18000bac1  jz      short loc_18000BB08
0x18000bac3  mov     [rdi], rcx
0x18000bac6  mov     eax, [rcx]
0x18000bac8  inc     eax
0x18000baca  mov     [rcx], eax
0x18000bacc  lea     rcx, [rsp+270h+var_238]
0x18000bad1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bad6  xor     ebx, ebx
0x18000bad8  lea     rcx, [rsp+270h+var_240]
0x18000badd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bae2  mov     eax, ebx
0x18000bae4  mov     rcx, [rbp+170h+var_10]
0x18000baeb  xor     rcx, rsp; StackCookie
0x18000baee  call    __security_check_cookie
0x18000baf3  lea     r11, [rsp+270h+var_s0]
0x18000bafb  mov     rbx, [r11+20h]
0x18000baff  mov     rdi, [r11+28h]
0x18000bb03  mov     rsp, r11
0x18000bb06  pop     rbp
0x18000bb07  retn
0x18000bb08  mov     r8, rdi
0x18000bb0b  lea     rdx, [rsp+270h+var_240]
0x18000bb10  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000bb15  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000bb1a  mov     ebx, eax
0x18000bb1c  test    eax, eax
0x18000bb1e  jns     short loc_18000BACC
0x18000bb20  mov     r9d, eax
0x18000bb23  mov     edx, 137h
0x18000bb28  jmp     loc_18000BA99
```
