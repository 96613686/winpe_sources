# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002aaa4`
- end: `0x18002ac0a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180025604`

## callees

- `0x18000a384`
- `0x1800273c4`
- `0x18002aaa4`
- `0x18002ac10`
- `0x18002ac44`
- `0x18002ac98`
- `0x180031960`
- `0x180033c44`
- `0x180034cb0`
- `0x180036488`
- `0x1800369d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002ab21`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002ab21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002aadc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002aadc`

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
0x18002aaa4  mov     [rsp-8+arg_10], rbx
0x18002aaa9  mov     [rsp-8+arg_18], rdi
0x18002aaae  push    rbp
0x18002aaaf  lea     rbp, [rsp-170h]
0x18002aab7  sub     rsp, 270h
0x18002aabe  mov     rax, cs:__security_cookie
0x18002aac5  xor     rax, rsp
0x18002aac8  mov     [rbp+170h+var_10], rax
0x18002aacf  mov     rdi, rdx
0x18002aad2  mov     qword ptr [rdx], 0
0x18002aad9  mov     rbx, rcx
0x18002aadc  call    cs:__imp_GetCurrentProcessId
0x18002aae2  mov     [rsp+270h+var_248], rbx
0x18002aae7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002aaee  mov     r9d, eax
0x18002aaf1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002aaf9  mov     edx, 104h; unsigned __int64
0x18002aafe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002ab03  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ab08  mov     r9d, 1F0001h; dwDesiredAccess
0x18002ab0e  mov     [rsp+270h+var_240], 0
0x18002ab17  xor     r8d, r8d; dwFlags
0x18002ab1a  lea     rdx, [rsp+270h+Name]; lpName
0x18002ab1f  xor     ecx, ecx; lpMutexAttributes
0x18002ab21  call    cs:__imp_CreateMutexExW
0x18002ab27  mov     rdx, rax
0x18002ab2a  lea     rcx, [rsp+270h+var_240]
0x18002ab2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002ab34  cmp     [rsp+270h+var_240], 0
0x18002ab3a  jnz     short loc_18002AB45
0x18002ab3c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002ab41  mov     ebx, eax
0x18002ab43  jmp     short loc_18002ABB8
0x18002ab45  lea     rdx, [rsp+270h+var_238]
0x18002ab4a  lea     rcx, [rsp+270h+var_240]
0x18002ab4f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002ab54  lea     rdx, [rsp+270h+var_230]; void **
0x18002ab59  mov     [rsp+270h+var_230], 0
0x18002ab62  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002ab67  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002ab6c  mov     ebx, eax
0x18002ab6e  test    eax, eax
0x18002ab70  jns     short loc_18002AB99
0x18002ab72  mov     edx, 12Eh; void *
0x18002ab77  mov     rcx, [rbp+178h]; this
0x18002ab7e  lea     r8, aWil; "wil"
0x18002ab85  mov     r9d, eax; char *
0x18002ab88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ab8d  lea     rcx, [rsp+270h+var_238]
0x18002ab92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ab97  jmp     short loc_18002ABB8
0x18002ab99  mov     rcx, [rsp+270h+var_230]
0x18002ab9e  test    rcx, rcx
0x18002aba1  jz      short loc_18002ABE8
0x18002aba3  mov     [rdi], rcx
0x18002aba6  mov     eax, [rcx]
0x18002aba8  inc     eax
0x18002abaa  mov     [rcx], eax
0x18002abac  lea     rcx, [rsp+270h+var_238]
0x18002abb1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002abb6  xor     ebx, ebx
0x18002abb8  lea     rcx, [rsp+270h+var_240]
0x18002abbd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002abc2  mov     eax, ebx
0x18002abc4  mov     rcx, [rbp+170h+var_10]
0x18002abcb  xor     rcx, rsp; StackCookie
0x18002abce  call    __security_check_cookie
0x18002abd3  lea     r11, [rsp+270h+var_s0]
0x18002abdb  mov     rbx, [r11+20h]
0x18002abdf  mov     rdi, [r11+28h]
0x18002abe3  mov     rsp, r11
0x18002abe6  pop     rbp
0x18002abe7  retn
0x18002abe8  mov     r8, rdi
0x18002abeb  lea     rdx, [rsp+270h+var_240]
0x18002abf0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002abf5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002abfa  mov     ebx, eax
0x18002abfc  test    eax, eax
0x18002abfe  jns     short loc_18002ABAC
0x18002ac00  mov     edx, 137h
0x18002ac05  jmp     loc_18002AB77
```
