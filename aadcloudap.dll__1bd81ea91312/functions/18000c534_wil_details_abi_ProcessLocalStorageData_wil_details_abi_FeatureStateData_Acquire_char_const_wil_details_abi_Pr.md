# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000c534`
- end: `0x18000c696`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180015da8`

## callees

- `0x180003c20`
- `0x18000a200`
- `0x18000a21c`
- `0x18000c534`
- `0x180015ba8`
- `0x180016bc8`
- `0x18001901c`
- `0x180019868`
- `0x180019e04`
- `0x18001a91c`
- `0x18001bb28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c5b1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c5b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c56c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c56c`

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
0x18000c534  mov     [rsp-8+arg_10], rbx
0x18000c539  mov     [rsp-8+arg_18], rdi
0x18000c53e  push    rbp
0x18000c53f  lea     rbp, [rsp-170h]
0x18000c547  sub     rsp, 270h
0x18000c54e  mov     rax, cs:__security_cookie
0x18000c555  xor     rax, rsp
0x18000c558  mov     [rbp+170h+var_10], rax
0x18000c55f  mov     rdi, rdx
0x18000c562  mov     rbx, rcx
0x18000c565  mov     qword ptr [rdx], 0
0x18000c56c  call    cs:__imp_GetCurrentProcessId
0x18000c572  mov     r9d, eax
0x18000c575  mov     [rsp+270h+var_248], rbx
0x18000c57a  mov     [rsp+270h+var_250], 130h; int
0x18000c582  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c589  mov     edx, 104h; unsigned __int64
0x18000c58e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c593  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c598  mov     [rsp+270h+var_240], 0
0x18000c5a1  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c5a7  xor     r8d, r8d; dwFlags
0x18000c5aa  lea     rdx, [rsp+270h+Name]; lpName
0x18000c5af  xor     ecx, ecx; lpMutexAttributes
0x18000c5b1  call    cs:__imp_CreateMutexExW
0x18000c5b7  mov     rdx, rax
0x18000c5ba  lea     rcx, [rsp+270h+var_240]
0x18000c5bf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c5c4  cmp     [rsp+270h+var_240], 0
0x18000c5ca  jnz     short loc_18000C5D5
0x18000c5cc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c5d1  mov     ebx, eax
0x18000c5d3  jmp     short loc_18000C643
0x18000c5d5  lea     rdx, [rsp+270h+var_238]
0x18000c5da  lea     rcx, [rsp+270h+var_240]
0x18000c5df  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000c5e4  nop
0x18000c5e5  mov     [rsp+270h+var_230], 0
0x18000c5ee  lea     rdx, [rsp+270h+var_230]; void **
0x18000c5f3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c5f8  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000c5fd  mov     ebx, eax
0x18000c5ff  test    eax, eax
0x18000c601  jns     short loc_18000C624
0x18000c603  mov     edx, 12Eh; void *
0x18000c608  mov     r9d, eax; char *
0x18000c60b  mov     rcx, [rbp+178h]; this
0x18000c612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c617  nop
0x18000c618  lea     rcx, [rsp+270h+var_238]
0x18000c61d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c622  jmp     short loc_18000C643
0x18000c624  mov     rcx, [rsp+270h+var_230]
0x18000c629  test    rcx, rcx
0x18000c62c  jz      short loc_18000C673
0x18000c62e  mov     [rdi], rcx
0x18000c631  mov     eax, [rcx]
0x18000c633  inc     eax
0x18000c635  mov     [rcx], eax
0x18000c637  lea     rcx, [rsp+270h+var_238]
0x18000c63c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c641  xor     ebx, ebx
0x18000c643  lea     rcx, [rsp+270h+var_240]
0x18000c648  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c64d  mov     eax, ebx
0x18000c64f  mov     rcx, [rbp+170h+var_10]
0x18000c656  xor     rcx, rsp; StackCookie
0x18000c659  call    __security_check_cookie
0x18000c65e  lea     r11, [rsp+270h+var_s0]
0x18000c666  mov     rbx, [r11+20h]
0x18000c66a  mov     rdi, [r11+28h]
0x18000c66e  mov     rsp, r11
0x18000c671  pop     rbp
0x18000c672  retn
0x18000c673  mov     r8, rdi
0x18000c676  lea     rdx, [rsp+270h+var_240]
0x18000c67b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c680  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000c685  mov     ebx, eax
0x18000c687  test    eax, eax
0x18000c689  jns     short loc_18000C637
0x18000c68b  mov     edx, 137h
0x18000c690  jmp     loc_18000C608
```
