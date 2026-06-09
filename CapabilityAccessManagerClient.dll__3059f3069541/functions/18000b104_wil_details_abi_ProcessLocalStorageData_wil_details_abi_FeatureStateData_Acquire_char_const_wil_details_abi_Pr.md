# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000b104`
- end: `0x18000b26a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c160`

## callees

- `0x180003c80`
- `0x18000aa7c`
- `0x18000aa98`
- `0x18000b104`
- `0x18000bf68`
- `0x18000cec0`
- `0x18000e21c`
- `0x18000ea70`
- `0x18000f01c`
- `0x18000fa64`
- `0x18000fda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b181`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b13c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b13c`

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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x18000b104  mov     [rsp-8+arg_10], rbx
0x18000b109  mov     [rsp-8+arg_18], rdi
0x18000b10e  push    rbp
0x18000b10f  lea     rbp, [rsp-170h]
0x18000b117  sub     rsp, 270h
0x18000b11e  mov     rax, cs:__security_cookie
0x18000b125  xor     rax, rsp
0x18000b128  mov     [rbp+170h+var_10], rax
0x18000b12f  mov     rdi, rdx
0x18000b132  mov     qword ptr [rdx], 0
0x18000b139  mov     rbx, rcx
0x18000b13c  call    cs:__imp_GetCurrentProcessId
0x18000b142  mov     [rsp+270h+var_248], rbx
0x18000b147  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b14e  mov     r9d, eax
0x18000b151  mov     [rsp+270h+var_250], 130h; int
0x18000b159  mov     edx, 104h; unsigned __int64
0x18000b15e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b163  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b168  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b16e  mov     [rsp+270h+var_240], 0
0x18000b177  xor     r8d, r8d; dwFlags
0x18000b17a  lea     rdx, [rsp+270h+Name]; lpName
0x18000b17f  xor     ecx, ecx; lpMutexAttributes
0x18000b181  call    cs:__imp_CreateMutexExW
0x18000b187  mov     rdx, rax
0x18000b18a  lea     rcx, [rsp+270h+var_240]
0x18000b18f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b194  cmp     [rsp+270h+var_240], 0
0x18000b19a  jnz     short loc_18000B1A5
0x18000b19c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b1a1  mov     ebx, eax
0x18000b1a3  jmp     short loc_18000B218
0x18000b1a5  lea     rdx, [rsp+270h+var_238]
0x18000b1aa  lea     rcx, [rsp+270h+var_240]
0x18000b1af  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000b1b4  lea     rdx, [rsp+270h+var_230]; void **
0x18000b1b9  mov     [rsp+270h+var_230], 0
0x18000b1c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b1c7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000b1cc  mov     ebx, eax
0x18000b1ce  test    eax, eax
0x18000b1d0  jns     short loc_18000B1F9
0x18000b1d2  mov     edx, 12Eh; void *
0x18000b1d7  mov     rcx, [rbp+178h]; this
0x18000b1de  lea     r8, aWil; "wil"
0x18000b1e5  mov     r9d, eax; char *
0x18000b1e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b1ed  lea     rcx, [rsp+270h+var_238]
0x18000b1f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b1f7  jmp     short loc_18000B218
0x18000b1f9  mov     rcx, [rsp+270h+var_230]
0x18000b1fe  test    rcx, rcx
0x18000b201  jz      short loc_18000B248
0x18000b203  mov     [rdi], rcx
0x18000b206  mov     eax, [rcx]
0x18000b208  inc     eax
0x18000b20a  mov     [rcx], eax
0x18000b20c  lea     rcx, [rsp+270h+var_238]
0x18000b211  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b216  xor     ebx, ebx
0x18000b218  lea     rcx, [rsp+270h+var_240]
0x18000b21d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b222  mov     eax, ebx
0x18000b224  mov     rcx, [rbp+170h+var_10]
0x18000b22b  xor     rcx, rsp; StackCookie
0x18000b22e  call    __security_check_cookie
0x18000b233  lea     r11, [rsp+270h+var_s0]
0x18000b23b  mov     rbx, [r11+20h]
0x18000b23f  mov     rdi, [r11+28h]
0x18000b243  mov     rsp, r11
0x18000b246  pop     rbp
0x18000b247  retn
0x18000b248  mov     r8, rdi
0x18000b24b  lea     rdx, [rsp+270h+var_240]
0x18000b250  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b255  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000b25a  mov     ebx, eax
0x18000b25c  test    eax, eax
0x18000b25e  jns     short loc_18000B20C
0x18000b260  mov     edx, 137h
0x18000b265  jmp     loc_18000B1D7
```
