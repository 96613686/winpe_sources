# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18009f0ec`
- end: `0x18009f28e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18009f8f8`

## callees

- `0x180002a00`
- `0x18009ef88`
- `0x18009efa8`
- `0x18009f0ec`
- `0x18009f710`
- `0x18009fc2c`
- `0x1800a01a0`
- `0x1800a07cc`
- `0x1800a08ac`
- `0x1800a0b00`
- `0x1800a0c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009f16f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009f16f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009f124`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009f124`

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
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 301;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 310;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18009f0ec  mov     [rsp-8+arg_10], rbx
0x18009f0f1  mov     [rsp-8+arg_18], rdi
0x18009f0f6  push    rbp
0x18009f0f7  lea     rbp, [rsp-170h]
0x18009f0ff  sub     rsp, 270h
0x18009f106  mov     rax, cs:__security_cookie
0x18009f10d  xor     rax, rsp
0x18009f110  mov     [rbp+170h+var_10], rax
0x18009f117  mov     rdi, rdx
0x18009f11a  mov     qword ptr [rdx], 0
0x18009f121  mov     rbx, rcx
0x18009f124  call    cs:__imp_GetCurrentProcessId
0x18009f12b  nop     dword ptr [rax+rax+00h]
0x18009f130  mov     [rsp+270h+var_248], rbx
0x18009f135  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18009f13c  mov     r9d, eax
0x18009f13f  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18009f147  mov     edx, 104h; unsigned __int64
0x18009f14c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18009f151  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009f156  mov     r9d, 1F0001h; dwDesiredAccess
0x18009f15c  mov     [rsp+270h+var_240], 0
0x18009f165  xor     r8d, r8d; dwFlags
0x18009f168  lea     rdx, [rsp+270h+Name]; lpName
0x18009f16d  xor     ecx, ecx; lpMutexAttributes
0x18009f16f  call    cs:__imp_CreateMutexExW
0x18009f176  nop     dword ptr [rax+rax+00h]
0x18009f17b  mov     rdx, rax
0x18009f17e  lea     rcx, [rsp+270h+var_240]
0x18009f183  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18009f188  cmp     [rsp+270h+var_240], 0
0x18009f18e  jnz     short loc_18009F19C
0x18009f190  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18009f195  mov     ebx, eax
0x18009f197  jmp     loc_18009F238
0x18009f19c  lea     rdx, [rsp+270h+var_238]
0x18009f1a1  lea     rcx, [rsp+270h+var_240]
0x18009f1a6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18009f1ab  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18009f1b0  mov     [rsp+270h+var_230], 0
0x18009f1b9  lea     rcx, [rsp+270h+Name]; pszSrc
0x18009f1be  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18009f1c3  mov     ebx, eax
0x18009f1c5  test    eax, eax
0x18009f1c7  jns     short loc_18009F211
0x18009f1c9  mov     rcx, [rbp+178h]; this
0x18009f1d0  mov     r9d, eax; char *
0x18009f1d3  mov     edx, 66h ; 'f'; void *
0x18009f1d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f1dd  mov     rcx, [rbp+178h]; this
0x18009f1e4  mov     r9d, ebx; char *
0x18009f1e7  mov     edx, 6Fh ; 'o'; void *
0x18009f1ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f1f1  mov     r9d, ebx; char *
0x18009f1f4  mov     edx, 12Dh; void *
0x18009f1f9  mov     rcx, [rbp+178h]; this
0x18009f200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f205  lea     rcx, [rsp+270h+var_238]
0x18009f20a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f20f  jmp     short loc_18009F238
0x18009f211  mov     rax, [rsp+270h+var_230]
0x18009f216  lea     rcx, ds:0[rax*4]
0x18009f21e  test    rcx, rcx
0x18009f221  jz      short loc_18009F269
0x18009f223  mov     [rdi], rcx
0x18009f226  mov     eax, [rcx]
0x18009f228  inc     eax
0x18009f22a  mov     [rcx], eax
0x18009f22c  lea     rcx, [rsp+270h+var_238]
0x18009f231  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f236  xor     ebx, ebx
0x18009f238  lea     rcx, [rsp+270h+var_240]
0x18009f23d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f242  mov     eax, ebx
0x18009f244  mov     rcx, [rbp+170h+var_10]
0x18009f24b  xor     rcx, rsp; StackCookie
0x18009f24e  call    __security_check_cookie
0x18009f253  lea     r11, [rsp+270h+var_s0]
0x18009f25b  mov     rbx, [r11+20h]
0x18009f25f  mov     rdi, [r11+28h]
0x18009f263  mov     rsp, r11
0x18009f266  pop     rbp
0x18009f267  retn
0x18009f269  mov     r8, rdi
0x18009f26c  lea     rdx, [rsp+270h+var_240]
0x18009f271  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18009f276  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18009f27b  mov     ebx, eax
0x18009f27d  test    eax, eax
0x18009f27f  jns     short loc_18009F22C
0x18009f281  mov     r9d, eax
0x18009f284  mov     edx, 136h
0x18009f289  jmp     loc_18009F1F9
```
