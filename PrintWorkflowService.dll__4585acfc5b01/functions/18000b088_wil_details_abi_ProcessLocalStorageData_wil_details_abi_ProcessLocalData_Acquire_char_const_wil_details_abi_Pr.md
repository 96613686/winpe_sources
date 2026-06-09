# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000b088`
- end: `0x18000b1ee`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d8ec`

## callees

- `0x180003ca0`
- `0x18000a128`
- `0x18000a144`
- `0x18000b088`
- `0x18000d158`
- `0x18000e754`
- `0x180010b0c`
- `0x1800114a4`
- `0x180011ac0`
- `0x1800128e0`
- `0x180014054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b105`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b0c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b0c0`

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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18000b088  mov     [rsp-8+arg_10], rbx
0x18000b08d  mov     [rsp-8+arg_18], rdi
0x18000b092  push    rbp
0x18000b093  lea     rbp, [rsp-170h]
0x18000b09b  sub     rsp, 270h
0x18000b0a2  mov     rax, cs:__security_cookie
0x18000b0a9  xor     rax, rsp
0x18000b0ac  mov     [rbp+170h+var_10], rax
0x18000b0b3  mov     rdi, rdx
0x18000b0b6  mov     qword ptr [rdx], 0
0x18000b0bd  mov     rbx, rcx
0x18000b0c0  call    cs:__imp_GetCurrentProcessId
0x18000b0c6  mov     [rsp+270h+var_248], rbx
0x18000b0cb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b0d2  mov     r9d, eax
0x18000b0d5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000b0dd  mov     edx, 104h; unsigned __int64
0x18000b0e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b0e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b0ec  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b0f2  mov     [rsp+270h+var_240], 0
0x18000b0fb  xor     r8d, r8d; dwFlags
0x18000b0fe  lea     rdx, [rsp+270h+Name]; lpName
0x18000b103  xor     ecx, ecx; lpMutexAttributes
0x18000b105  call    cs:__imp_CreateMutexExW
0x18000b10b  mov     rdx, rax
0x18000b10e  lea     rcx, [rsp+270h+var_240]
0x18000b113  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b118  cmp     [rsp+270h+var_240], 0
0x18000b11e  jnz     short loc_18000B129
0x18000b120  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b125  mov     ebx, eax
0x18000b127  jmp     short loc_18000B19C
0x18000b129  lea     rdx, [rsp+270h+var_238]
0x18000b12e  lea     rcx, [rsp+270h+var_240]
0x18000b133  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000b138  lea     rdx, [rsp+270h+var_230]; void **
0x18000b13d  mov     [rsp+270h+var_230], 0
0x18000b146  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b14b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000b150  mov     ebx, eax
0x18000b152  test    eax, eax
0x18000b154  jns     short loc_18000B17D
0x18000b156  mov     edx, 12Eh; void *
0x18000b15b  mov     rcx, [rbp+178h]; this
0x18000b162  lea     r8, aWil; "wil"
0x18000b169  mov     r9d, eax; char *
0x18000b16c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b171  lea     rcx, [rsp+270h+var_238]
0x18000b176  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b17b  jmp     short loc_18000B19C
0x18000b17d  mov     rcx, [rsp+270h+var_230]
0x18000b182  test    rcx, rcx
0x18000b185  jz      short loc_18000B1CC
0x18000b187  mov     [rdi], rcx
0x18000b18a  mov     eax, [rcx]
0x18000b18c  inc     eax
0x18000b18e  mov     [rcx], eax
0x18000b190  lea     rcx, [rsp+270h+var_238]
0x18000b195  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b19a  xor     ebx, ebx
0x18000b19c  lea     rcx, [rsp+270h+var_240]
0x18000b1a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b1a6  mov     eax, ebx
0x18000b1a8  mov     rcx, [rbp+170h+var_10]
0x18000b1af  xor     rcx, rsp; StackCookie
0x18000b1b2  call    __security_check_cookie
0x18000b1b7  lea     r11, [rsp+270h+var_s0]
0x18000b1bf  mov     rbx, [r11+20h]
0x18000b1c3  mov     rdi, [r11+28h]
0x18000b1c7  mov     rsp, r11
0x18000b1ca  pop     rbp
0x18000b1cb  retn
0x18000b1cc  mov     r8, rdi
0x18000b1cf  lea     rdx, [rsp+270h+var_240]
0x18000b1d4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b1d9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000b1de  mov     ebx, eax
0x18000b1e0  test    eax, eax
0x18000b1e2  jns     short loc_18000B190
0x18000b1e4  mov     edx, 137h
0x18000b1e9  jmp     loc_18000B15B
```
