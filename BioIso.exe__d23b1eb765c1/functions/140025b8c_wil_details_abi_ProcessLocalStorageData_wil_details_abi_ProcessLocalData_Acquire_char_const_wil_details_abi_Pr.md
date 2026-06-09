# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140025b8c`
- end: `0x140025cff`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140026bf0`

## callees

- `0x14000a420`
- `0x140018ef8`
- `0x14001bd40`
- `0x1400258a4`
- `0x1400258c4`
- `0x140025b8c`
- `0x14002717c`
- `0x1400289d8`
- `0x140028ec8`
- `0x1400296d4`
- `0x14002986c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140025c0f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140025c0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140025bc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140025bc4`

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
0x140025b8c  mov     [rsp-8+arg_10], rbx
0x140025b91  mov     [rsp-8+arg_18], rdi
0x140025b96  push    rbp
0x140025b97  lea     rbp, [rsp-170h]
0x140025b9f  sub     rsp, 270h
0x140025ba6  mov     rax, cs:__security_cookie
0x140025bad  xor     rax, rsp
0x140025bb0  mov     [rbp+170h+var_10], rax
0x140025bb7  mov     rdi, rdx
0x140025bba  mov     qword ptr [rdx], 0
0x140025bc1  mov     rbx, rcx
0x140025bc4  call    cs:__imp_GetCurrentProcessId
0x140025bcb  nop     dword ptr [rax+rax+00h]
0x140025bd0  mov     [rsp+270h+var_248], rbx
0x140025bd5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140025bdc  mov     r9d, eax
0x140025bdf  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140025be7  mov     edx, 104h; unsigned __int64
0x140025bec  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140025bf1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140025bf6  mov     r9d, 1F0001h; dwDesiredAccess
0x140025bfc  mov     [rsp+270h+var_240], 0
0x140025c05  xor     r8d, r8d; dwFlags
0x140025c08  lea     rdx, [rsp+270h+Name]; lpName
0x140025c0d  xor     ecx, ecx; lpMutexAttributes
0x140025c0f  call    cs:__imp_CreateMutexExW
0x140025c16  nop     dword ptr [rax+rax+00h]
0x140025c1b  mov     rdx, rax
0x140025c1e  lea     rcx, [rsp+270h+var_240]
0x140025c23  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140025c28  cmp     [rsp+270h+var_240], 0
0x140025c2e  jnz     short loc_140025C39
0x140025c30  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140025c35  mov     ebx, eax
0x140025c37  jmp     short loc_140025CAC
0x140025c39  lea     rdx, [rsp+270h+var_238]
0x140025c3e  lea     rcx, [rsp+270h+var_240]
0x140025c43  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140025c48  lea     rdx, [rsp+270h+var_230]; void **
0x140025c4d  mov     [rsp+270h+var_230], 0
0x140025c56  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140025c5b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140025c60  mov     ebx, eax
0x140025c62  test    eax, eax
0x140025c64  jns     short loc_140025C8D
0x140025c66  mov     edx, 12Eh; void *
0x140025c6b  mov     rcx, [rbp+178h]; this
0x140025c72  lea     r8, aWil; "wil"
0x140025c79  mov     r9d, eax; char *
0x140025c7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025c81  lea     rcx, [rsp+270h+var_238]
0x140025c86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140025c8b  jmp     short loc_140025CAC
0x140025c8d  mov     rcx, [rsp+270h+var_230]
0x140025c92  test    rcx, rcx
0x140025c95  jz      short loc_140025CDD
0x140025c97  mov     [rdi], rcx
0x140025c9a  mov     eax, [rcx]
0x140025c9c  inc     eax
0x140025c9e  mov     [rcx], eax
0x140025ca0  lea     rcx, [rsp+270h+var_238]
0x140025ca5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140025caa  xor     ebx, ebx
0x140025cac  lea     rcx, [rsp+270h+var_240]
0x140025cb1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140025cb6  mov     eax, ebx
0x140025cb8  mov     rcx, [rbp+170h+var_10]
0x140025cbf  xor     rcx, rsp; StackCookie
0x140025cc2  call    __security_check_cookie
0x140025cc7  lea     r11, [rsp+270h+var_s0]
0x140025ccf  mov     rbx, [r11+20h]
0x140025cd3  mov     rdi, [r11+28h]
0x140025cd7  mov     rsp, r11
0x140025cda  pop     rbp
0x140025cdb  retn
0x140025cdd  mov     r8, rdi
0x140025ce0  lea     rdx, [rsp+270h+var_240]
0x140025ce5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140025cea  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140025cef  mov     ebx, eax
0x140025cf1  test    eax, eax
0x140025cf3  jns     short loc_140025CA0
0x140025cf5  mov     edx, 137h
0x140025cfa  jmp     loc_140025C6B
```
