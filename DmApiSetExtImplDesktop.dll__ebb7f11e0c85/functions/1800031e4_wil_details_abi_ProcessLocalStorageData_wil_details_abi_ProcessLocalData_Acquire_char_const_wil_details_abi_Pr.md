# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800031e4`
- end: `0x18000339b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180003eec`

## callees

- `0x180003018`
- `0x180003038`
- `0x1800031e4`
- `0x180003c30`
- `0x1800046f4`
- `0x180004e04`
- `0x1800053c8`
- `0x180005548`
- `0x180005d08`
- `0x180006544`
- `0x180009f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003267`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000321c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000321c`

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
0x1800031e4  mov     [rsp-8+arg_10], rbx
0x1800031e9  mov     [rsp-8+arg_18], rdi
0x1800031ee  push    rbp
0x1800031ef  lea     rbp, [rsp-170h]
0x1800031f7  sub     rsp, 270h
0x1800031fe  mov     rax, cs:__security_cookie
0x180003205  xor     rax, rsp
0x180003208  mov     [rbp+170h+var_10], rax
0x18000320f  mov     rdi, rdx
0x180003212  mov     qword ptr [rdx], 0
0x180003219  mov     rbx, rcx
0x18000321c  call    cs:__imp_GetCurrentProcessId
0x180003223  nop     dword ptr [rax+rax+00h]
0x180003228  mov     [rsp+270h+var_248], rbx
0x18000322d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003234  mov     r9d, eax
0x180003237  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000323f  mov     edx, 104h; unsigned __int64
0x180003244  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003249  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000324e  mov     r9d, 1F0001h; dwDesiredAccess
0x180003254  mov     [rsp+270h+var_240], 0
0x18000325d  xor     r8d, r8d; dwFlags
0x180003260  lea     rdx, [rsp+270h+Name]; lpName
0x180003265  xor     ecx, ecx; lpMutexAttributes
0x180003267  call    cs:__imp_CreateMutexExW
0x18000326e  nop     dword ptr [rax+rax+00h]
0x180003273  mov     rdx, rax
0x180003276  lea     rcx, [rsp+270h+var_240]
0x18000327b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003280  cmp     [rsp+270h+var_240], 0
0x180003286  jnz     short loc_180003294
0x180003288  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000328d  mov     ebx, eax
0x18000328f  jmp     loc_180003345
0x180003294  lea     rdx, [rsp+270h+var_238]
0x180003299  lea     rcx, [rsp+270h+var_240]
0x18000329e  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800032a3  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800032a8  mov     [rsp+270h+var_230], 0
0x1800032b1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800032b6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800032bb  mov     ebx, eax
0x1800032bd  test    eax, eax
0x1800032bf  jns     short loc_18000331E
0x1800032c1  mov     rcx, [rbp+178h]; this
0x1800032c8  lea     r8, aWil; "wil"
0x1800032cf  mov     r9d, eax; char *
0x1800032d2  mov     edx, 66h ; 'f'; void *
0x1800032d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032dc  mov     rcx, [rbp+178h]; this
0x1800032e3  lea     r8, aWil; "wil"
0x1800032ea  mov     r9d, ebx; char *
0x1800032ed  mov     edx, 6Fh ; 'o'; void *
0x1800032f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032f7  mov     r9d, ebx; char *
0x1800032fa  mov     edx, 12Eh; void *
0x1800032ff  mov     rcx, [rbp+178h]; this
0x180003306  lea     r8, aWil; "wil"
0x18000330d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003312  lea     rcx, [rsp+270h+var_238]
0x180003317  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000331c  jmp     short loc_180003345
0x18000331e  mov     rax, [rsp+270h+var_230]
0x180003323  lea     rcx, ds:0[rax*4]
0x18000332b  test    rcx, rcx
0x18000332e  jz      short loc_180003376
0x180003330  mov     [rdi], rcx
0x180003333  mov     eax, [rcx]
0x180003335  inc     eax
0x180003337  mov     [rcx], eax
0x180003339  lea     rcx, [rsp+270h+var_238]
0x18000333e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003343  xor     ebx, ebx
0x180003345  lea     rcx, [rsp+270h+var_240]
0x18000334a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000334f  mov     eax, ebx
0x180003351  mov     rcx, [rbp+170h+var_10]
0x180003358  xor     rcx, rsp; StackCookie
0x18000335b  call    __security_check_cookie
0x180003360  lea     r11, [rsp+270h+var_s0]
0x180003368  mov     rbx, [r11+20h]
0x18000336c  mov     rdi, [r11+28h]
0x180003370  mov     rsp, r11
0x180003373  pop     rbp
0x180003374  retn
0x180003376  mov     r8, rdi
0x180003379  lea     rdx, [rsp+270h+var_240]
0x18000337e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003383  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003388  mov     ebx, eax
0x18000338a  test    eax, eax
0x18000338c  jns     short loc_180003339
0x18000338e  mov     r9d, eax
0x180003391  mov     edx, 137h
0x180003396  jmp     loc_1800032FF
```
