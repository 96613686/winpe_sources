# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800e6fe4`
- end: `0x1800e73e1`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800e76e8`

## callees

- `0x180003060`
- `0x180003a40`
- `0x1800e5fec`
- `0x1800e6fe4`
- `0x1800e73e8`
- `0x1800e793c`
- `0x1800e82b8`
- `0x1800e90b0`
- `0x1800eabf4`
- `0x1800eb6f4`
- `0x1800ebc8c`
- `0x1800ec608`
- `0x1800ec618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800e707c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800e707c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800e705b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800e705b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e7112`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e724e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e72ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e7112`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e724e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e72ea`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e72b7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e72b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e7217`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e7217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7225`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7225`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e701d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e701d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7123`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e71f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e725f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7300`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7123`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e71f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e725f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7300`

## string_xrefs

- `0x1800e735d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _DWORD *v23; // r14
  int v24; // eax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  __int128 v34; // xmm0
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v40);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v23 = (_DWORD *)v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v14;
  }
  *(_OWORD *)hObject = 0;
  if ( (v20 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
  v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v22,
          v20 >> 2);
  v14 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
    goto LABEL_23;
  }
  v34 = *(_OWORD *)hObject;
  *v23 = 1;
  *((_QWORD *)v23 + 1) = v6;
  *((_OWORD *)v23 + 1) = v34;
  memset_0(v23 + 10, 0, 0x108u);
  *((_QWORD *)v23 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v23 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v23 + 58), 0, 0);
  *((_QWORD *)v23 + 34) = 0;
  *((_QWORD *)v23 + 35) = 0;
  *((_QWORD *)v23 + 36) = 0;
  *((_QWORD *)v23 + 37) = 0;
  v6 = 0;
  *a2 = v23;
LABEL_28:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x1800e6fe4  mov     [rsp-8+arg_10], rbx
0x1800e6fe9  push    rbp
0x1800e6fea  push    rsi
0x1800e6feb  push    rdi
0x1800e6fec  push    r14
0x1800e6fee  push    r15
0x1800e6ff0  lea     rbp, [rsp-160h]
0x1800e6ff8  sub     rsp, 260h
0x1800e6fff  mov     rax, cs:__security_cookie
0x1800e7006  xor     rax, rsp
0x1800e7009  mov     [rbp+180h+var_30], rax
0x1800e7010  mov     r15, rdx
0x1800e7013  mov     qword ptr [rdx], 0
0x1800e701a  mov     rbx, rcx
0x1800e701d  call    cs:__imp_GetCurrentProcessId
0x1800e7023  mov     r14d, 130h
0x1800e7029  mov     [rsp+280h+var_258], rbx
0x1800e702e  mov     r9d, eax
0x1800e7031  mov     [rsp+280h+var_260], r14d; int
0x1800e7036  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800e703d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800e7042  lea     edx, [r14-2Ch]; unsigned __int64
0x1800e7046  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e704b  mov     r9d, 1F0001h; dwDesiredAccess
0x1800e7051  lea     rdx, [rsp+280h+Name]; lpName
0x1800e7056  xor     r8d, r8d; dwFlags
0x1800e7059  xor     ecx, ecx; lpMutexAttributes
0x1800e705b  call    cs:__imp_CreateMutexExW
0x1800e7061  mov     rbx, rax
0x1800e7064  test    rax, rax
0x1800e7067  jnz     short loc_1800E7073
0x1800e7069  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800e706e  jmp     loc_1800E730C
0x1800e7073  xor     r8d, r8d; bAlertable
0x1800e7076  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800e7079  mov     rcx, rbx; hHandle
0x1800e707c  call    cs:__imp_WaitForSingleObjectEx
0x1800e7082  cmp     eax, 102h
0x1800e7087  jz      short loc_1800E7099
0x1800e7089  test    eax, 0FFFFFF7Fh
0x1800e708e  jnz     loc_1800E7356
0x1800e7094  mov     rdi, rbx
0x1800e7097  jmp     short loc_1800E709B
0x1800e7099  xor     edi, edi
0x1800e709b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800e70a0  mov     [rsp+280h+hObject], 0
0x1800e70a9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800e70ae  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800e70b3  mov     esi, eax
0x1800e70b5  test    eax, eax
0x1800e70b7  jns     short loc_1800E7138
0x1800e70b9  mov     rcx, [rbp+188h]; this
0x1800e70c0  lea     r8, aWil; "wil"
0x1800e70c7  mov     r9d, eax; char *
0x1800e70ca  mov     edx, 66h ; 'f'; void *
0x1800e70cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e70d4  mov     rcx, [rbp+188h]; this
0x1800e70db  lea     r8, aWil; "wil"
0x1800e70e2  mov     r9d, esi; char *
0x1800e70e5  mov     edx, 6Fh ; 'o'; void *
0x1800e70ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e70ef  mov     rcx, [rbp+188h]; this
0x1800e70f6  lea     r8, aWil; "wil"
0x1800e70fd  mov     r9d, esi; char *
0x1800e7100  mov     edx, 12Eh; void *
0x1800e7105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e710a  test    rdi, rdi
0x1800e710d  jz      short loc_1800E7120
0x1800e710f  mov     rcx, rdi; hMutex
0x1800e7112  call    cs:__imp_ReleaseMutex
0x1800e7118  test    eax, eax
0x1800e711a  jz      loc_1800E736F
0x1800e7120  mov     rcx, rbx; hObject
0x1800e7123  call    cs:__imp_CloseHandle
0x1800e7129  test    eax, eax
0x1800e712b  jz      loc_1800E7381
0x1800e7131  mov     eax, esi
0x1800e7133  jmp     loc_1800E730C
0x1800e7138  mov     rax, [rsp+280h+hObject]
0x1800e713d  lea     rcx, ds:0[rax*4]
0x1800e7145  test    rcx, rcx
0x1800e7148  jz      short loc_1800E7158
0x1800e714a  mov     [r15], rcx
0x1800e714d  mov     eax, [rcx]
0x1800e714f  inc     eax
0x1800e7151  mov     [rcx], eax
0x1800e7153  jmp     loc_1800E72E2
0x1800e7158  mov     rdx, r14; dwBytes
0x1800e715b  mov     qword ptr [r15], 0
0x1800e7162  mov     ecx, 8; dwFlags
0x1800e7167  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800e716c  mov     r14, rax
0x1800e716f  test    rax, rax
0x1800e7172  jnz     short loc_1800E7199
0x1800e7174  mov     rcx, [rbp+188h]; this
0x1800e717b  lea     r8, aWil; "wil"
0x1800e7182  mov     esi, 8007000Eh
0x1800e7187  mov     edx, 14Bh; void *
0x1800e718c  mov     r9d, esi; char *
0x1800e718f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7194  jmp     loc_1800E722B
0x1800e7199  xorps   xmm0, xmm0
0x1800e719c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800e71a2  test    r14b, 3
0x1800e71a6  jnz     loc_1800E7393
0x1800e71ac  mov     r9, r14
0x1800e71af  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800e71b4  shr     r9, 2; unsigned __int64
0x1800e71b8  lea     rcx, [rsp+280h+hObject]; this
0x1800e71bd  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800e71c2  mov     esi, eax
0x1800e71c4  test    eax, eax
0x1800e71c6  jns     loc_1800E7272
0x1800e71cc  mov     rcx, [rbp+188h]; this
0x1800e71d3  lea     r8, aWil; "wil"
0x1800e71da  mov     r9d, eax; char *
0x1800e71dd  mov     edx, 14Eh; void *
0x1800e71e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e71e7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800e71ec  test    rcx, rcx
0x1800e71ef  jz      short loc_1800E71FF
0x1800e71f1  call    cs:__imp_CloseHandle
0x1800e71f7  test    eax, eax
0x1800e71f9  jz      loc_1800E7399
0x1800e71ff  mov     rcx, [rsp+280h+hObject]; hObject
0x1800e7204  test    rcx, rcx
0x1800e7207  jz      short loc_1800E7217
0x1800e7209  call    cs:__imp_CloseHandle
0x1800e720f  test    eax, eax
0x1800e7211  jz      loc_1800E73AB
0x1800e7217  call    cs:__imp_GetProcessHeap
0x1800e721d  mov     r8, r14; lpMem
0x1800e7220  xor     edx, edx; dwFlags
0x1800e7222  mov     rcx, rax; hHeap
0x1800e7225  call    cs:__imp_HeapFree
0x1800e722b  mov     rcx, [rbp+188h]; this
0x1800e7232  lea     r8, aWil; "wil"
0x1800e7239  mov     r9d, esi; char *
0x1800e723c  mov     edx, 137h; void *
0x1800e7241  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7246  test    rdi, rdi
0x1800e7249  jz      short loc_1800E725C
0x1800e724b  mov     rcx, rdi; hMutex
0x1800e724e  call    cs:__imp_ReleaseMutex
0x1800e7254  test    eax, eax
0x1800e7256  jz      loc_1800E73BD
0x1800e725c  mov     rcx, rbx; hObject
0x1800e725f  call    cs:__imp_CloseHandle
0x1800e7265  test    eax, eax
0x1800e7267  jz      loc_1800E7344
0x1800e726d  jmp     loc_1800E7131
0x1800e7272  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800e7277  lea     rcx, [r14+28h]; void *
0x1800e727b  mov     dword ptr [r14], 1
0x1800e7282  xor     edx, edx; Val
0x1800e7284  mov     [r14+8], rbx
0x1800e7288  mov     r8d, 108h; Size
0x1800e728e  movdqu  xmmword ptr [r14+10h], xmm0
0x1800e7294  call    memset_0
0x1800e7299  xor     eax, eax
0x1800e729b  lea     rcx, [r14+28h]; this
0x1800e729f  mov     [r14+20h], rax
0x1800e72a3  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800e72a8  lea     rbx, [r14+0E8h]
0x1800e72af  xor     r8d, r8d; Flags
0x1800e72b2  mov     rcx, rbx; lpCriticalSection
0x1800e72b5  xor     edx, edx; dwSpinCount
0x1800e72b7  call    cs:__imp_InitializeCriticalSectionEx
0x1800e72bd  mov     qword ptr [rbx+28h], 0
0x1800e72c5  mov     qword ptr [rbx+30h], 0
0x1800e72cd  mov     qword ptr [rbx+38h], 0
0x1800e72d5  mov     qword ptr [rbx+40h], 0
0x1800e72dd  xor     ebx, ebx
0x1800e72df  mov     [r15], r14
0x1800e72e2  test    rdi, rdi
0x1800e72e5  jz      short loc_1800E72F8
0x1800e72e7  mov     rcx, rdi; hMutex
0x1800e72ea  call    cs:__imp_ReleaseMutex
0x1800e72f0  test    eax, eax
0x1800e72f2  jz      loc_1800E73CF
0x1800e72f8  test    rbx, rbx
0x1800e72fb  jz      short loc_1800E730A
0x1800e72fd  mov     rcx, rbx; hObject
0x1800e7300  call    cs:__imp_CloseHandle
0x1800e7306  test    eax, eax
0x1800e7308  jz      short loc_1800E7332
0x1800e730a  xor     eax, eax
0x1800e730c  mov     rcx, [rbp+180h+var_30]
0x1800e7313  xor     rcx, rsp; StackCookie
0x1800e7316  call    __security_check_cookie
0x1800e731b  mov     rbx, [rsp+280h+arg_10]
0x1800e7323  add     rsp, 260h
0x1800e732a  pop     r15
0x1800e732c  pop     r14
0x1800e732e  pop     rdi
0x1800e732f  pop     rsi
0x1800e7330  pop     rbp
0x1800e7331  retn
0x1800e7332  mov     rcx, [rbp+188h]; this
0x1800e7339  mov     edx, 0A0Bh; void *
0x1800e733e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e7344  mov     rcx, [rbp+188h]; this
0x1800e734b  mov     edx, 0A0Bh; void *
0x1800e7350  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e7356  mov     rcx, [rbp+188h]; this
0x1800e735d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800e7364  mov     edx, 0E01h; void *
0x1800e7369  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800e736f  mov     rcx, [rbp+188h]; this
0x1800e7376  mov     edx, 0A15h; void *
0x1800e737b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e7381  mov     rcx, [rbp+188h]; this
0x1800e7388  mov     edx, 0A0Bh; void *
0x1800e738d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e7393  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800e7399  mov     rcx, [rbp+188h]; this
0x1800e73a0  mov     edx, 0A0Bh; void *
0x1800e73a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e73ab  mov     rcx, [rbp+188h]; this
0x1800e73b2  mov     edx, 0A0Bh; void *
0x1800e73b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e73bd  mov     rcx, [rbp+188h]; this
0x1800e73c4  mov     edx, 0A15h; void *
0x1800e73c9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e73cf  mov     rcx, [rbp+188h]; this
0x1800e73d6  mov     edx, 0A15h; void *
0x1800e73db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
