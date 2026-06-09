# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008b9c`
- end: `0x180008d0f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800097c8`

## callees

- `0x180004eb0`
- `0x1800089e8`
- `0x180008a08`
- `0x180008b9c`
- `0x180009510`
- `0x180009f7c`
- `0x18000a5c4`
- `0x18000ac30`
- `0x18000ae0c`
- `0x18000b2c0`
- `0x18000b3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008c1f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008c1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008bd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008bd4`

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
0x180008b9c  mov     [rsp-8+arg_10], rbx
0x180008ba1  mov     [rsp-8+arg_18], rdi
0x180008ba6  push    rbp
0x180008ba7  lea     rbp, [rsp-170h]
0x180008baf  sub     rsp, 270h
0x180008bb6  mov     rax, cs:__security_cookie
0x180008bbd  xor     rax, rsp
0x180008bc0  mov     [rbp+170h+var_10], rax
0x180008bc7  mov     rdi, rdx
0x180008bca  mov     qword ptr [rdx], 0
0x180008bd1  mov     rbx, rcx
0x180008bd4  call    cs:__imp_GetCurrentProcessId
0x180008bdb  nop     dword ptr [rax+rax+00h]
0x180008be0  mov     [rsp+270h+var_248], rbx
0x180008be5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008bec  mov     r9d, eax
0x180008bef  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180008bf7  mov     edx, 104h; unsigned __int64
0x180008bfc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008c01  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008c06  mov     r9d, 1F0001h; dwDesiredAccess
0x180008c0c  mov     [rsp+270h+var_240], 0
0x180008c15  xor     r8d, r8d; dwFlags
0x180008c18  lea     rdx, [rsp+270h+Name]; lpName
0x180008c1d  xor     ecx, ecx; lpMutexAttributes
0x180008c1f  call    cs:__imp_CreateMutexExW
0x180008c26  nop     dword ptr [rax+rax+00h]
0x180008c2b  mov     rdx, rax
0x180008c2e  lea     rcx, [rsp+270h+var_240]
0x180008c33  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008c38  cmp     [rsp+270h+var_240], 0
0x180008c3e  jnz     short loc_180008C49
0x180008c40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008c45  mov     ebx, eax
0x180008c47  jmp     short loc_180008CBC
0x180008c49  lea     rdx, [rsp+270h+var_238]
0x180008c4e  lea     rcx, [rsp+270h+var_240]
0x180008c53  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008c58  lea     rdx, [rsp+270h+var_230]; void **
0x180008c5d  mov     [rsp+270h+var_230], 0
0x180008c66  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008c6b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008c70  mov     ebx, eax
0x180008c72  test    eax, eax
0x180008c74  jns     short loc_180008C9D
0x180008c76  mov     edx, 12Eh; void *
0x180008c7b  mov     rcx, [rbp+178h]; this
0x180008c82  lea     r8, aWil; "wil"
0x180008c89  mov     r9d, eax; char *
0x180008c8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c91  lea     rcx, [rsp+270h+var_238]
0x180008c96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008c9b  jmp     short loc_180008CBC
0x180008c9d  mov     rcx, [rsp+270h+var_230]
0x180008ca2  test    rcx, rcx
0x180008ca5  jz      short loc_180008CED
0x180008ca7  mov     [rdi], rcx
0x180008caa  mov     eax, [rcx]
0x180008cac  inc     eax
0x180008cae  mov     [rcx], eax
0x180008cb0  lea     rcx, [rsp+270h+var_238]
0x180008cb5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008cba  xor     ebx, ebx
0x180008cbc  lea     rcx, [rsp+270h+var_240]
0x180008cc1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008cc6  mov     eax, ebx
0x180008cc8  mov     rcx, [rbp+170h+var_10]
0x180008ccf  xor     rcx, rsp; StackCookie
0x180008cd2  call    __security_check_cookie
0x180008cd7  lea     r11, [rsp+270h+var_s0]
0x180008cdf  mov     rbx, [r11+20h]
0x180008ce3  mov     rdi, [r11+28h]
0x180008ce7  mov     rsp, r11
0x180008cea  pop     rbp
0x180008ceb  retn
0x180008ced  mov     r8, rdi
0x180008cf0  lea     rdx, [rsp+270h+var_240]
0x180008cf5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008cfa  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008cff  mov     ebx, eax
0x180008d01  test    eax, eax
0x180008d03  jns     short loc_180008CB0
0x180008d05  mov     edx, 137h
0x180008d0a  jmp     loc_180008C7B
```
