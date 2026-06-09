# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003f58`
- end: `0x1800042f6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005780`

## callees

- `0x180001d30`
- `0x1800027c8`
- `0x180003f58`
- `0x1800046cc`
- `0x180004be8`
- `0x180005518`
- `0x1800061f8`
- `0x1800077c4`
- `0x1800082b8`
- `0x18000871c`
- `0x180008fcc`
- `0x180008fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003fd0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003fd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ff1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ff1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004072`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000419b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000420b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004072`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000419b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000420b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004179`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004179`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000416b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000416b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003f91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003f91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004083`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004145`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000415d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004221`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004083`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004145`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000415d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004221`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x180003f58  mov     [rsp-8+arg_10], rbx
0x180003f5d  push    rbp
0x180003f5e  push    rsi
0x180003f5f  push    rdi
0x180003f60  push    r14
0x180003f62  push    r15
0x180003f64  lea     rbp, [rsp-160h]
0x180003f6c  sub     rsp, 260h
0x180003f73  mov     rax, cs:__security_cookie
0x180003f7a  xor     rax, rsp
0x180003f7d  mov     [rbp+180h+var_30], rax
0x180003f84  mov     r15, rdx
0x180003f87  mov     qword ptr [rdx], 0
0x180003f8e  mov     rbx, rcx
0x180003f91  call    cs:__imp_GetCurrentProcessId
0x180003f97  mov     r14d, 78h ; 'x'
0x180003f9d  mov     [rsp+280h+var_258], rbx
0x180003fa2  mov     r9d, eax
0x180003fa5  mov     [rsp+280h+var_260], r14d; int
0x180003faa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003fb1  mov     edx, 104h; unsigned __int64
0x180003fb6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003fbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003fc0  mov     r9d, 1F0001h; dwDesiredAccess
0x180003fc6  lea     rdx, [rsp+280h+Name]; lpName
0x180003fcb  xor     r8d, r8d; dwFlags
0x180003fce  xor     ecx, ecx; lpMutexAttributes
0x180003fd0  call    cs:__imp_CreateMutexExW
0x180003fd6  mov     rbx, rax
0x180003fd9  test    rax, rax
0x180003fdc  jnz     short loc_180003FE8
0x180003fde  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003fe3  jmp     loc_18000422D
0x180003fe8  xor     r8d, r8d; bAlertable
0x180003feb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003fee  mov     rcx, rbx; hHandle
0x180003ff1  call    cs:__imp_WaitForSingleObjectEx
0x180003ff7  cmp     eax, 102h
0x180003ffc  jz      short loc_18000400E
0x180003ffe  test    eax, 0FFFFFF7Fh
0x180004003  jnz     loc_180004265
0x180004009  mov     rdi, rbx
0x18000400c  jmp     short loc_180004010
0x18000400e  xor     edi, edi
0x180004010  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004015  mov     [rsp+280h+hObject], 0
0x18000401e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004023  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004028  mov     esi, eax
0x18000402a  test    eax, eax
0x18000402c  jns     short loc_180004098
0x18000402e  mov     rcx, [rbp+188h]; this
0x180004035  mov     r9d, eax; char *
0x180004038  mov     edx, 66h ; 'f'; void *
0x18000403d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004042  mov     rcx, [rbp+188h]; this
0x180004049  mov     r9d, esi; char *
0x18000404c  mov     edx, 6Fh ; 'o'; void *
0x180004051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004056  mov     rcx, [rbp+188h]; this
0x18000405d  mov     r9d, esi; char *
0x180004060  mov     edx, 12Eh; void *
0x180004065  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000406a  test    rdi, rdi
0x18000406d  jz      short loc_180004080
0x18000406f  mov     rcx, rdi; hMutex
0x180004072  call    cs:__imp_ReleaseMutex
0x180004078  test    eax, eax
0x18000407a  jz      loc_180004272
0x180004080  mov     rcx, rbx; hObject
0x180004083  call    cs:__imp_CloseHandle
0x180004089  test    eax, eax
0x18000408b  jz      loc_180004284
0x180004091  mov     eax, esi
0x180004093  jmp     loc_18000422D
0x180004098  mov     rax, [rsp+280h+hObject]
0x18000409d  lea     rcx, ds:0[rax*4]
0x1800040a5  test    rcx, rcx
0x1800040a8  jz      short loc_1800040B8
0x1800040aa  mov     [r15], rcx
0x1800040ad  mov     eax, [rcx]
0x1800040af  inc     eax
0x1800040b1  mov     [rcx], eax
0x1800040b3  jmp     loc_180004203
0x1800040b8  mov     rdx, r14; dwBytes
0x1800040bb  mov     qword ptr [r15], 0
0x1800040c2  mov     ecx, 8; dwFlags
0x1800040c7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800040cc  mov     rsi, rax
0x1800040cf  test    rax, rax
0x1800040d2  jnz     short loc_1800040F3
0x1800040d4  mov     rcx, [rbp+188h]; this
0x1800040db  mov     r14d, 8007000Eh
0x1800040e1  mov     r9d, r14d; char *
0x1800040e4  mov     edx, 14Bh; void *
0x1800040e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040ee  jmp     loc_18000417F
0x1800040f3  xorps   xmm0, xmm0
0x1800040f6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800040fc  test    sil, 3
0x180004100  jnz     loc_180004296
0x180004106  mov     r9, rsi
0x180004109  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000410e  shr     r9, 2; unsigned __int64
0x180004112  lea     rcx, [rsp+280h+hObject]; this
0x180004117  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000411c  mov     r14d, eax
0x18000411f  test    eax, eax
0x180004121  jns     loc_1800041BF
0x180004127  mov     rcx, [rbp+188h]; this
0x18000412e  mov     r9d, eax; char *
0x180004131  mov     edx, 14Eh; void *
0x180004136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000413b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004140  test    rcx, rcx
0x180004143  jz      short loc_180004153
0x180004145  call    cs:__imp_CloseHandle
0x18000414b  test    eax, eax
0x18000414d  jz      loc_18000429C
0x180004153  mov     rcx, [rsp+280h+hObject]; hObject
0x180004158  test    rcx, rcx
0x18000415b  jz      short loc_18000416B
0x18000415d  call    cs:__imp_CloseHandle
0x180004163  test    eax, eax
0x180004165  jz      loc_1800042AE
0x18000416b  call    cs:__imp_GetProcessHeap
0x180004171  mov     r8, rsi; lpMem
0x180004174  xor     edx, edx; dwFlags
0x180004176  mov     rcx, rax; hHeap
0x180004179  call    cs:__imp_HeapFree
0x18000417f  mov     rcx, [rbp+188h]; this
0x180004186  mov     r9d, r14d; char *
0x180004189  mov     edx, 137h; void *
0x18000418e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004193  test    rdi, rdi
0x180004196  jz      short loc_1800041A9
0x180004198  mov     rcx, rdi; hMutex
0x18000419b  call    cs:__imp_ReleaseMutex
0x1800041a1  test    eax, eax
0x1800041a3  jz      loc_1800042C0
0x1800041a9  mov     rcx, rbx; hObject
0x1800041ac  call    cs:__imp_CloseHandle
0x1800041b2  test    eax, eax
0x1800041b4  jz      loc_1800042D2
0x1800041ba  mov     eax, r14d
0x1800041bd  jmp     short loc_18000422D
0x1800041bf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800041c4  xor     edx, edx; Val
0x1800041c6  mov     dword ptr [rsi], 1
0x1800041cc  lea     rcx, [rsi+22h]; void *
0x1800041d0  mov     [rsi+8], rbx
0x1800041d4  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800041d9  lea     r8d, [rdx+56h]; Size
0x1800041dd  call    memset_0
0x1800041e2  xor     edx, edx; Val
0x1800041e4  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800041ea  lea     rcx, [rsi+28h]; void *
0x1800041ee  mov     dword ptr [rsi+24h], 1
0x1800041f5  lea     r8d, [rdx+50h]; Size
0x1800041f9  call    memset_0
0x1800041fe  xor     ebx, ebx
0x180004200  mov     [r15], rsi
0x180004203  test    rdi, rdi
0x180004206  jz      short loc_180004219
0x180004208  mov     rcx, rdi; hMutex
0x18000420b  call    cs:__imp_ReleaseMutex
0x180004211  test    eax, eax
0x180004213  jz      loc_1800042E4
0x180004219  test    rbx, rbx
0x18000421c  jz      short loc_18000422B
0x18000421e  mov     rcx, rbx; hObject
0x180004221  call    cs:__imp_CloseHandle
0x180004227  test    eax, eax
0x180004229  jz      short loc_180004253
0x18000422b  xor     eax, eax
0x18000422d  mov     rcx, [rbp+180h+var_30]
0x180004234  xor     rcx, rsp; StackCookie
0x180004237  call    __security_check_cookie
0x18000423c  mov     rbx, [rsp+280h+arg_10]
0x180004244  add     rsp, 260h
0x18000424b  pop     r15
0x18000424d  pop     r14
0x18000424f  pop     rdi
0x180004250  pop     rsi
0x180004251  pop     rbp
0x180004252  retn
0x180004253  mov     rcx, [rbp+188h]; this
0x18000425a  mov     edx, 0A0Bh; void *
0x18000425f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004265  mov     rcx, [rbp+188h]; this
0x18000426c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004272  mov     rcx, [rbp+188h]; this
0x180004279  mov     edx, 0A15h; void *
0x18000427e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004284  mov     rcx, [rbp+188h]; this
0x18000428b  mov     edx, 0A0Bh; void *
0x180004290  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004296  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000429c  mov     rcx, [rbp+188h]; this
0x1800042a3  mov     edx, 0A0Bh; void *
0x1800042a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042ae  mov     rcx, [rbp+188h]; this
0x1800042b5  mov     edx, 0A0Bh; void *
0x1800042ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042c0  mov     rcx, [rbp+188h]; this
0x1800042c7  mov     edx, 0A15h; void *
0x1800042cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042d2  mov     rcx, [rbp+188h]; this
0x1800042d9  mov     edx, 0A0Bh; void *
0x1800042de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042e4  mov     rcx, [rbp+188h]; this
0x1800042eb  mov     edx, 0A15h; void *
0x1800042f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
