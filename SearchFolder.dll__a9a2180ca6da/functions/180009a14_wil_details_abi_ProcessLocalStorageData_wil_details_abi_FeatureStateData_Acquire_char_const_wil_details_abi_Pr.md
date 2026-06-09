# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009a14`
- end: `0x180009b7a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a194`

## callees

- `0x1800033d0`
- `0x180006900`
- `0x180009484`
- `0x1800094a0`
- `0x180009a14`
- `0x18000b6b8`
- `0x18000c494`
- `0x18000eec0`
- `0x18000f4dc`
- `0x18000ff4c`
- `0x180010230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009a91`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009a91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a4c`

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
0x180009a14  mov     [rsp-8+arg_10], rbx
0x180009a19  mov     [rsp-8+arg_18], rdi
0x180009a1e  push    rbp
0x180009a1f  lea     rbp, [rsp-170h]
0x180009a27  sub     rsp, 270h
0x180009a2e  mov     rax, cs:__security_cookie
0x180009a35  xor     rax, rsp
0x180009a38  mov     [rbp+170h+var_10], rax
0x180009a3f  mov     rdi, rdx
0x180009a42  mov     qword ptr [rdx], 0
0x180009a49  mov     rbx, rcx
0x180009a4c  call    cs:__imp_GetCurrentProcessId
0x180009a52  mov     [rsp+270h+var_248], rbx
0x180009a57  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009a5e  mov     r9d, eax
0x180009a61  mov     [rsp+270h+var_250], 130h; int
0x180009a69  mov     edx, 104h; unsigned __int64
0x180009a6e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009a73  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009a78  mov     r9d, 1F0001h; dwDesiredAccess
0x180009a7e  mov     [rsp+270h+var_240], 0
0x180009a87  xor     r8d, r8d; dwFlags
0x180009a8a  lea     rdx, [rsp+270h+Name]; lpName
0x180009a8f  xor     ecx, ecx; lpMutexAttributes
0x180009a91  call    cs:__imp_CreateMutexExW
0x180009a97  mov     rdx, rax
0x180009a9a  lea     rcx, [rsp+270h+var_240]
0x180009a9f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009aa4  cmp     [rsp+270h+var_240], 0
0x180009aaa  jnz     short loc_180009AB5
0x180009aac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009ab1  mov     ebx, eax
0x180009ab3  jmp     short loc_180009B28
0x180009ab5  lea     rdx, [rsp+270h+var_238]
0x180009aba  lea     rcx, [rsp+270h+var_240]
0x180009abf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180009ac4  lea     rdx, [rsp+270h+var_230]; void **
0x180009ac9  mov     [rsp+270h+var_230], 0
0x180009ad2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009ad7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180009adc  mov     ebx, eax
0x180009ade  test    eax, eax
0x180009ae0  jns     short loc_180009B09
0x180009ae2  mov     edx, 12Eh; void *
0x180009ae7  mov     rcx, [rbp+178h]; this
0x180009aee  lea     r8, aWil; "wil"
0x180009af5  mov     r9d, eax; char *
0x180009af8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009afd  lea     rcx, [rsp+270h+var_238]
0x180009b02  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009b07  jmp     short loc_180009B28
0x180009b09  mov     rcx, [rsp+270h+var_230]
0x180009b0e  test    rcx, rcx
0x180009b11  jz      short loc_180009B58
0x180009b13  mov     [rdi], rcx
0x180009b16  mov     eax, [rcx]
0x180009b18  inc     eax
0x180009b1a  mov     [rcx], eax
0x180009b1c  lea     rcx, [rsp+270h+var_238]
0x180009b21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009b26  xor     ebx, ebx
0x180009b28  lea     rcx, [rsp+270h+var_240]
0x180009b2d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009b32  mov     eax, ebx
0x180009b34  mov     rcx, [rbp+170h+var_10]
0x180009b3b  xor     rcx, rsp; StackCookie
0x180009b3e  call    __security_check_cookie
0x180009b43  lea     r11, [rsp+270h+var_s0]
0x180009b4b  mov     rbx, [r11+20h]
0x180009b4f  mov     rdi, [r11+28h]
0x180009b53  mov     rsp, r11
0x180009b56  pop     rbp
0x180009b57  retn
0x180009b58  mov     r8, rdi
0x180009b5b  lea     rdx, [rsp+270h+var_240]
0x180009b60  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009b65  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009b6a  mov     ebx, eax
0x180009b6c  test    eax, eax
0x180009b6e  jns     short loc_180009B1C
0x180009b70  mov     edx, 137h
0x180009b75  jmp     loc_180009AE7
```
