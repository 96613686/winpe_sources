# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004d48`
- end: `0x180004edd`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005988`

## callees

- `0x180004be4`
- `0x180004c00`
- `0x180004d48`
- `0x180005718`
- `0x1800061a0`
- `0x1800067ec`
- `0x180006b28`
- `0x180006ce0`
- `0x18000707c`
- `0x18000713c`
- `0x18000b710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004dc5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004dc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d80`

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
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  _DWORD *v16; // rcx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v19 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v21 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v21,
    Mutex);
  if ( v21 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v21,
      &v22);
    v23 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v23, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v11, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v12, (const char *)LastErrorFailHr, v20);
      v14 = LastErrorFailHr;
      v15 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v15, v13, (const char *)v14, v19);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
      goto LABEL_9;
    }
    v16 = (_DWORD *)(4 * v23);
    if ( 4 * v23 )
    {
      *a2 = v16;
      ++*v16;
    }
    else
    {
      v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v18;
      if ( v18 < 0 )
      {
        v14 = (unsigned int)v18;
        v15 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180004d48  mov     [rsp-8+arg_10], rbx
0x180004d4d  mov     [rsp-8+arg_18], rdi
0x180004d52  push    rbp
0x180004d53  lea     rbp, [rsp-170h]
0x180004d5b  sub     rsp, 270h
0x180004d62  mov     rax, cs:__security_cookie
0x180004d69  xor     rax, rsp
0x180004d6c  mov     [rbp+170h+var_10], rax
0x180004d73  mov     rdi, rdx
0x180004d76  mov     qword ptr [rdx], 0
0x180004d7d  mov     rbx, rcx
0x180004d80  call    cs:__imp_GetCurrentProcessId
0x180004d86  mov     [rsp+270h+var_248], rbx
0x180004d8b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004d92  mov     r9d, eax
0x180004d95  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004d9d  mov     edx, 104h; unsigned __int64
0x180004da2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004da7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004dac  mov     r9d, 1F0001h; dwDesiredAccess
0x180004db2  mov     [rsp+270h+var_240], 0
0x180004dbb  xor     r8d, r8d; dwFlags
0x180004dbe  lea     rdx, [rsp+270h+Name]; lpName
0x180004dc3  xor     ecx, ecx; lpMutexAttributes
0x180004dc5  call    cs:__imp_CreateMutexExW
0x180004dcb  mov     rdx, rax
0x180004dce  lea     rcx, [rsp+270h+var_240]
0x180004dd3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004dd8  cmp     [rsp+270h+var_240], 0
0x180004dde  jnz     short loc_180004DEC
0x180004de0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004de5  mov     ebx, eax
0x180004de7  jmp     loc_180004E88
0x180004dec  lea     rdx, [rsp+270h+var_238]
0x180004df1  lea     rcx, [rsp+270h+var_240]
0x180004df6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004dfb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180004e00  mov     [rsp+270h+var_230], 0
0x180004e09  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004e0e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004e13  mov     ebx, eax
0x180004e15  test    eax, eax
0x180004e17  jns     short loc_180004E61
0x180004e19  mov     rcx, [rbp+178h]; this
0x180004e20  mov     r9d, eax; char *
0x180004e23  mov     edx, 66h ; 'f'; void *
0x180004e28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e2d  mov     rcx, [rbp+178h]; this
0x180004e34  mov     r9d, ebx; char *
0x180004e37  mov     edx, 6Fh ; 'o'; void *
0x180004e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e41  mov     r9d, ebx; char *
0x180004e44  mov     edx, 12Eh; void *
0x180004e49  mov     rcx, [rbp+178h]; this
0x180004e50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e55  lea     rcx, [rsp+270h+var_238]
0x180004e5a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004e5f  jmp     short loc_180004E88
0x180004e61  mov     rax, [rsp+270h+var_230]
0x180004e66  lea     rcx, ds:0[rax*4]
0x180004e6e  test    rcx, rcx
0x180004e71  jz      short loc_180004EB8
0x180004e73  mov     [rdi], rcx
0x180004e76  mov     eax, [rcx]
0x180004e78  inc     eax
0x180004e7a  mov     [rcx], eax
0x180004e7c  lea     rcx, [rsp+270h+var_238]
0x180004e81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004e86  xor     ebx, ebx
0x180004e88  lea     rcx, [rsp+270h+var_240]
0x180004e8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004e92  mov     eax, ebx
0x180004e94  mov     rcx, [rbp+170h+var_10]
0x180004e9b  xor     rcx, rsp; StackCookie
0x180004e9e  call    __security_check_cookie
0x180004ea3  lea     r11, [rsp+270h+var_s0]
0x180004eab  mov     rbx, [r11+20h]
0x180004eaf  mov     rdi, [r11+28h]
0x180004eb3  mov     rsp, r11
0x180004eb6  pop     rbp
0x180004eb7  retn
0x180004eb8  mov     r8, rdi
0x180004ebb  lea     rdx, [rsp+270h+var_240]
0x180004ec0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004ec5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004eca  mov     ebx, eax
0x180004ecc  test    eax, eax
0x180004ece  jns     short loc_180004E7C
0x180004ed0  mov     r9d, eax
0x180004ed3  mov     edx, 137h
0x180004ed8  jmp     loc_180004E49
```
