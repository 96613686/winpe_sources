# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180053134`
- end: `0x1800532a0`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180054700`

## callees

- `0x180049590`
- `0x180049d00`
- `0x180052a34`
- `0x180052a54`
- `0x180053134`
- `0x1800555c0`
- `0x180056fb8`
- `0x18005768c`
- `0x180057ef4`
- `0x1800582c8`
- `0x180058614`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800531b7`
- `KERNEL32!CreateMutexExW` at `0x1800531b7`
- `KERNEL32!GetCurrentProcessId` at `0x18005316c`
- `KERNEL32!GetCurrentProcessId` at `0x18005316c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 304, a1);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(
                  pszDest,
                  &v21,
                  (wil::details **)a2);
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
0x180053134  mov     [rsp-8+arg_10], rbx
0x180053139  mov     [rsp-8+arg_18], rdi
0x18005313e  push    rbp
0x18005313f  lea     rbp, [rsp-170h]
0x180053147  sub     rsp, 270h
0x18005314e  mov     rax, cs:__security_cookie
0x180053155  xor     rax, rsp
0x180053158  mov     [rbp+170h+var_10], rax
0x18005315f  mov     rdi, rdx
0x180053162  mov     qword ptr [rdx], 0
0x180053169  mov     rbx, rcx
0x18005316c  call    cs:__imp_GetCurrentProcessId
0x180053173  nop     dword ptr [rax+rax+00h]
0x180053178  mov     [rsp+270h+var_248], rbx
0x18005317d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180053184  mov     r9d, eax
0x180053187  mov     [rsp+270h+var_250], 130h; int
0x18005318f  mov     edx, 104h; cchDest
0x180053194  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180053199  call    StringCchPrintfW
0x18005319e  mov     r9d, 1F0001h; dwDesiredAccess
0x1800531a4  mov     [rsp+270h+var_240], 0
0x1800531ad  xor     r8d, r8d; dwFlags
0x1800531b0  lea     rdx, [rsp+270h+pszDest]; lpName
0x1800531b5  xor     ecx, ecx; lpMutexAttributes
0x1800531b7  call    cs:__imp_CreateMutexExW
0x1800531be  nop     dword ptr [rax+rax+00h]
0x1800531c3  mov     rdx, rax
0x1800531c6  lea     rcx, [rsp+270h+var_240]
0x1800531cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800531d0  cmp     [rsp+270h+var_240], 0
0x1800531d6  jnz     short loc_1800531E1
0x1800531d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800531dd  mov     ebx, eax
0x1800531df  jmp     short loc_18005324D
0x1800531e1  lea     rdx, [rsp+270h+var_238]
0x1800531e6  lea     rcx, [rsp+270h+var_240]
0x1800531eb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800531f0  lea     rdx, [rsp+270h+var_230]; void **
0x1800531f5  mov     [rsp+270h+var_230], 0
0x1800531fe  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180053203  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180053208  mov     ebx, eax
0x18005320a  test    eax, eax
0x18005320c  jns     short loc_18005322E
0x18005320e  mov     edx, 12Eh; void *
0x180053213  mov     rcx, [rbp+178h]; this
0x18005321a  mov     r9d, eax; char *
0x18005321d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053222  lea     rcx, [rsp+270h+var_238]
0x180053227  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005322c  jmp     short loc_18005324D
0x18005322e  mov     rcx, [rsp+270h+var_230]
0x180053233  test    rcx, rcx
0x180053236  jz      short loc_18005327E
0x180053238  mov     [rdi], rcx
0x18005323b  mov     eax, [rcx]
0x18005323d  inc     eax
0x18005323f  mov     [rcx], eax
0x180053241  lea     rcx, [rsp+270h+var_238]
0x180053246  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005324b  xor     ebx, ebx
0x18005324d  lea     rcx, [rsp+270h+var_240]
0x180053252  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180053257  mov     eax, ebx
0x180053259  mov     rcx, [rbp+170h+var_10]
0x180053260  xor     rcx, rsp; StackCookie
0x180053263  call    __security_check_cookie
0x180053268  lea     r11, [rsp+270h+var_s0]
0x180053270  mov     rbx, [r11+20h]
0x180053274  mov     rdi, [r11+28h]
0x180053278  mov     rsp, r11
0x18005327b  pop     rbp
0x18005327c  retn
0x18005327e  mov     r8, rdi
0x180053281  lea     rdx, [rsp+270h+var_240]
0x180053286  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18005328b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180053290  mov     ebx, eax
0x180053292  test    eax, eax
0x180053294  jns     short loc_180053241
0x180053296  mov     edx, 137h
0x18005329b  jmp     loc_180053213
```
