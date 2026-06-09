# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180140944`
- end: `0x180140aaa`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801419e8`

## callees

- `0x1801378fc`
- `0x18013bad0`
- `0x1801405c0`
- `0x1801405dc`
- `0x180140944`
- `0x18014224c`
- `0x18014357c`
- `0x180143a74`
- `0x180143f40`
- `0x1801447a4`
- `0x180144a8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1801409c1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1801409c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18014097c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18014097c`

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
0x180140944  mov     [rsp-8+arg_10], rbx
0x180140949  mov     [rsp-8+arg_18], rdi
0x18014094e  push    rbp
0x18014094f  lea     rbp, [rsp-170h]
0x180140957  sub     rsp, 270h
0x18014095e  mov     rax, cs:__security_cookie
0x180140965  xor     rax, rsp
0x180140968  mov     [rbp+170h+var_10], rax
0x18014096f  mov     rdi, rdx
0x180140972  mov     qword ptr [rdx], 0
0x180140979  mov     rbx, rcx
0x18014097c  call    cs:__imp_GetCurrentProcessId
0x180140982  mov     [rsp+270h+var_248], rbx
0x180140987  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18014098e  mov     r9d, eax
0x180140991  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180140999  mov     edx, 104h; unsigned __int64
0x18014099e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1801409a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801409a8  mov     r9d, 1F0001h; dwDesiredAccess
0x1801409ae  mov     [rsp+270h+var_240], 0
0x1801409b7  xor     r8d, r8d; dwFlags
0x1801409ba  lea     rdx, [rsp+270h+Name]; lpName
0x1801409bf  xor     ecx, ecx; lpMutexAttributes
0x1801409c1  call    cs:__imp_CreateMutexExW
0x1801409c7  mov     rdx, rax
0x1801409ca  lea     rcx, [rsp+270h+var_240]
0x1801409cf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1801409d4  cmp     [rsp+270h+var_240], 0
0x1801409da  jnz     short loc_1801409E5
0x1801409dc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1801409e1  mov     ebx, eax
0x1801409e3  jmp     short loc_180140A58
0x1801409e5  lea     rdx, [rsp+270h+var_238]
0x1801409ea  lea     rcx, [rsp+270h+var_240]
0x1801409ef  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1801409f4  lea     rdx, [rsp+270h+var_230]; void **
0x1801409f9  mov     [rsp+270h+var_230], 0
0x180140a02  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180140a07  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180140a0c  mov     ebx, eax
0x180140a0e  test    eax, eax
0x180140a10  jns     short loc_180140A39
0x180140a12  mov     edx, 12Eh; void *
0x180140a17  mov     rcx, [rbp+178h]; this
0x180140a1e  lea     r8, aWil; "wil"
0x180140a25  mov     r9d, eax; char *
0x180140a28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140a2d  lea     rcx, [rsp+270h+var_238]
0x180140a32  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180140a37  jmp     short loc_180140A58
0x180140a39  mov     rcx, [rsp+270h+var_230]
0x180140a3e  test    rcx, rcx
0x180140a41  jz      short loc_180140A88
0x180140a43  mov     [rdi], rcx
0x180140a46  mov     eax, [rcx]
0x180140a48  inc     eax
0x180140a4a  mov     [rcx], eax
0x180140a4c  lea     rcx, [rsp+270h+var_238]
0x180140a51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180140a56  xor     ebx, ebx
0x180140a58  lea     rcx, [rsp+270h+var_240]
0x180140a5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180140a62  mov     eax, ebx
0x180140a64  mov     rcx, [rbp+170h+var_10]
0x180140a6b  xor     rcx, rsp; StackCookie
0x180140a6e  call    __security_check_cookie
0x180140a73  lea     r11, [rsp+270h+var_s0]
0x180140a7b  mov     rbx, [r11+20h]
0x180140a7f  mov     rdi, [r11+28h]
0x180140a83  mov     rsp, r11
0x180140a86  pop     rbp
0x180140a87  retn
0x180140a88  mov     r8, rdi
0x180140a8b  lea     rdx, [rsp+270h+var_240]
0x180140a90  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180140a95  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180140a9a  mov     ebx, eax
0x180140a9c  test    eax, eax
0x180140a9e  jns     short loc_180140A4C
0x180140aa0  mov     edx, 137h
0x180140aa5  jmp     loc_180140A17
```
