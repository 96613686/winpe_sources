# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180035bcc`
- end: `0x180035dd1`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180067454`

## callees

- `0x180035bcc`
- `0x180035dd8`
- `0x180035e6c`
- `0x18004a904`
- `0x18004a920`
- `0x18004aa2c`
- `0x180054cec`
- `0x180061320`
- `0x180066290`
- `0x180066888`
- `0x180067cd0`
- `0x180068a20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035c07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035c07`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180035c6b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180035c6b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180035c43`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180035c43`

## string_xrefs

- `0x180035c86`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  wil::details *v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v20 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v22[0] = v11;
  v21 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v21, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v18);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    LastErrorFailHr = v14;
    goto LABEL_14;
  }
  v15 = (_DWORD *)(4 * v21);
  if ( 4 * v21 )
  {
    *a2 = v15;
    ++*v15;
  }
  else
  {
    v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    LastErrorFailHr = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v16,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
      goto LABEL_14;
    }
    v6 = v20;
  }
  if ( v11 )
    wil::details::ReleaseMutex(v11, v13);
  if ( v6 )
    wil::details::CloseHandle(v6, v13);
  return 0;
}

```

## disassembly

```asm
0x180035bcc  mov     [rsp-8+arg_10], rbx
0x180035bd1  mov     [rsp-8+arg_18], rsi
0x180035bd6  push    rbp
0x180035bd7  push    rdi
0x180035bd8  push    r14
0x180035bda  lea     rbp, [rsp-170h]
0x180035be2  sub     rsp, 270h
0x180035be9  mov     rax, cs:__security_cookie
0x180035bf0  xor     rax, rsp
0x180035bf3  mov     [rbp+180h+var_20], rax
0x180035bfa  mov     r14, rdx
0x180035bfd  mov     qword ptr [rdx], 0
0x180035c04  mov     rbx, rcx
0x180035c07  call    cs:__imp_GetCurrentProcessId
0x180035c0d  mov     [rsp+280h+var_258], rbx
0x180035c12  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180035c19  mov     r9d, eax
0x180035c1c  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180035c24  mov     edx, 104h; unsigned __int64
0x180035c29  lea     rcx, [rsp+280h+Name]; Buffer
0x180035c2e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035c33  mov     r9d, 1F0001h; dwDesiredAccess
0x180035c39  lea     rdx, [rsp+280h+Name]; lpName
0x180035c3e  xor     r8d, r8d; dwFlags
0x180035c41  xor     ecx, ecx; lpMutexAttributes
0x180035c43  call    cs:__imp_CreateMutexExW
0x180035c49  mov     [rsp+280h+var_250], rax
0x180035c4e  mov     rbx, rax
0x180035c51  test    rax, rax
0x180035c54  jnz     short loc_180035C62
0x180035c56  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180035c5b  mov     ebx, eax
0x180035c5d  jmp     loc_180035D7B
0x180035c62  xor     r8d, r8d; bAlertable
0x180035c65  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035c68  mov     rcx, rbx; hHandle
0x180035c6b  call    cs:__imp_WaitForSingleObjectEx
0x180035c71  cmp     eax, 102h
0x180035c76  jz      short loc_180035C9D
0x180035c78  test    eax, 0FFFFFF7Fh
0x180035c7d  jz      short loc_180035C98
0x180035c7f  mov     rcx, [rbp+188h]; this
0x180035c86  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035c8d  mov     edx, 0E01h; void *
0x180035c92  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180035c98  mov     rdi, rbx
0x180035c9b  jmp     short loc_180035C9F
0x180035c9d  xor     edi, edi
0x180035c9f  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180035ca4  mov     [rsp+280h+var_240], rdi
0x180035ca9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180035cae  mov     [rsp+280h+var_248], 0
0x180035cb7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180035cbc  mov     esi, eax
0x180035cbe  test    eax, eax
0x180035cc0  jns     short loc_180035D21
0x180035cc2  mov     rcx, [rbp+188h]; this
0x180035cc9  lea     r8, aWil; "wil"
0x180035cd0  mov     r9d, eax; char *
0x180035cd3  mov     edx, 66h ; 'f'; void *
0x180035cd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035cdd  mov     rcx, [rbp+188h]; this
0x180035ce4  lea     r8, aWil; "wil"
0x180035ceb  mov     r9d, esi; char *
0x180035cee  mov     edx, 6Fh ; 'o'; void *
0x180035cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035cf8  mov     rcx, [rbp+188h]; this
0x180035cff  lea     r8, aWil; "wil"
0x180035d06  mov     r9d, esi; char *
0x180035d09  mov     edx, 12Eh; void *
0x180035d0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d13  lea     rcx, [rsp+280h+var_240]
0x180035d18  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035d1d  mov     ebx, esi
0x180035d1f  jmp     short loc_180035D7B
0x180035d21  mov     rax, [rsp+280h+var_248]
0x180035d26  lea     rcx, ds:0[rax*4]
0x180035d2e  test    rcx, rcx
0x180035d31  jz      short loc_180035D3E
0x180035d33  mov     [r14], rcx
0x180035d36  mov     eax, [rcx]
0x180035d38  inc     eax
0x180035d3a  mov     [rcx], eax
0x180035d3c  jmp     short loc_180035D8E
0x180035d3e  mov     r8, r14
0x180035d41  lea     rdx, [rsp+280h+var_250]
0x180035d46  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180035d4b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180035d50  mov     ebx, eax
0x180035d52  test    eax, eax
0x180035d54  jns     short loc_180035D89
0x180035d56  mov     rcx, [rbp+188h]; this
0x180035d5d  lea     r8, aWil; "wil"
0x180035d64  mov     r9d, eax; char *
0x180035d67  mov     edx, 137h; void *
0x180035d6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d71  lea     rcx, [rsp+280h+var_240]
0x180035d76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035d7b  lea     rcx, [rsp+280h+var_250]
0x180035d80  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035d85  mov     eax, ebx
0x180035d87  jmp     short loc_180035DAA
0x180035d89  mov     rbx, [rsp+280h+var_250]
0x180035d8e  test    rdi, rdi
0x180035d91  jz      short loc_180035D9B
0x180035d93  mov     rcx, rdi; this
0x180035d96  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180035d9b  test    rbx, rbx
0x180035d9e  jz      short loc_180035DA8
0x180035da0  mov     rcx, rbx; this
0x180035da3  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180035da8  xor     eax, eax
0x180035daa  mov     rcx, [rbp+180h+var_20]
0x180035db1  xor     rcx, rsp; StackCookie
0x180035db4  call    __security_check_cookie
0x180035db9  lea     r11, [rsp+280h+var_10]
0x180035dc1  mov     rbx, [r11+30h]
0x180035dc5  mov     rsi, [r11+38h]
0x180035dc9  mov     rsp, r11
0x180035dcc  pop     r14
0x180035dce  pop     rdi
0x180035dcf  pop     rbp
0x180035dd0  retn
```
