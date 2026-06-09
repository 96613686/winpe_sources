# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006338`
- end: `0x180006497`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800098fc`

## callees

- `0x180005624`
- `0x180005640`
- `0x180006338`
- `0x1800096fc`
- `0x18000c114`
- `0x18000e7dc`
- `0x180012864`
- `0x1800132d4`
- `0x180013eb0`
- `0x180014620`
- `0x18006c690`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800063b5`
- `KERNEL32!CreateMutexExW` at `0x1800063b5`
- `KERNEL32!GetCurrentProcessId` at `0x180006370`
- `KERNEL32!GetCurrentProcessId` at `0x180006370`

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
0x180006338  mov     [rsp-8+arg_10], rbx
0x18000633d  mov     [rsp-8+arg_18], rdi
0x180006342  push    rbp
0x180006343  lea     rbp, [rsp-170h]
0x18000634b  sub     rsp, 270h
0x180006352  mov     rax, cs:__security_cookie
0x180006359  xor     rax, rsp
0x18000635c  mov     [rbp+170h+var_10], rax
0x180006363  mov     rdi, rdx
0x180006366  mov     qword ptr [rdx], 0
0x18000636d  mov     rbx, rcx
0x180006370  call    cs:__imp_GetCurrentProcessId
0x180006376  mov     [rsp+270h+var_248], rbx
0x18000637b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006382  mov     r9d, eax
0x180006385  mov     [rsp+270h+var_250], 130h; int
0x18000638d  mov     edx, 104h; unsigned __int64
0x180006392  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006397  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000639c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800063a2  mov     [rsp+270h+var_240], 0
0x1800063ab  xor     r8d, r8d; dwFlags
0x1800063ae  lea     rdx, [rsp+270h+Name]; lpName
0x1800063b3  xor     ecx, ecx; lpMutexAttributes
0x1800063b5  call    cs:__imp_CreateMutexExW
0x1800063bb  mov     rdx, rax
0x1800063be  lea     rcx, [rsp+270h+var_240]
0x1800063c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800063c8  cmp     [rsp+270h+var_240], 0
0x1800063ce  jnz     short loc_1800063D9
0x1800063d0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800063d5  mov     ebx, eax
0x1800063d7  jmp     short loc_180006445
0x1800063d9  lea     rdx, [rsp+270h+var_238]
0x1800063de  lea     rcx, [rsp+270h+var_240]
0x1800063e3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800063e8  lea     rdx, [rsp+270h+var_230]; void **
0x1800063ed  mov     [rsp+270h+var_230], 0
0x1800063f6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800063fb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180006400  mov     ebx, eax
0x180006402  test    eax, eax
0x180006404  jns     short loc_180006426
0x180006406  mov     edx, 12Eh; void *
0x18000640b  mov     rcx, [rbp+178h]; this
0x180006412  mov     r9d, eax; char *
0x180006415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000641a  lea     rcx, [rsp+270h+var_238]
0x18000641f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006424  jmp     short loc_180006445
0x180006426  mov     rcx, [rsp+270h+var_230]
0x18000642b  test    rcx, rcx
0x18000642e  jz      short loc_180006475
0x180006430  mov     [rdi], rcx
0x180006433  mov     eax, [rcx]
0x180006435  inc     eax
0x180006437  mov     [rcx], eax
0x180006439  lea     rcx, [rsp+270h+var_238]
0x18000643e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006443  xor     ebx, ebx
0x180006445  lea     rcx, [rsp+270h+var_240]
0x18000644a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000644f  mov     eax, ebx
0x180006451  mov     rcx, [rbp+170h+var_10]
0x180006458  xor     rcx, rsp; StackCookie
0x18000645b  call    __security_check_cookie
0x180006460  lea     r11, [rsp+270h+var_s0]
0x180006468  mov     rbx, [r11+20h]
0x18000646c  mov     rdi, [r11+28h]
0x180006470  mov     rsp, r11
0x180006473  pop     rbp
0x180006474  retn
0x180006475  mov     r8, rdi
0x180006478  lea     rdx, [rsp+270h+var_240]
0x18000647d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006482  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006487  mov     ebx, eax
0x180006489  test    eax, eax
0x18000648b  jns     short loc_180006439
0x18000648d  mov     edx, 137h
0x180006492  jmp     loc_18000640B
```
