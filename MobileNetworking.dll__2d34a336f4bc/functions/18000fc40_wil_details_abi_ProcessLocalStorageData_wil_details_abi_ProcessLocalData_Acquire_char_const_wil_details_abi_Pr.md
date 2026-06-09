# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000fc40`
- end: `0x18000fdd5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800105c0`

## callees

- `0x18000917c`
- `0x180009850`
- `0x18000fbe0`
- `0x18000fbfc`
- `0x18000fc40`
- `0x180010b38`
- `0x180010ee8`
- `0x180011248`
- `0x180011300`
- `0x1800115e0`
- `0x1800116a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fc78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fc78`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000fcbd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000fcbd`

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
  _BYTE v22[8]; // [rsp+38h] [rbp-C8h] BYREF
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
      &v21,
      v22);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
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
0x18000fc40  mov     [rsp-8+arg_10], rbx
0x18000fc45  mov     [rsp-8+arg_18], rdi
0x18000fc4a  push    rbp
0x18000fc4b  lea     rbp, [rsp-170h]
0x18000fc53  sub     rsp, 270h
0x18000fc5a  mov     rax, cs:__security_cookie
0x18000fc61  xor     rax, rsp
0x18000fc64  mov     [rbp+170h+var_10], rax
0x18000fc6b  mov     rdi, rdx
0x18000fc6e  mov     qword ptr [rdx], 0
0x18000fc75  mov     rbx, rcx
0x18000fc78  call    cs:__imp_GetCurrentProcessId
0x18000fc7e  mov     [rsp+270h+var_248], rbx
0x18000fc83  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000fc8a  mov     r9d, eax
0x18000fc8d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000fc95  mov     edx, 104h; unsigned __int64
0x18000fc9a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000fc9f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fca4  mov     r9d, 1F0001h; dwDesiredAccess
0x18000fcaa  mov     [rsp+270h+var_240], 0
0x18000fcb3  xor     r8d, r8d; dwFlags
0x18000fcb6  lea     rdx, [rsp+270h+Name]; lpName
0x18000fcbb  xor     ecx, ecx; lpMutexAttributes
0x18000fcbd  call    cs:__imp_CreateMutexExW
0x18000fcc3  mov     rdx, rax
0x18000fcc6  lea     rcx, [rsp+270h+var_240]
0x18000fccb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000fcd0  cmp     [rsp+270h+var_240], 0
0x18000fcd6  jnz     short loc_18000FCE4
0x18000fcd8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000fcdd  mov     ebx, eax
0x18000fcdf  jmp     loc_18000FD80
0x18000fce4  lea     rdx, [rsp+270h+var_238]
0x18000fce9  lea     rcx, [rsp+270h+var_240]
0x18000fcee  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000fcf3  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000fcf8  mov     [rsp+270h+var_230], 0
0x18000fd01  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000fd06  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000fd0b  mov     ebx, eax
0x18000fd0d  test    eax, eax
0x18000fd0f  jns     short loc_18000FD59
0x18000fd11  mov     rcx, [rbp+178h]; this
0x18000fd18  mov     r9d, eax; char *
0x18000fd1b  mov     edx, 66h ; 'f'; void *
0x18000fd20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd25  mov     rcx, [rbp+178h]; this
0x18000fd2c  mov     r9d, ebx; char *
0x18000fd2f  mov     edx, 6Fh ; 'o'; void *
0x18000fd34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd39  mov     r9d, ebx; char *
0x18000fd3c  mov     edx, 12Eh; void *
0x18000fd41  mov     rcx, [rbp+178h]; this
0x18000fd48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd4d  lea     rcx, [rsp+270h+var_238]
0x18000fd52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fd57  jmp     short loc_18000FD80
0x18000fd59  mov     rax, [rsp+270h+var_230]
0x18000fd5e  lea     rcx, ds:0[rax*4]
0x18000fd66  test    rcx, rcx
0x18000fd69  jz      short loc_18000FDB0
0x18000fd6b  mov     [rdi], rcx
0x18000fd6e  mov     eax, [rcx]
0x18000fd70  inc     eax
0x18000fd72  mov     [rcx], eax
0x18000fd74  lea     rcx, [rsp+270h+var_238]
0x18000fd79  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fd7e  xor     ebx, ebx
0x18000fd80  lea     rcx, [rsp+270h+var_240]
0x18000fd85  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fd8a  mov     eax, ebx
0x18000fd8c  mov     rcx, [rbp+170h+var_10]
0x18000fd93  xor     rcx, rsp; StackCookie
0x18000fd96  call    __security_check_cookie
0x18000fd9b  lea     r11, [rsp+270h+var_s0]
0x18000fda3  mov     rbx, [r11+20h]
0x18000fda7  mov     rdi, [r11+28h]
0x18000fdab  mov     rsp, r11
0x18000fdae  pop     rbp
0x18000fdaf  retn
0x18000fdb0  mov     r8, rdi
0x18000fdb3  lea     rdx, [rsp+270h+var_240]
0x18000fdb8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000fdbd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000fdc2  mov     ebx, eax
0x18000fdc4  test    eax, eax
0x18000fdc6  jns     short loc_18000FD74
0x18000fdc8  mov     r9d, eax
0x18000fdcb  mov     edx, 137h
0x18000fdd0  jmp     loc_18000FD41
```
