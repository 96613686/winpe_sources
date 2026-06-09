# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140025d08`
- end: `0x140025e7b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140026138`

## callees

- `0x14000a420`
- `0x140018ef8`
- `0x14001bd40`
- `0x1400258a4`
- `0x1400258c4`
- `0x140025d08`
- `0x1400272b0`
- `0x1400289d8`
- `0x140028ec8`
- `0x1400296d4`
- `0x14002986c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140025d8b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140025d8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140025d40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140025d40`

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
0x140025d08  mov     [rsp-8+arg_10], rbx
0x140025d0d  mov     [rsp-8+arg_18], rdi
0x140025d12  push    rbp
0x140025d13  lea     rbp, [rsp-170h]
0x140025d1b  sub     rsp, 270h
0x140025d22  mov     rax, cs:__security_cookie
0x140025d29  xor     rax, rsp
0x140025d2c  mov     [rbp+170h+var_10], rax
0x140025d33  mov     rdi, rdx
0x140025d36  mov     qword ptr [rdx], 0
0x140025d3d  mov     rbx, rcx
0x140025d40  call    cs:__imp_GetCurrentProcessId
0x140025d47  nop     dword ptr [rax+rax+00h]
0x140025d4c  mov     [rsp+270h+var_248], rbx
0x140025d51  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140025d58  mov     r9d, eax
0x140025d5b  mov     [rsp+270h+var_250], 130h; int
0x140025d63  mov     edx, 104h; unsigned __int64
0x140025d68  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140025d6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140025d72  mov     r9d, 1F0001h; dwDesiredAccess
0x140025d78  mov     [rsp+270h+var_240], 0
0x140025d81  xor     r8d, r8d; dwFlags
0x140025d84  lea     rdx, [rsp+270h+Name]; lpName
0x140025d89  xor     ecx, ecx; lpMutexAttributes
0x140025d8b  call    cs:__imp_CreateMutexExW
0x140025d92  nop     dword ptr [rax+rax+00h]
0x140025d97  mov     rdx, rax
0x140025d9a  lea     rcx, [rsp+270h+var_240]
0x140025d9f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140025da4  cmp     [rsp+270h+var_240], 0
0x140025daa  jnz     short loc_140025DB5
0x140025dac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140025db1  mov     ebx, eax
0x140025db3  jmp     short loc_140025E28
0x140025db5  lea     rdx, [rsp+270h+var_238]
0x140025dba  lea     rcx, [rsp+270h+var_240]
0x140025dbf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140025dc4  lea     rdx, [rsp+270h+var_230]; void **
0x140025dc9  mov     [rsp+270h+var_230], 0
0x140025dd2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140025dd7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140025ddc  mov     ebx, eax
0x140025dde  test    eax, eax
0x140025de0  jns     short loc_140025E09
0x140025de2  mov     edx, 12Eh; void *
0x140025de7  mov     rcx, [rbp+178h]; this
0x140025dee  lea     r8, aWil; "wil"
0x140025df5  mov     r9d, eax; char *
0x140025df8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025dfd  lea     rcx, [rsp+270h+var_238]
0x140025e02  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140025e07  jmp     short loc_140025E28
0x140025e09  mov     rcx, [rsp+270h+var_230]
0x140025e0e  test    rcx, rcx
0x140025e11  jz      short loc_140025E59
0x140025e13  mov     [rdi], rcx
0x140025e16  mov     eax, [rcx]
0x140025e18  inc     eax
0x140025e1a  mov     [rcx], eax
0x140025e1c  lea     rcx, [rsp+270h+var_238]
0x140025e21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140025e26  xor     ebx, ebx
0x140025e28  lea     rcx, [rsp+270h+var_240]
0x140025e2d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140025e32  mov     eax, ebx
0x140025e34  mov     rcx, [rbp+170h+var_10]
0x140025e3b  xor     rcx, rsp; StackCookie
0x140025e3e  call    __security_check_cookie
0x140025e43  lea     r11, [rsp+270h+var_s0]
0x140025e4b  mov     rbx, [r11+20h]
0x140025e4f  mov     rdi, [r11+28h]
0x140025e53  mov     rsp, r11
0x140025e56  pop     rbp
0x140025e57  retn
0x140025e59  mov     r8, rdi
0x140025e5c  lea     rdx, [rsp+270h+var_240]
0x140025e61  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140025e66  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140025e6b  mov     ebx, eax
0x140025e6d  test    eax, eax
0x140025e6f  jns     short loc_140025E1C
0x140025e71  mov     edx, 137h
0x140025e76  jmp     loc_140025DE7
```
