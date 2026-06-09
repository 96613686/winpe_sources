# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800a66a4`
- end: `0x1800a684e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800a6c70`

## callees

- `0x180003180`
- `0x1800a4c74`
- `0x1800a4f38`
- `0x1800a65b0`
- `0x1800a65cc`
- `0x1800a66a4`
- `0x1800a6b84`
- `0x1800a6f5c`
- `0x1800a765c`
- `0x1800a7bcc`
- `0x1800a7c78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800a6721`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800a6721`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a66dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a66dc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800a66a4  mov     [rsp-8+arg_10], rbx
0x1800a66a9  mov     [rsp-8+arg_18], rdi
0x1800a66ae  push    rbp
0x1800a66af  lea     rbp, [rsp-170h]
0x1800a66b7  sub     rsp, 270h
0x1800a66be  mov     rax, cs:__security_cookie
0x1800a66c5  xor     rax, rsp
0x1800a66c8  mov     [rbp+170h+var_10], rax
0x1800a66cf  mov     rdi, rdx
0x1800a66d2  mov     qword ptr [rdx], 0
0x1800a66d9  mov     rbx, rcx
0x1800a66dc  call    cs:__imp_GetCurrentProcessId
0x1800a66e2  mov     [rsp+270h+var_248], rbx
0x1800a66e7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800a66ee  mov     r9d, eax
0x1800a66f1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800a66f9  mov     edx, 104h; unsigned __int64
0x1800a66fe  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800a6703  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a6708  mov     r9d, 1F0001h; dwDesiredAccess
0x1800a670e  mov     [rsp+270h+var_240], 0
0x1800a6717  xor     r8d, r8d; dwFlags
0x1800a671a  lea     rdx, [rsp+270h+Name]; lpName
0x1800a671f  xor     ecx, ecx; lpMutexAttributes
0x1800a6721  call    cs:__imp_CreateMutexExW
0x1800a6727  mov     rdx, rax
0x1800a672a  lea     rcx, [rsp+270h+var_240]
0x1800a672f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800a6734  cmp     [rsp+270h+var_240], 0
0x1800a673a  jnz     short loc_1800A6748
0x1800a673c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a6741  mov     ebx, eax
0x1800a6743  jmp     loc_1800A67F9
0x1800a6748  lea     rdx, [rsp+270h+var_238]
0x1800a674d  lea     rcx, [rsp+270h+var_240]
0x1800a6752  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800a6757  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800a675c  mov     [rsp+270h+var_230], 0
0x1800a6765  lea     rcx, [rsp+270h+Name]; pszSrc
0x1800a676a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800a676f  mov     ebx, eax
0x1800a6771  test    eax, eax
0x1800a6773  jns     short loc_1800A67D2
0x1800a6775  mov     rcx, [rbp+178h]; this
0x1800a677c  lea     r8, aWil; "wil"
0x1800a6783  mov     r9d, eax; char *
0x1800a6786  mov     edx, 66h ; 'f'; void *
0x1800a678b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6790  mov     rcx, [rbp+178h]; this
0x1800a6797  lea     r8, aWil; "wil"
0x1800a679e  mov     r9d, ebx; char *
0x1800a67a1  mov     edx, 6Fh ; 'o'; void *
0x1800a67a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a67ab  mov     r9d, ebx; char *
0x1800a67ae  mov     edx, 12Eh; void *
0x1800a67b3  mov     rcx, [rbp+178h]; this
0x1800a67ba  lea     r8, aWil; "wil"
0x1800a67c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a67c6  lea     rcx, [rsp+270h+var_238]
0x1800a67cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a67d0  jmp     short loc_1800A67F9
0x1800a67d2  mov     rax, [rsp+270h+var_230]
0x1800a67d7  lea     rcx, ds:0[rax*4]
0x1800a67df  test    rcx, rcx
0x1800a67e2  jz      short loc_1800A6829
0x1800a67e4  mov     [rdi], rcx
0x1800a67e7  mov     eax, [rcx]
0x1800a67e9  inc     eax
0x1800a67eb  mov     [rcx], eax
0x1800a67ed  lea     rcx, [rsp+270h+var_238]
0x1800a67f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a67f7  xor     ebx, ebx
0x1800a67f9  lea     rcx, [rsp+270h+var_240]
0x1800a67fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a6803  mov     eax, ebx
0x1800a6805  mov     rcx, [rbp+170h+var_10]
0x1800a680c  xor     rcx, rsp; StackCookie
0x1800a680f  call    __security_check_cookie
0x1800a6814  lea     r11, [rsp+270h+var_s0]
0x1800a681c  mov     rbx, [r11+20h]
0x1800a6820  mov     rdi, [r11+28h]
0x1800a6824  mov     rsp, r11
0x1800a6827  pop     rbp
0x1800a6828  retn
0x1800a6829  mov     r8, rdi
0x1800a682c  lea     rdx, [rsp+270h+var_240]
0x1800a6831  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800a6836  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800a683b  mov     ebx, eax
0x1800a683d  test    eax, eax
0x1800a683f  jns     short loc_1800A67ED
0x1800a6841  mov     r9d, eax
0x1800a6844  mov     edx, 137h
0x1800a6849  jmp     loc_1800A67B3
```
