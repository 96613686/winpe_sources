# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004da8`
- end: `0x180004f0e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006d08`

## callees

- `0x1800021d0`
- `0x1800046b0`
- `0x1800046cc`
- `0x180004da8`
- `0x1800069b8`
- `0x1800077c8`
- `0x18000972c`
- `0x180009f8c`
- `0x18000a58c`
- `0x18000aef4`
- `0x18000b38c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004de0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004de0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e25`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e25`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180004da8  mov     [rsp-8+arg_10], rbx
0x180004dad  mov     [rsp-8+arg_18], rdi
0x180004db2  push    rbp
0x180004db3  lea     rbp, [rsp-170h]
0x180004dbb  sub     rsp, 270h
0x180004dc2  mov     rax, cs:__security_cookie
0x180004dc9  xor     rax, rsp
0x180004dcc  mov     [rbp+170h+var_10], rax
0x180004dd3  mov     rdi, rdx
0x180004dd6  mov     qword ptr [rdx], 0
0x180004ddd  mov     rbx, rcx
0x180004de0  call    cs:__imp_GetCurrentProcessId
0x180004de6  mov     [rsp+270h+var_248], rbx
0x180004deb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004df2  mov     r9d, eax
0x180004df5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004dfd  mov     edx, 104h; unsigned __int64
0x180004e02  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004e07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004e0c  mov     r9d, 1F0001h; dwDesiredAccess
0x180004e12  mov     [rsp+270h+var_240], 0
0x180004e1b  xor     r8d, r8d; dwFlags
0x180004e1e  lea     rdx, [rsp+270h+Name]; lpName
0x180004e23  xor     ecx, ecx; lpMutexAttributes
0x180004e25  call    cs:__imp_CreateMutexExW
0x180004e2b  mov     rdx, rax
0x180004e2e  lea     rcx, [rsp+270h+var_240]
0x180004e33  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004e38  cmp     [rsp+270h+var_240], 0
0x180004e3e  jnz     short loc_180004E49
0x180004e40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004e45  mov     ebx, eax
0x180004e47  jmp     short loc_180004EBC
0x180004e49  lea     rdx, [rsp+270h+var_238]
0x180004e4e  lea     rcx, [rsp+270h+var_240]
0x180004e53  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004e58  lea     rdx, [rsp+270h+var_230]; void **
0x180004e5d  mov     [rsp+270h+var_230], 0
0x180004e66  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004e6b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004e70  mov     ebx, eax
0x180004e72  test    eax, eax
0x180004e74  jns     short loc_180004E9D
0x180004e76  mov     edx, 12Eh; void *
0x180004e7b  mov     rcx, [rbp+178h]; this
0x180004e82  lea     r8, aWil; "wil"
0x180004e89  mov     r9d, eax; char *
0x180004e8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e91  lea     rcx, [rsp+270h+var_238]
0x180004e96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004e9b  jmp     short loc_180004EBC
0x180004e9d  mov     rcx, [rsp+270h+var_230]
0x180004ea2  test    rcx, rcx
0x180004ea5  jz      short loc_180004EEC
0x180004ea7  mov     [rdi], rcx
0x180004eaa  mov     eax, [rcx]
0x180004eac  inc     eax
0x180004eae  mov     [rcx], eax
0x180004eb0  lea     rcx, [rsp+270h+var_238]
0x180004eb5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004eba  xor     ebx, ebx
0x180004ebc  lea     rcx, [rsp+270h+var_240]
0x180004ec1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004ec6  mov     eax, ebx
0x180004ec8  mov     rcx, [rbp+170h+var_10]
0x180004ecf  xor     rcx, rsp; StackCookie
0x180004ed2  call    __security_check_cookie
0x180004ed7  lea     r11, [rsp+270h+var_s0]
0x180004edf  mov     rbx, [r11+20h]
0x180004ee3  mov     rdi, [r11+28h]
0x180004ee7  mov     rsp, r11
0x180004eea  pop     rbp
0x180004eeb  retn
0x180004eec  mov     r8, rdi
0x180004eef  lea     rdx, [rsp+270h+var_240]
0x180004ef4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004ef9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004efe  mov     ebx, eax
0x180004f00  test    eax, eax
0x180004f02  jns     short loc_180004EB0
0x180004f04  mov     edx, 137h
0x180004f09  jmp     loc_180004E7B
```
