# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000f0a4`
- end: `0x18000f239`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000fbc8`

## callees

- `0x18000d090`
- `0x18000ef38`
- `0x18000ef54`
- `0x18000f0a4`
- `0x18000f928`
- `0x180010304`
- `0x180010994`
- `0x180010ee8`
- `0x180011058`
- `0x1800113ec`
- `0x1800114f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f121`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f121`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f0dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f0dc`

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
0x18000f0a4  mov     [rsp-8+arg_10], rbx
0x18000f0a9  mov     [rsp-8+arg_18], rdi
0x18000f0ae  push    rbp
0x18000f0af  lea     rbp, [rsp-170h]
0x18000f0b7  sub     rsp, 270h
0x18000f0be  mov     rax, cs:__security_cookie
0x18000f0c5  xor     rax, rsp
0x18000f0c8  mov     [rbp+170h+var_10], rax
0x18000f0cf  mov     rdi, rdx
0x18000f0d2  mov     qword ptr [rdx], 0
0x18000f0d9  mov     rbx, rcx
0x18000f0dc  call    cs:__imp_GetCurrentProcessId
0x18000f0e2  mov     [rsp+270h+var_248], rbx
0x18000f0e7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000f0ee  mov     r9d, eax
0x18000f0f1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000f0f9  mov     edx, 104h; unsigned __int64
0x18000f0fe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f103  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f108  mov     r9d, 1F0001h; dwDesiredAccess
0x18000f10e  mov     [rsp+270h+var_240], 0
0x18000f117  xor     r8d, r8d; dwFlags
0x18000f11a  lea     rdx, [rsp+270h+Name]; lpName
0x18000f11f  xor     ecx, ecx; lpMutexAttributes
0x18000f121  call    cs:__imp_CreateMutexExW
0x18000f127  mov     rdx, rax
0x18000f12a  lea     rcx, [rsp+270h+var_240]
0x18000f12f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f134  cmp     [rsp+270h+var_240], 0
0x18000f13a  jnz     short loc_18000F148
0x18000f13c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f141  mov     ebx, eax
0x18000f143  jmp     loc_18000F1E4
0x18000f148  lea     rdx, [rsp+270h+var_238]
0x18000f14d  lea     rcx, [rsp+270h+var_240]
0x18000f152  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000f157  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000f15c  mov     [rsp+270h+var_230], 0
0x18000f165  lea     rcx, [rsp+270h+Name]; pszSrc
0x18000f16a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000f16f  mov     ebx, eax
0x18000f171  test    eax, eax
0x18000f173  jns     short loc_18000F1BD
0x18000f175  mov     rcx, [rbp+178h]; this
0x18000f17c  mov     r9d, eax; char *
0x18000f17f  mov     edx, 66h ; 'f'; void *
0x18000f184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f189  mov     rcx, [rbp+178h]; this
0x18000f190  mov     r9d, ebx; char *
0x18000f193  mov     edx, 6Fh ; 'o'; void *
0x18000f198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f19d  mov     r9d, ebx; char *
0x18000f1a0  mov     edx, 12Eh; void *
0x18000f1a5  mov     rcx, [rbp+178h]; this
0x18000f1ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f1b1  lea     rcx, [rsp+270h+var_238]
0x18000f1b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f1bb  jmp     short loc_18000F1E4
0x18000f1bd  mov     rax, [rsp+270h+var_230]
0x18000f1c2  lea     rcx, ds:0[rax*4]
0x18000f1ca  test    rcx, rcx
0x18000f1cd  jz      short loc_18000F214
0x18000f1cf  mov     [rdi], rcx
0x18000f1d2  mov     eax, [rcx]
0x18000f1d4  inc     eax
0x18000f1d6  mov     [rcx], eax
0x18000f1d8  lea     rcx, [rsp+270h+var_238]
0x18000f1dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f1e2  xor     ebx, ebx
0x18000f1e4  lea     rcx, [rsp+270h+var_240]
0x18000f1e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f1ee  mov     eax, ebx
0x18000f1f0  mov     rcx, [rbp+170h+var_10]
0x18000f1f7  xor     rcx, rsp; StackCookie
0x18000f1fa  call    __security_check_cookie
0x18000f1ff  lea     r11, [rsp+270h+var_s0]
0x18000f207  mov     rbx, [r11+20h]
0x18000f20b  mov     rdi, [r11+28h]
0x18000f20f  mov     rsp, r11
0x18000f212  pop     rbp
0x18000f213  retn
0x18000f214  mov     r8, rdi
0x18000f217  lea     rdx, [rsp+270h+var_240]
0x18000f21c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f221  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000f226  mov     ebx, eax
0x18000f228  test    eax, eax
0x18000f22a  jns     short loc_18000F1D8
0x18000f22c  mov     r9d, eax
0x18000f22f  mov     edx, 137h
0x18000f234  jmp     loc_18000F1A5
```
