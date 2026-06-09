# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800073a8`
- end: `0x18000750e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800087b0`

## callees

- `0x180003390`
- `0x180006d4c`
- `0x180006d68`
- `0x1800073a8`
- `0x180008408`
- `0x180009220`
- `0x18000aa7c`
- `0x18000b218`
- `0x18000b77c`
- `0x18000c1e4`
- `0x18000c68c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007425`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007425`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800073e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800073e0`

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
0x1800073a8  mov     [rsp-8+arg_10], rbx
0x1800073ad  mov     [rsp-8+arg_18], rdi
0x1800073b2  push    rbp
0x1800073b3  lea     rbp, [rsp-170h]
0x1800073bb  sub     rsp, 270h
0x1800073c2  mov     rax, cs:__security_cookie
0x1800073c9  xor     rax, rsp
0x1800073cc  mov     [rbp+170h+var_10], rax
0x1800073d3  mov     rdi, rdx
0x1800073d6  mov     qword ptr [rdx], 0
0x1800073dd  mov     rbx, rcx
0x1800073e0  call    cs:__imp_GetCurrentProcessId
0x1800073e6  mov     [rsp+270h+var_248], rbx
0x1800073eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800073f2  mov     r9d, eax
0x1800073f5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800073fd  mov     edx, 104h; unsigned __int64
0x180007402  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007407  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000740c  mov     r9d, 1F0001h; dwDesiredAccess
0x180007412  mov     [rsp+270h+var_240], 0
0x18000741b  xor     r8d, r8d; dwFlags
0x18000741e  lea     rdx, [rsp+270h+Name]; lpName
0x180007423  xor     ecx, ecx; lpMutexAttributes
0x180007425  call    cs:__imp_CreateMutexExW
0x18000742b  mov     rdx, rax
0x18000742e  lea     rcx, [rsp+270h+var_240]
0x180007433  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007438  cmp     [rsp+270h+var_240], 0
0x18000743e  jnz     short loc_180007449
0x180007440  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007445  mov     ebx, eax
0x180007447  jmp     short loc_1800074BC
0x180007449  lea     rdx, [rsp+270h+var_238]
0x18000744e  lea     rcx, [rsp+270h+var_240]
0x180007453  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180007458  lea     rdx, [rsp+270h+var_230]; void **
0x18000745d  mov     [rsp+270h+var_230], 0
0x180007466  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000746b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180007470  mov     ebx, eax
0x180007472  test    eax, eax
0x180007474  jns     short loc_18000749D
0x180007476  mov     edx, 12Eh; void *
0x18000747b  mov     rcx, [rbp+178h]; this
0x180007482  lea     r8, aWil; "wil"
0x180007489  mov     r9d, eax; char *
0x18000748c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007491  lea     rcx, [rsp+270h+var_238]
0x180007496  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000749b  jmp     short loc_1800074BC
0x18000749d  mov     rcx, [rsp+270h+var_230]
0x1800074a2  test    rcx, rcx
0x1800074a5  jz      short loc_1800074EC
0x1800074a7  mov     [rdi], rcx
0x1800074aa  mov     eax, [rcx]
0x1800074ac  inc     eax
0x1800074ae  mov     [rcx], eax
0x1800074b0  lea     rcx, [rsp+270h+var_238]
0x1800074b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800074ba  xor     ebx, ebx
0x1800074bc  lea     rcx, [rsp+270h+var_240]
0x1800074c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800074c6  mov     eax, ebx
0x1800074c8  mov     rcx, [rbp+170h+var_10]
0x1800074cf  xor     rcx, rsp; StackCookie
0x1800074d2  call    __security_check_cookie
0x1800074d7  lea     r11, [rsp+270h+var_s0]
0x1800074df  mov     rbx, [r11+20h]
0x1800074e3  mov     rdi, [r11+28h]
0x1800074e7  mov     rsp, r11
0x1800074ea  pop     rbp
0x1800074eb  retn
0x1800074ec  mov     r8, rdi
0x1800074ef  lea     rdx, [rsp+270h+var_240]
0x1800074f4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800074f9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800074fe  mov     ebx, eax
0x180007500  test    eax, eax
0x180007502  jns     short loc_1800074B0
0x180007504  mov     edx, 137h
0x180007509  jmp     loc_18000747B
```
