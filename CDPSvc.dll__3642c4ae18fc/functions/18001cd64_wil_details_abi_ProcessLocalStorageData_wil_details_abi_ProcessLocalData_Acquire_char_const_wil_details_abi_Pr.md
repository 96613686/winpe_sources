# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001cd64`
- end: `0x18001ceca`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180028be8`

## callees

- `0x1800130ec`
- `0x18001cd64`
- `0x18001d10c`
- `0x18001d128`
- `0x18001d15c`
- `0x18001d1b0`
- `0x1800225a0`
- `0x180027eac`
- `0x180029310`
- `0x18002a7cc`
- `0x18002b234`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001cd9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001cd9c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001cde1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001cde1`

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
0x18001cd64  mov     [rsp-8+arg_10], rbx
0x18001cd69  mov     [rsp-8+arg_18], rdi
0x18001cd6e  push    rbp
0x18001cd6f  lea     rbp, [rsp-170h]
0x18001cd77  sub     rsp, 270h
0x18001cd7e  mov     rax, cs:__security_cookie
0x18001cd85  xor     rax, rsp
0x18001cd88  mov     [rbp+170h+var_10], rax
0x18001cd8f  mov     rdi, rdx
0x18001cd92  mov     qword ptr [rdx], 0
0x18001cd99  mov     rbx, rcx
0x18001cd9c  call    cs:__imp_GetCurrentProcessId
0x18001cda2  mov     [rsp+270h+var_248], rbx
0x18001cda7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001cdae  mov     r9d, eax
0x18001cdb1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001cdb9  mov     edx, 104h; unsigned __int64
0x18001cdbe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001cdc3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cdc8  mov     r9d, 1F0001h; dwDesiredAccess
0x18001cdce  mov     [rsp+270h+var_240], 0
0x18001cdd7  xor     r8d, r8d; dwFlags
0x18001cdda  lea     rdx, [rsp+270h+Name]; lpName
0x18001cddf  xor     ecx, ecx; lpMutexAttributes
0x18001cde1  call    cs:__imp_CreateMutexExW
0x18001cde7  mov     rdx, rax
0x18001cdea  lea     rcx, [rsp+270h+var_240]
0x18001cdef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001cdf4  cmp     [rsp+270h+var_240], 0
0x18001cdfa  jnz     short loc_18001CE05
0x18001cdfc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001ce01  mov     ebx, eax
0x18001ce03  jmp     short loc_18001CE78
0x18001ce05  lea     rdx, [rsp+270h+var_238]
0x18001ce0a  lea     rcx, [rsp+270h+var_240]
0x18001ce0f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001ce14  lea     rdx, [rsp+270h+var_230]; void **
0x18001ce19  mov     [rsp+270h+var_230], 0
0x18001ce22  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001ce27  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001ce2c  mov     ebx, eax
0x18001ce2e  test    eax, eax
0x18001ce30  jns     short loc_18001CE59
0x18001ce32  mov     edx, 12Eh; void *
0x18001ce37  mov     rcx, [rbp+178h]; this
0x18001ce3e  lea     r8, aWil; "wil"
0x18001ce45  mov     r9d, eax; char *
0x18001ce48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ce4d  lea     rcx, [rsp+270h+var_238]
0x18001ce52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ce57  jmp     short loc_18001CE78
0x18001ce59  mov     rcx, [rsp+270h+var_230]
0x18001ce5e  test    rcx, rcx
0x18001ce61  jz      short loc_18001CEA8
0x18001ce63  mov     [rdi], rcx
0x18001ce66  mov     eax, [rcx]
0x18001ce68  inc     eax
0x18001ce6a  mov     [rcx], eax
0x18001ce6c  lea     rcx, [rsp+270h+var_238]
0x18001ce71  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ce76  xor     ebx, ebx
0x18001ce78  lea     rcx, [rsp+270h+var_240]
0x18001ce7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ce82  mov     eax, ebx
0x18001ce84  mov     rcx, [rbp+170h+var_10]
0x18001ce8b  xor     rcx, rsp; StackCookie
0x18001ce8e  call    __security_check_cookie
0x18001ce93  lea     r11, [rsp+270h+var_s0]
0x18001ce9b  mov     rbx, [r11+20h]
0x18001ce9f  mov     rdi, [r11+28h]
0x18001cea3  mov     rsp, r11
0x18001cea6  pop     rbp
0x18001cea7  retn
0x18001cea8  mov     r8, rdi
0x18001ceab  lea     rdx, [rsp+270h+var_240]
0x18001ceb0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001ceb5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001ceba  mov     ebx, eax
0x18001cebc  test    eax, eax
0x18001cebe  jns     short loc_18001CE6C
0x18001cec0  mov     edx, 137h
0x18001cec5  jmp     loc_18001CE37
```
