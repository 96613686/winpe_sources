# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008ecc`
- end: `0x180009032`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800096f4`

## callees

- `0x180003160`
- `0x1800056f0`
- `0x18000570c`
- `0x1800060b8`
- `0x180006e84`
- `0x180007484`
- `0x180007638`
- `0x180007ac0`
- `0x180007bb0`
- `0x180008ecc`
- `0x18000a0e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008f49`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008f49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f04`

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
0x180008ecc  mov     [rsp-8+arg_10], rbx
0x180008ed1  mov     [rsp-8+arg_18], rdi
0x180008ed6  push    rbp
0x180008ed7  lea     rbp, [rsp-170h]
0x180008edf  sub     rsp, 270h
0x180008ee6  mov     rax, cs:__security_cookie
0x180008eed  xor     rax, rsp
0x180008ef0  mov     [rbp+170h+var_10], rax
0x180008ef7  mov     rdi, rdx
0x180008efa  mov     qword ptr [rdx], 0
0x180008f01  mov     rbx, rcx
0x180008f04  call    cs:__imp_GetCurrentProcessId
0x180008f0a  mov     [rsp+270h+var_248], rbx
0x180008f0f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008f16  mov     r9d, eax
0x180008f19  mov     [rsp+270h+var_250], 130h; int
0x180008f21  mov     edx, 104h; unsigned __int64
0x180008f26  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008f2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008f30  mov     r9d, 1F0001h; dwDesiredAccess
0x180008f36  mov     [rsp+270h+var_240], 0
0x180008f3f  xor     r8d, r8d; dwFlags
0x180008f42  lea     rdx, [rsp+270h+Name]; lpName
0x180008f47  xor     ecx, ecx; lpMutexAttributes
0x180008f49  call    cs:__imp_CreateMutexExW
0x180008f4f  mov     rdx, rax
0x180008f52  lea     rcx, [rsp+270h+var_240]
0x180008f57  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008f5c  cmp     [rsp+270h+var_240], 0
0x180008f62  jnz     short loc_180008F6D
0x180008f64  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008f69  mov     ebx, eax
0x180008f6b  jmp     short loc_180008FE0
0x180008f6d  lea     rdx, [rsp+270h+var_238]
0x180008f72  lea     rcx, [rsp+270h+var_240]
0x180008f77  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008f7c  lea     rdx, [rsp+270h+var_230]; void **
0x180008f81  mov     [rsp+270h+var_230], 0
0x180008f8a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008f8f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008f94  mov     ebx, eax
0x180008f96  test    eax, eax
0x180008f98  jns     short loc_180008FC1
0x180008f9a  mov     edx, 12Eh; void *
0x180008f9f  mov     rcx, [rbp+178h]; this
0x180008fa6  lea     r8, aWil; "wil"
0x180008fad  mov     r9d, eax; char *
0x180008fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fb5  lea     rcx, [rsp+270h+var_238]
0x180008fba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008fbf  jmp     short loc_180008FE0
0x180008fc1  mov     rcx, [rsp+270h+var_230]
0x180008fc6  test    rcx, rcx
0x180008fc9  jz      short loc_180009010
0x180008fcb  mov     [rdi], rcx
0x180008fce  mov     eax, [rcx]
0x180008fd0  inc     eax
0x180008fd2  mov     [rcx], eax
0x180008fd4  lea     rcx, [rsp+270h+var_238]
0x180008fd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008fde  xor     ebx, ebx
0x180008fe0  lea     rcx, [rsp+270h+var_240]
0x180008fe5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008fea  mov     eax, ebx
0x180008fec  mov     rcx, [rbp+170h+var_10]
0x180008ff3  xor     rcx, rsp; StackCookie
0x180008ff6  call    __security_check_cookie
0x180008ffb  lea     r11, [rsp+270h+var_s0]
0x180009003  mov     rbx, [r11+20h]
0x180009007  mov     rdi, [r11+28h]
0x18000900b  mov     rsp, r11
0x18000900e  pop     rbp
0x18000900f  retn
0x180009010  mov     r8, rdi
0x180009013  lea     rdx, [rsp+270h+var_240]
0x180009018  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000901d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009022  mov     ebx, eax
0x180009024  test    eax, eax
0x180009026  jns     short loc_180008FD4
0x180009028  mov     edx, 137h
0x18000902d  jmp     loc_180008F9F
```
