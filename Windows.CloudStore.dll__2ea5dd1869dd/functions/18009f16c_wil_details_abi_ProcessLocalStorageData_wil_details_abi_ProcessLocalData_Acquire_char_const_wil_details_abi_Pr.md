# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18009f16c`
- end: `0x18009f36d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180047ad4`

## callees

- `0x180043e44`
- `0x180043fd8`
- `0x1800440c4`
- `0x18004436c`
- `0x1800443f8`
- `0x180044840`
- `0x18009f16c`
- `0x1800c8458`
- `0x1800d1d50`
- `0x1800ede94`
- `0x1801201a0`
- `0x1801264fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009f1a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009f1a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18009f209`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18009f209`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009f1e3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009f1e3`

## string_xrefs

- `0x18009f224`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rsi
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rbx
  int ValueInternal; // eax
  unsigned int v13; // edi
  void *v14; // rdx
  _DWORD *v15; // rcx
  int v16; // eax
  unsigned int v17; // ebx
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
    return wil::details::GetLastErrorFailHr(v5);
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v10);
    v11 = v6;
  }
  v22[0] = v11;
  v21 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v21, (bool *)v10);
  v13 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v15 = (_DWORD *)(4 * v21);
    if ( 4 * v21 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v16,
          120);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
        return v17;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x66,
    (unsigned int)"wil",
    (const char *)(unsigned int)ValueInternal,
    120);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v13, v18);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v13, v19);
  if ( v11 )
    wil::details::ReleaseMutex(v11, v14);
  wil::details::CloseHandle(v6, v14);
  return v13;
}

```

## disassembly

```asm
0x18009f16c  mov     [rsp-8+arg_10], rbx
0x18009f171  mov     [rsp-8+arg_18], rsi
0x18009f176  push    rbp
0x18009f177  push    rdi
0x18009f178  push    r14
0x18009f17a  lea     rbp, [rsp-170h]
0x18009f182  sub     rsp, 270h
0x18009f189  mov     rax, cs:__security_cookie
0x18009f190  xor     rax, rsp
0x18009f193  mov     [rbp+180h+var_20], rax
0x18009f19a  mov     r14, rdx
0x18009f19d  mov     qword ptr [rdx], 0
0x18009f1a4  mov     rbx, rcx
0x18009f1a7  call    cs:__imp_GetCurrentProcessId
0x18009f1ad  mov     [rsp+280h+var_258], rbx
0x18009f1b2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18009f1b9  mov     r9d, eax
0x18009f1bc  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x18009f1c4  mov     edx, 104h; unsigned __int64
0x18009f1c9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18009f1ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009f1d3  mov     r9d, 1F0001h; dwDesiredAccess
0x18009f1d9  lea     rdx, [rsp+280h+Name]; lpName
0x18009f1de  xor     r8d, r8d; dwFlags
0x18009f1e1  xor     ecx, ecx; lpMutexAttributes
0x18009f1e3  call    cs:__imp_CreateMutexExW
0x18009f1e9  mov     [rsp+280h+var_250], rax
0x18009f1ee  mov     rsi, rax
0x18009f1f1  test    rax, rax
0x18009f1f4  jnz     short loc_18009F200
0x18009f1f6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18009f1fb  jmp     loc_18009F2FB
0x18009f200  xor     r8d, r8d; bAlertable
0x18009f203  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009f206  mov     rcx, rsi; hHandle
0x18009f209  call    cs:__imp_WaitForSingleObjectEx
0x18009f20f  cmp     eax, 102h
0x18009f214  jz      short loc_18009F23B
0x18009f216  test    eax, 0FFFFFF7Fh
0x18009f21b  jz      short loc_18009F236
0x18009f21d  mov     rcx, [rbp+188h]; this
0x18009f224  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009f22b  mov     edx, 0E01h; void *
0x18009f230  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18009f236  mov     rbx, rsi
0x18009f239  jmp     short loc_18009F23D
0x18009f23b  xor     ebx, ebx
0x18009f23d  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18009f242  mov     [rsp+280h+var_240], rbx
0x18009f247  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18009f24c  mov     [rsp+280h+var_248], 0
0x18009f255  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18009f25a  mov     edi, eax
0x18009f25c  test    eax, eax
0x18009f25e  jns     short loc_18009F2CA
0x18009f260  mov     rcx, [rbp+188h]; this
0x18009f267  lea     r8, aWil; "wil"
0x18009f26e  mov     r9d, eax; char *
0x18009f271  mov     edx, 66h ; 'f'; void *
0x18009f276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f27b  mov     rcx, [rbp+188h]; this
0x18009f282  lea     r8, aWil; "wil"
0x18009f289  mov     r9d, edi; char *
0x18009f28c  mov     edx, 6Fh ; 'o'; void *
0x18009f291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f296  mov     rcx, [rbp+188h]; this
0x18009f29d  lea     r8, aWil; "wil"
0x18009f2a4  mov     r9d, edi; char *
0x18009f2a7  mov     edx, 12Eh; void *
0x18009f2ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f2b1  test    rbx, rbx
0x18009f2b4  jz      short loc_18009F2BE
0x18009f2b6  mov     rcx, rbx; this
0x18009f2b9  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18009f2be  mov     rcx, rsi; this
0x18009f2c1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18009f2c6  mov     eax, edi
0x18009f2c8  jmp     short loc_18009F2FB
0x18009f2ca  mov     rax, [rsp+280h+var_248]
0x18009f2cf  lea     rcx, ds:0[rax*4]
0x18009f2d7  test    rcx, rcx
0x18009f2da  jz      short loc_18009F322
0x18009f2dc  mov     [r14], rcx
0x18009f2df  mov     eax, [rcx]
0x18009f2e1  inc     eax
0x18009f2e3  mov     [rcx], eax
0x18009f2e5  lea     rcx, [rsp+280h+var_240]
0x18009f2ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f2ef  lea     rcx, [rsp+280h+var_250]
0x18009f2f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f2f9  xor     eax, eax
0x18009f2fb  mov     rcx, [rbp+180h+var_20]
0x18009f302  xor     rcx, rsp; StackCookie
0x18009f305  call    __security_check_cookie
0x18009f30a  lea     r11, [rsp+280h+var_10]
0x18009f312  mov     rbx, [r11+30h]
0x18009f316  mov     rsi, [r11+38h]
0x18009f31a  mov     rsp, r11
0x18009f31d  pop     r14
0x18009f31f  pop     rdi
0x18009f320  pop     rbp
0x18009f321  retn
0x18009f322  mov     r8, r14
0x18009f325  lea     rdx, [rsp+280h+var_250]
0x18009f32a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18009f32f  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18009f334  mov     ebx, eax
0x18009f336  test    eax, eax
0x18009f338  jns     short loc_18009F2E5
0x18009f33a  mov     rcx, [rbp+188h]; this
0x18009f341  lea     r8, aWil; "wil"
0x18009f348  mov     r9d, eax; char *
0x18009f34b  mov     edx, 137h; void *
0x18009f350  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f355  lea     rcx, [rsp+280h+var_240]
0x18009f35a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f35f  lea     rcx, [rsp+280h+var_250]
0x18009f364  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f369  mov     eax, ebx
0x18009f36b  jmp     short loc_18009F2FB
```
