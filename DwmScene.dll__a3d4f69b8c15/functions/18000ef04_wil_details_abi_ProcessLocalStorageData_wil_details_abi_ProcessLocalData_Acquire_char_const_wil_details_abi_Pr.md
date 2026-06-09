# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000ef04`
- end: `0x18000f0ae`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000fa68`

## callees

- `0x18000ca90`
- `0x18000ed34`
- `0x18000ed50`
- `0x18000ef04`
- `0x18000f7d8`
- `0x1800101dc`
- `0x180010734`
- `0x180010ce4`
- `0x180010eec`
- `0x180011328`
- `0x18001142c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ef81`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ef81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ef3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ef3c`

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
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000ef04  mov     [rsp-8+arg_10], rbx
0x18000ef09  mov     [rsp-8+arg_18], rdi
0x18000ef0e  push    rbp
0x18000ef0f  lea     rbp, [rsp-170h]
0x18000ef17  sub     rsp, 270h
0x18000ef1e  mov     rax, cs:__security_cookie
0x18000ef25  xor     rax, rsp
0x18000ef28  mov     [rbp+170h+var_10], rax
0x18000ef2f  mov     rdi, rdx
0x18000ef32  mov     qword ptr [rdx], 0
0x18000ef39  mov     rbx, rcx
0x18000ef3c  call    cs:__imp_GetCurrentProcessId
0x18000ef42  mov     [rsp+270h+var_248], rbx
0x18000ef47  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000ef4e  mov     r9d, eax
0x18000ef51  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000ef59  mov     edx, 104h; unsigned __int64
0x18000ef5e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000ef63  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000ef68  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ef6e  mov     [rsp+270h+var_240], 0
0x18000ef77  xor     r8d, r8d; dwFlags
0x18000ef7a  lea     rdx, [rsp+270h+Name]; lpName
0x18000ef7f  xor     ecx, ecx; lpMutexAttributes
0x18000ef81  call    cs:__imp_CreateMutexExW
0x18000ef87  mov     rdx, rax
0x18000ef8a  lea     rcx, [rsp+270h+var_240]
0x18000ef8f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ef94  cmp     [rsp+270h+var_240], 0
0x18000ef9a  jnz     short loc_18000EFA8
0x18000ef9c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000efa1  mov     ebx, eax
0x18000efa3  jmp     loc_18000F059
0x18000efa8  lea     rdx, [rsp+270h+var_238]
0x18000efad  lea     rcx, [rsp+270h+var_240]
0x18000efb2  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000efb7  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000efbc  mov     [rsp+270h+var_230], 0
0x18000efc5  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000efca  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000efcf  mov     ebx, eax
0x18000efd1  test    eax, eax
0x18000efd3  jns     short loc_18000F032
0x18000efd5  mov     rcx, [rbp+178h]; this
0x18000efdc  lea     r8, aWil; "wil"
0x18000efe3  mov     r9d, eax; char *
0x18000efe6  mov     edx, 66h ; 'f'; void *
0x18000efeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eff0  mov     rcx, [rbp+178h]; this
0x18000eff7  lea     r8, aWil; "wil"
0x18000effe  mov     r9d, ebx; char *
0x18000f001  mov     edx, 6Fh ; 'o'; void *
0x18000f006  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f00b  mov     r9d, ebx; char *
0x18000f00e  mov     edx, 12Eh; void *
0x18000f013  mov     rcx, [rbp+178h]; this
0x18000f01a  lea     r8, aWil; "wil"
0x18000f021  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f026  lea     rcx, [rsp+270h+var_238]
0x18000f02b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f030  jmp     short loc_18000F059
0x18000f032  mov     rax, [rsp+270h+var_230]
0x18000f037  lea     rcx, ds:0[rax*4]
0x18000f03f  test    rcx, rcx
0x18000f042  jz      short loc_18000F089
0x18000f044  mov     [rdi], rcx
0x18000f047  mov     eax, [rcx]
0x18000f049  inc     eax
0x18000f04b  mov     [rcx], eax
0x18000f04d  lea     rcx, [rsp+270h+var_238]
0x18000f052  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f057  xor     ebx, ebx
0x18000f059  lea     rcx, [rsp+270h+var_240]
0x18000f05e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f063  mov     eax, ebx
0x18000f065  mov     rcx, [rbp+170h+var_10]
0x18000f06c  xor     rcx, rsp; StackCookie
0x18000f06f  call    __security_check_cookie
0x18000f074  lea     r11, [rsp+270h+var_s0]
0x18000f07c  mov     rbx, [r11+20h]
0x18000f080  mov     rdi, [r11+28h]
0x18000f084  mov     rsp, r11
0x18000f087  pop     rbp
0x18000f088  retn
0x18000f089  mov     r8, rdi
0x18000f08c  lea     rdx, [rsp+270h+var_240]
0x18000f091  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000f096  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000f09b  mov     ebx, eax
0x18000f09d  test    eax, eax
0x18000f09f  jns     short loc_18000F04D
0x18000f0a1  mov     r9d, eax
0x18000f0a4  mov     edx, 137h
0x18000f0a9  jmp     loc_18000F013
```
