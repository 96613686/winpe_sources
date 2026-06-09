# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005968`
- end: `0x180005ace`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006530`

## callees

- `0x180002a90`
- `0x18000538c`
- `0x1800053a8`
- `0x180005968`
- `0x180006248`
- `0x180006c70`
- `0x180007654`
- `0x180007c2c`
- `0x180007d98`
- `0x1800084cc`
- `0x180008710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800059e5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800059e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800059a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800059a0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180005968  mov     [rsp-8+arg_10], rbx
0x18000596d  mov     [rsp-8+arg_18], rdi
0x180005972  push    rbp
0x180005973  lea     rbp, [rsp-170h]
0x18000597b  sub     rsp, 270h
0x180005982  mov     rax, cs:__security_cookie
0x180005989  xor     rax, rsp
0x18000598c  mov     [rbp+170h+var_10], rax
0x180005993  mov     rdi, rdx
0x180005996  mov     qword ptr [rdx], 0
0x18000599d  mov     rbx, rcx
0x1800059a0  call    cs:__imp_GetCurrentProcessId
0x1800059a6  mov     [rsp+270h+var_248], rbx
0x1800059ab  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800059b2  mov     r9d, eax
0x1800059b5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800059bd  mov     edx, 104h; unsigned __int64
0x1800059c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800059c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800059cc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800059d2  mov     [rsp+270h+var_240], 0
0x1800059db  xor     r8d, r8d; dwFlags
0x1800059de  lea     rdx, [rsp+270h+Name]; lpName
0x1800059e3  xor     ecx, ecx; lpMutexAttributes
0x1800059e5  call    cs:__imp_CreateMutexExW
0x1800059eb  mov     rdx, rax
0x1800059ee  lea     rcx, [rsp+270h+var_240]
0x1800059f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800059f8  cmp     [rsp+270h+var_240], 0
0x1800059fe  jnz     short loc_180005A09
0x180005a00  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005a05  mov     ebx, eax
0x180005a07  jmp     short loc_180005A7C
0x180005a09  lea     rdx, [rsp+270h+var_238]
0x180005a0e  lea     rcx, [rsp+270h+var_240]
0x180005a13  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005a18  lea     rdx, [rsp+270h+var_230]; void **
0x180005a1d  mov     [rsp+270h+var_230], 0
0x180005a26  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005a2b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005a30  mov     ebx, eax
0x180005a32  test    eax, eax
0x180005a34  jns     short loc_180005A5D
0x180005a36  mov     edx, 12Eh; void *
0x180005a3b  mov     rcx, [rbp+178h]; this
0x180005a42  lea     r8, aWil; "wil"
0x180005a49  mov     r9d, eax; char *
0x180005a4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a51  lea     rcx, [rsp+270h+var_238]
0x180005a56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005a5b  jmp     short loc_180005A7C
0x180005a5d  mov     rcx, [rsp+270h+var_230]
0x180005a62  test    rcx, rcx
0x180005a65  jz      short loc_180005AAC
0x180005a67  mov     [rdi], rcx
0x180005a6a  mov     eax, [rcx]
0x180005a6c  inc     eax
0x180005a6e  mov     [rcx], eax
0x180005a70  lea     rcx, [rsp+270h+var_238]
0x180005a75  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005a7a  xor     ebx, ebx
0x180005a7c  lea     rcx, [rsp+270h+var_240]
0x180005a81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005a86  mov     eax, ebx
0x180005a88  mov     rcx, [rbp+170h+var_10]
0x180005a8f  xor     rcx, rsp; StackCookie
0x180005a92  call    __security_check_cookie
0x180005a97  lea     r11, [rsp+270h+var_s0]
0x180005a9f  mov     rbx, [r11+20h]
0x180005aa3  mov     rdi, [r11+28h]
0x180005aa7  mov     rsp, r11
0x180005aaa  pop     rbp
0x180005aab  retn
0x180005aac  mov     r8, rdi
0x180005aaf  lea     rdx, [rsp+270h+var_240]
0x180005ab4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005ab9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005abe  mov     ebx, eax
0x180005ac0  test    eax, eax
0x180005ac2  jns     short loc_180005A70
0x180005ac4  mov     edx, 137h
0x180005ac9  jmp     loc_180005A3B
```
