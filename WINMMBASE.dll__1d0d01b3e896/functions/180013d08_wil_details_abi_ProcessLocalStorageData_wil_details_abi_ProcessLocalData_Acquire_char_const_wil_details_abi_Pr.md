# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180013d08`
- end: `0x180013e9d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800149f0`

## callees

- `0x18000a6fc`
- `0x1800106c0`
- `0x180013b40`
- `0x180013b5c`
- `0x180013d08`
- `0x18001481c`
- `0x180015214`
- `0x180015a94`
- `0x180016158`
- `0x18001657c`
- `0x1800167e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013d40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013d40`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180013d85`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180013d85`

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
0x180013d08  mov     [rsp-8+arg_10], rbx
0x180013d0d  mov     [rsp-8+arg_18], rdi
0x180013d12  push    rbp
0x180013d13  lea     rbp, [rsp-170h]
0x180013d1b  sub     rsp, 270h
0x180013d22  mov     rax, cs:__security_cookie
0x180013d29  xor     rax, rsp
0x180013d2c  mov     [rbp+170h+var_10], rax
0x180013d33  mov     rdi, rdx
0x180013d36  mov     qword ptr [rdx], 0
0x180013d3d  mov     rbx, rcx
0x180013d40  call    cs:__imp_GetCurrentProcessId
0x180013d46  mov     [rsp+270h+var_248], rbx
0x180013d4b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180013d52  mov     r9d, eax
0x180013d55  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180013d5d  mov     edx, 104h; unsigned __int64
0x180013d62  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180013d67  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013d6c  mov     r9d, 1F0001h; dwDesiredAccess
0x180013d72  mov     [rsp+270h+var_240], 0
0x180013d7b  xor     r8d, r8d; dwFlags
0x180013d7e  lea     rdx, [rsp+270h+Name]; lpName
0x180013d83  xor     ecx, ecx; lpMutexAttributes
0x180013d85  call    cs:__imp_CreateMutexExW
0x180013d8b  mov     rdx, rax
0x180013d8e  lea     rcx, [rsp+270h+var_240]
0x180013d93  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180013d98  cmp     [rsp+270h+var_240], 0
0x180013d9e  jnz     short loc_180013DAC
0x180013da0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180013da5  mov     ebx, eax
0x180013da7  jmp     loc_180013E48
0x180013dac  lea     rdx, [rsp+270h+var_238]
0x180013db1  lea     rcx, [rsp+270h+var_240]
0x180013db6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180013dbb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180013dc0  mov     [rsp+270h+var_230], 0
0x180013dc9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180013dce  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180013dd3  mov     ebx, eax
0x180013dd5  test    eax, eax
0x180013dd7  jns     short loc_180013E21
0x180013dd9  mov     rcx, [rbp+178h]; this
0x180013de0  mov     r9d, eax; char *
0x180013de3  mov     edx, 66h ; 'f'; void *
0x180013de8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ded  mov     rcx, [rbp+178h]; this
0x180013df4  mov     r9d, ebx; char *
0x180013df7  mov     edx, 6Fh ; 'o'; void *
0x180013dfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e01  mov     r9d, ebx; char *
0x180013e04  mov     edx, 12Eh; void *
0x180013e09  mov     rcx, [rbp+178h]; this
0x180013e10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e15  lea     rcx, [rsp+270h+var_238]
0x180013e1a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013e1f  jmp     short loc_180013E48
0x180013e21  mov     rax, [rsp+270h+var_230]
0x180013e26  lea     rcx, ds:0[rax*4]
0x180013e2e  test    rcx, rcx
0x180013e31  jz      short loc_180013E78
0x180013e33  mov     [rdi], rcx
0x180013e36  mov     eax, [rcx]
0x180013e38  inc     eax
0x180013e3a  mov     [rcx], eax
0x180013e3c  lea     rcx, [rsp+270h+var_238]
0x180013e41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013e46  xor     ebx, ebx
0x180013e48  lea     rcx, [rsp+270h+var_240]
0x180013e4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013e52  mov     eax, ebx
0x180013e54  mov     rcx, [rbp+170h+var_10]
0x180013e5b  xor     rcx, rsp; StackCookie
0x180013e5e  call    __security_check_cookie
0x180013e63  lea     r11, [rsp+270h+var_s0]
0x180013e6b  mov     rbx, [r11+20h]
0x180013e6f  mov     rdi, [r11+28h]
0x180013e73  mov     rsp, r11
0x180013e76  pop     rbp
0x180013e77  retn
0x180013e78  mov     r8, rdi
0x180013e7b  lea     rdx, [rsp+270h+var_240]
0x180013e80  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180013e85  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180013e8a  mov     ebx, eax
0x180013e8c  test    eax, eax
0x180013e8e  jns     short loc_180013E3C
0x180013e90  mov     r9d, eax
0x180013e93  mov     edx, 137h
0x180013e98  jmp     loc_180013E09
```
