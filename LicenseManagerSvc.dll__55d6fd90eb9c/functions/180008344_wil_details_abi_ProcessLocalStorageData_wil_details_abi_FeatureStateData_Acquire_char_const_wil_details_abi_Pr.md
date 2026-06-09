# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008344`
- end: `0x1800084aa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009070`

## callees

- `0x180002bc8`
- `0x180002be4`
- `0x180002c80`
- `0x180002cd4`
- `0x1800033d0`
- `0x1800051c0`
- `0x180006c90`
- `0x180007338`
- `0x1800075a4`
- `0x180008344`
- `0x1800093e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800083c1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800083c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000837c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000837c`

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
0x180008344  mov     [rsp-8+arg_10], rbx
0x180008349  mov     [rsp-8+arg_18], rdi
0x18000834e  push    rbp
0x18000834f  lea     rbp, [rsp-170h]
0x180008357  sub     rsp, 270h
0x18000835e  mov     rax, cs:__security_cookie
0x180008365  xor     rax, rsp
0x180008368  mov     [rbp+170h+var_10], rax
0x18000836f  mov     rdi, rdx
0x180008372  mov     qword ptr [rdx], 0
0x180008379  mov     rbx, rcx
0x18000837c  call    cs:__imp_GetCurrentProcessId
0x180008382  mov     [rsp+270h+var_248], rbx
0x180008387  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000838e  mov     r9d, eax
0x180008391  mov     [rsp+270h+var_250], 130h; int
0x180008399  mov     edx, 104h; unsigned __int64
0x18000839e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800083a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800083a8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800083ae  mov     [rsp+270h+var_240], 0
0x1800083b7  xor     r8d, r8d; dwFlags
0x1800083ba  lea     rdx, [rsp+270h+Name]; lpName
0x1800083bf  xor     ecx, ecx; lpMutexAttributes
0x1800083c1  call    cs:__imp_CreateMutexExW
0x1800083c7  mov     rdx, rax
0x1800083ca  lea     rcx, [rsp+270h+var_240]
0x1800083cf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800083d4  cmp     [rsp+270h+var_240], 0
0x1800083da  jnz     short loc_1800083E5
0x1800083dc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800083e1  mov     ebx, eax
0x1800083e3  jmp     short loc_180008458
0x1800083e5  lea     rdx, [rsp+270h+var_238]
0x1800083ea  lea     rcx, [rsp+270h+var_240]
0x1800083ef  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800083f4  lea     rdx, [rsp+270h+var_230]; void **
0x1800083f9  mov     [rsp+270h+var_230], 0
0x180008402  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008407  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000840c  mov     ebx, eax
0x18000840e  test    eax, eax
0x180008410  jns     short loc_180008439
0x180008412  mov     edx, 12Eh; void *
0x180008417  mov     rcx, [rbp+178h]; this
0x18000841e  lea     r8, aWil; "wil"
0x180008425  mov     r9d, eax; char *
0x180008428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000842d  lea     rcx, [rsp+270h+var_238]
0x180008432  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008437  jmp     short loc_180008458
0x180008439  mov     rcx, [rsp+270h+var_230]
0x18000843e  test    rcx, rcx
0x180008441  jz      short loc_180008488
0x180008443  mov     [rdi], rcx
0x180008446  mov     eax, [rcx]
0x180008448  inc     eax
0x18000844a  mov     [rcx], eax
0x18000844c  lea     rcx, [rsp+270h+var_238]
0x180008451  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008456  xor     ebx, ebx
0x180008458  lea     rcx, [rsp+270h+var_240]
0x18000845d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008462  mov     eax, ebx
0x180008464  mov     rcx, [rbp+170h+var_10]
0x18000846b  xor     rcx, rsp; StackCookie
0x18000846e  call    __security_check_cookie
0x180008473  lea     r11, [rsp+270h+var_s0]
0x18000847b  mov     rbx, [r11+20h]
0x18000847f  mov     rdi, [r11+28h]
0x180008483  mov     rsp, r11
0x180008486  pop     rbp
0x180008487  retn
0x180008488  mov     r8, rdi
0x18000848b  lea     rdx, [rsp+270h+var_240]
0x180008490  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008495  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000849a  mov     ebx, eax
0x18000849c  test    eax, eax
0x18000849e  jns     short loc_18000844C
0x1800084a0  mov     edx, 137h
0x1800084a5  jmp     loc_180008417
```
