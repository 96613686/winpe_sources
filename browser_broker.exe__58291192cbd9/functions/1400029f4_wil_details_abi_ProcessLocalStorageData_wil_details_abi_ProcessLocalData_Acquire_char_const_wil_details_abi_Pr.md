# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400029f4`
- end: `0x140002b89`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140003518`

## callees

- `0x140001600`
- `0x140002974`
- `0x140002990`
- `0x1400029f4`
- `0x140003278`
- `0x140003c80`
- `0x1400040f8`
- `0x140004584`
- `0x140004694`
- `0x140004a4c`
- `0x140004b0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002a71`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002a71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002a2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002a2c`

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
  void *v11; // rdx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  void *v17; // rdx
  _DWORD *v18; // rcx
  int v20; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  wil::details *v23; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v24; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v21 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v23 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v23,
    Mutex);
  if ( v23 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v23,
      &v24);
    v25 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v25, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v12, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v13, (const char *)LastErrorFailHr, v22);
      v15 = LastErrorFailHr;
      v16 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v16, v14, (const char *)v15, v21);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v24,
        v17);
      goto LABEL_9;
    }
    v18 = (_DWORD *)(4 * v25);
    if ( 4 * v25 )
    {
      *a2 = v18;
      ++*v18;
    }
    else
    {
      v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v20;
      if ( v20 < 0 )
      {
        v15 = (unsigned int)v20;
        v16 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v11);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v23,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1400029f4  mov     [rsp-8+arg_10], rbx
0x1400029f9  mov     [rsp-8+arg_18], rdi
0x1400029fe  push    rbp
0x1400029ff  lea     rbp, [rsp-170h]
0x140002a07  sub     rsp, 270h
0x140002a0e  mov     rax, cs:__security_cookie
0x140002a15  xor     rax, rsp
0x140002a18  mov     [rbp+170h+var_10], rax
0x140002a1f  mov     rdi, rdx
0x140002a22  mov     qword ptr [rdx], 0
0x140002a29  mov     rbx, rcx
0x140002a2c  call    cs:__imp_GetCurrentProcessId
0x140002a32  mov     [rsp+270h+var_248], rbx
0x140002a37  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002a3e  mov     r9d, eax
0x140002a41  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140002a49  mov     edx, 104h; unsigned __int64
0x140002a4e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140002a53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002a58  mov     r9d, 1F0001h; dwDesiredAccess
0x140002a5e  mov     [rsp+270h+var_240], 0
0x140002a67  xor     r8d, r8d; dwFlags
0x140002a6a  lea     rdx, [rsp+270h+Name]; lpName
0x140002a6f  xor     ecx, ecx; lpMutexAttributes
0x140002a71  call    cs:__imp_CreateMutexExW
0x140002a77  mov     rdx, rax
0x140002a7a  lea     rcx, [rsp+270h+var_240]
0x140002a7f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140002a84  cmp     [rsp+270h+var_240], 0
0x140002a8a  jnz     short loc_140002A98
0x140002a8c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002a91  mov     ebx, eax
0x140002a93  jmp     loc_140002B34
0x140002a98  lea     rdx, [rsp+270h+var_238]
0x140002a9d  lea     rcx, [rsp+270h+var_240]
0x140002aa2  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140002aa7  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x140002aac  mov     [rsp+270h+var_230], 0
0x140002ab5  lea     rcx, [rsp+270h+Name]; pszSrc
0x140002aba  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140002abf  mov     ebx, eax
0x140002ac1  test    eax, eax
0x140002ac3  jns     short loc_140002B0D
0x140002ac5  mov     rcx, [rbp+178h]; this
0x140002acc  mov     r9d, eax; char *
0x140002acf  mov     edx, 66h ; 'f'; void *
0x140002ad4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002ad9  mov     rcx, [rbp+178h]; this
0x140002ae0  mov     r9d, ebx; char *
0x140002ae3  mov     edx, 6Fh ; 'o'; void *
0x140002ae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002aed  mov     r9d, ebx; char *
0x140002af0  mov     edx, 12Eh; void *
0x140002af5  mov     rcx, [rbp+178h]; this
0x140002afc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002b01  lea     rcx, [rsp+270h+var_238]
0x140002b06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140002b0b  jmp     short loc_140002B34
0x140002b0d  mov     rax, [rsp+270h+var_230]
0x140002b12  lea     rcx, ds:0[rax*4]
0x140002b1a  test    rcx, rcx
0x140002b1d  jz      short loc_140002B64
0x140002b1f  mov     [rdi], rcx
0x140002b22  mov     eax, [rcx]
0x140002b24  inc     eax
0x140002b26  mov     [rcx], eax
0x140002b28  lea     rcx, [rsp+270h+var_238]
0x140002b2d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140002b32  xor     ebx, ebx
0x140002b34  lea     rcx, [rsp+270h+var_240]
0x140002b39  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140002b3e  mov     eax, ebx
0x140002b40  mov     rcx, [rbp+170h+var_10]
0x140002b47  xor     rcx, rsp; StackCookie
0x140002b4a  call    __security_check_cookie
0x140002b4f  lea     r11, [rsp+270h+var_s0]
0x140002b57  mov     rbx, [r11+20h]
0x140002b5b  mov     rdi, [r11+28h]
0x140002b5f  mov     rsp, r11
0x140002b62  pop     rbp
0x140002b63  retn
0x140002b64  mov     r8, rdi
0x140002b67  lea     rdx, [rsp+270h+var_240]
0x140002b6c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140002b71  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140002b76  mov     ebx, eax
0x140002b78  test    eax, eax
0x140002b7a  jns     short loc_140002B28
0x140002b7c  mov     r9d, eax
0x140002b7f  mov     edx, 137h
0x140002b84  jmp     loc_140002AF5
```
