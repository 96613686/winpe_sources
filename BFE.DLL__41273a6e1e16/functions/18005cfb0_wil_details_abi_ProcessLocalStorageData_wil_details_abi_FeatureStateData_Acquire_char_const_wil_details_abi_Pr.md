# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18005cfb0`
- end: `0x18005d12c`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005d560`

## callees

- `0x180056350`
- `0x180056400`
- `0x18005aa60`
- `0x18005cb18`
- `0x18005cb38`
- `0x18005cfb0`
- `0x18005e7d4`
- `0x18005fd14`
- `0x1800601f4`
- `0x180060af4`
- `0x180060d3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005d033`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005d033`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005cfe8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005cfe8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
    v12 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      &v12);
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
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x18005cfb0  mov     [rsp-8+arg_10], rbx
0x18005cfb5  mov     [rsp-8+arg_18], rdi
0x18005cfba  push    rbp
0x18005cfbb  lea     rbp, [rsp-170h]
0x18005cfc3  sub     rsp, 270h
0x18005cfca  mov     rax, cs:__security_cookie
0x18005cfd1  xor     rax, rsp
0x18005cfd4  mov     [rbp+170h+var_10], rax
0x18005cfdb  mov     rdi, rdx
0x18005cfde  mov     qword ptr [rdx], 0
0x18005cfe5  mov     rbx, rcx
0x18005cfe8  call    cs:__imp_GetCurrentProcessId
0x18005cfef  nop     dword ptr [rax+rax+00h]
0x18005cff4  mov     [rsp+270h+var_248], rbx
0x18005cff9  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18005d000  mov     r9d, eax
0x18005d003  mov     [rsp+270h+var_250], 130h; int
0x18005d00b  mov     edx, 104h; unsigned __int64
0x18005d010  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005d015  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005d01a  mov     r9d, 1F0001h; dwDesiredAccess
0x18005d020  mov     [rsp+270h+var_240], 0
0x18005d029  xor     r8d, r8d; dwFlags
0x18005d02c  lea     rdx, [rsp+270h+Name]; lpName
0x18005d031  xor     ecx, ecx; lpMutexAttributes
0x18005d033  call    cs:__imp_CreateMutexExW
0x18005d03a  nop     dword ptr [rax+rax+00h]
0x18005d03f  mov     rdx, rax
0x18005d042  lea     rcx, [rsp+270h+var_240]
0x18005d047  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005d04c  cmp     [rsp+270h+var_240], 0
0x18005d052  jnz     short loc_18005D05D
0x18005d054  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005d059  mov     ebx, eax
0x18005d05b  jmp     short loc_18005D0D9
0x18005d05d  lea     rdx, [rsp+270h+var_238]
0x18005d062  mov     [rsp+270h+var_238], 0
0x18005d06b  lea     rcx, [rsp+270h+var_240]
0x18005d070  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18005d075  lea     rdx, [rsp+270h+var_230]; void **
0x18005d07a  mov     [rsp+270h+var_230], 0
0x18005d083  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005d088  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18005d08d  mov     ebx, eax
0x18005d08f  test    eax, eax
0x18005d091  jns     short loc_18005D0BA
0x18005d093  mov     edx, 12Eh; void *
0x18005d098  mov     rcx, [rbp+178h]; this
0x18005d09f  lea     r8, aWil; "wil"
0x18005d0a6  mov     r9d, eax; char *
0x18005d0a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d0ae  lea     rcx, [rsp+270h+var_238]
0x18005d0b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005d0b8  jmp     short loc_18005D0D9
0x18005d0ba  mov     rcx, [rsp+270h+var_230]
0x18005d0bf  test    rcx, rcx
0x18005d0c2  jz      short loc_18005D10A
0x18005d0c4  mov     [rdi], rcx
0x18005d0c7  mov     eax, [rcx]
0x18005d0c9  inc     eax
0x18005d0cb  mov     [rcx], eax
0x18005d0cd  lea     rcx, [rsp+270h+var_238]
0x18005d0d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005d0d7  xor     ebx, ebx
0x18005d0d9  lea     rcx, [rsp+270h+var_240]
0x18005d0de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005d0e3  mov     eax, ebx
0x18005d0e5  mov     rcx, [rbp+170h+var_10]
0x18005d0ec  xor     rcx, rsp; StackCookie
0x18005d0ef  call    __security_check_cookie
0x18005d0f4  lea     r11, [rsp+270h+var_s0]
0x18005d0fc  mov     rbx, [r11+20h]
0x18005d100  mov     rdi, [r11+28h]
0x18005d104  mov     rsp, r11
0x18005d107  pop     rbp
0x18005d108  retn
0x18005d10a  mov     r8, rdi
0x18005d10d  lea     rdx, [rsp+270h+var_240]
0x18005d112  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005d117  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005d11c  mov     ebx, eax
0x18005d11e  test    eax, eax
0x18005d120  jns     short loc_18005D0CD
0x18005d122  mov     edx, 137h
0x18005d127  jmp     loc_18005D098
```
