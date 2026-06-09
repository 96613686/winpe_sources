# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180018a30`
- end: `0x180018bc4`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `404`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800194cc`

## callees

- `0x180001bd6`
- `0x1800035c8`
- `0x1800189b0`
- `0x1800189cc`
- `0x180018a30`
- `0x180019358`
- `0x180019d60`
- `0x18001a9d4`
- `0x18001ad74`
- `0x18001b080`
- `0x18001b12c`
- `0x18001b980`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180018aac`
- `KERNEL32!CreateMutexExW` at `0x180018aac`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId_0; // eax
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
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v19 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId_0);
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
0x180018a30  mov     [rsp-8+arg_10], rbx
0x180018a35  mov     [rsp-8+arg_18], rdi
0x180018a3a  push    rbp
0x180018a3b  lea     rbp, [rsp-170h]
0x180018a43  sub     rsp, 270h
0x180018a4a  mov     rax, cs:__security_cookie
0x180018a51  xor     rax, rsp
0x180018a54  mov     [rbp+170h+var_10], rax
0x180018a5b  mov     rdi, rdx
0x180018a5e  mov     qword ptr [rdx], 0
0x180018a65  mov     rbx, rcx
0x180018a68  call    GetCurrentProcessId_0
0x180018a6d  mov     r9d, eax
0x180018a70  mov     [rsp+270h+var_248], rbx
0x180018a75  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180018a7c  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180018a84  mov     edx, 104h; unsigned __int64
0x180018a89  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018a8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018a93  mov     r9d, 1F0001h; dwDesiredAccess
0x180018a99  mov     [rsp+270h+var_240], 0
0x180018aa2  xor     r8d, r8d; dwFlags
0x180018aa5  lea     rdx, [rsp+270h+Name]; lpName
0x180018aaa  xor     ecx, ecx; lpMutexAttributes
0x180018aac  call    cs:__imp_CreateMutexExW
0x180018ab2  mov     rdx, rax
0x180018ab5  lea     rcx, [rsp+270h+var_240]
0x180018aba  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180018abf  cmp     [rsp+270h+var_240], 0
0x180018ac5  jnz     short loc_180018AD3
0x180018ac7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018acc  mov     ebx, eax
0x180018ace  jmp     loc_180018B6F
0x180018ad3  lea     rdx, [rsp+270h+var_238]
0x180018ad8  lea     rcx, [rsp+270h+var_240]
0x180018add  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180018ae2  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180018ae7  mov     [rsp+270h+var_230], 0
0x180018af0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018af5  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180018afa  mov     ebx, eax
0x180018afc  test    eax, eax
0x180018afe  jns     short loc_180018B48
0x180018b00  mov     rcx, [rbp+178h]; this
0x180018b07  mov     r9d, eax; char *
0x180018b0a  mov     edx, 66h ; 'f'; void *
0x180018b0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b14  mov     rcx, [rbp+178h]; this
0x180018b1b  mov     r9d, ebx; char *
0x180018b1e  mov     edx, 6Fh ; 'o'; void *
0x180018b23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b28  mov     r9d, ebx; char *
0x180018b2b  mov     edx, 12Eh; void *
0x180018b30  mov     rcx, [rbp+178h]; this
0x180018b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b3c  lea     rcx, [rsp+270h+var_238]
0x180018b41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018b46  jmp     short loc_180018B6F
0x180018b48  mov     rax, [rsp+270h+var_230]
0x180018b4d  lea     rcx, ds:0[rax*4]
0x180018b55  test    rcx, rcx
0x180018b58  jz      short loc_180018B9F
0x180018b5a  mov     [rdi], rcx
0x180018b5d  mov     eax, [rcx]
0x180018b5f  inc     eax
0x180018b61  mov     [rcx], eax
0x180018b63  lea     rcx, [rsp+270h+var_238]
0x180018b68  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018b6d  xor     ebx, ebx
0x180018b6f  lea     rcx, [rsp+270h+var_240]
0x180018b74  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018b79  mov     eax, ebx
0x180018b7b  mov     rcx, [rbp+170h+var_10]
0x180018b82  xor     rcx, rsp; StackCookie
0x180018b85  call    __security_check_cookie
0x180018b8a  lea     r11, [rsp+270h+var_s0]
0x180018b92  mov     rbx, [r11+20h]
0x180018b96  mov     rdi, [r11+28h]
0x180018b9a  mov     rsp, r11
0x180018b9d  pop     rbp
0x180018b9e  retn
0x180018b9f  mov     r8, rdi
0x180018ba2  lea     rdx, [rsp+270h+var_240]
0x180018ba7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018bac  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180018bb1  mov     ebx, eax
0x180018bb3  test    eax, eax
0x180018bb5  jns     short loc_180018B63
0x180018bb7  mov     r9d, eax
0x180018bba  mov     edx, 137h
0x180018bbf  jmp     loc_180018B30
```
