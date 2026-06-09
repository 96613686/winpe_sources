# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003314`
- end: `0x1800034be`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180003eec`

## callees

- `0x1800019f0`
- `0x180003194`
- `0x1800031b0`
- `0x180003314`
- `0x180003c90`
- `0x180004644`
- `0x180004bd0`
- `0x180004f78`
- `0x180005088`
- `0x180005460`
- `0x1800056a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003391`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003391`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000334c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000334c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v18 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v18,
    Mutex);
  if ( v18 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v18,
      &v19);
    v20 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v17);
      v11 = LastErrorFailHr;
      v12 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)"wil", (const char *)v11, v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
      goto LABEL_9;
    }
    v13 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v13;
      ++*v13;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v15;
      if ( v15 < 0 )
      {
        v11 = (unsigned int)v15;
        v12 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v18,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180003314  mov     [rsp-8+arg_10], rbx
0x180003319  mov     [rsp-8+arg_18], rdi
0x18000331e  push    rbp
0x18000331f  lea     rbp, [rsp-170h]
0x180003327  sub     rsp, 270h
0x18000332e  mov     rax, cs:__security_cookie
0x180003335  xor     rax, rsp
0x180003338  mov     [rbp+170h+var_10], rax
0x18000333f  mov     rdi, rdx
0x180003342  mov     qword ptr [rdx], 0
0x180003349  mov     rbx, rcx
0x18000334c  call    cs:__imp_GetCurrentProcessId
0x180003352  mov     [rsp+270h+var_248], rbx
0x180003357  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000335e  mov     r9d, eax
0x180003361  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003369  mov     edx, 104h; unsigned __int64
0x18000336e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003373  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003378  mov     r9d, 1F0001h; dwDesiredAccess
0x18000337e  mov     [rsp+270h+var_240], 0
0x180003387  xor     r8d, r8d; dwFlags
0x18000338a  lea     rdx, [rsp+270h+Name]; lpName
0x18000338f  xor     ecx, ecx; lpMutexAttributes
0x180003391  call    cs:__imp_CreateMutexExW
0x180003397  mov     rdx, rax
0x18000339a  lea     rcx, [rsp+270h+var_240]
0x18000339f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800033a4  cmp     [rsp+270h+var_240], 0
0x1800033aa  jnz     short loc_1800033B8
0x1800033ac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800033b1  mov     ebx, eax
0x1800033b3  jmp     loc_180003469
0x1800033b8  lea     rdx, [rsp+270h+var_238]
0x1800033bd  lea     rcx, [rsp+270h+var_240]
0x1800033c2  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800033c7  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800033cc  mov     [rsp+270h+var_230], 0
0x1800033d5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800033da  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800033df  mov     ebx, eax
0x1800033e1  test    eax, eax
0x1800033e3  jns     short loc_180003442
0x1800033e5  mov     rcx, [rbp+178h]; this
0x1800033ec  lea     r8, aWil; "wil"
0x1800033f3  mov     r9d, eax; char *
0x1800033f6  mov     edx, 66h ; 'f'; void *
0x1800033fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003400  mov     rcx, [rbp+178h]; this
0x180003407  lea     r8, aWil; "wil"
0x18000340e  mov     r9d, ebx; char *
0x180003411  mov     edx, 6Fh ; 'o'; void *
0x180003416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000341b  mov     r9d, ebx; char *
0x18000341e  mov     edx, 12Eh; void *
0x180003423  mov     rcx, [rbp+178h]; this
0x18000342a  lea     r8, aWil; "wil"
0x180003431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003436  lea     rcx, [rsp+270h+var_238]
0x18000343b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003440  jmp     short loc_180003469
0x180003442  mov     rax, [rsp+270h+var_230]
0x180003447  lea     rcx, ds:0[rax*4]
0x18000344f  test    rcx, rcx
0x180003452  jz      short loc_180003499
0x180003454  mov     [rdi], rcx
0x180003457  mov     eax, [rcx]
0x180003459  inc     eax
0x18000345b  mov     [rcx], eax
0x18000345d  lea     rcx, [rsp+270h+var_238]
0x180003462  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003467  xor     ebx, ebx
0x180003469  lea     rcx, [rsp+270h+var_240]
0x18000346e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003473  mov     eax, ebx
0x180003475  mov     rcx, [rbp+170h+var_10]
0x18000347c  xor     rcx, rsp; StackCookie
0x18000347f  call    __security_check_cookie
0x180003484  lea     r11, [rsp+270h+var_s0]
0x18000348c  mov     rbx, [r11+20h]
0x180003490  mov     rdi, [r11+28h]
0x180003494  mov     rsp, r11
0x180003497  pop     rbp
0x180003498  retn
0x180003499  mov     r8, rdi
0x18000349c  lea     rdx, [rsp+270h+var_240]
0x1800034a1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800034a6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800034ab  mov     ebx, eax
0x1800034ad  test    eax, eax
0x1800034af  jns     short loc_18000345D
0x1800034b1  mov     r9d, eax
0x1800034b4  mov     edx, 137h
0x1800034b9  jmp     loc_180003423
```
