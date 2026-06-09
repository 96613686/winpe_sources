# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a6c8`
- end: `0x18000a827`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d3c8`

## callees

- `0x180003fc0`
- `0x180009f80`
- `0x180009f9c`
- `0x18000a6c8`
- `0x18000d060`
- `0x18000df7c`
- `0x18001025c`
- `0x180011390`
- `0x180011808`
- `0x1800129dc`
- `0x180012d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a745`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a745`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a700`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a700`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18000a6c8  mov     [rsp-8+arg_10], rbx
0x18000a6cd  mov     [rsp-8+arg_18], rdi
0x18000a6d2  push    rbp
0x18000a6d3  lea     rbp, [rsp-170h]
0x18000a6db  sub     rsp, 270h
0x18000a6e2  mov     rax, cs:__security_cookie
0x18000a6e9  xor     rax, rsp
0x18000a6ec  mov     [rbp+170h+var_10], rax
0x18000a6f3  mov     rdi, rdx
0x18000a6f6  mov     qword ptr [rdx], 0
0x18000a6fd  mov     rbx, rcx
0x18000a700  call    cs:__imp_GetCurrentProcessId
0x18000a706  mov     [rsp+270h+var_248], rbx
0x18000a70b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a712  mov     r9d, eax
0x18000a715  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000a71d  mov     edx, 104h; unsigned __int64
0x18000a722  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a727  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a72c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a732  mov     [rsp+270h+var_240], 0
0x18000a73b  xor     r8d, r8d; dwFlags
0x18000a73e  lea     rdx, [rsp+270h+Name]; lpName
0x18000a743  xor     ecx, ecx; lpMutexAttributes
0x18000a745  call    cs:__imp_CreateMutexExW
0x18000a74b  mov     rdx, rax
0x18000a74e  lea     rcx, [rsp+270h+var_240]
0x18000a753  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a758  cmp     [rsp+270h+var_240], 0
0x18000a75e  jnz     short loc_18000A769
0x18000a760  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a765  mov     ebx, eax
0x18000a767  jmp     short loc_18000A7D5
0x18000a769  lea     rdx, [rsp+270h+var_238]
0x18000a76e  lea     rcx, [rsp+270h+var_240]
0x18000a773  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a778  lea     rdx, [rsp+270h+var_230]; void **
0x18000a77d  mov     [rsp+270h+var_230], 0
0x18000a786  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a78b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a790  mov     ebx, eax
0x18000a792  test    eax, eax
0x18000a794  jns     short loc_18000A7B6
0x18000a796  mov     edx, 12Eh; void *
0x18000a79b  mov     rcx, [rbp+178h]; this
0x18000a7a2  mov     r9d, eax; char *
0x18000a7a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7aa  lea     rcx, [rsp+270h+var_238]
0x18000a7af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a7b4  jmp     short loc_18000A7D5
0x18000a7b6  mov     rcx, [rsp+270h+var_230]
0x18000a7bb  test    rcx, rcx
0x18000a7be  jz      short loc_18000A805
0x18000a7c0  mov     [rdi], rcx
0x18000a7c3  mov     eax, [rcx]
0x18000a7c5  inc     eax
0x18000a7c7  mov     [rcx], eax
0x18000a7c9  lea     rcx, [rsp+270h+var_238]
0x18000a7ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a7d3  xor     ebx, ebx
0x18000a7d5  lea     rcx, [rsp+270h+var_240]
0x18000a7da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a7df  mov     eax, ebx
0x18000a7e1  mov     rcx, [rbp+170h+var_10]
0x18000a7e8  xor     rcx, rsp; StackCookie
0x18000a7eb  call    __security_check_cookie
0x18000a7f0  lea     r11, [rsp+270h+var_s0]
0x18000a7f8  mov     rbx, [r11+20h]
0x18000a7fc  mov     rdi, [r11+28h]
0x18000a800  mov     rsp, r11
0x18000a803  pop     rbp
0x18000a804  retn
0x18000a805  mov     r8, rdi
0x18000a808  lea     rdx, [rsp+270h+var_240]
0x18000a80d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a812  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a817  mov     ebx, eax
0x18000a819  test    eax, eax
0x18000a81b  jns     short loc_18000A7C9
0x18000a81d  mov     edx, 137h
0x18000a822  jmp     loc_18000A79B
```
