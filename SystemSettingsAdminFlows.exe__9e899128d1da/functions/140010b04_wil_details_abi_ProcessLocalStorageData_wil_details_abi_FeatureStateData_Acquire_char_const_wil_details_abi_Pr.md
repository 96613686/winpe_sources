# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140010b04`
- end: `0x140010c6a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140019b40`

## callees

- `0x140005f30`
- `0x14000ee0c`
- `0x14000ee28`
- `0x140010b04`
- `0x1400199b8`
- `0x14001ae74`
- `0x14001f3d4`
- `0x140026134`
- `0x1400267d8`
- `0x14002adac`
- `0x14002c37c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010b3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010b3c`
- `KERNEL32!CreateMutexExW` at `0x140010b81`
- `KERNEL32!CreateMutexExW` at `0x140010b81`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x140010b04  mov     [rsp-8+arg_10], rbx
0x140010b09  mov     [rsp-8+arg_18], rdi
0x140010b0e  push    rbp
0x140010b0f  lea     rbp, [rsp-170h]
0x140010b17  sub     rsp, 270h
0x140010b1e  mov     rax, cs:__security_cookie
0x140010b25  xor     rax, rsp
0x140010b28  mov     [rbp+170h+var_10], rax
0x140010b2f  mov     rdi, rdx
0x140010b32  mov     qword ptr [rdx], 0
0x140010b39  mov     rbx, rcx
0x140010b3c  call    cs:__imp_GetCurrentProcessId
0x140010b42  mov     [rsp+270h+var_248], rbx
0x140010b47  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140010b4e  mov     r9d, eax
0x140010b51  mov     [rsp+270h+var_250], 130h; int
0x140010b59  mov     edx, 104h; unsigned __int64
0x140010b5e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140010b63  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010b68  mov     r9d, 1F0001h; dwDesiredAccess
0x140010b6e  mov     [rsp+270h+var_240], 0
0x140010b77  xor     r8d, r8d; dwFlags
0x140010b7a  lea     rdx, [rsp+270h+Name]; lpName
0x140010b7f  xor     ecx, ecx; lpMutexAttributes
0x140010b81  call    cs:__imp_CreateMutexExW
0x140010b87  mov     rdx, rax
0x140010b8a  lea     rcx, [rsp+270h+var_240]
0x140010b8f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140010b94  cmp     [rsp+270h+var_240], 0
0x140010b9a  jnz     short loc_140010BA5
0x140010b9c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140010ba1  mov     ebx, eax
0x140010ba3  jmp     short loc_140010C18
0x140010ba5  lea     rdx, [rsp+270h+var_238]
0x140010baa  lea     rcx, [rsp+270h+var_240]
0x140010baf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140010bb4  lea     rdx, [rsp+270h+var_230]; void **
0x140010bb9  mov     [rsp+270h+var_230], 0
0x140010bc2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140010bc7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140010bcc  mov     ebx, eax
0x140010bce  test    eax, eax
0x140010bd0  jns     short loc_140010BF9
0x140010bd2  mov     edx, 12Eh; void *
0x140010bd7  mov     rcx, [rbp+178h]; this
0x140010bde  lea     r8, aWil; "wil"
0x140010be5  mov     r9d, eax; char *
0x140010be8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010bed  lea     rcx, [rsp+270h+var_238]
0x140010bf2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140010bf7  jmp     short loc_140010C18
0x140010bf9  mov     rcx, [rsp+270h+var_230]
0x140010bfe  test    rcx, rcx
0x140010c01  jz      short loc_140010C48
0x140010c03  mov     [rdi], rcx
0x140010c06  mov     eax, [rcx]
0x140010c08  inc     eax
0x140010c0a  mov     [rcx], eax
0x140010c0c  lea     rcx, [rsp+270h+var_238]
0x140010c11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140010c16  xor     ebx, ebx
0x140010c18  lea     rcx, [rsp+270h+var_240]
0x140010c1d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140010c22  mov     eax, ebx
0x140010c24  mov     rcx, [rbp+170h+var_10]
0x140010c2b  xor     rcx, rsp; StackCookie
0x140010c2e  call    __security_check_cookie
0x140010c33  lea     r11, [rsp+270h+var_s0]
0x140010c3b  mov     rbx, [r11+20h]
0x140010c3f  mov     rdi, [r11+28h]
0x140010c43  mov     rsp, r11
0x140010c46  pop     rbp
0x140010c47  retn
0x140010c48  mov     r8, rdi
0x140010c4b  lea     rdx, [rsp+270h+var_240]
0x140010c50  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140010c55  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140010c5a  mov     ebx, eax
0x140010c5c  test    eax, eax
0x140010c5e  jns     short loc_140010C0C
0x140010c60  mov     edx, 137h
0x140010c65  jmp     loc_140010BD7
```
