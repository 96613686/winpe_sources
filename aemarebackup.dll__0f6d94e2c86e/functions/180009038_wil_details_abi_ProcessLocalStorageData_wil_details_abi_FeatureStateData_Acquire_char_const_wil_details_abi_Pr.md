# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009038`
- end: `0x180009429`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180009714`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x1800080e0`
- `0x180009038`
- `0x180009430`
- `0x180009970`
- `0x18000a2a8`
- `0x18000b368`
- `0x18000cac4`
- `0x18000d62c`
- `0x18000dc68`
- `0x18000e53c`
- `0x18000e54c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800090af`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800090af`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800090d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800090d0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000930b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000930b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009166`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800092a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000933e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009166`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800092a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000933e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000926b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000926b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009279`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009279`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009071`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009071`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009245`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000925d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009354`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009245`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000925d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009354`

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
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x180009038  mov     [rsp-8+arg_10], rbx
0x18000903d  push    rbp
0x18000903e  push    rsi
0x18000903f  push    rdi
0x180009040  push    r14
0x180009042  push    r15
0x180009044  lea     rbp, [rsp-160h]
0x18000904c  sub     rsp, 260h
0x180009053  mov     rax, cs:__security_cookie
0x18000905a  xor     rax, rsp
0x18000905d  mov     [rbp+180h+var_30], rax
0x180009064  mov     r15, rdx
0x180009067  mov     qword ptr [rdx], 0
0x18000906e  mov     rbx, rcx
0x180009071  call    cs:__imp_GetCurrentProcessId
0x180009077  mov     r14d, 130h
0x18000907d  mov     [rsp+280h+var_258], rbx
0x180009082  mov     r9d, eax
0x180009085  mov     [rsp+280h+var_260], r14d; int
0x18000908a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009091  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009096  lea     edx, [r14-2Ch]; unsigned __int64
0x18000909a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000909f  mov     r9d, 1F0001h; dwDesiredAccess
0x1800090a5  lea     rdx, [rsp+280h+Name]; lpName
0x1800090aa  xor     r8d, r8d; dwFlags
0x1800090ad  xor     ecx, ecx; lpMutexAttributes
0x1800090af  call    cs:__imp_CreateMutexExW
0x1800090b5  mov     rbx, rax
0x1800090b8  test    rax, rax
0x1800090bb  jnz     short loc_1800090C7
0x1800090bd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800090c2  jmp     loc_180009360
0x1800090c7  xor     r8d, r8d; bAlertable
0x1800090ca  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800090cd  mov     rcx, rbx; hHandle
0x1800090d0  call    cs:__imp_WaitForSingleObjectEx
0x1800090d6  cmp     eax, 102h
0x1800090db  jz      short loc_1800090ED
0x1800090dd  test    eax, 0FFFFFF7Fh
0x1800090e2  jnz     loc_1800093AA
0x1800090e8  mov     rdi, rbx
0x1800090eb  jmp     short loc_1800090EF
0x1800090ed  xor     edi, edi
0x1800090ef  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800090f4  mov     [rsp+280h+hObject], 0
0x1800090fd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009102  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009107  mov     esi, eax
0x180009109  test    eax, eax
0x18000910b  jns     short loc_18000918C
0x18000910d  mov     rcx, [rbp+188h]; this
0x180009114  lea     r8, aWil; "wil"
0x18000911b  mov     r9d, eax; char *
0x18000911e  mov     edx, 66h ; 'f'; void *
0x180009123  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009128  mov     rcx, [rbp+188h]; this
0x18000912f  lea     r8, aWil; "wil"
0x180009136  mov     r9d, esi; char *
0x180009139  mov     edx, 6Fh ; 'o'; void *
0x18000913e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009143  mov     rcx, [rbp+188h]; this
0x18000914a  lea     r8, aWil; "wil"
0x180009151  mov     r9d, esi; char *
0x180009154  mov     edx, 12Eh; void *
0x180009159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000915e  test    rdi, rdi
0x180009161  jz      short loc_180009174
0x180009163  mov     rcx, rdi; hMutex
0x180009166  call    cs:__imp_ReleaseMutex
0x18000916c  test    eax, eax
0x18000916e  jz      loc_1800093B7
0x180009174  mov     rcx, rbx; hObject
0x180009177  call    cs:__imp_CloseHandle
0x18000917d  test    eax, eax
0x18000917f  jz      loc_1800093C9
0x180009185  mov     eax, esi
0x180009187  jmp     loc_180009360
0x18000918c  mov     rax, [rsp+280h+hObject]
0x180009191  lea     rcx, ds:0[rax*4]
0x180009199  test    rcx, rcx
0x18000919c  jz      short loc_1800091AC
0x18000919e  mov     [r15], rcx
0x1800091a1  mov     eax, [rcx]
0x1800091a3  inc     eax
0x1800091a5  mov     [rcx], eax
0x1800091a7  jmp     loc_180009336
0x1800091ac  mov     rdx, r14; dwBytes
0x1800091af  mov     qword ptr [r15], 0
0x1800091b6  mov     ecx, 8; dwFlags
0x1800091bb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800091c0  mov     r14, rax
0x1800091c3  test    rax, rax
0x1800091c6  jnz     short loc_1800091ED
0x1800091c8  mov     rcx, [rbp+188h]; this
0x1800091cf  lea     r8, aWil; "wil"
0x1800091d6  mov     esi, 8007000Eh
0x1800091db  mov     edx, 14Bh; void *
0x1800091e0  mov     r9d, esi; char *
0x1800091e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091e8  jmp     loc_18000927F
0x1800091ed  xorps   xmm0, xmm0
0x1800091f0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800091f6  test    r14b, 3
0x1800091fa  jnz     loc_1800093DB
0x180009200  mov     r9, r14
0x180009203  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009208  shr     r9, 2; unsigned __int64
0x18000920c  lea     rcx, [rsp+280h+hObject]; this
0x180009211  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009216  mov     esi, eax
0x180009218  test    eax, eax
0x18000921a  jns     loc_1800092C6
0x180009220  mov     rcx, [rbp+188h]; this
0x180009227  lea     r8, aWil; "wil"
0x18000922e  mov     r9d, eax; char *
0x180009231  mov     edx, 14Eh; void *
0x180009236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000923b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009240  test    rcx, rcx
0x180009243  jz      short loc_180009253
0x180009245  call    cs:__imp_CloseHandle
0x18000924b  test    eax, eax
0x18000924d  jz      loc_1800093E1
0x180009253  mov     rcx, [rsp+280h+hObject]; hObject
0x180009258  test    rcx, rcx
0x18000925b  jz      short loc_18000926B
0x18000925d  call    cs:__imp_CloseHandle
0x180009263  test    eax, eax
0x180009265  jz      loc_1800093F3
0x18000926b  call    cs:__imp_GetProcessHeap
0x180009271  mov     r8, r14; lpMem
0x180009274  xor     edx, edx; dwFlags
0x180009276  mov     rcx, rax; hHeap
0x180009279  call    cs:__imp_HeapFree
0x18000927f  mov     rcx, [rbp+188h]; this
0x180009286  lea     r8, aWil; "wil"
0x18000928d  mov     r9d, esi; char *
0x180009290  mov     edx, 137h; void *
0x180009295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000929a  test    rdi, rdi
0x18000929d  jz      short loc_1800092B0
0x18000929f  mov     rcx, rdi; hMutex
0x1800092a2  call    cs:__imp_ReleaseMutex
0x1800092a8  test    eax, eax
0x1800092aa  jz      loc_180009405
0x1800092b0  mov     rcx, rbx; hObject
0x1800092b3  call    cs:__imp_CloseHandle
0x1800092b9  test    eax, eax
0x1800092bb  jz      loc_180009398
0x1800092c1  jmp     loc_180009185
0x1800092c6  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800092cb  lea     rcx, [r14+28h]; void *
0x1800092cf  mov     dword ptr [r14], 1
0x1800092d6  xor     edx, edx; Val
0x1800092d8  mov     [r14+8], rbx
0x1800092dc  mov     r8d, 108h; Size
0x1800092e2  movdqu  xmmword ptr [r14+10h], xmm0
0x1800092e8  call    memset_0
0x1800092ed  xor     eax, eax
0x1800092ef  lea     rcx, [r14+28h]; this
0x1800092f3  mov     [r14+20h], rax
0x1800092f7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800092fc  lea     rbx, [r14+0E8h]
0x180009303  xor     r8d, r8d; Flags
0x180009306  mov     rcx, rbx; lpCriticalSection
0x180009309  xor     edx, edx; dwSpinCount
0x18000930b  call    cs:__imp_InitializeCriticalSectionEx
0x180009311  mov     qword ptr [rbx+28h], 0
0x180009319  mov     qword ptr [rbx+30h], 0
0x180009321  mov     qword ptr [rbx+38h], 0
0x180009329  mov     qword ptr [rbx+40h], 0
0x180009331  xor     ebx, ebx
0x180009333  mov     [r15], r14
0x180009336  test    rdi, rdi
0x180009339  jz      short loc_18000934C
0x18000933b  mov     rcx, rdi; hMutex
0x18000933e  call    cs:__imp_ReleaseMutex
0x180009344  test    eax, eax
0x180009346  jz      loc_180009417
0x18000934c  test    rbx, rbx
0x18000934f  jz      short loc_18000935E
0x180009351  mov     rcx, rbx; hObject
0x180009354  call    cs:__imp_CloseHandle
0x18000935a  test    eax, eax
0x18000935c  jz      short loc_180009386
0x18000935e  xor     eax, eax
0x180009360  mov     rcx, [rbp+180h+var_30]
0x180009367  xor     rcx, rsp; StackCookie
0x18000936a  call    __security_check_cookie
0x18000936f  mov     rbx, [rsp+280h+arg_10]
0x180009377  add     rsp, 260h
0x18000937e  pop     r15
0x180009380  pop     r14
0x180009382  pop     rdi
0x180009383  pop     rsi
0x180009384  pop     rbp
0x180009385  retn
0x180009386  mov     rcx, [rbp+188h]; this
0x18000938d  mov     edx, 0A0Bh; void *
0x180009392  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009398  mov     rcx, [rbp+188h]; this
0x18000939f  mov     edx, 0A0Bh; void *
0x1800093a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093aa  mov     rcx, [rbp+188h]; this
0x1800093b1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800093b7  mov     rcx, [rbp+188h]; this
0x1800093be  mov     edx, 0A15h; void *
0x1800093c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093c9  mov     rcx, [rbp+188h]; this
0x1800093d0  mov     edx, 0A0Bh; void *
0x1800093d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800093e1  mov     rcx, [rbp+188h]; this
0x1800093e8  mov     edx, 0A0Bh; void *
0x1800093ed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093f3  mov     rcx, [rbp+188h]; this
0x1800093fa  mov     edx, 0A0Bh; void *
0x1800093ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009405  mov     rcx, [rbp+188h]; this
0x18000940c  mov     edx, 0A15h; void *
0x180009411  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009417  mov     rcx, [rbp+188h]; this
0x18000941e  mov     edx, 0A15h; void *
0x180009423  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
