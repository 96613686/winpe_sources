# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003d18`
- end: `0x180003e77`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800053b4`

## callees

- `0x180001e00`
- `0x18000373c`
- `0x180003758`
- `0x180003d18`
- `0x180005098`
- `0x180005d50`
- `0x1800074cc`
- `0x180007d1c`
- `0x180008210`
- `0x180008a14`
- `0x180008de8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003d95`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003d95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d50`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rdx
  _DWORD *v13; // rcx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v16; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( v15 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v15,
      &v16);
    v17 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v12);
      goto LABEL_9;
    }
    v13 = v17;
    if ( v17 )
    {
      *a2 = v17;
      ++*v13;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v16,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180003d18  mov     [rsp-8+arg_10], rbx
0x180003d1d  mov     [rsp-8+arg_18], rdi
0x180003d22  push    rbp
0x180003d23  lea     rbp, [rsp-170h]
0x180003d2b  sub     rsp, 270h
0x180003d32  mov     rax, cs:__security_cookie
0x180003d39  xor     rax, rsp
0x180003d3c  mov     [rbp+170h+var_10], rax
0x180003d43  mov     rdi, rdx
0x180003d46  mov     qword ptr [rdx], 0
0x180003d4d  mov     rbx, rcx
0x180003d50  call    cs:__imp_GetCurrentProcessId
0x180003d56  mov     [rsp+270h+var_248], rbx
0x180003d5b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003d62  mov     r9d, eax
0x180003d65  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003d6d  mov     edx, 104h; unsigned __int64
0x180003d72  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003d77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003d7c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003d82  mov     [rsp+270h+var_240], 0
0x180003d8b  xor     r8d, r8d; dwFlags
0x180003d8e  lea     rdx, [rsp+270h+Name]; lpName
0x180003d93  xor     ecx, ecx; lpMutexAttributes
0x180003d95  call    cs:__imp_CreateMutexExW
0x180003d9b  mov     rdx, rax
0x180003d9e  lea     rcx, [rsp+270h+var_240]
0x180003da3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003da8  cmp     [rsp+270h+var_240], 0
0x180003dae  jnz     short loc_180003DB9
0x180003db0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003db5  mov     ebx, eax
0x180003db7  jmp     short loc_180003E25
0x180003db9  lea     rdx, [rsp+270h+var_238]
0x180003dbe  lea     rcx, [rsp+270h+var_240]
0x180003dc3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003dc8  lea     rdx, [rsp+270h+var_230]; void **
0x180003dcd  mov     [rsp+270h+var_230], 0
0x180003dd6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003ddb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180003de0  mov     ebx, eax
0x180003de2  test    eax, eax
0x180003de4  jns     short loc_180003E06
0x180003de6  mov     edx, 12Eh; void *
0x180003deb  mov     rcx, [rbp+178h]; this
0x180003df2  mov     r9d, eax; char *
0x180003df5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003dfa  lea     rcx, [rsp+270h+var_238]
0x180003dff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e04  jmp     short loc_180003E25
0x180003e06  mov     rcx, [rsp+270h+var_230]
0x180003e0b  test    rcx, rcx
0x180003e0e  jz      short loc_180003E55
0x180003e10  mov     [rdi], rcx
0x180003e13  mov     eax, [rcx]
0x180003e15  inc     eax
0x180003e17  mov     [rcx], eax
0x180003e19  lea     rcx, [rsp+270h+var_238]
0x180003e1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e23  xor     ebx, ebx
0x180003e25  lea     rcx, [rsp+270h+var_240]
0x180003e2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e2f  mov     eax, ebx
0x180003e31  mov     rcx, [rbp+170h+var_10]
0x180003e38  xor     rcx, rsp; StackCookie
0x180003e3b  call    __security_check_cookie
0x180003e40  lea     r11, [rsp+270h+var_s0]
0x180003e48  mov     rbx, [r11+20h]
0x180003e4c  mov     rdi, [r11+28h]
0x180003e50  mov     rsp, r11
0x180003e53  pop     rbp
0x180003e54  retn
0x180003e55  mov     r8, rdi
0x180003e58  lea     rdx, [rsp+270h+var_240]
0x180003e5d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003e62  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003e67  mov     ebx, eax
0x180003e69  test    eax, eax
0x180003e6b  jns     short loc_180003E19
0x180003e6d  mov     edx, 137h
0x180003e72  jmp     loc_180003DEB
```
