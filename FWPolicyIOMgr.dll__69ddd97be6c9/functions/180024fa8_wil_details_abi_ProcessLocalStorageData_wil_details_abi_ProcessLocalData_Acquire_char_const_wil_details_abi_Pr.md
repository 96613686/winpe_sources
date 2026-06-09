# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180024fa8`
- end: `0x180025110`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `360`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180027b54`

## callees

- `0x180019e0c`
- `0x18001ef6c`
- `0x18001f650`
- `0x180024df8`
- `0x180024e14`
- `0x180024fa8`
- `0x180028340`
- `0x180028ae4`
- `0x1800293b8`
- `0x180029c64`
- `0x180029d54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024fe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024fe0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180025025`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180025025`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
    v13 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x180024fa8  mov     [rsp-8+arg_10], rbx
0x180024fad  mov     [rsp-8+arg_18], rdi
0x180024fb2  push    rbp
0x180024fb3  lea     rbp, [rsp-170h]
0x180024fbb  sub     rsp, 270h
0x180024fc2  mov     rax, cs:__security_cookie
0x180024fc9  xor     rax, rsp
0x180024fcc  mov     [rbp+170h+var_10], rax
0x180024fd3  mov     rdi, rdx
0x180024fd6  mov     qword ptr [rdx], 0
0x180024fdd  mov     rbx, rcx
0x180024fe0  call    cs:__imp_GetCurrentProcessId
0x180024fe6  mov     [rsp+270h+var_248], rbx
0x180024feb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180024ff2  mov     r9d, eax
0x180024ff5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180024ffd  mov     edx, 104h; unsigned __int64
0x180025002  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025007  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002500c  mov     r9d, 1F0001h; dwDesiredAccess
0x180025012  mov     [rsp+270h+var_240], 0
0x18002501b  xor     r8d, r8d; dwFlags
0x18002501e  lea     rdx, [rsp+270h+Name]; lpName
0x180025023  xor     ecx, ecx; lpMutexAttributes
0x180025025  call    cs:__imp_CreateMutexExW
0x18002502b  mov     rdx, rax
0x18002502e  lea     rcx, [rsp+270h+var_240]
0x180025033  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180025038  cmp     [rsp+270h+var_240], 0
0x18002503e  jnz     short loc_180025049
0x180025040  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180025045  mov     ebx, eax
0x180025047  jmp     short loc_1800250BE
0x180025049  lea     rdx, [rsp+270h+var_238]
0x18002504e  mov     [rsp+270h+var_238], 0
0x180025057  lea     rcx, [rsp+270h+var_240]
0x18002505c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180025061  lea     rdx, [rsp+270h+var_230]; void **
0x180025066  mov     [rsp+270h+var_230], 0
0x18002506f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025074  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180025079  mov     ebx, eax
0x18002507b  test    eax, eax
0x18002507d  jns     short loc_18002509F
0x18002507f  mov     edx, 12Eh; void *
0x180025084  mov     rcx, [rbp+178h]; this
0x18002508b  mov     r9d, eax; char *
0x18002508e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025093  lea     rcx, [rsp+270h+var_238]
0x180025098  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002509d  jmp     short loc_1800250BE
0x18002509f  mov     rcx, [rsp+270h+var_230]
0x1800250a4  test    rcx, rcx
0x1800250a7  jz      short loc_1800250EE
0x1800250a9  mov     [rdi], rcx
0x1800250ac  mov     eax, [rcx]
0x1800250ae  inc     eax
0x1800250b0  mov     [rcx], eax
0x1800250b2  lea     rcx, [rsp+270h+var_238]
0x1800250b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800250bc  xor     ebx, ebx
0x1800250be  lea     rcx, [rsp+270h+var_240]
0x1800250c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800250c8  mov     eax, ebx
0x1800250ca  mov     rcx, [rbp+170h+var_10]
0x1800250d1  xor     rcx, rsp; StackCookie
0x1800250d4  call    __security_check_cookie
0x1800250d9  lea     r11, [rsp+270h+var_s0]
0x1800250e1  mov     rbx, [r11+20h]
0x1800250e5  mov     rdi, [r11+28h]
0x1800250e9  mov     rsp, r11
0x1800250ec  pop     rbp
0x1800250ed  retn
0x1800250ee  mov     r8, rdi
0x1800250f1  lea     rdx, [rsp+270h+var_240]
0x1800250f6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800250fb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180025100  mov     ebx, eax
0x180025102  test    eax, eax
0x180025104  jns     short loc_1800250B2
0x180025106  mov     edx, 137h
0x18002510b  jmp     loc_180025084
```
