# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005eb4`
- end: `0x180006293`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `991`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800069ec`

## callees

- `0x180002140`
- `0x180002c48`
- `0x180003ce4`
- `0x1800045e4`
- `0x180005c5c`
- `0x180005eb4`
- `0x18000629c`
- `0x1800067fc`
- `0x18000753c`
- `0x1800091a0`
- `0x18000922c`
- `0x180009518`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005eed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005eed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006116`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006116`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005f59`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005f59`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005f32`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005f32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000612d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000612d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061d5`

## string_xrefs

- `0x180006239`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  unsigned __int64 v28; // rax
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v36[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v36, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v34);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_23;
  }
  *a2 = 0;
  v20 = wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v36 = 0;
  v22 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v36, Name, v20);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v35);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v24, v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v36[0];
  v28 = v36[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v36[0] = 0;
  *((_QWORD *)v21 + 3) = v28;
  v36[1] = 0;
  memset_0((char *)v21 + 34, 0, 0x56u);
  *((_WORD *)v21 + 16) = 88;
  v21[9] = 1;
  memset_0(v21 + 10, 0, 0x50u);
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_23:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x180005eb4  mov     [rsp-8+arg_10], rbx
0x180005eb9  push    rbp
0x180005eba  push    rsi
0x180005ebb  push    rdi
0x180005ebc  push    r14
0x180005ebe  push    r15
0x180005ec0  lea     rbp, [rsp-160h]
0x180005ec8  sub     rsp, 260h
0x180005ecf  mov     rax, cs:__security_cookie
0x180005ed6  xor     rax, rsp
0x180005ed9  mov     [rbp+180h+var_30], rax
0x180005ee0  mov     r15, rdx
0x180005ee3  mov     qword ptr [rdx], 0
0x180005eea  mov     rbx, rcx
0x180005eed  call    cs:__imp_GetCurrentProcessId
0x180005ef4  nop     dword ptr [rax+rax+00h]
0x180005ef9  mov     r14d, 78h ; 'x'
0x180005eff  mov     [rsp+280h+var_258], rbx
0x180005f04  mov     r9d, eax
0x180005f07  mov     [rsp+280h+var_260], r14d; int
0x180005f0c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005f13  mov     edx, 104h; unsigned __int64
0x180005f18  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005f1d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005f22  mov     r9d, 1F0001h; dwDesiredAccess
0x180005f28  lea     rdx, [rsp+280h+Name]; lpName
0x180005f2d  xor     r8d, r8d; dwFlags
0x180005f30  xor     ecx, ecx; lpMutexAttributes
0x180005f32  call    cs:__imp_CreateMutexExW
0x180005f39  nop     dword ptr [rax+rax+00h]
0x180005f3e  mov     rbx, rax
0x180005f41  test    rax, rax
0x180005f44  jnz     short loc_180005F50
0x180005f46  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005f4b  jmp     loc_1800061E7
0x180005f50  xor     r8d, r8d; bAlertable
0x180005f53  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005f56  mov     rcx, rbx; hHandle
0x180005f59  call    cs:__imp_WaitForSingleObjectEx
0x180005f60  nop     dword ptr [rax+rax+00h]
0x180005f65  cmp     eax, 102h
0x180005f6a  jz      short loc_180005F7C
0x180005f6c  test    eax, 0FFFFFF7Fh
0x180005f71  jnz     loc_180006232
0x180005f77  mov     rdi, rbx
0x180005f7a  jmp     short loc_180005F7E
0x180005f7c  xor     edi, edi
0x180005f7e  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180005f83  mov     [rsp+280h+var_250], 0
0x180005f8c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005f91  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005f96  mov     esi, eax
0x180005f98  test    eax, eax
0x180005f9a  jns     loc_18000602B
0x180005fa0  mov     rcx, [rbp+188h]; this
0x180005fa7  lea     r8, aWil; "wil"
0x180005fae  mov     r9d, eax; char *
0x180005fb1  mov     edx, 66h ; 'f'; void *
0x180005fb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fbb  mov     rcx, [rbp+188h]; this
0x180005fc2  lea     r8, aWil; "wil"
0x180005fc9  mov     r9d, esi; char *
0x180005fcc  mov     edx, 6Fh ; 'o'; void *
0x180005fd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fd6  mov     rcx, [rbp+188h]; this
0x180005fdd  lea     r8, aWil; "wil"
0x180005fe4  mov     r9d, esi; char *
0x180005fe7  mov     edx, 12Eh; void *
0x180005fec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ff1  test    rdi, rdi
0x180005ff4  jz      short loc_18000600D
0x180005ff6  mov     rcx, rdi; hMutex
0x180005ff9  call    cs:__imp_ReleaseMutex
0x180006000  nop     dword ptr [rax+rax+00h]
0x180006005  test    eax, eax
0x180006007  jz      loc_18000624B
0x18000600d  mov     rcx, rbx; hObject
0x180006010  call    cs:__imp_CloseHandle
0x180006017  nop     dword ptr [rax+rax+00h]
0x18000601c  test    eax, eax
0x18000601e  jz      loc_18000625D
0x180006024  mov     eax, esi
0x180006026  jmp     loc_1800061E7
0x18000602b  mov     rax, [rsp+280h+var_250]
0x180006030  lea     rcx, ds:0[rax*4]
0x180006038  test    rcx, rcx
0x18000603b  jz      short loc_18000604B
0x18000603d  mov     [r15], rcx
0x180006040  mov     eax, [rcx]
0x180006042  inc     eax
0x180006044  mov     [rcx], eax
0x180006046  jmp     loc_1800061B1
0x18000604b  mov     rdx, r14; dwBytes
0x18000604e  mov     qword ptr [r15], 0
0x180006055  mov     ecx, 8; dwFlags
0x18000605a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000605f  mov     r14, rax
0x180006062  test    rax, rax
0x180006065  jnz     short loc_180006089
0x180006067  mov     rcx, [rbp+188h]; this
0x18000606e  lea     r8, aWil; "wil"
0x180006075  mov     esi, 8007000Eh
0x18000607a  mov     edx, 14Bh; void *
0x18000607f  mov     r9d, esi; char *
0x180006082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006087  jmp     short loc_1800060F3
0x180006089  xorps   xmm0, xmm0
0x18000608c  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006091  mov     r8, r14; void *
0x180006094  lea     rcx, [rsp+280h+var_250]; this
0x180006099  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000609f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800060a4  mov     esi, eax
0x1800060a6  test    eax, eax
0x1800060a8  jns     loc_180006146
0x1800060ae  mov     rcx, [rbp+188h]; this
0x1800060b5  lea     r8, aWil; "wil"
0x1800060bc  mov     r9d, eax; char *
0x1800060bf  mov     edx, 14Eh; void *
0x1800060c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060c9  lea     rcx, [rsp+280h+var_250]; this
0x1800060ce  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800060d3  call    cs:__imp_GetProcessHeap
0x1800060da  nop     dword ptr [rax+rax+00h]
0x1800060df  mov     r8, r14; lpMem
0x1800060e2  xor     edx, edx; dwFlags
0x1800060e4  mov     rcx, rax; hHeap
0x1800060e7  call    cs:__imp_HeapFree
0x1800060ee  nop     dword ptr [rax+rax+00h]
0x1800060f3  mov     rcx, [rbp+188h]; this
0x1800060fa  lea     r8, aWil; "wil"
0x180006101  mov     r9d, esi; char *
0x180006104  mov     edx, 137h; void *
0x180006109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000610e  test    rdi, rdi
0x180006111  jz      short loc_18000612A
0x180006113  mov     rcx, rdi; hMutex
0x180006116  call    cs:__imp_ReleaseMutex
0x18000611d  nop     dword ptr [rax+rax+00h]
0x180006122  test    eax, eax
0x180006124  jz      loc_18000626F
0x18000612a  mov     rcx, rbx; hObject
0x18000612d  call    cs:__imp_CloseHandle
0x180006134  nop     dword ptr [rax+rax+00h]
0x180006139  test    eax, eax
0x18000613b  jz      loc_180006220
0x180006141  jmp     loc_180006024
0x180006146  mov     rax, [rsp+280h+var_250]
0x18000614b  lea     rcx, [r14+22h]; void *
0x18000614f  xor     edx, edx; Val
0x180006151  mov     [r14+10h], rax
0x180006155  mov     rax, [rsp+280h+var_250+8]
0x18000615a  mov     dword ptr [r14], 1
0x180006161  mov     [r14+8], rbx
0x180006165  lea     r8d, [rdx+56h]; Size
0x180006169  mov     [rsp+280h+var_250], 0
0x180006172  mov     [r14+18h], rax
0x180006176  mov     [rsp+280h+var_250+8], 0
0x18000617f  call    memset_0
0x180006184  xor     edx, edx; Val
0x180006186  mov     word ptr [r14+20h], 58h ; 'X'
0x18000618d  lea     rcx, [r14+28h]; void *
0x180006191  mov     dword ptr [r14+24h], 1
0x180006199  lea     r8d, [rdx+50h]; Size
0x18000619d  call    memset_0
0x1800061a2  lea     rcx, [rsp+280h+var_250]; this
0x1800061a7  mov     [r15], r14
0x1800061aa  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800061af  xor     ebx, ebx
0x1800061b1  test    rdi, rdi
0x1800061b4  jz      short loc_1800061CD
0x1800061b6  mov     rcx, rdi; hMutex
0x1800061b9  call    cs:__imp_ReleaseMutex
0x1800061c0  nop     dword ptr [rax+rax+00h]
0x1800061c5  test    eax, eax
0x1800061c7  jz      loc_180006281
0x1800061cd  test    rbx, rbx
0x1800061d0  jz      short loc_1800061E5
0x1800061d2  mov     rcx, rbx; hObject
0x1800061d5  call    cs:__imp_CloseHandle
0x1800061dc  nop     dword ptr [rax+rax+00h]
0x1800061e1  test    eax, eax
0x1800061e3  jz      short loc_18000620E
0x1800061e5  xor     eax, eax
0x1800061e7  mov     rcx, [rbp+180h+var_30]
0x1800061ee  xor     rcx, rsp; StackCookie
0x1800061f1  call    __security_check_cookie
0x1800061f6  mov     rbx, [rsp+280h+arg_10]
0x1800061fe  add     rsp, 260h
0x180006205  pop     r15
0x180006207  pop     r14
0x180006209  pop     rdi
0x18000620a  pop     rsi
0x18000620b  pop     rbp
0x18000620c  retn
0x18000620e  mov     rcx, [rbp+188h]; this
0x180006215  mov     edx, 0A0Bh; void *
0x18000621a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006220  mov     rcx, [rbp+188h]; this
0x180006227  mov     edx, 0A0Bh; void *
0x18000622c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006232  mov     rcx, [rbp+188h]; this
0x180006239  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006240  mov     edx, 0E01h; void *
0x180006245  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000624b  mov     rcx, [rbp+188h]; this
0x180006252  mov     edx, 0A15h; void *
0x180006257  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000625d  mov     rcx, [rbp+188h]; this
0x180006264  mov     edx, 0A0Bh; void *
0x180006269  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000626f  mov     rcx, [rbp+188h]; this
0x180006276  mov     edx, 0A15h; void *
0x18000627b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006281  mov     rcx, [rbp+188h]; this
0x180006288  mov     edx, 0A15h; void *
0x18000628d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
