# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004e08`
- end: `0x140004f9d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140005a20`

## callees

- `0x140002210`
- `0x140004b98`
- `0x140004bb4`
- `0x140004e08`
- `0x140005738`
- `0x1400062dc`
- `0x140006a54`
- `0x140007090`
- `0x140007248`
- `0x14000777c`
- `0x140007b34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004e85`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004e85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004e40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004e40`

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
0x140004e08  mov     [rsp-8+arg_10], rbx
0x140004e0d  mov     [rsp-8+arg_18], rdi
0x140004e12  push    rbp
0x140004e13  lea     rbp, [rsp-170h]
0x140004e1b  sub     rsp, 270h
0x140004e22  mov     rax, cs:__security_cookie
0x140004e29  xor     rax, rsp
0x140004e2c  mov     [rbp+170h+var_10], rax
0x140004e33  mov     rdi, rdx
0x140004e36  mov     qword ptr [rdx], 0
0x140004e3d  mov     rbx, rcx
0x140004e40  call    cs:__imp_GetCurrentProcessId
0x140004e46  mov     [rsp+270h+var_248], rbx
0x140004e4b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004e52  mov     r9d, eax
0x140004e55  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140004e5d  mov     edx, 104h; unsigned __int64
0x140004e62  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004e67  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004e6c  mov     r9d, 1F0001h; dwDesiredAccess
0x140004e72  mov     [rsp+270h+var_240], 0
0x140004e7b  xor     r8d, r8d; dwFlags
0x140004e7e  lea     rdx, [rsp+270h+Name]; lpName
0x140004e83  xor     ecx, ecx; lpMutexAttributes
0x140004e85  call    cs:__imp_CreateMutexExW
0x140004e8b  mov     rdx, rax
0x140004e8e  lea     rcx, [rsp+270h+var_240]
0x140004e93  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004e98  cmp     [rsp+270h+var_240], 0
0x140004e9e  jnz     short loc_140004EAC
0x140004ea0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004ea5  mov     ebx, eax
0x140004ea7  jmp     loc_140004F48
0x140004eac  lea     rdx, [rsp+270h+var_238]
0x140004eb1  lea     rcx, [rsp+270h+var_240]
0x140004eb6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140004ebb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x140004ec0  mov     [rsp+270h+var_230], 0
0x140004ec9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004ece  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004ed3  mov     ebx, eax
0x140004ed5  test    eax, eax
0x140004ed7  jns     short loc_140004F21
0x140004ed9  mov     rcx, [rbp+178h]; this
0x140004ee0  mov     r9d, eax; char *
0x140004ee3  mov     edx, 66h ; 'f'; void *
0x140004ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004eed  mov     rcx, [rbp+178h]; this
0x140004ef4  mov     r9d, ebx; char *
0x140004ef7  mov     edx, 6Fh ; 'o'; void *
0x140004efc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004f01  mov     r9d, ebx; char *
0x140004f04  mov     edx, 12Eh; void *
0x140004f09  mov     rcx, [rbp+178h]; this
0x140004f10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004f15  lea     rcx, [rsp+270h+var_238]
0x140004f1a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004f1f  jmp     short loc_140004F48
0x140004f21  mov     rax, [rsp+270h+var_230]
0x140004f26  lea     rcx, ds:0[rax*4]
0x140004f2e  test    rcx, rcx
0x140004f31  jz      short loc_140004F78
0x140004f33  mov     [rdi], rcx
0x140004f36  mov     eax, [rcx]
0x140004f38  inc     eax
0x140004f3a  mov     [rcx], eax
0x140004f3c  lea     rcx, [rsp+270h+var_238]
0x140004f41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004f46  xor     ebx, ebx
0x140004f48  lea     rcx, [rsp+270h+var_240]
0x140004f4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004f52  mov     eax, ebx
0x140004f54  mov     rcx, [rbp+170h+var_10]
0x140004f5b  xor     rcx, rsp; StackCookie
0x140004f5e  call    __security_check_cookie
0x140004f63  lea     r11, [rsp+270h+var_s0]
0x140004f6b  mov     rbx, [r11+20h]
0x140004f6f  mov     rdi, [r11+28h]
0x140004f73  mov     rsp, r11
0x140004f76  pop     rbp
0x140004f77  retn
0x140004f78  mov     r8, rdi
0x140004f7b  lea     rdx, [rsp+270h+var_240]
0x140004f80  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004f85  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140004f8a  mov     ebx, eax
0x140004f8c  test    eax, eax
0x140004f8e  jns     short loc_140004F3C
0x140004f90  mov     r9d, eax
0x140004f93  mov     edx, 137h
0x140004f98  jmp     loc_140004F09
```
