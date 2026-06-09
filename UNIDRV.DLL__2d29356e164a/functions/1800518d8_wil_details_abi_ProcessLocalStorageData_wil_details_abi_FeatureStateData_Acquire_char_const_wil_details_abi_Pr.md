# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800518d8`
- end: `0x180051a37`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180052d60`

## callees

- `0x1800480c4`
- `0x1800487e0`
- `0x18005120c`
- `0x180051228`
- `0x1800518d8`
- `0x180053b30`
- `0x180055430`
- `0x180055bfc`
- `0x180056424`
- `0x18005686c`
- `0x180056ba0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180051955`
- `KERNEL32!CreateMutexExW` at `0x180051955`
- `KERNEL32!GetCurrentProcessId` at `0x180051910`
- `KERNEL32!GetCurrentProcessId` at `0x180051910`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
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
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(pszDest);
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
0x1800518d8  mov     [rsp-8+arg_10], rbx
0x1800518dd  mov     [rsp-8+arg_18], rdi
0x1800518e2  push    rbp
0x1800518e3  lea     rbp, [rsp-170h]
0x1800518eb  sub     rsp, 270h
0x1800518f2  mov     rax, cs:__security_cookie
0x1800518f9  xor     rax, rsp
0x1800518fc  mov     [rbp+170h+var_10], rax
0x180051903  mov     rdi, rdx
0x180051906  mov     qword ptr [rdx], 0
0x18005190d  mov     rbx, rcx
0x180051910  call    cs:__imp_GetCurrentProcessId
0x180051916  mov     [rsp+270h+var_248], rbx
0x18005191b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180051922  mov     r9d, eax
0x180051925  mov     [rsp+270h+var_250], 130h; int
0x18005192d  mov     edx, 104h; cchDest
0x180051932  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180051937  call    StringCchPrintfW
0x18005193c  mov     r9d, 1F0001h; dwDesiredAccess
0x180051942  mov     [rsp+270h+var_240], 0
0x18005194b  xor     r8d, r8d; dwFlags
0x18005194e  lea     rdx, [rsp+270h+pszDest]; lpName
0x180051953  xor     ecx, ecx; lpMutexAttributes
0x180051955  call    cs:__imp_CreateMutexExW
0x18005195b  mov     rdx, rax
0x18005195e  lea     rcx, [rsp+270h+var_240]
0x180051963  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180051968  cmp     [rsp+270h+var_240], 0
0x18005196e  jnz     short loc_180051979
0x180051970  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180051975  mov     ebx, eax
0x180051977  jmp     short loc_1800519E5
0x180051979  lea     rdx, [rsp+270h+var_238]
0x18005197e  lea     rcx, [rsp+270h+var_240]
0x180051983  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180051988  lea     rdx, [rsp+270h+var_230]; void **
0x18005198d  mov     [rsp+270h+var_230], 0
0x180051996  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18005199b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800519a0  mov     ebx, eax
0x1800519a2  test    eax, eax
0x1800519a4  jns     short loc_1800519C6
0x1800519a6  mov     edx, 12Eh; void *
0x1800519ab  mov     rcx, [rbp+178h]; this
0x1800519b2  mov     r9d, eax; char *
0x1800519b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800519ba  lea     rcx, [rsp+270h+var_238]
0x1800519bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800519c4  jmp     short loc_1800519E5
0x1800519c6  mov     rcx, [rsp+270h+var_230]
0x1800519cb  test    rcx, rcx
0x1800519ce  jz      short loc_180051A15
0x1800519d0  mov     [rdi], rcx
0x1800519d3  mov     eax, [rcx]
0x1800519d5  inc     eax
0x1800519d7  mov     [rcx], eax
0x1800519d9  lea     rcx, [rsp+270h+var_238]
0x1800519de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800519e3  xor     ebx, ebx
0x1800519e5  lea     rcx, [rsp+270h+var_240]
0x1800519ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800519ef  mov     eax, ebx
0x1800519f1  mov     rcx, [rbp+170h+var_10]
0x1800519f8  xor     rcx, rsp; StackCookie
0x1800519fb  call    __security_check_cookie
0x180051a00  lea     r11, [rsp+270h+var_s0]
0x180051a08  mov     rbx, [r11+20h]
0x180051a0c  mov     rdi, [r11+28h]
0x180051a10  mov     rsp, r11
0x180051a13  pop     rbp
0x180051a14  retn
0x180051a15  mov     r8, rdi
0x180051a18  lea     rdx, [rsp+270h+var_240]
0x180051a1d  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180051a22  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180051a27  mov     ebx, eax
0x180051a29  test    eax, eax
0x180051a2b  jns     short loc_1800519D9
0x180051a2d  mov     edx, 137h
0x180051a32  jmp     loc_1800519AB
```
