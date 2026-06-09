# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800290b4`
- end: `0x18002921a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180029488`

## callees

- `0x180003560`
- `0x180004fd8`
- `0x180004ff4`
- `0x1800059f8`
- `0x180006b14`
- `0x1800070e0`
- `0x18000723c`
- `0x1800076c0`
- `0x1800077bc`
- `0x1800290b4`
- `0x1800297fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029131`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029131`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800290ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800290ec`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800290b4  mov     [rsp-8+arg_10], rbx
0x1800290b9  mov     [rsp-8+arg_18], rdi
0x1800290be  push    rbp
0x1800290bf  lea     rbp, [rsp-170h]
0x1800290c7  sub     rsp, 270h
0x1800290ce  mov     rax, cs:__security_cookie
0x1800290d5  xor     rax, rsp
0x1800290d8  mov     [rbp+170h+var_10], rax
0x1800290df  mov     rdi, rdx
0x1800290e2  mov     qword ptr [rdx], 0
0x1800290e9  mov     rbx, rcx
0x1800290ec  call    cs:__imp_GetCurrentProcessId
0x1800290f2  mov     [rsp+270h+var_248], rbx
0x1800290f7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800290fe  mov     r9d, eax
0x180029101  mov     [rsp+270h+var_250], 130h; int
0x180029109  mov     edx, 104h; unsigned __int64
0x18002910e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029113  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180029118  mov     r9d, 1F0001h; dwDesiredAccess
0x18002911e  mov     [rsp+270h+var_240], 0
0x180029127  xor     r8d, r8d; dwFlags
0x18002912a  lea     rdx, [rsp+270h+Name]; lpName
0x18002912f  xor     ecx, ecx; lpMutexAttributes
0x180029131  call    cs:__imp_CreateMutexExW
0x180029137  mov     rdx, rax
0x18002913a  lea     rcx, [rsp+270h+var_240]
0x18002913f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180029144  cmp     [rsp+270h+var_240], 0
0x18002914a  jnz     short loc_180029155
0x18002914c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180029151  mov     ebx, eax
0x180029153  jmp     short loc_1800291C8
0x180029155  lea     rdx, [rsp+270h+var_238]
0x18002915a  lea     rcx, [rsp+270h+var_240]
0x18002915f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180029164  lea     rdx, [rsp+270h+var_230]; void **
0x180029169  mov     [rsp+270h+var_230], 0
0x180029172  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029177  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18002917c  mov     ebx, eax
0x18002917e  test    eax, eax
0x180029180  jns     short loc_1800291A9
0x180029182  mov     edx, 12Eh; void *
0x180029187  mov     rcx, [rbp+178h]; this
0x18002918e  lea     r8, aWil; "wil"
0x180029195  mov     r9d, eax; char *
0x180029198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002919d  lea     rcx, [rsp+270h+var_238]
0x1800291a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800291a7  jmp     short loc_1800291C8
0x1800291a9  mov     rcx, [rsp+270h+var_230]
0x1800291ae  test    rcx, rcx
0x1800291b1  jz      short loc_1800291F8
0x1800291b3  mov     [rdi], rcx
0x1800291b6  mov     eax, [rcx]
0x1800291b8  inc     eax
0x1800291ba  mov     [rcx], eax
0x1800291bc  lea     rcx, [rsp+270h+var_238]
0x1800291c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800291c6  xor     ebx, ebx
0x1800291c8  lea     rcx, [rsp+270h+var_240]
0x1800291cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800291d2  mov     eax, ebx
0x1800291d4  mov     rcx, [rbp+170h+var_10]
0x1800291db  xor     rcx, rsp; StackCookie
0x1800291de  call    __security_check_cookie
0x1800291e3  lea     r11, [rsp+270h+var_s0]
0x1800291eb  mov     rbx, [r11+20h]
0x1800291ef  mov     rdi, [r11+28h]
0x1800291f3  mov     rsp, r11
0x1800291f6  pop     rbp
0x1800291f7  retn
0x1800291f8  mov     r8, rdi
0x1800291fb  lea     rdx, [rsp+270h+var_240]
0x180029200  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029205  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002920a  mov     ebx, eax
0x18002920c  test    eax, eax
0x18002920e  jns     short loc_1800291BC
0x180029210  mov     edx, 137h
0x180029215  jmp     loc_180029187
```
