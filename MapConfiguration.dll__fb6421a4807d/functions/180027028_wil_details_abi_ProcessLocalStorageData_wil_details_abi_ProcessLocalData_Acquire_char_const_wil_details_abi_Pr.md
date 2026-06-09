# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180027028`
- end: `0x1800271bd`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002784c`

## callees

- `0x1800094a0`
- `0x180026f2c`
- `0x180026f48`
- `0x180027028`
- `0x1800275ac`
- `0x180027a5c`
- `0x180027e74`
- `0x1800283fc`
- `0x1800284e8`
- `0x180028790`
- `0x180028894`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027060`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027060`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800270a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800270a5`

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
0x180027028  mov     [rsp-8+arg_10], rbx
0x18002702d  mov     [rsp-8+arg_18], rdi
0x180027032  push    rbp
0x180027033  lea     rbp, [rsp-170h]
0x18002703b  sub     rsp, 270h
0x180027042  mov     rax, cs:__security_cookie
0x180027049  xor     rax, rsp
0x18002704c  mov     [rbp+170h+var_10], rax
0x180027053  mov     rdi, rdx
0x180027056  mov     qword ptr [rdx], 0
0x18002705d  mov     rbx, rcx
0x180027060  call    cs:__imp_GetCurrentProcessId
0x180027066  mov     [rsp+270h+var_248], rbx
0x18002706b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180027072  mov     r9d, eax
0x180027075  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002707d  mov     edx, 104h; unsigned __int64
0x180027082  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180027087  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002708c  mov     r9d, 1F0001h; dwDesiredAccess
0x180027092  mov     [rsp+270h+var_240], 0
0x18002709b  xor     r8d, r8d; dwFlags
0x18002709e  lea     rdx, [rsp+270h+Name]; lpName
0x1800270a3  xor     ecx, ecx; lpMutexAttributes
0x1800270a5  call    cs:__imp_CreateMutexExW
0x1800270ab  mov     rdx, rax
0x1800270ae  lea     rcx, [rsp+270h+var_240]
0x1800270b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800270b8  cmp     [rsp+270h+var_240], 0
0x1800270be  jnz     short loc_1800270CC
0x1800270c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800270c5  mov     ebx, eax
0x1800270c7  jmp     loc_180027168
0x1800270cc  lea     rdx, [rsp+270h+var_238]
0x1800270d1  lea     rcx, [rsp+270h+var_240]
0x1800270d6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800270db  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800270e0  mov     [rsp+270h+var_230], 0
0x1800270e9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800270ee  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800270f3  mov     ebx, eax
0x1800270f5  test    eax, eax
0x1800270f7  jns     short loc_180027141
0x1800270f9  mov     rcx, [rbp+178h]; this
0x180027100  mov     r9d, eax; char *
0x180027103  mov     edx, 66h ; 'f'; void *
0x180027108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002710d  mov     rcx, [rbp+178h]; this
0x180027114  mov     r9d, ebx; char *
0x180027117  mov     edx, 6Fh ; 'o'; void *
0x18002711c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027121  mov     r9d, ebx; char *
0x180027124  mov     edx, 12Eh; void *
0x180027129  mov     rcx, [rbp+178h]; this
0x180027130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027135  lea     rcx, [rsp+270h+var_238]
0x18002713a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002713f  jmp     short loc_180027168
0x180027141  mov     rax, [rsp+270h+var_230]
0x180027146  lea     rcx, ds:0[rax*4]
0x18002714e  test    rcx, rcx
0x180027151  jz      short loc_180027198
0x180027153  mov     [rdi], rcx
0x180027156  mov     eax, [rcx]
0x180027158  inc     eax
0x18002715a  mov     [rcx], eax
0x18002715c  lea     rcx, [rsp+270h+var_238]
0x180027161  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027166  xor     ebx, ebx
0x180027168  lea     rcx, [rsp+270h+var_240]
0x18002716d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027172  mov     eax, ebx
0x180027174  mov     rcx, [rbp+170h+var_10]
0x18002717b  xor     rcx, rsp; StackCookie
0x18002717e  call    __security_check_cookie
0x180027183  lea     r11, [rsp+270h+var_s0]
0x18002718b  mov     rbx, [r11+20h]
0x18002718f  mov     rdi, [r11+28h]
0x180027193  mov     rsp, r11
0x180027196  pop     rbp
0x180027197  retn
0x180027198  mov     r8, rdi
0x18002719b  lea     rdx, [rsp+270h+var_240]
0x1800271a0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800271a5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800271aa  mov     ebx, eax
0x1800271ac  test    eax, eax
0x1800271ae  jns     short loc_18002715C
0x1800271b0  mov     r9d, eax
0x1800271b3  mov     edx, 137h
0x1800271b8  jmp     loc_180027129
```
