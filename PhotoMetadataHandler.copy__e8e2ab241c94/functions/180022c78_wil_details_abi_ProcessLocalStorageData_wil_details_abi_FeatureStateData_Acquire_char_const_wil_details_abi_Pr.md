# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180022c78`
- end: `0x180022dd6`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800238a4`

## callees

- `0x1800076b0`
- `0x1800150a4`
- `0x180015200`
- `0x180015374`
- `0x180016020`
- `0x180016cec`
- `0x180022944`
- `0x180022960`
- `0x180022c78`
- `0x1800253c8`
- `0x180025b74`
- `0x180025d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022cf4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022cf4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId_0; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId_0 = GetCurrentProcessId_0();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId_0);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180022c78  mov     [rsp-8+arg_10], rbx
0x180022c7d  mov     [rsp-8+arg_18], rdi
0x180022c82  push    rbp
0x180022c83  lea     rbp, [rsp-170h]
0x180022c8b  sub     rsp, 270h
0x180022c92  mov     rax, cs:__security_cookie
0x180022c99  xor     rax, rsp
0x180022c9c  mov     [rbp+170h+var_10], rax
0x180022ca3  mov     rdi, rdx
0x180022ca6  mov     qword ptr [rdx], 0
0x180022cad  mov     rbx, rcx
0x180022cb0  call    GetCurrentProcessId_0
0x180022cb5  mov     r9d, eax
0x180022cb8  mov     [rsp+270h+var_248], rbx
0x180022cbd  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180022cc4  mov     [rsp+270h+var_250], 130h; int
0x180022ccc  mov     edx, 104h; unsigned __int64
0x180022cd1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022cd6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022cdb  mov     r9d, 1F0001h; dwDesiredAccess
0x180022ce1  mov     [rsp+270h+var_240], 0
0x180022cea  xor     r8d, r8d; dwFlags
0x180022ced  lea     rdx, [rsp+270h+Name]; lpName
0x180022cf2  xor     ecx, ecx; lpMutexAttributes
0x180022cf4  call    cs:__imp_CreateMutexExW
0x180022cfa  mov     rdx, rax
0x180022cfd  lea     rcx, [rsp+270h+var_240]
0x180022d02  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180022d07  cmp     [rsp+270h+var_240], 0
0x180022d0d  jnz     short loc_180022D18
0x180022d0f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180022d14  mov     ebx, eax
0x180022d16  jmp     short loc_180022D84
0x180022d18  lea     rdx, [rsp+270h+var_238]
0x180022d1d  lea     rcx, [rsp+270h+var_240]
0x180022d22  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180022d27  lea     rdx, [rsp+270h+var_230]; void **
0x180022d2c  mov     [rsp+270h+var_230], 0
0x180022d35  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022d3a  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180022d3f  mov     ebx, eax
0x180022d41  test    eax, eax
0x180022d43  jns     short loc_180022D65
0x180022d45  mov     edx, 12Eh; void *
0x180022d4a  mov     rcx, [rbp+178h]; this
0x180022d51  mov     r9d, eax; char *
0x180022d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022d59  lea     rcx, [rsp+270h+var_238]
0x180022d5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022d63  jmp     short loc_180022D84
0x180022d65  mov     rcx, [rsp+270h+var_230]
0x180022d6a  test    rcx, rcx
0x180022d6d  jz      short loc_180022DB4
0x180022d6f  mov     [rdi], rcx
0x180022d72  mov     eax, [rcx]
0x180022d74  inc     eax
0x180022d76  mov     [rcx], eax
0x180022d78  lea     rcx, [rsp+270h+var_238]
0x180022d7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022d82  xor     ebx, ebx
0x180022d84  lea     rcx, [rsp+270h+var_240]
0x180022d89  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022d8e  mov     eax, ebx
0x180022d90  mov     rcx, [rbp+170h+var_10]
0x180022d97  xor     rcx, rsp; StackCookie
0x180022d9a  call    __security_check_cookie
0x180022d9f  lea     r11, [rsp+270h+var_s0]
0x180022da7  mov     rbx, [r11+20h]
0x180022dab  mov     rdi, [r11+28h]
0x180022daf  mov     rsp, r11
0x180022db2  pop     rbp
0x180022db3  retn
0x180022db4  mov     r8, rdi
0x180022db7  lea     rdx, [rsp+270h+var_240]
0x180022dbc  lea     rcx, [rsp+270h+Name]
0x180022dc1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180022dc6  mov     ebx, eax
0x180022dc8  test    eax, eax
0x180022dca  jns     short loc_180022D78
0x180022dcc  mov     edx, 137h
0x180022dd1  jmp     loc_180022D4A
```
