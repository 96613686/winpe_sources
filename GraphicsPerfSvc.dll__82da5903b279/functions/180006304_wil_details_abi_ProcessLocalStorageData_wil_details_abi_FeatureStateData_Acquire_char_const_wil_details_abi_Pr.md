# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006304`
- end: `0x18000646a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000713c`

## callees

- `0x180003ab0`
- `0x180005d04`
- `0x180005d20`
- `0x180006304`
- `0x180006f38`
- `0x180007e54`
- `0x1800091bc`
- `0x180009908`
- `0x180009d88`
- `0x18000a7a4`
- `0x18000aac8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006381`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006381`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000633c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000633c`

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
0x180006304  mov     [rsp-8+arg_10], rbx
0x180006309  mov     [rsp-8+arg_18], rdi
0x18000630e  push    rbp
0x18000630f  lea     rbp, [rsp-170h]
0x180006317  sub     rsp, 270h
0x18000631e  mov     rax, cs:__security_cookie
0x180006325  xor     rax, rsp
0x180006328  mov     [rbp+170h+var_10], rax
0x18000632f  mov     rdi, rdx
0x180006332  mov     qword ptr [rdx], 0
0x180006339  mov     rbx, rcx
0x18000633c  call    cs:__imp_GetCurrentProcessId
0x180006342  mov     [rsp+270h+var_248], rbx
0x180006347  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000634e  mov     r9d, eax
0x180006351  mov     [rsp+270h+var_250], 130h; int
0x180006359  mov     edx, 104h; unsigned __int64
0x18000635e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006363  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006368  mov     r9d, 1F0001h; dwDesiredAccess
0x18000636e  mov     [rsp+270h+var_240], 0
0x180006377  xor     r8d, r8d; dwFlags
0x18000637a  lea     rdx, [rsp+270h+Name]; lpName
0x18000637f  xor     ecx, ecx; lpMutexAttributes
0x180006381  call    cs:__imp_CreateMutexExW
0x180006387  mov     rdx, rax
0x18000638a  lea     rcx, [rsp+270h+var_240]
0x18000638f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006394  cmp     [rsp+270h+var_240], 0
0x18000639a  jnz     short loc_1800063A5
0x18000639c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800063a1  mov     ebx, eax
0x1800063a3  jmp     short loc_180006418
0x1800063a5  lea     rdx, [rsp+270h+var_238]
0x1800063aa  lea     rcx, [rsp+270h+var_240]
0x1800063af  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800063b4  lea     rdx, [rsp+270h+var_230]; void **
0x1800063b9  mov     [rsp+270h+var_230], 0
0x1800063c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800063c7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800063cc  mov     ebx, eax
0x1800063ce  test    eax, eax
0x1800063d0  jns     short loc_1800063F9
0x1800063d2  mov     edx, 12Eh; void *
0x1800063d7  mov     rcx, [rbp+178h]; this
0x1800063de  lea     r8, aWil; "wil"
0x1800063e5  mov     r9d, eax; char *
0x1800063e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063ed  lea     rcx, [rsp+270h+var_238]
0x1800063f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800063f7  jmp     short loc_180006418
0x1800063f9  mov     rcx, [rsp+270h+var_230]
0x1800063fe  test    rcx, rcx
0x180006401  jz      short loc_180006448
0x180006403  mov     [rdi], rcx
0x180006406  mov     eax, [rcx]
0x180006408  inc     eax
0x18000640a  mov     [rcx], eax
0x18000640c  lea     rcx, [rsp+270h+var_238]
0x180006411  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006416  xor     ebx, ebx
0x180006418  lea     rcx, [rsp+270h+var_240]
0x18000641d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006422  mov     eax, ebx
0x180006424  mov     rcx, [rbp+170h+var_10]
0x18000642b  xor     rcx, rsp; StackCookie
0x18000642e  call    __security_check_cookie
0x180006433  lea     r11, [rsp+270h+var_s0]
0x18000643b  mov     rbx, [r11+20h]
0x18000643f  mov     rdi, [r11+28h]
0x180006443  mov     rsp, r11
0x180006446  pop     rbp
0x180006447  retn
0x180006448  mov     r8, rdi
0x18000644b  lea     rdx, [rsp+270h+var_240]
0x180006450  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006455  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000645a  mov     ebx, eax
0x18000645c  test    eax, eax
0x18000645e  jns     short loc_18000640C
0x180006460  mov     edx, 137h
0x180006465  jmp     loc_1800063D7
```
