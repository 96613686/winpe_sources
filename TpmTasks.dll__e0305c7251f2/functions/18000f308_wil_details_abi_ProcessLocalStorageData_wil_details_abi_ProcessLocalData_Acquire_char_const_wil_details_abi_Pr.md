# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000f308`
- end: `0x18000f46e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180014970`

## callees

- `0x1800078b0`
- `0x18000e570`
- `0x18000e58c`
- `0x18000f308`
- `0x18001413c`
- `0x18001602c`
- `0x18001a42c`
- `0x18001be20`
- `0x18001d93c`
- `0x180023d5c`
- `0x1800249b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f385`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f340`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f340`

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
0x18000f308  mov     [rsp-8+arg_10], rbx
0x18000f30d  mov     [rsp-8+arg_18], rdi
0x18000f312  push    rbp
0x18000f313  lea     rbp, [rsp-170h]
0x18000f31b  sub     rsp, 270h
0x18000f322  mov     rax, cs:__security_cookie
0x18000f329  xor     rax, rsp
0x18000f32c  mov     [rbp+170h+var_10], rax
0x18000f333  mov     rdi, rdx
0x18000f336  mov     qword ptr [rdx], 0
0x18000f33d  mov     rbx, rcx
0x18000f340  call    cs:__imp_GetCurrentProcessId
0x18000f346  mov     [rsp+270h+var_248], rbx
0x18000f34b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000f352  mov     r9d, eax
0x18000f355  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000f35d  mov     edx, 104h; unsigned __int64
0x18000f362  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f367  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f36c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000f372  mov     [rsp+270h+var_240], 0
0x18000f37b  xor     r8d, r8d; dwFlags
0x18000f37e  lea     rdx, [rsp+270h+Name]; lpName
0x18000f383  xor     ecx, ecx; lpMutexAttributes
0x18000f385  call    cs:__imp_CreateMutexExW
0x18000f38b  mov     rdx, rax
0x18000f38e  lea     rcx, [rsp+270h+var_240]
0x18000f393  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f398  cmp     [rsp+270h+var_240], 0
0x18000f39e  jnz     short loc_18000F3A9
0x18000f3a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f3a5  mov     ebx, eax
0x18000f3a7  jmp     short loc_18000F41C
0x18000f3a9  lea     rdx, [rsp+270h+var_238]
0x18000f3ae  lea     rcx, [rsp+270h+var_240]
0x18000f3b3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000f3b8  lea     rdx, [rsp+270h+var_230]; void **
0x18000f3bd  mov     [rsp+270h+var_230], 0
0x18000f3c6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f3cb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000f3d0  mov     ebx, eax
0x18000f3d2  test    eax, eax
0x18000f3d4  jns     short loc_18000F3FD
0x18000f3d6  mov     edx, 12Eh; void *
0x18000f3db  mov     rcx, [rbp+178h]; this
0x18000f3e2  lea     r8, aWil; "wil"
0x18000f3e9  mov     r9d, eax; char *
0x18000f3ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f3f1  lea     rcx, [rsp+270h+var_238]
0x18000f3f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f3fb  jmp     short loc_18000F41C
0x18000f3fd  mov     rcx, [rsp+270h+var_230]
0x18000f402  test    rcx, rcx
0x18000f405  jz      short loc_18000F44C
0x18000f407  mov     [rdi], rcx
0x18000f40a  mov     eax, [rcx]
0x18000f40c  inc     eax
0x18000f40e  mov     [rcx], eax
0x18000f410  lea     rcx, [rsp+270h+var_238]
0x18000f415  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f41a  xor     ebx, ebx
0x18000f41c  lea     rcx, [rsp+270h+var_240]
0x18000f421  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f426  mov     eax, ebx
0x18000f428  mov     rcx, [rbp+170h+var_10]
0x18000f42f  xor     rcx, rsp; StackCookie
0x18000f432  call    __security_check_cookie
0x18000f437  lea     r11, [rsp+270h+var_s0]
0x18000f43f  mov     rbx, [r11+20h]
0x18000f443  mov     rdi, [r11+28h]
0x18000f447  mov     rsp, r11
0x18000f44a  pop     rbp
0x18000f44b  retn
0x18000f44c  mov     r8, rdi
0x18000f44f  lea     rdx, [rsp+270h+var_240]
0x18000f454  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f459  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000f45e  mov     ebx, eax
0x18000f460  test    eax, eax
0x18000f462  jns     short loc_18000F410
0x18000f464  mov     edx, 137h
0x18000f469  jmp     loc_18000F3DB
```
