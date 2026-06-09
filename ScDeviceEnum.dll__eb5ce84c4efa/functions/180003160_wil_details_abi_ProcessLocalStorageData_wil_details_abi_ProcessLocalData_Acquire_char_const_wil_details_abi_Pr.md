# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003160`
- end: `0x1800032f5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180003c78`

## callees

- `0x18000302c`
- `0x180003048`
- `0x180003160`
- `0x1800039d8`
- `0x1800043b4`
- `0x180004a44`
- `0x180004f98`
- `0x180005110`
- `0x1800056ac`
- `0x180005c04`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800031dd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800031dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003198`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003198`

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
0x180003160  mov     [rsp-8+arg_10], rbx
0x180003165  mov     [rsp-8+arg_18], rdi
0x18000316a  push    rbp
0x18000316b  lea     rbp, [rsp-170h]
0x180003173  sub     rsp, 270h
0x18000317a  mov     rax, cs:__security_cookie
0x180003181  xor     rax, rsp
0x180003184  mov     [rbp+170h+var_10], rax
0x18000318b  mov     rdi, rdx
0x18000318e  mov     qword ptr [rdx], 0
0x180003195  mov     rbx, rcx
0x180003198  call    cs:__imp_GetCurrentProcessId
0x18000319e  mov     [rsp+270h+var_248], rbx
0x1800031a3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800031aa  mov     r9d, eax
0x1800031ad  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800031b5  mov     edx, 104h; unsigned __int64
0x1800031ba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800031bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800031c4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800031ca  mov     [rsp+270h+var_240], 0
0x1800031d3  xor     r8d, r8d; dwFlags
0x1800031d6  lea     rdx, [rsp+270h+Name]; lpName
0x1800031db  xor     ecx, ecx; lpMutexAttributes
0x1800031dd  call    cs:__imp_CreateMutexExW
0x1800031e3  mov     rdx, rax
0x1800031e6  lea     rcx, [rsp+270h+var_240]
0x1800031eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800031f0  cmp     [rsp+270h+var_240], 0
0x1800031f6  jnz     short loc_180003204
0x1800031f8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800031fd  mov     ebx, eax
0x1800031ff  jmp     loc_1800032A0
0x180003204  lea     rdx, [rsp+270h+var_238]
0x180003209  lea     rcx, [rsp+270h+var_240]
0x18000320e  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003213  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180003218  mov     [rsp+270h+var_230], 0
0x180003221  lea     rcx, [rsp+270h+Name]; pszSrc
0x180003226  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000322b  mov     ebx, eax
0x18000322d  test    eax, eax
0x18000322f  jns     short loc_180003279
0x180003231  mov     rcx, [rbp+178h]; this
0x180003238  mov     r9d, eax; char *
0x18000323b  mov     edx, 66h ; 'f'; void *
0x180003240  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003245  mov     rcx, [rbp+178h]; this
0x18000324c  mov     r9d, ebx; char *
0x18000324f  mov     edx, 6Fh ; 'o'; void *
0x180003254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003259  mov     r9d, ebx; char *
0x18000325c  mov     edx, 12Eh; void *
0x180003261  mov     rcx, [rbp+178h]; this
0x180003268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000326d  lea     rcx, [rsp+270h+var_238]
0x180003272  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003277  jmp     short loc_1800032A0
0x180003279  mov     rax, [rsp+270h+var_230]
0x18000327e  lea     rcx, ds:0[rax*4]
0x180003286  test    rcx, rcx
0x180003289  jz      short loc_1800032D0
0x18000328b  mov     [rdi], rcx
0x18000328e  mov     eax, [rcx]
0x180003290  inc     eax
0x180003292  mov     [rcx], eax
0x180003294  lea     rcx, [rsp+270h+var_238]
0x180003299  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000329e  xor     ebx, ebx
0x1800032a0  lea     rcx, [rsp+270h+var_240]
0x1800032a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800032aa  mov     eax, ebx
0x1800032ac  mov     rcx, [rbp+170h+var_10]
0x1800032b3  xor     rcx, rsp; StackCookie
0x1800032b6  call    __security_check_cookie
0x1800032bb  lea     r11, [rsp+270h+var_s0]
0x1800032c3  mov     rbx, [r11+20h]
0x1800032c7  mov     rdi, [r11+28h]
0x1800032cb  mov     rsp, r11
0x1800032ce  pop     rbp
0x1800032cf  retn
0x1800032d0  mov     r8, rdi
0x1800032d3  lea     rdx, [rsp+270h+var_240]
0x1800032d8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800032dd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800032e2  mov     ebx, eax
0x1800032e4  test    eax, eax
0x1800032e6  jns     short loc_180003294
0x1800032e8  mov     r9d, eax
0x1800032eb  mov     edx, 137h
0x1800032f0  jmp     loc_180003261
```
