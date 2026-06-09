# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800062a4`
- end: `0x18000640a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800070c4`

## callees

- `0x180003450`
- `0x180005c74`
- `0x180005c90`
- `0x1800062a4`
- `0x180006f08`
- `0x180007dd4`
- `0x18000912c`
- `0x1800098c8`
- `0x180009d48`
- `0x18000a624`
- `0x18000a958`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006321`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006321`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800062dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800062dc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x1800062a4  mov     [rsp-8+arg_10], rbx
0x1800062a9  mov     [rsp-8+arg_18], rdi
0x1800062ae  push    rbp
0x1800062af  lea     rbp, [rsp-170h]
0x1800062b7  sub     rsp, 270h
0x1800062be  mov     rax, cs:__security_cookie
0x1800062c5  xor     rax, rsp
0x1800062c8  mov     [rbp+170h+var_10], rax
0x1800062cf  mov     rdi, rdx
0x1800062d2  mov     qword ptr [rdx], 0
0x1800062d9  mov     rbx, rcx
0x1800062dc  call    cs:__imp_GetCurrentProcessId
0x1800062e2  mov     [rsp+270h+var_248], rbx
0x1800062e7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800062ee  mov     r9d, eax
0x1800062f1  mov     [rsp+270h+var_250], 130h; int
0x1800062f9  mov     edx, 104h; unsigned __int64
0x1800062fe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006303  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006308  mov     r9d, 1F0001h; dwDesiredAccess
0x18000630e  mov     [rsp+270h+var_240], 0
0x180006317  xor     r8d, r8d; dwFlags
0x18000631a  lea     rdx, [rsp+270h+Name]; lpName
0x18000631f  xor     ecx, ecx; lpMutexAttributes
0x180006321  call    cs:__imp_CreateMutexExW
0x180006327  mov     rdx, rax
0x18000632a  lea     rcx, [rsp+270h+var_240]
0x18000632f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006334  cmp     [rsp+270h+var_240], 0
0x18000633a  jnz     short loc_180006345
0x18000633c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006341  mov     ebx, eax
0x180006343  jmp     short loc_1800063B8
0x180006345  lea     rdx, [rsp+270h+var_238]
0x18000634a  lea     rcx, [rsp+270h+var_240]
0x18000634f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006354  lea     rdx, [rsp+270h+var_230]; void **
0x180006359  mov     [rsp+270h+var_230], 0
0x180006362  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006367  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000636c  mov     ebx, eax
0x18000636e  test    eax, eax
0x180006370  jns     short loc_180006399
0x180006372  mov     edx, 12Eh; void *
0x180006377  mov     rcx, [rbp+178h]; this
0x18000637e  lea     r8, aWil; "wil"
0x180006385  mov     r9d, eax; char *
0x180006388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000638d  lea     rcx, [rsp+270h+var_238]
0x180006392  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006397  jmp     short loc_1800063B8
0x180006399  mov     rcx, [rsp+270h+var_230]
0x18000639e  test    rcx, rcx
0x1800063a1  jz      short loc_1800063E8
0x1800063a3  mov     [rdi], rcx
0x1800063a6  mov     eax, [rcx]
0x1800063a8  inc     eax
0x1800063aa  mov     [rcx], eax
0x1800063ac  lea     rcx, [rsp+270h+var_238]
0x1800063b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800063b6  xor     ebx, ebx
0x1800063b8  lea     rcx, [rsp+270h+var_240]
0x1800063bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800063c2  mov     eax, ebx
0x1800063c4  mov     rcx, [rbp+170h+var_10]
0x1800063cb  xor     rcx, rsp; StackCookie
0x1800063ce  call    __security_check_cookie
0x1800063d3  lea     r11, [rsp+270h+var_s0]
0x1800063db  mov     rbx, [r11+20h]
0x1800063df  mov     rdi, [r11+28h]
0x1800063e3  mov     rsp, r11
0x1800063e6  pop     rbp
0x1800063e7  retn
0x1800063e8  mov     r8, rdi
0x1800063eb  lea     rdx, [rsp+270h+var_240]
0x1800063f0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800063f5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800063fa  mov     ebx, eax
0x1800063fc  test    eax, eax
0x1800063fe  jns     short loc_1800063AC
0x180006400  mov     edx, 137h
0x180006405  jmp     loc_180006377
```
