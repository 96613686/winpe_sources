# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002f5c0`
- end: `0x18002f772`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002f20c`

## callees

- `0x18002f5c0`
- `0x180030294`
- `0x180060bd8`
- `0x1800614e4`
- `0x180061514`
- `0x180061c98`
- `0x180061f80`
- `0x18006ebf0`
- `0x180075e60`
- `0x180082f98`
- `0x180082ff8`
- `0x1800833c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002f657`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002f657`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002f631`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002f631`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002f5f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002f5f5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v6; // rcx
  wil::details *v7; // rbx
  DWORD v9; // eax
  unsigned int v10; // edx
  wil::details::in1diag3 *v11; // rcx
  const char *v12; // r8
  bool *v13; // r9
  int ValueInternal; // eax
  unsigned int v15; // edx
  int v16; // r9d
  unsigned int v17; // edi
  unsigned int v18; // edx
  int v19; // r9d
  unsigned int v20; // edx
  int v21; // r9d
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v24; // edx
  int v25; // r9d
  void *v26; // rdx
  wil::details *v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v29[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v27 = Mutex;
  v7 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v7 = 0;
  }
  else if ( (v9 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(v11, v10, v12);
  }
  v29[0] = v7;
  v28 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v10, &v28, v13);
  v17 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)0x66,
      v15,
      (const char *)(unsigned int)ValueInternal,
      v16);
    wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)0x6F, v18, (const char *)v17, v19);
    wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)0x12E, v20, (const char *)v17, v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
    return v17;
  }
  v22 = (_DWORD *)(4 * v28);
  if ( 4 * v28 )
  {
    *a2 = v22;
    ++*v22;
  }
  else
  {
    v23 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v17 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)0x137, v24, (const char *)(unsigned int)v23, v25);
      if ( v7 )
        wil::details::ReleaseMutex(v7, v26);
      if ( v27 )
        wil::details::CloseHandle(v27, v26);
      return v17;
    }
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
  return 0;
}

```

## disassembly

```asm
0x18002f5c0  mov     [rsp-8+arg_10], rbx
0x18002f5c5  push    rbp
0x18002f5c6  push    rsi
0x18002f5c7  push    rdi
0x18002f5c8  lea     rbp, [rsp-170h]
0x18002f5d0  sub     rsp, 270h
0x18002f5d7  mov     rax, cs:__security_cookie
0x18002f5de  xor     rax, rsp
0x18002f5e1  mov     [rbp+180h+var_20], rax
0x18002f5e8  mov     rsi, rdx
0x18002f5eb  mov     qword ptr [rdx], 0
0x18002f5f2  mov     rbx, rcx
0x18002f5f5  call    cs:__imp_GetCurrentProcessId
0x18002f5fb  mov     [rsp+280h+var_258], rbx
0x18002f600  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002f607  mov     r9d, eax
0x18002f60a  mov     [rsp+280h+var_260], 78h ; 'x'
0x18002f612  mov     edx, 104h; unsigned __int64
0x18002f617  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002f61c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f621  mov     r9d, 1F0001h; dwDesiredAccess
0x18002f627  lea     rdx, [rsp+280h+Name]; lpName
0x18002f62c  xor     r8d, r8d; dwFlags
0x18002f62f  xor     ecx, ecx; lpMutexAttributes
0x18002f631  call    cs:__imp_CreateMutexExW
0x18002f637  mov     [rsp+280h+var_250], rax
0x18002f63c  mov     rbx, rax
0x18002f63f  test    rax, rax
0x18002f642  jnz     short loc_18002F64E
0x18002f644  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002f649  jmp     loc_18002F706
0x18002f64e  xor     r8d, r8d; bAlertable
0x18002f651  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002f654  mov     rcx, rax; hHandle
0x18002f657  call    cs:__imp_WaitForSingleObjectEx
0x18002f65d  cmp     eax, 102h
0x18002f662  jz      short loc_18002F671
0x18002f664  test    eax, 0FFFFFF7Fh
0x18002f669  jz      short loc_18002F673
0x18002f66b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(uint,char const *)
0x18002f671  xor     ebx, ebx
0x18002f673  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18002f678  mov     [rsp+280h+var_240], rbx
0x18002f67d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002f682  mov     [rsp+280h+var_248], 0
0x18002f68b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18002f690  mov     edi, eax
0x18002f692  test    eax, eax
0x18002f694  jns     short loc_18002F6D5
0x18002f696  mov     r8d, eax; char *
0x18002f699  mov     ecx, 66h ; 'f'; this
0x18002f69e  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18002f6a3  mov     r8d, edi; char *
0x18002f6a6  mov     ecx, 6Fh ; 'o'; this
0x18002f6ab  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18002f6b0  mov     r8d, edi; char *
0x18002f6b3  mov     ecx, 12Eh; this
0x18002f6b8  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18002f6bd  lea     rcx, [rsp+280h+var_240]
0x18002f6c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002f6c7  lea     rcx, [rsp+280h+var_250]
0x18002f6cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002f6d1  mov     eax, edi
0x18002f6d3  jmp     short loc_18002F706
0x18002f6d5  mov     rax, [rsp+280h+var_248]
0x18002f6da  lea     rcx, ds:0[rax*4]
0x18002f6e2  test    rcx, rcx
0x18002f6e5  jz      short loc_18002F728
0x18002f6e7  mov     [rsi], rcx
0x18002f6ea  mov     eax, [rcx]
0x18002f6ec  inc     eax
0x18002f6ee  mov     [rcx], eax
0x18002f6f0  lea     rcx, [rsp+280h+var_240]
0x18002f6f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002f6fa  lea     rcx, [rsp+280h+var_250]
0x18002f6ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002f704  xor     eax, eax
0x18002f706  mov     rcx, [rbp+180h+var_20]
0x18002f70d  xor     rcx, rsp; StackCookie
0x18002f710  call    __security_check_cookie
0x18002f715  mov     rbx, [rsp+280h+arg_10]
0x18002f71d  add     rsp, 270h
0x18002f724  pop     rdi
0x18002f725  pop     rsi
0x18002f726  pop     rbp
0x18002f727  retn
0x18002f728  mov     r8, rsi
0x18002f72b  lea     rdx, [rsp+280h+var_250]
0x18002f730  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002f735  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002f73a  mov     edi, eax
0x18002f73c  test    eax, eax
0x18002f73e  jns     short loc_18002F6F0
0x18002f740  mov     r8d, eax; char *
0x18002f743  mov     ecx, 137h; this
0x18002f748  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18002f74d  test    rbx, rbx
0x18002f750  jz      short loc_18002F75A
0x18002f752  mov     rcx, rbx; this
0x18002f755  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18002f75a  mov     rcx, [rsp+280h+var_250]; this
0x18002f75f  test    rcx, rcx
0x18002f762  jz      loc_18002F6D1
0x18002f768  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18002f76d  jmp     loc_18002F6D1
```
