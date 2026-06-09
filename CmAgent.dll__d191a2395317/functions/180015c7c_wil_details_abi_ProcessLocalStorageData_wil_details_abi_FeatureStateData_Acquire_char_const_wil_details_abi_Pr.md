# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180015c7c`
- end: `0x180016088`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1036`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18001698c`

## callees

- `0x180002140`
- `0x180002c48`
- `0x180003ce4`
- `0x1800045e4`
- `0x180005c5c`
- `0x18000629c`
- `0x1800067fc`
- `0x18000753c`
- `0x1800091a0`
- `0x18000922c`
- `0x180009518`
- `0x180014c64`
- `0x180015c7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015cb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015cb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015dc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015edd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015fae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015dc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015edd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015fae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015d20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015d20`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015cf9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015cf9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180015f6b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180015f6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015eae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015eae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015dd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ef4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015dd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ef4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fca`

## string_xrefs

- `0x18001602e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
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
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // r8
  const char *v18; // r9
  _DWORD *v19; // rcx
  _DWORD *v20; // rax
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v35[2]; // [rsp+30h] [rbp-D0h] BYREF
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v35[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v35, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v32);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v33);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * v35[0]);
  if ( 4 * v35[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_23;
  }
  *a2 = 0;
  v20 = wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v21 = v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v35 = 0;
  v22 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v35, Name, v20);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v35);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v34);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v24, v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v35[0];
  *((_QWORD *)v21 + 3) = v35[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v35[0] = 0;
  v35[1] = 0;
  memset_0(v21 + 10, 0, 0x108u);
  *((_QWORD *)v21 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 58), 0, 0);
  *((_QWORD *)v21 + 34) = 0;
  *((_QWORD *)v21 + 35) = 0;
  *((_QWORD *)v21 + 36) = 0;
  *((_QWORD *)v21 + 37) = 0;
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v35);
  v6 = 0;
LABEL_23:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v28, v29);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
  return 0;
}

```

## disassembly

```asm
0x180015c7c  mov     [rsp-8+arg_10], rbx
0x180015c81  push    rbp
0x180015c82  push    rsi
0x180015c83  push    rdi
0x180015c84  push    r14
0x180015c86  push    r15
0x180015c88  lea     rbp, [rsp-160h]
0x180015c90  sub     rsp, 260h
0x180015c97  mov     rax, cs:__security_cookie
0x180015c9e  xor     rax, rsp
0x180015ca1  mov     [rbp+180h+var_30], rax
0x180015ca8  mov     r15, rdx
0x180015cab  mov     qword ptr [rdx], 0
0x180015cb2  mov     rbx, rcx
0x180015cb5  call    cs:__imp_GetCurrentProcessId
0x180015cbc  nop     dword ptr [rax+rax+00h]
0x180015cc1  mov     r14d, 130h
0x180015cc7  mov     [rsp+280h+var_258], rbx
0x180015ccc  mov     r9d, eax
0x180015ccf  mov     [rsp+280h+var_260], r14d; int
0x180015cd4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180015cdb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180015ce0  lea     edx, [r14-2Ch]; unsigned __int64
0x180015ce4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015ce9  mov     r9d, 1F0001h; dwDesiredAccess
0x180015cef  lea     rdx, [rsp+280h+Name]; lpName
0x180015cf4  xor     r8d, r8d; dwFlags
0x180015cf7  xor     ecx, ecx; lpMutexAttributes
0x180015cf9  call    cs:__imp_CreateMutexExW
0x180015d00  nop     dword ptr [rax+rax+00h]
0x180015d05  mov     rbx, rax
0x180015d08  test    rax, rax
0x180015d0b  jnz     short loc_180015D17
0x180015d0d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180015d12  jmp     loc_180015FDC
0x180015d17  xor     r8d, r8d; bAlertable
0x180015d1a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180015d1d  mov     rcx, rbx; hHandle
0x180015d20  call    cs:__imp_WaitForSingleObjectEx
0x180015d27  nop     dword ptr [rax+rax+00h]
0x180015d2c  cmp     eax, 102h
0x180015d31  jz      short loc_180015D43
0x180015d33  test    eax, 0FFFFFF7Fh
0x180015d38  jnz     loc_180016027
0x180015d3e  mov     rdi, rbx
0x180015d41  jmp     short loc_180015D45
0x180015d43  xor     edi, edi
0x180015d45  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180015d4a  mov     [rsp+280h+var_250], 0
0x180015d53  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180015d58  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180015d5d  mov     esi, eax
0x180015d5f  test    eax, eax
0x180015d61  jns     loc_180015DF2
0x180015d67  mov     rcx, [rbp+188h]; this
0x180015d6e  lea     r8, aWil; "wil"
0x180015d75  mov     r9d, eax; char *
0x180015d78  mov     edx, 66h ; 'f'; void *
0x180015d7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015d82  mov     rcx, [rbp+188h]; this
0x180015d89  lea     r8, aWil; "wil"
0x180015d90  mov     r9d, esi; char *
0x180015d93  mov     edx, 6Fh ; 'o'; void *
0x180015d98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015d9d  mov     rcx, [rbp+188h]; this
0x180015da4  lea     r8, aWil; "wil"
0x180015dab  mov     r9d, esi; char *
0x180015dae  mov     edx, 12Eh; void *
0x180015db3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015db8  test    rdi, rdi
0x180015dbb  jz      short loc_180015DD4
0x180015dbd  mov     rcx, rdi; hMutex
0x180015dc0  call    cs:__imp_ReleaseMutex
0x180015dc7  nop     dword ptr [rax+rax+00h]
0x180015dcc  test    eax, eax
0x180015dce  jz      loc_180016040
0x180015dd4  mov     rcx, rbx; hObject
0x180015dd7  call    cs:__imp_CloseHandle
0x180015dde  nop     dword ptr [rax+rax+00h]
0x180015de3  test    eax, eax
0x180015de5  jz      loc_180016052
0x180015deb  mov     eax, esi
0x180015ded  jmp     loc_180015FDC
0x180015df2  mov     rax, [rsp+280h+var_250]
0x180015df7  lea     rcx, ds:0[rax*4]
0x180015dff  test    rcx, rcx
0x180015e02  jz      short loc_180015E12
0x180015e04  mov     [r15], rcx
0x180015e07  mov     eax, [rcx]
0x180015e09  inc     eax
0x180015e0b  mov     [rcx], eax
0x180015e0d  jmp     loc_180015FA6
0x180015e12  mov     rdx, r14; dwBytes
0x180015e15  mov     qword ptr [r15], 0
0x180015e1c  mov     ecx, 8; dwFlags
0x180015e21  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015e26  mov     r14, rax
0x180015e29  test    rax, rax
0x180015e2c  jnz     short loc_180015E50
0x180015e2e  mov     rcx, [rbp+188h]; this
0x180015e35  lea     r8, aWil; "wil"
0x180015e3c  mov     esi, 8007000Eh
0x180015e41  mov     edx, 14Bh; void *
0x180015e46  mov     r9d, esi; char *
0x180015e49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e4e  jmp     short loc_180015EBA
0x180015e50  xorps   xmm0, xmm0
0x180015e53  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180015e58  mov     r8, r14; void *
0x180015e5b  lea     rcx, [rsp+280h+var_250]; this
0x180015e60  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180015e66  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180015e6b  mov     esi, eax
0x180015e6d  test    eax, eax
0x180015e6f  jns     loc_180015F0D
0x180015e75  mov     rcx, [rbp+188h]; this
0x180015e7c  lea     r8, aWil; "wil"
0x180015e83  mov     r9d, eax; char *
0x180015e86  mov     edx, 14Eh; void *
0x180015e8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e90  lea     rcx, [rsp+280h+var_250]; this
0x180015e95  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180015e9a  call    cs:__imp_GetProcessHeap
0x180015ea1  nop     dword ptr [rax+rax+00h]
0x180015ea6  mov     r8, r14; lpMem
0x180015ea9  xor     edx, edx; dwFlags
0x180015eab  mov     rcx, rax; hHeap
0x180015eae  call    cs:__imp_HeapFree
0x180015eb5  nop     dword ptr [rax+rax+00h]
0x180015eba  mov     rcx, [rbp+188h]; this
0x180015ec1  lea     r8, aWil; "wil"
0x180015ec8  mov     r9d, esi; char *
0x180015ecb  mov     edx, 137h; void *
0x180015ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ed5  test    rdi, rdi
0x180015ed8  jz      short loc_180015EF1
0x180015eda  mov     rcx, rdi; hMutex
0x180015edd  call    cs:__imp_ReleaseMutex
0x180015ee4  nop     dword ptr [rax+rax+00h]
0x180015ee9  test    eax, eax
0x180015eeb  jz      loc_180016064
0x180015ef1  mov     rcx, rbx; hObject
0x180015ef4  call    cs:__imp_CloseHandle
0x180015efb  nop     dword ptr [rax+rax+00h]
0x180015f00  test    eax, eax
0x180015f02  jz      loc_180016015
0x180015f08  jmp     loc_180015DEB
0x180015f0d  mov     rax, [rsp+280h+var_250]
0x180015f12  lea     rcx, [r14+28h]; void *
0x180015f16  mov     [r14+10h], rax
0x180015f1a  xor     edx, edx; Val
0x180015f1c  mov     rax, [rsp+280h+var_250+8]
0x180015f21  mov     r8d, 108h; Size
0x180015f27  mov     [r14+18h], rax
0x180015f2b  mov     dword ptr [r14], 1
0x180015f32  mov     [r14+8], rbx
0x180015f36  mov     [rsp+280h+var_250], 0
0x180015f3f  mov     [rsp+280h+var_250+8], 0
0x180015f48  call    memset_0
0x180015f4d  xor     eax, eax
0x180015f4f  lea     rcx, [r14+28h]; this
0x180015f53  mov     [r14+20h], rax
0x180015f57  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180015f5c  lea     rbx, [r14+0E8h]
0x180015f63  xor     r8d, r8d; Flags
0x180015f66  mov     rcx, rbx; lpCriticalSection
0x180015f69  xor     edx, edx; dwSpinCount
0x180015f6b  call    cs:__imp_InitializeCriticalSectionEx
0x180015f72  nop     dword ptr [rax+rax+00h]
0x180015f77  mov     qword ptr [rbx+28h], 0
0x180015f7f  lea     rcx, [rsp+280h+var_250]; this
0x180015f84  mov     qword ptr [rbx+30h], 0
0x180015f8c  mov     qword ptr [rbx+38h], 0
0x180015f94  mov     qword ptr [rbx+40h], 0
0x180015f9c  mov     [r15], r14
0x180015f9f  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180015fa4  xor     ebx, ebx
0x180015fa6  test    rdi, rdi
0x180015fa9  jz      short loc_180015FC2
0x180015fab  mov     rcx, rdi; hMutex
0x180015fae  call    cs:__imp_ReleaseMutex
0x180015fb5  nop     dword ptr [rax+rax+00h]
0x180015fba  test    eax, eax
0x180015fbc  jz      loc_180016076
0x180015fc2  test    rbx, rbx
0x180015fc5  jz      short loc_180015FDA
0x180015fc7  mov     rcx, rbx; hObject
0x180015fca  call    cs:__imp_CloseHandle
0x180015fd1  nop     dword ptr [rax+rax+00h]
0x180015fd6  test    eax, eax
0x180015fd8  jz      short loc_180016003
0x180015fda  xor     eax, eax
0x180015fdc  mov     rcx, [rbp+180h+var_30]
0x180015fe3  xor     rcx, rsp; StackCookie
0x180015fe6  call    __security_check_cookie
0x180015feb  mov     rbx, [rsp+280h+arg_10]
0x180015ff3  add     rsp, 260h
0x180015ffa  pop     r15
0x180015ffc  pop     r14
0x180015ffe  pop     rdi
0x180015fff  pop     rsi
0x180016000  pop     rbp
0x180016001  retn
0x180016003  mov     rcx, [rbp+188h]; this
0x18001600a  mov     edx, 0A0Bh; void *
0x18001600f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016015  mov     rcx, [rbp+188h]; this
0x18001601c  mov     edx, 0A0Bh; void *
0x180016021  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016027  mov     rcx, [rbp+188h]; this
0x18001602e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016035  mov     edx, 0E01h; void *
0x18001603a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016040  mov     rcx, [rbp+188h]; this
0x180016047  mov     edx, 0A15h; void *
0x18001604c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016052  mov     rcx, [rbp+188h]; this
0x180016059  mov     edx, 0A0Bh; void *
0x18001605e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016064  mov     rcx, [rbp+188h]; this
0x18001606b  mov     edx, 0A15h; void *
0x180016070  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016076  mov     rcx, [rbp+188h]; this
0x18001607d  mov     edx, 0A15h; void *
0x180016082  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
