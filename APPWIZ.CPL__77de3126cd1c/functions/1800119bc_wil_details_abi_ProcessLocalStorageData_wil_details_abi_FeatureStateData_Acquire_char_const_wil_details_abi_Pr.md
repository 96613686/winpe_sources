# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800119bc`
- end: `0x180011b22`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180013f04`

## callees

- `0x180005e58`
- `0x180005e74`
- `0x180006758`
- `0x180007560`
- `0x180007960`
- `0x180007a70`
- `0x180007f00`
- `0x180007fac`
- `0x1800119bc`
- `0x1800150e8`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011a39`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011a39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800119f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800119f4`

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
0x1800119bc  mov     [rsp-8+arg_10], rbx
0x1800119c1  mov     [rsp-8+arg_18], rdi
0x1800119c6  push    rbp
0x1800119c7  lea     rbp, [rsp-170h]
0x1800119cf  sub     rsp, 270h
0x1800119d6  mov     rax, cs:__security_cookie
0x1800119dd  xor     rax, rsp
0x1800119e0  mov     [rbp+170h+var_10], rax
0x1800119e7  mov     rdi, rdx
0x1800119ea  mov     qword ptr [rdx], 0
0x1800119f1  mov     rbx, rcx
0x1800119f4  call    cs:__imp_GetCurrentProcessId
0x1800119fa  mov     [rsp+270h+var_248], rbx
0x1800119ff  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180011a06  mov     r9d, eax
0x180011a09  mov     [rsp+270h+var_250], 130h; int
0x180011a11  mov     edx, 104h; unsigned __int64
0x180011a16  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011a1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011a20  mov     r9d, 1F0001h; dwDesiredAccess
0x180011a26  mov     [rsp+270h+var_240], 0
0x180011a2f  xor     r8d, r8d; dwFlags
0x180011a32  lea     rdx, [rsp+270h+Name]; lpName
0x180011a37  xor     ecx, ecx; lpMutexAttributes
0x180011a39  call    cs:__imp_CreateMutexExW
0x180011a3f  mov     rdx, rax
0x180011a42  lea     rcx, [rsp+270h+var_240]
0x180011a47  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180011a4c  cmp     [rsp+270h+var_240], 0
0x180011a52  jnz     short loc_180011A5D
0x180011a54  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011a59  mov     ebx, eax
0x180011a5b  jmp     short loc_180011AD0
0x180011a5d  lea     rdx, [rsp+270h+var_238]
0x180011a62  lea     rcx, [rsp+270h+var_240]
0x180011a67  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180011a6c  lea     rdx, [rsp+270h+var_230]; void **
0x180011a71  mov     [rsp+270h+var_230], 0
0x180011a7a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011a7f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180011a84  mov     ebx, eax
0x180011a86  test    eax, eax
0x180011a88  jns     short loc_180011AB1
0x180011a8a  mov     edx, 12Eh; void *
0x180011a8f  mov     rcx, [rbp+178h]; this
0x180011a96  lea     r8, aWil; "wil"
0x180011a9d  mov     r9d, eax; char *
0x180011aa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011aa5  lea     rcx, [rsp+270h+var_238]
0x180011aaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011aaf  jmp     short loc_180011AD0
0x180011ab1  mov     rcx, [rsp+270h+var_230]
0x180011ab6  test    rcx, rcx
0x180011ab9  jz      short loc_180011B00
0x180011abb  mov     [rdi], rcx
0x180011abe  mov     eax, [rcx]
0x180011ac0  inc     eax
0x180011ac2  mov     [rcx], eax
0x180011ac4  lea     rcx, [rsp+270h+var_238]
0x180011ac9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011ace  xor     ebx, ebx
0x180011ad0  lea     rcx, [rsp+270h+var_240]
0x180011ad5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011ada  mov     eax, ebx
0x180011adc  mov     rcx, [rbp+170h+var_10]
0x180011ae3  xor     rcx, rsp; StackCookie
0x180011ae6  call    __security_check_cookie
0x180011aeb  lea     r11, [rsp+270h+var_s0]
0x180011af3  mov     rbx, [r11+20h]
0x180011af7  mov     rdi, [r11+28h]
0x180011afb  mov     rsp, r11
0x180011afe  pop     rbp
0x180011aff  retn
0x180011b00  mov     r8, rdi
0x180011b03  lea     rdx, [rsp+270h+var_240]
0x180011b08  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011b0d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180011b12  mov     ebx, eax
0x180011b14  test    eax, eax
0x180011b16  jns     short loc_180011AC4
0x180011b18  mov     edx, 137h
0x180011b1d  jmp     loc_180011A8F
```
