# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800101f0`
- end: `0x1800103f7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1800138a4`

## callees

- `0x180007c78`
- `0x1800101f0`
- `0x180010400`
- `0x180017cf0`
- `0x180018410`
- `0x18001aed8`
- `0x18001eb38`
- `0x180021650`
- `0x180022478`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001025e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001025e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001028c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001028c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001021c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001021c`

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
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rbx
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  void *v16; // rdx
  _DWORD *v17; // rax
  int v18; // eax
  unsigned int v19; // edi
  void *v20; // rdx
  int v21; // [rsp+20h] [rbp-258h]
  int v22; // [rsp+20h] [rbp-258h]
  wil::details *v23; // [rsp+30h] [rbp-248h]
  unsigned __int64 v24; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v23 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
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
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (__int64)v9, &v24, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)v15, v21);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, (unsigned int)"wil", (const char *)v15, v22);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v16);
    wil::details::CloseHandle(v6, v16);
    return v15;
  }
  v17 = (_DWORD *)(4 * v24);
  if ( 4 * v24 )
  {
    *a2 = v17;
    *(_DWORD *)*a2 = *v17 + 1;
LABEL_14:
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v23 )
      wil::details::CloseHandle(v23, v14);
    return 0;
  }
  v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  v19 = v18;
  if ( v18 >= 0 )
    goto LABEL_14;
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, (unsigned int)"wil", (const char *)(unsigned int)v18, 304);
  if ( v12 )
    wil::details::ReleaseMutex(v12, v20);
  if ( v23 )
    wil::details::CloseHandle(v23, v20);
  return v19;
}

```

## disassembly

```asm
0x1800101f0  mov     [rsp+arg_10], rbx
0x1800101f5  push    rbp
0x1800101f6  push    rsi
0x1800101f7  push    rdi
0x1800101f8  sub     rsp, 260h
0x1800101ff  mov     rax, cs:__security_cookie
0x180010206  xor     rax, rsp
0x180010209  mov     [rsp+278h+var_28], rax
0x180010211  xor     esi, esi
0x180010213  mov     rdi, rdx
0x180010216  mov     [rdx], rsi
0x180010219  mov     rbx, rcx
0x18001021c  call    cs:__imp_GetCurrentProcessId
0x180010223  nop     dword ptr [rax+rax+00h]
0x180010228  mov     [rsp+278h+var_250], rbx
0x18001022d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010234  mov     r9d, eax
0x180010237  mov     [rsp+278h+var_258], 130h; int
0x18001023f  mov     edx, 104h; unsigned __int64
0x180010244  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180010249  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001024e  mov     r9d, 1F0001h; dwDesiredAccess
0x180010254  lea     rdx, [rsp+278h+Name]; lpName
0x180010259  xor     r8d, r8d; dwFlags
0x18001025c  xor     ecx, ecx; lpMutexAttributes
0x18001025e  call    cs:__imp_CreateMutexExW
0x180010265  nop     dword ptr [rax+rax+00h]
0x18001026a  mov     [rsp+278h+var_248], rax
0x18001026f  mov     rbp, rax
0x180010272  test    rax, rax
0x180010275  jnz     short loc_180010281
0x180010277  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001027c  jmp     loc_18001037F
0x180010281  xor     r8d, r8d; bAlertable
0x180010284  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180010289  mov     rcx, rbp; hHandle
0x18001028c  call    cs:__imp_WaitForSingleObjectEx
0x180010293  nop     dword ptr [rax+rax+00h]
0x180010298  cmp     eax, 102h
0x18001029d  jz      short loc_1800102B9
0x18001029f  test    eax, 0FFFFFF7Fh
0x1800102a4  jz      short loc_1800102B4
0x1800102a6  mov     rcx, [rsp+278h]; this
0x1800102ae  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800102b4  mov     rbx, rbp
0x1800102b7  jmp     short loc_1800102BC
0x1800102b9  mov     rbx, rsi
0x1800102bc  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x1800102c1  mov     [rsp+278h+var_240], rsi
0x1800102c6  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800102cb  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800102d0  mov     esi, eax
0x1800102d2  test    eax, eax
0x1800102d4  jns     short loc_180010343
0x1800102d6  mov     rcx, [rsp+278h]; this
0x1800102de  lea     r8, aWil; "wil"
0x1800102e5  mov     r9d, eax; char *
0x1800102e8  mov     edx, 64h ; 'd'; void *
0x1800102ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102f2  mov     rcx, [rsp+278h]; this
0x1800102fa  lea     r8, aWil; "wil"
0x180010301  mov     r9d, esi; char *
0x180010304  mov     edx, 6Dh ; 'm'; void *
0x180010309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001030e  mov     rcx, [rsp+278h]; this
0x180010316  lea     r8, aWil; "wil"
0x18001031d  mov     r9d, esi; char *
0x180010320  mov     edx, 12Bh; void *
0x180010325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001032a  test    rbx, rbx
0x18001032d  jz      short loc_180010337
0x18001032f  mov     rcx, rbx; this
0x180010332  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180010337  mov     rcx, rbp; this
0x18001033a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001033f  mov     eax, esi
0x180010341  jmp     short loc_18001037F
0x180010343  mov     rax, [rsp+278h+var_240]
0x180010348  lea     rax, ds:0[rax*4]
0x180010350  test    rax, rax
0x180010353  jz      short loc_1800103A3
0x180010355  mov     [rdi], rax
0x180010358  mov     ecx, [rax]
0x18001035a  mov     rax, [rdi]
0x18001035d  inc     ecx
0x18001035f  mov     [rax], ecx
0x180010361  test    rbx, rbx
0x180010364  jz      short loc_18001036E
0x180010366  mov     rcx, rbx; this
0x180010369  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001036e  mov     rcx, [rsp+278h+var_248]; this
0x180010373  test    rcx, rcx
0x180010376  jz      short loc_18001037D
0x180010378  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001037d  xor     eax, eax
0x18001037f  mov     rcx, [rsp+278h+var_28]
0x180010387  xor     rcx, rsp; StackCookie
0x18001038a  call    __security_check_cookie
0x18001038f  mov     rbx, [rsp+278h+arg_10]
0x180010397  add     rsp, 260h
0x18001039e  pop     rdi
0x18001039f  pop     rsi
0x1800103a0  pop     rbp
0x1800103a1  retn
0x1800103a3  mov     r8, rdi
0x1800103a6  lea     rdx, [rsp+278h+var_248]
0x1800103ab  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800103b0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800103b5  mov     edi, eax
0x1800103b7  test    eax, eax
0x1800103b9  jns     short loc_180010361
0x1800103bb  mov     rcx, [rsp+278h]; this
0x1800103c3  lea     r8, aWil; "wil"
0x1800103ca  mov     r9d, eax; char *
0x1800103cd  mov     edx, 134h; void *
0x1800103d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103d7  test    rbx, rbx
0x1800103da  jz      short loc_1800103E4
0x1800103dc  mov     rcx, rbx; this
0x1800103df  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800103e4  mov     rcx, [rsp+278h+var_248]; this
0x1800103e9  test    rcx, rcx
0x1800103ec  jz      short loc_1800103F3
0x1800103ee  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800103f3  mov     eax, edi
0x1800103f5  jmp     short loc_18001037F
```
