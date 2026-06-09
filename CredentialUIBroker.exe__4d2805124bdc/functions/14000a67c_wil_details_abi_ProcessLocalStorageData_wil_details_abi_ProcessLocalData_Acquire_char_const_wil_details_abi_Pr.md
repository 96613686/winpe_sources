# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000a67c`
- end: `0x14000a7e2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000df10`

## callees

- `0x140003620`
- `0x1400091f0`
- `0x14000920c`
- `0x14000a67c`
- `0x14000d9e8`
- `0x14000f370`
- `0x1400136fc`
- `0x1400163c8`
- `0x140016dbc`
- `0x140018fe0`
- `0x14001af84`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x14000a6f9`
- `KERNEL32!CreateMutexExW` at `0x14000a6f9`
- `KERNEL32!GetCurrentProcessId` at `0x14000a6b4`
- `KERNEL32!GetCurrentProcessId` at `0x14000a6b4`

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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x14000a67c  mov     [rsp-8+arg_10], rbx
0x14000a681  mov     [rsp-8+arg_18], rdi
0x14000a686  push    rbp
0x14000a687  lea     rbp, [rsp-170h]
0x14000a68f  sub     rsp, 270h
0x14000a696  mov     rax, cs:__security_cookie
0x14000a69d  xor     rax, rsp
0x14000a6a0  mov     [rbp+170h+var_10], rax
0x14000a6a7  mov     rdi, rdx
0x14000a6aa  mov     qword ptr [rdx], 0
0x14000a6b1  mov     rbx, rcx
0x14000a6b4  call    cs:__imp_GetCurrentProcessId
0x14000a6ba  mov     [rsp+270h+var_248], rbx
0x14000a6bf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000a6c6  mov     r9d, eax
0x14000a6c9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x14000a6d1  mov     edx, 104h; unsigned __int64
0x14000a6d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000a6db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a6e0  mov     r9d, 1F0001h; dwDesiredAccess
0x14000a6e6  mov     [rsp+270h+var_240], 0
0x14000a6ef  xor     r8d, r8d; dwFlags
0x14000a6f2  lea     rdx, [rsp+270h+Name]; lpName
0x14000a6f7  xor     ecx, ecx; lpMutexAttributes
0x14000a6f9  call    cs:__imp_CreateMutexExW
0x14000a6ff  mov     rdx, rax
0x14000a702  lea     rcx, [rsp+270h+var_240]
0x14000a707  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000a70c  cmp     [rsp+270h+var_240], 0
0x14000a712  jnz     short loc_14000A71D
0x14000a714  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000a719  mov     ebx, eax
0x14000a71b  jmp     short loc_14000A790
0x14000a71d  lea     rdx, [rsp+270h+var_238]
0x14000a722  lea     rcx, [rsp+270h+var_240]
0x14000a727  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000a72c  lea     rdx, [rsp+270h+var_230]; void **
0x14000a731  mov     [rsp+270h+var_230], 0
0x14000a73a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000a73f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14000a744  mov     ebx, eax
0x14000a746  test    eax, eax
0x14000a748  jns     short loc_14000A771
0x14000a74a  mov     edx, 12Eh; void *
0x14000a74f  mov     rcx, [rbp+178h]; this
0x14000a756  lea     r8, aWil; "wil"
0x14000a75d  mov     r9d, eax; char *
0x14000a760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a765  lea     rcx, [rsp+270h+var_238]
0x14000a76a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000a76f  jmp     short loc_14000A790
0x14000a771  mov     rcx, [rsp+270h+var_230]
0x14000a776  test    rcx, rcx
0x14000a779  jz      short loc_14000A7C0
0x14000a77b  mov     [rdi], rcx
0x14000a77e  mov     eax, [rcx]
0x14000a780  inc     eax
0x14000a782  mov     [rcx], eax
0x14000a784  lea     rcx, [rsp+270h+var_238]
0x14000a789  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000a78e  xor     ebx, ebx
0x14000a790  lea     rcx, [rsp+270h+var_240]
0x14000a795  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000a79a  mov     eax, ebx
0x14000a79c  mov     rcx, [rbp+170h+var_10]
0x14000a7a3  xor     rcx, rsp; StackCookie
0x14000a7a6  call    __security_check_cookie
0x14000a7ab  lea     r11, [rsp+270h+var_s0]
0x14000a7b3  mov     rbx, [r11+20h]
0x14000a7b7  mov     rdi, [r11+28h]
0x14000a7bb  mov     rsp, r11
0x14000a7be  pop     rbp
0x14000a7bf  retn
0x14000a7c0  mov     r8, rdi
0x14000a7c3  lea     rdx, [rsp+270h+var_240]
0x14000a7c8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000a7cd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000a7d2  mov     ebx, eax
0x14000a7d4  test    eax, eax
0x14000a7d6  jns     short loc_14000A784
0x14000a7d8  mov     edx, 137h
0x14000a7dd  jmp     loc_14000A74F
```
