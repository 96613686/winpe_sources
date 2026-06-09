# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009f58`
- end: `0x18000a320`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000af74`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x180009f58`
- `0x18000a328`
- `0x18000a614`
- `0x18000ac68`
- `0x18000b7e8`
- `0x18000bbd4`
- `0x18000c638`
- `0x18000c71c`
- `0x18000cba8`
- `0x18000cbb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009ff1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009ff1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009fd0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009fd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a087`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a235`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a087`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a235`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a18e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a18e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a19c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a19c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009f91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009f91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a168`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a24b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a168`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a24b`

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
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180009f58  mov     [rsp-8+arg_10], rbx
0x180009f5d  push    rbp
0x180009f5e  push    rsi
0x180009f5f  push    rdi
0x180009f60  push    r14
0x180009f62  push    r15
0x180009f64  lea     rbp, [rsp-160h]
0x180009f6c  sub     rsp, 260h
0x180009f73  mov     rax, cs:__security_cookie
0x180009f7a  xor     rax, rsp
0x180009f7d  mov     [rbp+180h+var_30], rax
0x180009f84  mov     r15, rdx
0x180009f87  mov     qword ptr [rdx], 0
0x180009f8e  mov     rbx, rcx
0x180009f91  call    cs:__imp_GetCurrentProcessId
0x180009f97  mov     r14d, 78h ; 'x'
0x180009f9d  mov     [rsp+280h+var_258], rbx
0x180009fa2  mov     r9d, eax
0x180009fa5  mov     [rsp+280h+var_260], r14d; int
0x180009faa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009fb1  mov     edx, 104h; unsigned __int64
0x180009fb6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009fbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009fc0  mov     r9d, 1F0001h; dwDesiredAccess
0x180009fc6  lea     rdx, [rsp+280h+Name]; lpName
0x180009fcb  xor     r8d, r8d; dwFlags
0x180009fce  xor     ecx, ecx; lpMutexAttributes
0x180009fd0  call    cs:__imp_CreateMutexExW
0x180009fd6  mov     rbx, rax
0x180009fd9  test    rax, rax
0x180009fdc  jnz     short loc_180009FE8
0x180009fde  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009fe3  jmp     loc_18000A257
0x180009fe8  xor     r8d, r8d; bAlertable
0x180009feb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009fee  mov     rcx, rbx; hHandle
0x180009ff1  call    cs:__imp_WaitForSingleObjectEx
0x180009ff7  cmp     eax, 102h
0x180009ffc  jz      short loc_18000A00E
0x180009ffe  test    eax, 0FFFFFF7Fh
0x18000a003  jnz     loc_18000A28F
0x18000a009  mov     rdi, rbx
0x18000a00c  jmp     short loc_18000A010
0x18000a00e  xor     edi, edi
0x18000a010  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000a015  mov     [rsp+280h+hObject], 0
0x18000a01e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a023  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a028  mov     esi, eax
0x18000a02a  test    eax, eax
0x18000a02c  jns     short loc_18000A0AD
0x18000a02e  mov     rcx, [rbp+188h]; this
0x18000a035  lea     r8, aWil; "wil"
0x18000a03c  mov     r9d, eax; char *
0x18000a03f  mov     edx, 66h ; 'f'; void *
0x18000a044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a049  mov     rcx, [rbp+188h]; this
0x18000a050  lea     r8, aWil; "wil"
0x18000a057  mov     r9d, esi; char *
0x18000a05a  mov     edx, 6Fh ; 'o'; void *
0x18000a05f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a064  mov     rcx, [rbp+188h]; this
0x18000a06b  lea     r8, aWil; "wil"
0x18000a072  mov     r9d, esi; char *
0x18000a075  mov     edx, 12Eh; void *
0x18000a07a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a07f  test    rdi, rdi
0x18000a082  jz      short loc_18000A095
0x18000a084  mov     rcx, rdi; hMutex
0x18000a087  call    cs:__imp_ReleaseMutex
0x18000a08d  test    eax, eax
0x18000a08f  jz      loc_18000A29C
0x18000a095  mov     rcx, rbx; hObject
0x18000a098  call    cs:__imp_CloseHandle
0x18000a09e  test    eax, eax
0x18000a0a0  jz      loc_18000A2AE
0x18000a0a6  mov     eax, esi
0x18000a0a8  jmp     loc_18000A257
0x18000a0ad  mov     rax, [rsp+280h+hObject]
0x18000a0b2  lea     rcx, ds:0[rax*4]
0x18000a0ba  test    rcx, rcx
0x18000a0bd  jz      short loc_18000A0CD
0x18000a0bf  mov     [r15], rcx
0x18000a0c2  mov     eax, [rcx]
0x18000a0c4  inc     eax
0x18000a0c6  mov     [rcx], eax
0x18000a0c8  jmp     loc_18000A22D
0x18000a0cd  mov     rdx, r14; dwBytes
0x18000a0d0  mov     qword ptr [r15], 0
0x18000a0d7  mov     ecx, 8; dwFlags
0x18000a0dc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a0e1  mov     rsi, rax
0x18000a0e4  test    rax, rax
0x18000a0e7  jnz     short loc_18000A10F
0x18000a0e9  mov     rcx, [rbp+188h]; this
0x18000a0f0  lea     r8, aWil; "wil"
0x18000a0f7  mov     r14d, 8007000Eh
0x18000a0fd  mov     edx, 14Bh; void *
0x18000a102  mov     r9d, r14d; char *
0x18000a105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a10a  jmp     loc_18000A1A2
0x18000a10f  xorps   xmm0, xmm0
0x18000a112  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000a118  test    sil, 3
0x18000a11c  jnz     loc_18000A2C0
0x18000a122  mov     r9, rsi
0x18000a125  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000a12a  shr     r9, 2; unsigned __int64
0x18000a12e  lea     rcx, [rsp+280h+hObject]; this
0x18000a133  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000a138  mov     r14d, eax
0x18000a13b  test    eax, eax
0x18000a13d  jns     loc_18000A1E9
0x18000a143  mov     rcx, [rbp+188h]; this
0x18000a14a  lea     r8, aWil; "wil"
0x18000a151  mov     r9d, eax; char *
0x18000a154  mov     edx, 14Eh; void *
0x18000a159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a15e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000a163  test    rcx, rcx
0x18000a166  jz      short loc_18000A176
0x18000a168  call    cs:__imp_CloseHandle
0x18000a16e  test    eax, eax
0x18000a170  jz      loc_18000A2C6
0x18000a176  mov     rcx, [rsp+280h+hObject]; hObject
0x18000a17b  test    rcx, rcx
0x18000a17e  jz      short loc_18000A18E
0x18000a180  call    cs:__imp_CloseHandle
0x18000a186  test    eax, eax
0x18000a188  jz      loc_18000A2D8
0x18000a18e  call    cs:__imp_GetProcessHeap
0x18000a194  mov     r8, rsi; lpMem
0x18000a197  xor     edx, edx; dwFlags
0x18000a199  mov     rcx, rax; hHeap
0x18000a19c  call    cs:__imp_HeapFree
0x18000a1a2  mov     rcx, [rbp+188h]; this
0x18000a1a9  lea     r8, aWil; "wil"
0x18000a1b0  mov     r9d, r14d; char *
0x18000a1b3  mov     edx, 137h; void *
0x18000a1b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a1bd  test    rdi, rdi
0x18000a1c0  jz      short loc_18000A1D3
0x18000a1c2  mov     rcx, rdi; hMutex
0x18000a1c5  call    cs:__imp_ReleaseMutex
0x18000a1cb  test    eax, eax
0x18000a1cd  jz      loc_18000A2EA
0x18000a1d3  mov     rcx, rbx; hObject
0x18000a1d6  call    cs:__imp_CloseHandle
0x18000a1dc  test    eax, eax
0x18000a1de  jz      loc_18000A2FC
0x18000a1e4  mov     eax, r14d
0x18000a1e7  jmp     short loc_18000A257
0x18000a1e9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000a1ee  xor     edx, edx; Val
0x18000a1f0  mov     dword ptr [rsi], 1
0x18000a1f6  lea     rcx, [rsi+22h]; void *
0x18000a1fa  mov     [rsi+8], rbx
0x18000a1fe  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000a203  lea     r8d, [rdx+56h]; Size
0x18000a207  call    memset_0
0x18000a20c  xor     edx, edx; Val
0x18000a20e  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000a214  lea     rcx, [rsi+28h]; void *
0x18000a218  mov     dword ptr [rsi+24h], 1
0x18000a21f  lea     r8d, [rdx+50h]; Size
0x18000a223  call    memset_0
0x18000a228  xor     ebx, ebx
0x18000a22a  mov     [r15], rsi
0x18000a22d  test    rdi, rdi
0x18000a230  jz      short loc_18000A243
0x18000a232  mov     rcx, rdi; hMutex
0x18000a235  call    cs:__imp_ReleaseMutex
0x18000a23b  test    eax, eax
0x18000a23d  jz      loc_18000A30E
0x18000a243  test    rbx, rbx
0x18000a246  jz      short loc_18000A255
0x18000a248  mov     rcx, rbx; hObject
0x18000a24b  call    cs:__imp_CloseHandle
0x18000a251  test    eax, eax
0x18000a253  jz      short loc_18000A27D
0x18000a255  xor     eax, eax
0x18000a257  mov     rcx, [rbp+180h+var_30]
0x18000a25e  xor     rcx, rsp; StackCookie
0x18000a261  call    __security_check_cookie
0x18000a266  mov     rbx, [rsp+280h+arg_10]
0x18000a26e  add     rsp, 260h
0x18000a275  pop     r15
0x18000a277  pop     r14
0x18000a279  pop     rdi
0x18000a27a  pop     rsi
0x18000a27b  pop     rbp
0x18000a27c  retn
0x18000a27d  mov     rcx, [rbp+188h]; this
0x18000a284  mov     edx, 0A0Bh; void *
0x18000a289  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a28f  mov     rcx, [rbp+188h]; this
0x18000a296  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a29c  mov     rcx, [rbp+188h]; this
0x18000a2a3  mov     edx, 0A15h; void *
0x18000a2a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2ae  mov     rcx, [rbp+188h]; this
0x18000a2b5  mov     edx, 0A0Bh; void *
0x18000a2ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2c0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a2c6  mov     rcx, [rbp+188h]; this
0x18000a2cd  mov     edx, 0A0Bh; void *
0x18000a2d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2d8  mov     rcx, [rbp+188h]; this
0x18000a2df  mov     edx, 0A0Bh; void *
0x18000a2e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2ea  mov     rcx, [rbp+188h]; this
0x18000a2f1  mov     edx, 0A15h; void *
0x18000a2f6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2fc  mov     rcx, [rbp+188h]; this
0x18000a303  mov     edx, 0A0Bh; void *
0x18000a308  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a30e  mov     rcx, [rbp+188h]; this
0x18000a315  mov     edx, 0A15h; void *
0x18000a31a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
