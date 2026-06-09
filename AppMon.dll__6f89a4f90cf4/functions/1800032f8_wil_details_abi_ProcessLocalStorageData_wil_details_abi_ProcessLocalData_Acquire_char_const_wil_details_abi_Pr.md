# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800032f8`
- end: `0x18000348d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180003de8`

## callees

- `0x180001620`
- `0x1800031a8`
- `0x1800031c4`
- `0x1800032f8`
- `0x180003b48`
- `0x180004508`
- `0x180004bd4`
- `0x18000516c`
- `0x180005328`
- `0x180005638`
- `0x180005728`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003375`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003375`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003330`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003330`

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
0x1800032f8  mov     [rsp-8+arg_10], rbx
0x1800032fd  mov     [rsp-8+arg_18], rdi
0x180003302  push    rbp
0x180003303  lea     rbp, [rsp-170h]
0x18000330b  sub     rsp, 270h
0x180003312  mov     rax, cs:__security_cookie
0x180003319  xor     rax, rsp
0x18000331c  mov     [rbp+170h+var_10], rax
0x180003323  mov     rdi, rdx
0x180003326  mov     qword ptr [rdx], 0
0x18000332d  mov     rbx, rcx
0x180003330  call    cs:__imp_GetCurrentProcessId
0x180003336  mov     [rsp+270h+var_248], rbx
0x18000333b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003342  mov     r9d, eax
0x180003345  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000334d  mov     edx, 104h; unsigned __int64
0x180003352  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003357  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000335c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003362  mov     [rsp+270h+var_240], 0
0x18000336b  xor     r8d, r8d; dwFlags
0x18000336e  lea     rdx, [rsp+270h+Name]; lpName
0x180003373  xor     ecx, ecx; lpMutexAttributes
0x180003375  call    cs:__imp_CreateMutexExW
0x18000337b  mov     rdx, rax
0x18000337e  lea     rcx, [rsp+270h+var_240]
0x180003383  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003388  cmp     [rsp+270h+var_240], 0
0x18000338e  jnz     short loc_18000339C
0x180003390  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003395  mov     ebx, eax
0x180003397  jmp     loc_180003438
0x18000339c  lea     rdx, [rsp+270h+var_238]
0x1800033a1  lea     rcx, [rsp+270h+var_240]
0x1800033a6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800033ab  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800033b0  mov     [rsp+270h+var_230], 0
0x1800033b9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800033be  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800033c3  mov     ebx, eax
0x1800033c5  test    eax, eax
0x1800033c7  jns     short loc_180003411
0x1800033c9  mov     rcx, [rbp+178h]; this
0x1800033d0  mov     r9d, eax; char *
0x1800033d3  mov     edx, 66h ; 'f'; void *
0x1800033d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033dd  mov     rcx, [rbp+178h]; this
0x1800033e4  mov     r9d, ebx; char *
0x1800033e7  mov     edx, 6Fh ; 'o'; void *
0x1800033ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033f1  mov     r9d, ebx; char *
0x1800033f4  mov     edx, 12Eh; void *
0x1800033f9  mov     rcx, [rbp+178h]; this
0x180003400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003405  lea     rcx, [rsp+270h+var_238]
0x18000340a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000340f  jmp     short loc_180003438
0x180003411  mov     rax, [rsp+270h+var_230]
0x180003416  lea     rcx, ds:0[rax*4]
0x18000341e  test    rcx, rcx
0x180003421  jz      short loc_180003468
0x180003423  mov     [rdi], rcx
0x180003426  mov     eax, [rcx]
0x180003428  inc     eax
0x18000342a  mov     [rcx], eax
0x18000342c  lea     rcx, [rsp+270h+var_238]
0x180003431  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003436  xor     ebx, ebx
0x180003438  lea     rcx, [rsp+270h+var_240]
0x18000343d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003442  mov     eax, ebx
0x180003444  mov     rcx, [rbp+170h+var_10]
0x18000344b  xor     rcx, rsp; StackCookie
0x18000344e  call    __security_check_cookie
0x180003453  lea     r11, [rsp+270h+var_s0]
0x18000345b  mov     rbx, [r11+20h]
0x18000345f  mov     rdi, [r11+28h]
0x180003463  mov     rsp, r11
0x180003466  pop     rbp
0x180003467  retn
0x180003468  mov     r8, rdi
0x18000346b  lea     rdx, [rsp+270h+var_240]
0x180003470  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003475  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000347a  mov     ebx, eax
0x18000347c  test    eax, eax
0x18000347e  jns     short loc_18000342C
0x180003480  mov     r9d, eax
0x180003483  mov     edx, 137h
0x180003488  jmp     loc_1800033F9
```
