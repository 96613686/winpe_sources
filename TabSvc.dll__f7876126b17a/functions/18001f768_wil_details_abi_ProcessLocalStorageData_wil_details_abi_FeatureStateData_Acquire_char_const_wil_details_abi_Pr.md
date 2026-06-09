# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001f768`
- end: `0x18001f8ce`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180022a24`

## callees

- `0x1800037d0`
- `0x18001b3f0`
- `0x18001bbe0`
- `0x18001f1e8`
- `0x18001f204`
- `0x18001f768`
- `0x18002382c`
- `0x180025a34`
- `0x1800278fc`
- `0x180028c04`
- `0x18002a20c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f7a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f7a0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f7e5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f7e5`

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
0x18001f768  mov     [rsp-8+arg_10], rbx
0x18001f76d  mov     [rsp-8+arg_18], rdi
0x18001f772  push    rbp
0x18001f773  lea     rbp, [rsp-170h]
0x18001f77b  sub     rsp, 270h
0x18001f782  mov     rax, cs:__security_cookie
0x18001f789  xor     rax, rsp
0x18001f78c  mov     [rbp+170h+var_10], rax
0x18001f793  mov     rdi, rdx
0x18001f796  mov     qword ptr [rdx], 0
0x18001f79d  mov     rbx, rcx
0x18001f7a0  call    cs:__imp_GetCurrentProcessId
0x18001f7a6  mov     [rsp+270h+var_248], rbx
0x18001f7ab  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001f7b2  mov     r9d, eax
0x18001f7b5  mov     [rsp+270h+var_250], 130h; int
0x18001f7bd  mov     edx, 104h; unsigned __int64
0x18001f7c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f7c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f7cc  mov     r9d, 1F0001h; dwDesiredAccess
0x18001f7d2  mov     [rsp+270h+var_240], 0
0x18001f7db  xor     r8d, r8d; dwFlags
0x18001f7de  lea     rdx, [rsp+270h+Name]; lpName
0x18001f7e3  xor     ecx, ecx; lpMutexAttributes
0x18001f7e5  call    cs:__imp_CreateMutexExW
0x18001f7eb  mov     rdx, rax
0x18001f7ee  lea     rcx, [rsp+270h+var_240]
0x18001f7f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001f7f8  cmp     [rsp+270h+var_240], 0
0x18001f7fe  jnz     short loc_18001F809
0x18001f800  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001f805  mov     ebx, eax
0x18001f807  jmp     short loc_18001F87C
0x18001f809  lea     rdx, [rsp+270h+var_238]
0x18001f80e  lea     rcx, [rsp+270h+var_240]
0x18001f813  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001f818  lea     rdx, [rsp+270h+var_230]; void **
0x18001f81d  mov     [rsp+270h+var_230], 0
0x18001f826  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f82b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001f830  mov     ebx, eax
0x18001f832  test    eax, eax
0x18001f834  jns     short loc_18001F85D
0x18001f836  mov     edx, 12Eh; void *
0x18001f83b  mov     rcx, [rbp+178h]; this
0x18001f842  lea     r8, aWil; "wil"
0x18001f849  mov     r9d, eax; char *
0x18001f84c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f851  lea     rcx, [rsp+270h+var_238]
0x18001f856  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f85b  jmp     short loc_18001F87C
0x18001f85d  mov     rcx, [rsp+270h+var_230]
0x18001f862  test    rcx, rcx
0x18001f865  jz      short loc_18001F8AC
0x18001f867  mov     [rdi], rcx
0x18001f86a  mov     eax, [rcx]
0x18001f86c  inc     eax
0x18001f86e  mov     [rcx], eax
0x18001f870  lea     rcx, [rsp+270h+var_238]
0x18001f875  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f87a  xor     ebx, ebx
0x18001f87c  lea     rcx, [rsp+270h+var_240]
0x18001f881  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f886  mov     eax, ebx
0x18001f888  mov     rcx, [rbp+170h+var_10]
0x18001f88f  xor     rcx, rsp; StackCookie
0x18001f892  call    __security_check_cookie
0x18001f897  lea     r11, [rsp+270h+var_s0]
0x18001f89f  mov     rbx, [r11+20h]
0x18001f8a3  mov     rdi, [r11+28h]
0x18001f8a7  mov     rsp, r11
0x18001f8aa  pop     rbp
0x18001f8ab  retn
0x18001f8ac  mov     r8, rdi
0x18001f8af  lea     rdx, [rsp+270h+var_240]
0x18001f8b4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f8b9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001f8be  mov     ebx, eax
0x18001f8c0  test    eax, eax
0x18001f8c2  jns     short loc_18001F870
0x18001f8c4  mov     edx, 137h
0x18001f8c9  jmp     loc_18001F83B
```
