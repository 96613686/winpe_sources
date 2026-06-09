# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180039cf0`
- end: `0x180039e63`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003bad4`

## callees

- `0x180033430`
- `0x1800361e4`
- `0x1800394b4`
- `0x180039b50`
- `0x180039b70`
- `0x180039cf0`
- `0x18003c00c`
- `0x18003d8b0`
- `0x18003e100`
- `0x18003e264`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039d28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039d28`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180039d73`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180039d73`

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
0x180039cf0  mov     [rsp-8+arg_10], rbx
0x180039cf5  mov     [rsp-8+arg_18], rdi
0x180039cfa  push    rbp
0x180039cfb  lea     rbp, [rsp-170h]
0x180039d03  sub     rsp, 270h
0x180039d0a  mov     rax, cs:__security_cookie
0x180039d11  xor     rax, rsp
0x180039d14  mov     [rbp+170h+var_10], rax
0x180039d1b  mov     rdi, rdx
0x180039d1e  mov     qword ptr [rdx], 0
0x180039d25  mov     rbx, rcx
0x180039d28  call    cs:__imp_GetCurrentProcessId
0x180039d2f  nop     dword ptr [rax+rax+00h]
0x180039d34  mov     [rsp+270h+var_248], rbx
0x180039d39  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180039d40  mov     r9d, eax
0x180039d43  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180039d4b  mov     edx, 104h; unsigned __int64
0x180039d50  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180039d55  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039d5a  mov     r9d, 1F0001h; dwDesiredAccess
0x180039d60  mov     [rsp+270h+var_240], 0
0x180039d69  xor     r8d, r8d; dwFlags
0x180039d6c  lea     rdx, [rsp+270h+Name]; lpName
0x180039d71  xor     ecx, ecx; lpMutexAttributes
0x180039d73  call    cs:__imp_CreateMutexExW
0x180039d7a  nop     dword ptr [rax+rax+00h]
0x180039d7f  mov     rdx, rax
0x180039d82  lea     rcx, [rsp+270h+var_240]
0x180039d87  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180039d8c  cmp     [rsp+270h+var_240], 0
0x180039d92  jnz     short loc_180039D9D
0x180039d94  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180039d99  mov     ebx, eax
0x180039d9b  jmp     short loc_180039E10
0x180039d9d  lea     rdx, [rsp+270h+var_238]
0x180039da2  lea     rcx, [rsp+270h+var_240]
0x180039da7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180039dac  lea     rdx, [rsp+270h+var_230]; void **
0x180039db1  mov     [rsp+270h+var_230], 0
0x180039dba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180039dbf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180039dc4  mov     ebx, eax
0x180039dc6  test    eax, eax
0x180039dc8  jns     short loc_180039DF1
0x180039dca  mov     edx, 12Eh; void *
0x180039dcf  mov     rcx, [rbp+178h]; this
0x180039dd6  lea     r8, aWil; "wil"
0x180039ddd  mov     r9d, eax; char *
0x180039de0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039de5  lea     rcx, [rsp+270h+var_238]
0x180039dea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180039def  jmp     short loc_180039E10
0x180039df1  mov     rcx, [rsp+270h+var_230]
0x180039df6  test    rcx, rcx
0x180039df9  jz      short loc_180039E41
0x180039dfb  mov     [rdi], rcx
0x180039dfe  mov     eax, [rcx]
0x180039e00  inc     eax
0x180039e02  mov     [rcx], eax
0x180039e04  lea     rcx, [rsp+270h+var_238]
0x180039e09  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180039e0e  xor     ebx, ebx
0x180039e10  lea     rcx, [rsp+270h+var_240]
0x180039e15  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180039e1a  mov     eax, ebx
0x180039e1c  mov     rcx, [rbp+170h+var_10]
0x180039e23  xor     rcx, rsp; StackCookie
0x180039e26  call    __security_check_cookie
0x180039e2b  lea     r11, [rsp+270h+var_s0]
0x180039e33  mov     rbx, [r11+20h]
0x180039e37  mov     rdi, [r11+28h]
0x180039e3b  mov     rsp, r11
0x180039e3e  pop     rbp
0x180039e3f  retn
0x180039e41  mov     r8, rdi
0x180039e44  lea     rdx, [rsp+270h+var_240]
0x180039e49  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180039e4e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180039e53  mov     ebx, eax
0x180039e55  test    eax, eax
0x180039e57  jns     short loc_180039E04
0x180039e59  mov     edx, 137h
0x180039e5e  jmp     loc_180039DCF
```
