# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004ce0`
- end: `0x180004e53`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800063c8`

## callees

- `0x18000473c`
- `0x18000475c`
- `0x180004ce0`
- `0x180006080`
- `0x180006edc`
- `0x1800087ec`
- `0x180008f60`
- `0x180009368`
- `0x180009e24`
- `0x18000a614`
- `0x180028860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004d63`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004d63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d18`

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
0x180004ce0  mov     [rsp-8+arg_10], rbx
0x180004ce5  mov     [rsp-8+arg_18], rdi
0x180004cea  push    rbp
0x180004ceb  lea     rbp, [rsp-170h]
0x180004cf3  sub     rsp, 270h
0x180004cfa  mov     rax, cs:__security_cookie
0x180004d01  xor     rax, rsp
0x180004d04  mov     [rbp+170h+var_10], rax
0x180004d0b  mov     rdi, rdx
0x180004d0e  mov     qword ptr [rdx], 0
0x180004d15  mov     rbx, rcx
0x180004d18  call    cs:__imp_GetCurrentProcessId
0x180004d1f  nop     dword ptr [rax+rax+00h]
0x180004d24  mov     [rsp+270h+var_248], rbx
0x180004d29  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004d30  mov     r9d, eax
0x180004d33  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004d3b  mov     edx, 104h; unsigned __int64
0x180004d40  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004d45  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d4a  mov     r9d, 1F0001h; dwDesiredAccess
0x180004d50  mov     [rsp+270h+var_240], 0
0x180004d59  xor     r8d, r8d; dwFlags
0x180004d5c  lea     rdx, [rsp+270h+Name]; lpName
0x180004d61  xor     ecx, ecx; lpMutexAttributes
0x180004d63  call    cs:__imp_CreateMutexExW
0x180004d6a  nop     dword ptr [rax+rax+00h]
0x180004d6f  mov     rdx, rax
0x180004d72  lea     rcx, [rsp+270h+var_240]
0x180004d77  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004d7c  cmp     [rsp+270h+var_240], 0
0x180004d82  jnz     short loc_180004D8D
0x180004d84  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004d89  mov     ebx, eax
0x180004d8b  jmp     short loc_180004E00
0x180004d8d  lea     rdx, [rsp+270h+var_238]
0x180004d92  lea     rcx, [rsp+270h+var_240]
0x180004d97  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004d9c  lea     rdx, [rsp+270h+var_230]; void **
0x180004da1  mov     [rsp+270h+var_230], 0
0x180004daa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004daf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004db4  mov     ebx, eax
0x180004db6  test    eax, eax
0x180004db8  jns     short loc_180004DE1
0x180004dba  mov     edx, 12Eh; void *
0x180004dbf  mov     rcx, [rbp+178h]; this
0x180004dc6  lea     r8, aWil; "wil"
0x180004dcd  mov     r9d, eax; char *
0x180004dd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dd5  lea     rcx, [rsp+270h+var_238]
0x180004dda  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004ddf  jmp     short loc_180004E00
0x180004de1  mov     rcx, [rsp+270h+var_230]
0x180004de6  test    rcx, rcx
0x180004de9  jz      short loc_180004E31
0x180004deb  mov     [rdi], rcx
0x180004dee  mov     eax, [rcx]
0x180004df0  inc     eax
0x180004df2  mov     [rcx], eax
0x180004df4  lea     rcx, [rsp+270h+var_238]
0x180004df9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004dfe  xor     ebx, ebx
0x180004e00  lea     rcx, [rsp+270h+var_240]
0x180004e05  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004e0a  mov     eax, ebx
0x180004e0c  mov     rcx, [rbp+170h+var_10]
0x180004e13  xor     rcx, rsp; StackCookie
0x180004e16  call    __security_check_cookie
0x180004e1b  lea     r11, [rsp+270h+var_s0]
0x180004e23  mov     rbx, [r11+20h]
0x180004e27  mov     rdi, [r11+28h]
0x180004e2b  mov     rsp, r11
0x180004e2e  pop     rbp
0x180004e2f  retn
0x180004e31  mov     r8, rdi
0x180004e34  lea     rdx, [rsp+270h+var_240]
0x180004e39  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004e3e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004e43  mov     ebx, eax
0x180004e45  test    eax, eax
0x180004e47  jns     short loc_180004DF4
0x180004e49  mov     edx, 137h
0x180004e4e  jmp     loc_180004DBF
```
