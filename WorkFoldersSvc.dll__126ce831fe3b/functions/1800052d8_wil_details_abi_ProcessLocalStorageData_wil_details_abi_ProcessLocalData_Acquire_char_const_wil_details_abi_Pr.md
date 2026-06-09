# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800052d8`
- end: `0x180005453`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005e18`

## callees

- `0x180002ab0`
- `0x18000500c`
- `0x180005028`
- `0x1800052d8`
- `0x180005b78`
- `0x180006554`
- `0x1800069a4`
- `0x180006fa0`
- `0x18000711c`
- `0x180007504`
- `0x180007608`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180005355`
- `KERNEL32!CreateMutexExW` at `0x180005355`
- `KERNEL32!GetCurrentProcessId` at `0x180005310`
- `KERNEL32!GetCurrentProcessId` at `0x180005310`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  _DWORD *v9; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer >= 0 )
    {
      v9 = v15;
      if ( v15 )
      {
        *a2 = v15;
        ++*v9;
      }
      else
      {
        v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v12, (const char *)(unsigned int)v11, 120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800052d8  mov     [rsp-8+arg_10], rbx
0x1800052dd  mov     [rsp-8+arg_18], rdi
0x1800052e2  push    rbp
0x1800052e3  lea     rbp, [rsp-170h]
0x1800052eb  sub     rsp, 270h
0x1800052f2  mov     rax, cs:__security_cookie
0x1800052f9  xor     rax, rsp
0x1800052fc  mov     [rbp+170h+var_10], rax
0x180005303  mov     rdi, rdx
0x180005306  mov     rbx, rcx
0x180005309  mov     qword ptr [rdx], 0
0x180005310  call    cs:__imp_GetCurrentProcessId
0x180005316  mov     r9d, eax
0x180005319  mov     [rsp+270h+var_248], rbx
0x18000531e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180005326  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000532d  mov     edx, 104h; unsigned __int64
0x180005332  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005337  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000533c  mov     [rsp+270h+var_240], 0
0x180005345  mov     r9d, 1F0001h; dwDesiredAccess
0x18000534b  xor     r8d, r8d; dwFlags
0x18000534e  lea     rdx, [rsp+270h+Name]; lpName
0x180005353  xor     ecx, ecx; lpMutexAttributes
0x180005355  call    cs:__imp_CreateMutexExW
0x18000535b  mov     rdx, rax
0x18000535e  lea     rcx, [rsp+270h+var_240]
0x180005363  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005368  cmp     [rsp+270h+var_240], 0
0x18000536e  jnz     short loc_180005379
0x180005370  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005375  mov     ebx, eax
0x180005377  jmp     short loc_1800053E9
0x180005379  lea     rdx, [rsp+270h+var_238]
0x18000537e  lea     rcx, [rsp+270h+var_240]
0x180005383  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005388  nop
0x180005389  mov     [rsp+270h+var_230], 0
0x180005392  lea     rdx, [rsp+270h+var_230]; void **
0x180005397  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000539c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800053a1  mov     ebx, eax
0x1800053a3  test    eax, eax
0x1800053a5  jns     short loc_1800053C9
0x1800053a7  mov     rcx, [rbp+178h]; this
0x1800053ae  mov     r9d, eax; char *
0x1800053b1  mov     edx, 12Eh; void *
0x1800053b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053bb  nop
0x1800053bc  lea     rcx, [rsp+270h+var_238]
0x1800053c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800053c6  nop
0x1800053c7  jmp     short loc_1800053E9
0x1800053c9  mov     rcx, [rsp+270h+var_230]
0x1800053ce  test    rcx, rcx
0x1800053d1  jz      short loc_180005419
0x1800053d3  mov     [rdi], rcx
0x1800053d6  mov     eax, [rcx]
0x1800053d8  inc     eax
0x1800053da  mov     [rcx], eax
0x1800053dc  lea     rcx, [rsp+270h+var_238]
0x1800053e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800053e6  nop
0x1800053e7  xor     ebx, ebx
0x1800053e9  lea     rcx, [rsp+270h+var_240]
0x1800053ee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800053f3  mov     eax, ebx
0x1800053f5  mov     rcx, [rbp+170h+var_10]
0x1800053fc  xor     rcx, rsp; StackCookie
0x1800053ff  call    __security_check_cookie
0x180005404  lea     r11, [rsp+270h+var_s0]
0x18000540c  mov     rbx, [r11+20h]
0x180005410  mov     rdi, [r11+28h]
0x180005414  mov     rsp, r11
0x180005417  pop     rbp
0x180005418  retn
0x180005419  mov     r8, rdi
0x18000541c  lea     rdx, [rsp+270h+var_240]
0x180005421  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005426  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000542b  mov     ebx, eax
0x18000542d  test    eax, eax
0x18000542f  jns     short loc_1800053DC
0x180005431  mov     rcx, [rbp+178h]; this
0x180005438  mov     r9d, eax; char *
0x18000543b  mov     edx, 137h; void *
0x180005440  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005445  nop
0x180005446  lea     rcx, [rsp+270h+var_238]
0x18000544b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005450  nop
0x180005451  jmp     short loc_1800053E9
```
