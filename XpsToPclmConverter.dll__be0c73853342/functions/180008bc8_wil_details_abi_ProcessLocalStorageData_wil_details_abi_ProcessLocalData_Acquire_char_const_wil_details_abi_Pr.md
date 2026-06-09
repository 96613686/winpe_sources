# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008bc8`
- end: `0x180008d27`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009c24`

## callees

- `0x1800015f0`
- `0x1800087a4`
- `0x1800087c0`
- `0x180008bc8`
- `0x1800098f8`
- `0x18000a54c`
- `0x18000b8bc`
- `0x18000bffc`
- `0x18000c428`
- `0x18000cb54`
- `0x18000ce8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008c45`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008c45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008c00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008c00`

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
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
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
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180008bc8  mov     [rsp-8+arg_10], rbx
0x180008bcd  mov     [rsp-8+arg_18], rdi
0x180008bd2  push    rbp
0x180008bd3  lea     rbp, [rsp-170h]
0x180008bdb  sub     rsp, 270h
0x180008be2  mov     rax, cs:__security_cookie
0x180008be9  xor     rax, rsp
0x180008bec  mov     [rbp+170h+var_10], rax
0x180008bf3  mov     rdi, rdx
0x180008bf6  mov     qword ptr [rdx], 0
0x180008bfd  mov     rbx, rcx
0x180008c00  call    cs:__imp_GetCurrentProcessId
0x180008c06  mov     [rsp+270h+var_248], rbx
0x180008c0b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008c12  mov     r9d, eax
0x180008c15  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180008c1d  mov     edx, 104h; unsigned __int64
0x180008c22  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008c27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008c2c  mov     r9d, 1F0001h; dwDesiredAccess
0x180008c32  mov     [rsp+270h+var_240], 0
0x180008c3b  xor     r8d, r8d; dwFlags
0x180008c3e  lea     rdx, [rsp+270h+Name]; lpName
0x180008c43  xor     ecx, ecx; lpMutexAttributes
0x180008c45  call    cs:__imp_CreateMutexExW
0x180008c4b  mov     rdx, rax
0x180008c4e  lea     rcx, [rsp+270h+var_240]
0x180008c53  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008c58  cmp     [rsp+270h+var_240], 0
0x180008c5e  jnz     short loc_180008C69
0x180008c60  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008c65  mov     ebx, eax
0x180008c67  jmp     short loc_180008CD5
0x180008c69  lea     rdx, [rsp+270h+var_238]
0x180008c6e  lea     rcx, [rsp+270h+var_240]
0x180008c73  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008c78  lea     rdx, [rsp+270h+var_230]; void **
0x180008c7d  mov     [rsp+270h+var_230], 0
0x180008c86  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008c8b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008c90  mov     ebx, eax
0x180008c92  test    eax, eax
0x180008c94  jns     short loc_180008CB6
0x180008c96  mov     edx, 12Eh; void *
0x180008c9b  mov     rcx, [rbp+178h]; this
0x180008ca2  mov     r9d, eax; char *
0x180008ca5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008caa  lea     rcx, [rsp+270h+var_238]
0x180008caf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008cb4  jmp     short loc_180008CD5
0x180008cb6  mov     rcx, [rsp+270h+var_230]
0x180008cbb  test    rcx, rcx
0x180008cbe  jz      short loc_180008D05
0x180008cc0  mov     [rdi], rcx
0x180008cc3  mov     eax, [rcx]
0x180008cc5  inc     eax
0x180008cc7  mov     [rcx], eax
0x180008cc9  lea     rcx, [rsp+270h+var_238]
0x180008cce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008cd3  xor     ebx, ebx
0x180008cd5  lea     rcx, [rsp+270h+var_240]
0x180008cda  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008cdf  mov     eax, ebx
0x180008ce1  mov     rcx, [rbp+170h+var_10]
0x180008ce8  xor     rcx, rsp; StackCookie
0x180008ceb  call    __security_check_cookie
0x180008cf0  lea     r11, [rsp+270h+var_s0]
0x180008cf8  mov     rbx, [r11+20h]
0x180008cfc  mov     rdi, [r11+28h]
0x180008d00  mov     rsp, r11
0x180008d03  pop     rbp
0x180008d04  retn
0x180008d05  mov     r8, rdi
0x180008d08  lea     rdx, [rsp+270h+var_240]
0x180008d0d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008d12  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008d17  mov     ebx, eax
0x180008d19  test    eax, eax
0x180008d1b  jns     short loc_180008CC9
0x180008d1d  mov     edx, 137h
0x180008d22  jmp     loc_180008C9B
```
