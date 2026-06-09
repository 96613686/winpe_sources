# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180052fc0`
- end: `0x18005312c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800548f0`

## callees

- `0x180049590`
- `0x180049d00`
- `0x180052a34`
- `0x180052a54`
- `0x180052fc0`
- `0x18005549c`
- `0x180056fb8`
- `0x18005768c`
- `0x180057ef4`
- `0x1800582c8`
- `0x180058614`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180053043`
- `KERNEL32!CreateMutexExW` at `0x180053043`
- `KERNEL32!GetCurrentProcessId` at `0x180052ff8`
- `KERNEL32!GetCurrentProcessId` at `0x180052ff8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  __int64 v6; // rdx
  wil::details *v7; // rcx
  __int64 v8; // r8
  const char *v9; // r9
  void *v10; // rdx
  unsigned int LastErrorFailHr; // ebx
  __int64 v12; // r8
  bool *v13; // r9
  int Pointer; // eax
  void *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  void *v18; // rdx
  _DWORD *v19; // rcx
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v22; // [rsp+38h] [rbp-C8h] BYREF
  void *v23; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  v21 = 0;
  Mutex = (wil::details *)CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v21,
    Mutex);
  if ( v21 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v21,
      &v22);
    v23 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v23, v12, v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v17 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, v17, v16, (const char *)(unsigned int)Pointer);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v22,
        v18);
      goto LABEL_9;
    }
    v19 = v23;
    if ( v23 )
    {
      *a2 = v23;
      ++*v19;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
                  pszDest,
                  &v21,
                  a2);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v17 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v15);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v7, v6, v8, v9);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v10);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180052fc0  mov     [rsp-8+arg_10], rbx
0x180052fc5  mov     [rsp-8+arg_18], rdi
0x180052fca  push    rbp
0x180052fcb  lea     rbp, [rsp-170h]
0x180052fd3  sub     rsp, 270h
0x180052fda  mov     rax, cs:__security_cookie
0x180052fe1  xor     rax, rsp
0x180052fe4  mov     [rbp+170h+var_10], rax
0x180052feb  mov     rdi, rdx
0x180052fee  mov     qword ptr [rdx], 0
0x180052ff5  mov     rbx, rcx
0x180052ff8  call    cs:__imp_GetCurrentProcessId
0x180052fff  nop     dword ptr [rax+rax+00h]
0x180053004  mov     [rsp+270h+var_248], rbx
0x180053009  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180053010  mov     r9d, eax
0x180053013  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18005301b  mov     edx, 104h; cchDest
0x180053020  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180053025  call    StringCchPrintfW
0x18005302a  mov     r9d, 1F0001h; dwDesiredAccess
0x180053030  mov     [rsp+270h+var_240], 0
0x180053039  xor     r8d, r8d; dwFlags
0x18005303c  lea     rdx, [rsp+270h+pszDest]; lpName
0x180053041  xor     ecx, ecx; lpMutexAttributes
0x180053043  call    cs:__imp_CreateMutexExW
0x18005304a  nop     dword ptr [rax+rax+00h]
0x18005304f  mov     rdx, rax
0x180053052  lea     rcx, [rsp+270h+var_240]
0x180053057  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005305c  cmp     [rsp+270h+var_240], 0
0x180053062  jnz     short loc_18005306D
0x180053064  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180053069  mov     ebx, eax
0x18005306b  jmp     short loc_1800530D9
0x18005306d  lea     rdx, [rsp+270h+var_238]
0x180053072  lea     rcx, [rsp+270h+var_240]
0x180053077  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18005307c  lea     rdx, [rsp+270h+var_230]; void **
0x180053081  mov     [rsp+270h+var_230], 0
0x18005308a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18005308f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180053094  mov     ebx, eax
0x180053096  test    eax, eax
0x180053098  jns     short loc_1800530BA
0x18005309a  mov     edx, 12Eh; void *
0x18005309f  mov     rcx, [rbp+178h]; this
0x1800530a6  mov     r9d, eax; char *
0x1800530a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800530ae  lea     rcx, [rsp+270h+var_238]
0x1800530b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800530b8  jmp     short loc_1800530D9
0x1800530ba  mov     rcx, [rsp+270h+var_230]
0x1800530bf  test    rcx, rcx
0x1800530c2  jz      short loc_18005310A
0x1800530c4  mov     [rdi], rcx
0x1800530c7  mov     eax, [rcx]
0x1800530c9  inc     eax
0x1800530cb  mov     [rcx], eax
0x1800530cd  lea     rcx, [rsp+270h+var_238]
0x1800530d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800530d7  xor     ebx, ebx
0x1800530d9  lea     rcx, [rsp+270h+var_240]
0x1800530de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800530e3  mov     eax, ebx
0x1800530e5  mov     rcx, [rbp+170h+var_10]
0x1800530ec  xor     rcx, rsp; StackCookie
0x1800530ef  call    __security_check_cookie
0x1800530f4  lea     r11, [rsp+270h+var_s0]
0x1800530fc  mov     rbx, [r11+20h]
0x180053100  mov     rdi, [r11+28h]
0x180053104  mov     rsp, r11
0x180053107  pop     rbp
0x180053108  retn
0x18005310a  mov     r8, rdi
0x18005310d  lea     rdx, [rsp+270h+var_240]
0x180053112  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180053117  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005311c  mov     ebx, eax
0x18005311e  test    eax, eax
0x180053120  jns     short loc_1800530CD
0x180053122  mov     edx, 137h
0x180053127  jmp     loc_18005309F
```
