# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180019b74`
- end: `0x180019ce1`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `365`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180023af8`

## callees

- `0x18000720c`
- `0x180010084`
- `0x180019b74`
- `0x180019ce8`
- `0x18001a0f4`
- `0x18001a110`
- `0x18001a1ac`
- `0x18001afac`
- `0x18001afc8`
- `0x180023eec`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019bf1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019bf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019bac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019bac`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  HANDLE v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
      &v12,
      0,
      0xFFFFFFFF);
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
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x180019b74  mov     [rsp-8+arg_10], rbx
0x180019b79  mov     [rsp-8+arg_18], rdi
0x180019b7e  push    rbp
0x180019b7f  lea     rbp, [rsp-170h]
0x180019b87  sub     rsp, 270h
0x180019b8e  mov     rax, cs:__security_cookie
0x180019b95  xor     rax, rsp
0x180019b98  mov     [rbp+170h+var_10], rax
0x180019b9f  mov     rdi, rdx
0x180019ba2  mov     qword ptr [rdx], 0
0x180019ba9  mov     rbx, rcx
0x180019bac  call    cs:__imp_GetCurrentProcessId
0x180019bb2  mov     [rsp+270h+var_248], rbx
0x180019bb7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180019bbe  mov     r9d, eax
0x180019bc1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180019bc9  mov     edx, 104h; unsigned __int64
0x180019bce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180019bd3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019bd8  mov     r9d, 1F0001h; dwDesiredAccess
0x180019bde  mov     [rsp+270h+var_240], 0
0x180019be7  xor     r8d, r8d; dwFlags
0x180019bea  lea     rdx, [rsp+270h+Name]; lpName
0x180019bef  xor     ecx, ecx; lpMutexAttributes
0x180019bf1  call    cs:__imp_CreateMutexExW
0x180019bf7  mov     rdx, rax
0x180019bfa  lea     rcx, [rsp+270h+var_240]
0x180019bff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180019c04  cmp     [rsp+270h+var_240], 0
0x180019c0a  jnz     short loc_180019C15
0x180019c0c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019c11  mov     ebx, eax
0x180019c13  jmp     short loc_180019C8F
0x180019c15  or      r9d, 0FFFFFFFFh
0x180019c19  lea     rdx, [rsp+270h+var_238]
0x180019c1e  xor     r8d, r8d
0x180019c21  lea     rcx, [rsp+270h+var_240]
0x180019c26  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180019c2b  lea     rdx, [rsp+270h+var_230]; void **
0x180019c30  mov     [rsp+270h+var_230], 0
0x180019c39  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180019c3e  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180019c43  mov     ebx, eax
0x180019c45  test    eax, eax
0x180019c47  jns     short loc_180019C70
0x180019c49  mov     edx, 12Eh; void *
0x180019c4e  mov     rcx, [rbp+178h]; this
0x180019c55  lea     r8, aWil; "wil"
0x180019c5c  mov     r9d, eax; char *
0x180019c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c64  lea     rcx, [rsp+270h+var_238]
0x180019c69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019c6e  jmp     short loc_180019C8F
0x180019c70  mov     rcx, [rsp+270h+var_230]
0x180019c75  test    rcx, rcx
0x180019c78  jz      short loc_180019CBF
0x180019c7a  mov     [rdi], rcx
0x180019c7d  mov     eax, [rcx]
0x180019c7f  inc     eax
0x180019c81  mov     [rcx], eax
0x180019c83  lea     rcx, [rsp+270h+var_238]
0x180019c88  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019c8d  xor     ebx, ebx
0x180019c8f  lea     rcx, [rsp+270h+var_240]
0x180019c94  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019c99  mov     eax, ebx
0x180019c9b  mov     rcx, [rbp+170h+var_10]
0x180019ca2  xor     rcx, rsp; StackCookie
0x180019ca5  call    __security_check_cookie
0x180019caa  lea     r11, [rsp+270h+var_s0]
0x180019cb2  mov     rbx, [r11+20h]
0x180019cb6  mov     rdi, [r11+28h]
0x180019cba  mov     rsp, r11
0x180019cbd  pop     rbp
0x180019cbe  retn
0x180019cbf  mov     r8, rdi
0x180019cc2  lea     rdx, [rsp+270h+var_240]
0x180019cc7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180019ccc  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180019cd1  mov     ebx, eax
0x180019cd3  test    eax, eax
0x180019cd5  jns     short loc_180019C83
0x180019cd7  mov     edx, 137h
0x180019cdc  jmp     loc_180019C4E
```
