# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800c4700`
- end: `0x1800c485f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c545c`

## callees

- `0x1800180e4`
- `0x1800c4290`
- `0x1800c42ac`
- `0x1800c4700`
- `0x1800c5228`
- `0x1800c608c`
- `0x1800c706c`
- `0x1800c7a4c`
- `0x1800c8194`
- `0x1800c8320`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800c477d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800c477d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c4738`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c4738`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800c4700  mov     [rsp-8+arg_10], rbx
0x1800c4705  mov     [rsp-8+arg_18], rdi
0x1800c470a  push    rbp
0x1800c470b  lea     rbp, [rsp-170h]
0x1800c4713  sub     rsp, 270h
0x1800c471a  mov     rax, cs:__security_cookie
0x1800c4721  xor     rax, rsp
0x1800c4724  mov     [rbp+170h+var_10], rax
0x1800c472b  mov     rdi, rdx
0x1800c472e  mov     qword ptr [rdx], 0
0x1800c4735  mov     rbx, rcx
0x1800c4738  call    cs:__imp_GetCurrentProcessId
0x1800c473e  mov     [rsp+270h+var_248], rbx
0x1800c4743  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800c474a  mov     r9d, eax
0x1800c474d  mov     [rsp+270h+var_250], 130h; int
0x1800c4755  mov     edx, 104h; unsigned __int64
0x1800c475a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800c475f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c4764  mov     r9d, 1F0001h; dwDesiredAccess
0x1800c476a  mov     [rsp+270h+var_240], 0
0x1800c4773  xor     r8d, r8d; dwFlags
0x1800c4776  lea     rdx, [rsp+270h+Name]; lpName
0x1800c477b  xor     ecx, ecx; lpMutexAttributes
0x1800c477d  call    cs:__imp_CreateMutexExW
0x1800c4783  mov     rdx, rax
0x1800c4786  lea     rcx, [rsp+270h+var_240]
0x1800c478b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800c4790  cmp     [rsp+270h+var_240], 0
0x1800c4796  jnz     short loc_1800C47A1
0x1800c4798  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800c479d  mov     ebx, eax
0x1800c479f  jmp     short loc_1800C480D
0x1800c47a1  lea     rdx, [rsp+270h+var_238]
0x1800c47a6  lea     rcx, [rsp+270h+var_240]
0x1800c47ab  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800c47b0  lea     rdx, [rsp+270h+var_230]; void **
0x1800c47b5  mov     [rsp+270h+var_230], 0
0x1800c47be  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800c47c3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800c47c8  mov     ebx, eax
0x1800c47ca  test    eax, eax
0x1800c47cc  jns     short loc_1800C47EE
0x1800c47ce  mov     edx, 12Eh; void *
0x1800c47d3  mov     rcx, [rbp+178h]; this
0x1800c47da  mov     r9d, eax; char *
0x1800c47dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c47e2  lea     rcx, [rsp+270h+var_238]
0x1800c47e7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c47ec  jmp     short loc_1800C480D
0x1800c47ee  mov     rcx, [rsp+270h+var_230]
0x1800c47f3  test    rcx, rcx
0x1800c47f6  jz      short loc_1800C483D
0x1800c47f8  mov     [rdi], rcx
0x1800c47fb  mov     eax, [rcx]
0x1800c47fd  inc     eax
0x1800c47ff  mov     [rcx], eax
0x1800c4801  lea     rcx, [rsp+270h+var_238]
0x1800c4806  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c480b  xor     ebx, ebx
0x1800c480d  lea     rcx, [rsp+270h+var_240]
0x1800c4812  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c4817  mov     eax, ebx
0x1800c4819  mov     rcx, [rbp+170h+var_10]
0x1800c4820  xor     rcx, rsp; StackCookie
0x1800c4823  call    __security_check_cookie
0x1800c4828  lea     r11, [rsp+270h+var_s0]
0x1800c4830  mov     rbx, [r11+20h]
0x1800c4834  mov     rdi, [r11+28h]
0x1800c4838  mov     rsp, r11
0x1800c483b  pop     rbp
0x1800c483c  retn
0x1800c483d  mov     r8, rdi
0x1800c4840  lea     rdx, [rsp+270h+var_240]
0x1800c4845  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800c484a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800c484f  mov     ebx, eax
0x1800c4851  test    eax, eax
0x1800c4853  jns     short loc_1800C4801
0x1800c4855  mov     edx, 137h
0x1800c485a  jmp     loc_1800C47D3
```
