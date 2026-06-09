# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000c3a4`
- end: `0x18000c50a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000fde0`

## callees

- `0x18000bd24`
- `0x18000bd40`
- `0x18000c3a4`
- `0x18000fb98`
- `0x180014608`
- `0x1800166cc`
- `0x180016f24`
- `0x1800174c0`
- `0x180018810`
- `0x180018f64`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c421`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c421`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c3dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c3dc`

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
0x18000c3a4  mov     [rsp-8+arg_10], rbx
0x18000c3a9  mov     [rsp-8+arg_18], rdi
0x18000c3ae  push    rbp
0x18000c3af  lea     rbp, [rsp-170h]
0x18000c3b7  sub     rsp, 270h
0x18000c3be  mov     rax, cs:__security_cookie
0x18000c3c5  xor     rax, rsp
0x18000c3c8  mov     [rbp+170h+var_10], rax
0x18000c3cf  mov     rdi, rdx
0x18000c3d2  mov     qword ptr [rdx], 0
0x18000c3d9  mov     rbx, rcx
0x18000c3dc  call    cs:__imp_GetCurrentProcessId
0x18000c3e2  mov     [rsp+270h+var_248], rbx
0x18000c3e7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c3ee  mov     r9d, eax
0x18000c3f1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000c3f9  mov     edx, 104h; unsigned __int64
0x18000c3fe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c403  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c408  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c40e  mov     [rsp+270h+var_240], 0
0x18000c417  xor     r8d, r8d; dwFlags
0x18000c41a  lea     rdx, [rsp+270h+Name]; lpName
0x18000c41f  xor     ecx, ecx; lpMutexAttributes
0x18000c421  call    cs:__imp_CreateMutexExW
0x18000c427  mov     rdx, rax
0x18000c42a  lea     rcx, [rsp+270h+var_240]
0x18000c42f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c434  cmp     [rsp+270h+var_240], 0
0x18000c43a  jnz     short loc_18000C445
0x18000c43c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c441  mov     ebx, eax
0x18000c443  jmp     short loc_18000C4B8
0x18000c445  lea     rdx, [rsp+270h+var_238]
0x18000c44a  lea     rcx, [rsp+270h+var_240]
0x18000c44f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000c454  lea     rdx, [rsp+270h+var_230]; void **
0x18000c459  mov     [rsp+270h+var_230], 0
0x18000c462  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c467  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000c46c  mov     ebx, eax
0x18000c46e  test    eax, eax
0x18000c470  jns     short loc_18000C499
0x18000c472  mov     edx, 12Eh; void *
0x18000c477  mov     rcx, [rbp+178h]; this
0x18000c47e  lea     r8, aWil; "wil"
0x18000c485  mov     r9d, eax; char *
0x18000c488  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c48d  lea     rcx, [rsp+270h+var_238]
0x18000c492  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c497  jmp     short loc_18000C4B8
0x18000c499  mov     rcx, [rsp+270h+var_230]
0x18000c49e  test    rcx, rcx
0x18000c4a1  jz      short loc_18000C4E8
0x18000c4a3  mov     [rdi], rcx
0x18000c4a6  mov     eax, [rcx]
0x18000c4a8  inc     eax
0x18000c4aa  mov     [rcx], eax
0x18000c4ac  lea     rcx, [rsp+270h+var_238]
0x18000c4b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c4b6  xor     ebx, ebx
0x18000c4b8  lea     rcx, [rsp+270h+var_240]
0x18000c4bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c4c2  mov     eax, ebx
0x18000c4c4  mov     rcx, [rbp+170h+var_10]
0x18000c4cb  xor     rcx, rsp; StackCookie
0x18000c4ce  call    __security_check_cookie
0x18000c4d3  lea     r11, [rsp+270h+var_s0]
0x18000c4db  mov     rbx, [r11+20h]
0x18000c4df  mov     rdi, [r11+28h]
0x18000c4e3  mov     rsp, r11
0x18000c4e6  pop     rbp
0x18000c4e7  retn
0x18000c4e8  mov     r8, rdi
0x18000c4eb  lea     rdx, [rsp+270h+var_240]
0x18000c4f0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c4f5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000c4fa  mov     ebx, eax
0x18000c4fc  test    eax, eax
0x18000c4fe  jns     short loc_18000C4AC
0x18000c500  mov     edx, 137h
0x18000c505  jmp     loc_18000C477
```
