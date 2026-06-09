# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140006ee4`
- end: `0x14000704a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140007298`

## callees

- `0x1400030a0`
- `0x140006890`
- `0x1400068ac`
- `0x140006ee4`
- `0x140007bb0`
- `0x140008a1c`
- `0x140009f14`
- `0x14000a684`
- `0x14000abcc`
- `0x14000b644`
- `0x14000bc5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006f61`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006f61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006f1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006f1c`

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
0x140006ee4  mov     [rsp-8+arg_10], rbx
0x140006ee9  mov     [rsp-8+arg_18], rdi
0x140006eee  push    rbp
0x140006eef  lea     rbp, [rsp-170h]
0x140006ef7  sub     rsp, 270h
0x140006efe  mov     rax, cs:__security_cookie
0x140006f05  xor     rax, rsp
0x140006f08  mov     [rbp+170h+var_10], rax
0x140006f0f  mov     rdi, rdx
0x140006f12  mov     qword ptr [rdx], 0
0x140006f19  mov     rbx, rcx
0x140006f1c  call    cs:__imp_GetCurrentProcessId
0x140006f22  mov     [rsp+270h+var_248], rbx
0x140006f27  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140006f2e  mov     r9d, eax
0x140006f31  mov     [rsp+270h+var_250], 130h; int
0x140006f39  mov     edx, 104h; unsigned __int64
0x140006f3e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140006f43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006f48  mov     r9d, 1F0001h; dwDesiredAccess
0x140006f4e  mov     [rsp+270h+var_240], 0
0x140006f57  xor     r8d, r8d; dwFlags
0x140006f5a  lea     rdx, [rsp+270h+Name]; lpName
0x140006f5f  xor     ecx, ecx; lpMutexAttributes
0x140006f61  call    cs:__imp_CreateMutexExW
0x140006f67  mov     rdx, rax
0x140006f6a  lea     rcx, [rsp+270h+var_240]
0x140006f6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140006f74  cmp     [rsp+270h+var_240], 0
0x140006f7a  jnz     short loc_140006F85
0x140006f7c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006f81  mov     ebx, eax
0x140006f83  jmp     short loc_140006FF8
0x140006f85  lea     rdx, [rsp+270h+var_238]
0x140006f8a  lea     rcx, [rsp+270h+var_240]
0x140006f8f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140006f94  lea     rdx, [rsp+270h+var_230]; void **
0x140006f99  mov     [rsp+270h+var_230], 0
0x140006fa2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140006fa7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x140006fac  mov     ebx, eax
0x140006fae  test    eax, eax
0x140006fb0  jns     short loc_140006FD9
0x140006fb2  mov     edx, 12Eh; void *
0x140006fb7  mov     rcx, [rbp+178h]; this
0x140006fbe  lea     r8, aWil; "wil"
0x140006fc5  mov     r9d, eax; char *
0x140006fc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006fcd  lea     rcx, [rsp+270h+var_238]
0x140006fd2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006fd7  jmp     short loc_140006FF8
0x140006fd9  mov     rcx, [rsp+270h+var_230]
0x140006fde  test    rcx, rcx
0x140006fe1  jz      short loc_140007028
0x140006fe3  mov     [rdi], rcx
0x140006fe6  mov     eax, [rcx]
0x140006fe8  inc     eax
0x140006fea  mov     [rcx], eax
0x140006fec  lea     rcx, [rsp+270h+var_238]
0x140006ff1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006ff6  xor     ebx, ebx
0x140006ff8  lea     rcx, [rsp+270h+var_240]
0x140006ffd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007002  mov     eax, ebx
0x140007004  mov     rcx, [rbp+170h+var_10]
0x14000700b  xor     rcx, rsp; StackCookie
0x14000700e  call    __security_check_cookie
0x140007013  lea     r11, [rsp+270h+var_s0]
0x14000701b  mov     rbx, [r11+20h]
0x14000701f  mov     rdi, [r11+28h]
0x140007023  mov     rsp, r11
0x140007026  pop     rbp
0x140007027  retn
0x140007028  mov     r8, rdi
0x14000702b  lea     rdx, [rsp+270h+var_240]
0x140007030  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140007035  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000703a  mov     ebx, eax
0x14000703c  test    eax, eax
0x14000703e  jns     short loc_140006FEC
0x140007040  mov     edx, 137h
0x140007045  jmp     loc_140006FB7
```
