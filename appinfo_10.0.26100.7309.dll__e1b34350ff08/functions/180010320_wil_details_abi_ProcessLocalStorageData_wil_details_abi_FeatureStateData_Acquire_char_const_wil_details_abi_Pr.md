# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180010320`
- end: `0x180010533`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1800138fc`

## callees

- `0x180007c78`
- `0x180010320`
- `0x18001053c`
- `0x180017fa0`
- `0x1800186c0`
- `0x18001b2a8`
- `0x18001ef78`
- `0x1800203dc`
- `0x180021208`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800103bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800103bc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001038e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001038e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001034c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001034c`

## string_xrefs

- `0x1800103de`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbp
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rbx
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  void *v15; // rdx
  _DWORD *v16; // rax
  int v17; // eax
  unsigned int v18; // edi
  void *v19; // rdx
  int v20; // [rsp+20h] [rbp-258h]
  int v21; // [rsp+20h] [rbp-258h]
  wil::details *v22; // [rsp+30h] [rbp-248h]
  unsigned __int64 v23; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
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
        (void *)0xC37,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v23, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)v14, v20);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, (unsigned int)"wil", (const char *)v14, v21);
    if ( v11 )
      wil::details::ReleaseMutex(v11, v15);
    wil::details::CloseHandle(v6, v15);
    return v14;
  }
  v16 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v16;
    *(_DWORD *)*a2 = *v16 + 1;
LABEL_14:
    if ( v11 )
      wil::details::ReleaseMutex(v11, v13);
    if ( v22 )
      wil::details::CloseHandle(v22, v13);
    return 0;
  }
  v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  v18 = v17;
  if ( v17 >= 0 )
    goto LABEL_14;
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, (unsigned int)"wil", (const char *)(unsigned int)v17, 304);
  if ( v11 )
    wil::details::ReleaseMutex(v11, v19);
  if ( v22 )
    wil::details::CloseHandle(v22, v19);
  return v18;
}

```

## disassembly

```asm
0x180010320  mov     [rsp+arg_10], rbx
0x180010325  push    rbp
0x180010326  push    rsi
0x180010327  push    rdi
0x180010328  sub     rsp, 260h
0x18001032f  mov     rax, cs:__security_cookie
0x180010336  xor     rax, rsp
0x180010339  mov     [rsp+278h+var_28], rax
0x180010341  xor     esi, esi
0x180010343  mov     rdi, rdx
0x180010346  mov     [rdx], rsi
0x180010349  mov     rbx, rcx
0x18001034c  call    cs:__imp_GetCurrentProcessId
0x180010353  nop     dword ptr [rax+rax+00h]
0x180010358  mov     [rsp+278h+var_250], rbx
0x18001035d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010364  mov     r9d, eax
0x180010367  mov     [rsp+278h+var_258], 130h; int
0x18001036f  mov     edx, 104h; unsigned __int64
0x180010374  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180010379  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001037e  mov     r9d, 1F0001h; dwDesiredAccess
0x180010384  lea     rdx, [rsp+278h+Name]; lpName
0x180010389  xor     r8d, r8d; dwFlags
0x18001038c  xor     ecx, ecx; lpMutexAttributes
0x18001038e  call    cs:__imp_CreateMutexExW
0x180010395  nop     dword ptr [rax+rax+00h]
0x18001039a  mov     [rsp+278h+var_248], rax
0x18001039f  mov     rbp, rax
0x1800103a2  test    rax, rax
0x1800103a5  jnz     short loc_1800103B1
0x1800103a7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800103ac  jmp     loc_1800104BB
0x1800103b1  xor     r8d, r8d; bAlertable
0x1800103b4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800103b9  mov     rcx, rbp; hHandle
0x1800103bc  call    cs:__imp_WaitForSingleObjectEx
0x1800103c3  nop     dword ptr [rax+rax+00h]
0x1800103c8  cmp     eax, 102h
0x1800103cd  jz      short loc_1800103F5
0x1800103cf  test    eax, 0FFFFFF7Fh
0x1800103d4  jz      short loc_1800103F0
0x1800103d6  mov     rcx, [rsp+278h]; this
0x1800103de  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800103e5  mov     edx, 0C37h; void *
0x1800103ea  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800103f0  mov     rbx, rbp
0x1800103f3  jmp     short loc_1800103F8
0x1800103f5  mov     rbx, rsi
0x1800103f8  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x1800103fd  mov     [rsp+278h+var_240], rsi
0x180010402  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180010407  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001040c  mov     esi, eax
0x18001040e  test    eax, eax
0x180010410  jns     short loc_18001047F
0x180010412  mov     rcx, [rsp+278h]; this
0x18001041a  lea     r8, aWil; "wil"
0x180010421  mov     r9d, eax; char *
0x180010424  mov     edx, 64h ; 'd'; void *
0x180010429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001042e  mov     rcx, [rsp+278h]; this
0x180010436  lea     r8, aWil; "wil"
0x18001043d  mov     r9d, esi; char *
0x180010440  mov     edx, 6Dh ; 'm'; void *
0x180010445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001044a  mov     rcx, [rsp+278h]; this
0x180010452  lea     r8, aWil; "wil"
0x180010459  mov     r9d, esi; char *
0x18001045c  mov     edx, 12Bh; void *
0x180010461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010466  test    rbx, rbx
0x180010469  jz      short loc_180010473
0x18001046b  mov     rcx, rbx; this
0x18001046e  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180010473  mov     rcx, rbp; this
0x180010476  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001047b  mov     eax, esi
0x18001047d  jmp     short loc_1800104BB
0x18001047f  mov     rax, [rsp+278h+var_240]
0x180010484  lea     rax, ds:0[rax*4]
0x18001048c  test    rax, rax
0x18001048f  jz      short loc_1800104DF
0x180010491  mov     [rdi], rax
0x180010494  mov     ecx, [rax]
0x180010496  mov     rax, [rdi]
0x180010499  inc     ecx
0x18001049b  mov     [rax], ecx
0x18001049d  test    rbx, rbx
0x1800104a0  jz      short loc_1800104AA
0x1800104a2  mov     rcx, rbx; this
0x1800104a5  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800104aa  mov     rcx, [rsp+278h+var_248]; this
0x1800104af  test    rcx, rcx
0x1800104b2  jz      short loc_1800104B9
0x1800104b4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800104b9  xor     eax, eax
0x1800104bb  mov     rcx, [rsp+278h+var_28]
0x1800104c3  xor     rcx, rsp; StackCookie
0x1800104c6  call    __security_check_cookie
0x1800104cb  mov     rbx, [rsp+278h+arg_10]
0x1800104d3  add     rsp, 260h
0x1800104da  pop     rdi
0x1800104db  pop     rsi
0x1800104dc  pop     rbp
0x1800104dd  retn
0x1800104df  mov     r8, rdi
0x1800104e2  lea     rdx, [rsp+278h+var_248]
0x1800104e7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800104ec  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800104f1  mov     edi, eax
0x1800104f3  test    eax, eax
0x1800104f5  jns     short loc_18001049D
0x1800104f7  mov     rcx, [rsp+278h]; this
0x1800104ff  lea     r8, aWil; "wil"
0x180010506  mov     r9d, eax; char *
0x180010509  mov     edx, 134h; void *
0x18001050e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010513  test    rbx, rbx
0x180010516  jz      short loc_180010520
0x180010518  mov     rcx, rbx; this
0x18001051b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180010520  mov     rcx, [rsp+278h+var_248]; this
0x180010525  test    rcx, rcx
0x180010528  jz      short loc_18001052F
0x18001052a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001052f  mov     eax, edi
0x180010531  jmp     short loc_1800104BB
```
