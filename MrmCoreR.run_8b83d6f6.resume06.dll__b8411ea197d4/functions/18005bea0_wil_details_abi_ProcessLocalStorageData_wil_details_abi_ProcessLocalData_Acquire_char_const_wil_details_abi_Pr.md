# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18005bea0`
- end: `0x18005c0c8`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180072828`

## callees

- `0x18002c8d0`
- `0x18002eb8c`
- `0x18005ba04`
- `0x18005bea0`
- `0x18005c160`
- `0x18005c224`
- `0x18005c680`
- `0x18005c720`
- `0x18005cb08`
- `0x18005e01c`
- `0x1800862f0`
- `0x1800897a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005bf20`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005bf20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005bf72`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005bf72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005bedb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005bedb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rdi
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rbx
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  _DWORD *v16; // rcx
  void *v17; // rdx
  void *v18; // rdx
  int v19; // eax
  unsigned int v20; // edi
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = (wil::details *)hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v24, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v22);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v17);
    wil::details::CloseHandle(v6, v17);
    return v15;
  }
  else
  {
    v16 = (_DWORD *)(4 * v24);
    if ( 4 * v24 )
    {
      *a2 = v16;
      ++*v16;
LABEL_8:
      if ( v12 )
        wil::details::ReleaseMutex(v12, v14);
      if ( v6 )
        wil::details::CloseHandle(v6, v14);
      return 0;
    }
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v20 = v19;
    if ( v19 >= 0 )
    {
      v6 = (wil::details *)hHandle;
      goto LABEL_8;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v19, 120);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v18);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return v20;
  }
}

```

## disassembly

```asm
0x18005bea0  mov     [rsp-8+arg_10], rbx
0x18005bea5  mov     [rsp-8+arg_18], rsi
0x18005beaa  push    rbp
0x18005beab  push    rdi
0x18005beac  push    r14
0x18005beae  lea     rbp, [rsp-160h]
0x18005beb6  sub     rsp, 260h
0x18005bebd  mov     rax, cs:__security_cookie
0x18005bec4  xor     rax, rsp
0x18005bec7  mov     [rbp+170h+var_20], rax
0x18005bece  mov     r14, rdx
0x18005bed1  mov     qword ptr [rdx], 0
0x18005bed8  mov     rbx, rcx
0x18005bedb  call    cs:__imp_GetCurrentProcessId
0x18005bee1  mov     [rsp+270h+var_248], rbx
0x18005bee6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18005beed  mov     r9d, eax
0x18005bef0  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18005bef8  mov     edx, 104h; unsigned __int64
0x18005befd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005bf02  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005bf07  mov     r9d, 1F0001h; dwDesiredAccess
0x18005bf0d  mov     [rsp+270h+hHandle], 0
0x18005bf16  xor     r8d, r8d; dwFlags
0x18005bf19  lea     rdx, [rsp+270h+Name]; lpName
0x18005bf1e  xor     ecx, ecx; lpMutexAttributes
0x18005bf20  call    cs:__imp_CreateMutexExW
0x18005bf26  mov     rdx, rax
0x18005bf29  lea     rcx, [rsp+270h+hHandle]
0x18005bf2e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005bf33  mov     rdi, [rsp+270h+hHandle]
0x18005bf38  test    rdi, rdi
0x18005bf3b  jnz     short loc_18005BF69
0x18005bf3d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005bf42  mov     rcx, [rbp+170h+var_20]
0x18005bf49  xor     rcx, rsp; StackCookie
0x18005bf4c  call    __security_check_cookie
0x18005bf51  lea     r11, [rsp+270h+var_10]
0x18005bf59  mov     rbx, [r11+30h]
0x18005bf5d  mov     rsi, [r11+38h]
0x18005bf61  mov     rsp, r11
0x18005bf64  pop     r14
0x18005bf66  pop     rdi
0x18005bf67  pop     rbp
0x18005bf68  retn
0x18005bf69  xor     r8d, r8d; bAlertable
0x18005bf6c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005bf6f  mov     rcx, rdi; hHandle
0x18005bf72  call    cs:__imp_WaitForSingleObjectEx
0x18005bf78  cmp     eax, 102h
0x18005bf7d  jnz     short loc_18005BFD7
0x18005bf7f  xor     ebx, ebx
0x18005bf81  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18005bf86  mov     [rsp+270h+var_238], 0
0x18005bf8f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005bf94  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18005bf99  mov     esi, eax
0x18005bf9b  test    eax, eax
0x18005bf9d  js      short loc_18005BFF1
0x18005bf9f  mov     rax, [rsp+270h+var_238]
0x18005bfa4  lea     rcx, ds:0[rax*4]
0x18005bfac  test    rcx, rcx
0x18005bfaf  jz      loc_18005C0A6
0x18005bfb5  mov     [r14], rcx
0x18005bfb8  mov     eax, [rcx]
0x18005bfba  inc     eax
0x18005bfbc  mov     [rcx], eax
0x18005bfbe  test    rbx, rbx
0x18005bfc1  jnz     short loc_18005BFE7
0x18005bfc3  test    rdi, rdi
0x18005bfc6  jz      short loc_18005BFD0
0x18005bfc8  mov     rcx, rdi; this
0x18005bfcb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005bfd0  xor     eax, eax
0x18005bfd2  jmp     loc_18005BF42
0x18005bfd7  test    eax, 0FFFFFF7Fh
0x18005bfdc  jnz     loc_18005C099
0x18005bfe2  mov     rbx, rdi
0x18005bfe5  jmp     short loc_18005BF81
0x18005bfe7  mov     rcx, rbx; this
0x18005bfea  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18005bfef  jmp     short loc_18005BFC3
0x18005bff1  mov     rcx, [rbp+178h]; this
0x18005bff8  lea     r8, aWil; "wil"
0x18005bfff  mov     r9d, esi; char *
0x18005c002  mov     edx, 66h ; 'f'; void *
0x18005c007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c00c  mov     rcx, [rbp+178h]; this
0x18005c013  lea     r8, aWil; "wil"
0x18005c01a  mov     r9d, esi; char *
0x18005c01d  mov     edx, 6Fh ; 'o'; void *
0x18005c022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c027  mov     rcx, [rbp+178h]; this
0x18005c02e  lea     r8, aWil; "wil"
0x18005c035  mov     r9d, esi; char *
0x18005c038  mov     edx, 12Eh; void *
0x18005c03d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c042  test    rbx, rbx
0x18005c045  jnz     short loc_18005C056
0x18005c047  mov     rcx, rdi; this
0x18005c04a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005c04f  mov     eax, esi
0x18005c051  jmp     loc_18005BF42
0x18005c056  mov     rcx, rbx; this
0x18005c059  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18005c05e  jmp     short loc_18005C047
0x18005c060  mov     rcx, [rbp+178h]; this
0x18005c067  lea     r8, aWil; "wil"
0x18005c06e  mov     r9d, edi; char *
0x18005c071  mov     edx, 137h; void *
0x18005c076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c07b  test    rbx, rbx
0x18005c07e  jz      short loc_18005C088
0x18005c080  mov     rcx, rbx; this
0x18005c083  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18005c088  lea     rcx, [rsp+270h+hHandle]
0x18005c08d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005c092  mov     eax, edi
0x18005c094  jmp     loc_18005BF42
0x18005c099  mov     rcx, [rbp+178h]; this
0x18005c0a0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18005c0a6  mov     r8, r14
0x18005c0a9  lea     rdx, [rsp+270h+hHandle]
0x18005c0ae  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005c0b3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005c0b8  mov     edi, eax
0x18005c0ba  test    eax, eax
0x18005c0bc  js      short loc_18005C060
0x18005c0be  mov     rdi, [rsp+270h+hHandle]
0x18005c0c3  jmp     loc_18005BFBE
```
