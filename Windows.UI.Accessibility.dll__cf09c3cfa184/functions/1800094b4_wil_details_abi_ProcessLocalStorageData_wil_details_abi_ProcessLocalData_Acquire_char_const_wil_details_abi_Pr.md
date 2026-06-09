# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800094b4`
- end: `0x18000961a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a4ec`

## callees

- `0x180003980`
- `0x180006c10`
- `0x180009020`
- `0x18000903c`
- `0x1800094b4`
- `0x18000a10c`
- `0x18000a9f4`
- `0x18000be1c`
- `0x18000c7d4`
- `0x18000cfe4`
- `0x18000d308`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800094ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800094ec`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009531`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009531`

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
0x1800094b4  mov     [rsp-8+arg_10], rbx
0x1800094b9  mov     [rsp-8+arg_18], rdi
0x1800094be  push    rbp
0x1800094bf  lea     rbp, [rsp-170h]
0x1800094c7  sub     rsp, 270h
0x1800094ce  mov     rax, cs:__security_cookie
0x1800094d5  xor     rax, rsp
0x1800094d8  mov     [rbp+170h+var_10], rax
0x1800094df  mov     rdi, rdx
0x1800094e2  mov     qword ptr [rdx], 0
0x1800094e9  mov     rbx, rcx
0x1800094ec  call    cs:__imp_GetCurrentProcessId
0x1800094f2  mov     [rsp+270h+var_248], rbx
0x1800094f7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800094fe  mov     r9d, eax
0x180009501  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180009509  mov     edx, 104h; unsigned __int64
0x18000950e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009513  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009518  mov     r9d, 1F0001h; dwDesiredAccess
0x18000951e  mov     [rsp+270h+var_240], 0
0x180009527  xor     r8d, r8d; dwFlags
0x18000952a  lea     rdx, [rsp+270h+Name]; lpName
0x18000952f  xor     ecx, ecx; lpMutexAttributes
0x180009531  call    cs:__imp_CreateMutexExW
0x180009537  mov     rdx, rax
0x18000953a  lea     rcx, [rsp+270h+var_240]
0x18000953f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009544  cmp     [rsp+270h+var_240], 0
0x18000954a  jnz     short loc_180009555
0x18000954c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009551  mov     ebx, eax
0x180009553  jmp     short loc_1800095C8
0x180009555  lea     rdx, [rsp+270h+var_238]
0x18000955a  lea     rcx, [rsp+270h+var_240]
0x18000955f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180009564  lea     rdx, [rsp+270h+var_230]; void **
0x180009569  mov     [rsp+270h+var_230], 0
0x180009572  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009577  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000957c  mov     ebx, eax
0x18000957e  test    eax, eax
0x180009580  jns     short loc_1800095A9
0x180009582  mov     edx, 12Eh; void *
0x180009587  mov     rcx, [rbp+178h]; this
0x18000958e  lea     r8, aWil; "wil"
0x180009595  mov     r9d, eax; char *
0x180009598  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000959d  lea     rcx, [rsp+270h+var_238]
0x1800095a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800095a7  jmp     short loc_1800095C8
0x1800095a9  mov     rcx, [rsp+270h+var_230]
0x1800095ae  test    rcx, rcx
0x1800095b1  jz      short loc_1800095F8
0x1800095b3  mov     [rdi], rcx
0x1800095b6  mov     eax, [rcx]
0x1800095b8  inc     eax
0x1800095ba  mov     [rcx], eax
0x1800095bc  lea     rcx, [rsp+270h+var_238]
0x1800095c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800095c6  xor     ebx, ebx
0x1800095c8  lea     rcx, [rsp+270h+var_240]
0x1800095cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800095d2  mov     eax, ebx
0x1800095d4  mov     rcx, [rbp+170h+var_10]
0x1800095db  xor     rcx, rsp; StackCookie
0x1800095de  call    __security_check_cookie
0x1800095e3  lea     r11, [rsp+270h+var_s0]
0x1800095eb  mov     rbx, [r11+20h]
0x1800095ef  mov     rdi, [r11+28h]
0x1800095f3  mov     rsp, r11
0x1800095f6  pop     rbp
0x1800095f7  retn
0x1800095f8  mov     r8, rdi
0x1800095fb  lea     rdx, [rsp+270h+var_240]
0x180009600  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009605  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000960a  mov     ebx, eax
0x18000960c  test    eax, eax
0x18000960e  jns     short loc_1800095BC
0x180009610  mov     edx, 137h
0x180009615  jmp     loc_180009587
```
