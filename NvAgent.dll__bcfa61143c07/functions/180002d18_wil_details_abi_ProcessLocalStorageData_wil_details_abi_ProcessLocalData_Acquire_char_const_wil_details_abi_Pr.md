# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180002d18`
- end: `0x1800030b6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180003b90`

## callees

- `0x180001590`
- `0x180001f4a`
- `0x180002d18`
- `0x1800030bc`
- `0x1800032e0`
- `0x180003928`
- `0x1800043f8`
- `0x1800046d4`
- `0x180005060`
- `0x18000513c`
- `0x1800054ec`
- `0x1800054fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002d90`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002d90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002db1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002e32`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002f5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002fcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002e32`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002f5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002fcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002d51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002d51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002e43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002e43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fe1`

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
0x180002d18  mov     [rsp-8+arg_10], rbx
0x180002d1d  push    rbp
0x180002d1e  push    rsi
0x180002d1f  push    rdi
0x180002d20  push    r14
0x180002d22  push    r15
0x180002d24  lea     rbp, [rsp-160h]
0x180002d2c  sub     rsp, 260h
0x180002d33  mov     rax, cs:__security_cookie
0x180002d3a  xor     rax, rsp
0x180002d3d  mov     [rbp+180h+var_30], rax
0x180002d44  mov     r15, rdx
0x180002d47  mov     qword ptr [rdx], 0
0x180002d4e  mov     rbx, rcx
0x180002d51  call    cs:__imp_GetCurrentProcessId
0x180002d57  mov     r14d, 78h ; 'x'
0x180002d5d  mov     [rsp+280h+var_258], rbx
0x180002d62  mov     r9d, eax
0x180002d65  mov     [rsp+280h+var_260], r14d; int
0x180002d6a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180002d71  mov     edx, 104h; unsigned __int64
0x180002d76  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180002d7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002d80  mov     r9d, 1F0001h; dwDesiredAccess
0x180002d86  lea     rdx, [rsp+280h+Name]; lpName
0x180002d8b  xor     r8d, r8d; dwFlags
0x180002d8e  xor     ecx, ecx; lpMutexAttributes
0x180002d90  call    cs:__imp_CreateMutexExW
0x180002d96  mov     rbx, rax
0x180002d99  test    rax, rax
0x180002d9c  jnz     short loc_180002DA8
0x180002d9e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180002da3  jmp     loc_180002FED
0x180002da8  xor     r8d, r8d; bAlertable
0x180002dab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002dae  mov     rcx, rbx; hHandle
0x180002db1  call    cs:__imp_WaitForSingleObjectEx
0x180002db7  cmp     eax, 102h
0x180002dbc  jz      short loc_180002DCE
0x180002dbe  test    eax, 0FFFFFF7Fh
0x180002dc3  jnz     loc_180003025
0x180002dc9  mov     rdi, rbx
0x180002dcc  jmp     short loc_180002DD0
0x180002dce  xor     edi, edi
0x180002dd0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180002dd5  mov     [rsp+280h+hObject], 0
0x180002dde  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180002de3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180002de8  mov     esi, eax
0x180002dea  test    eax, eax
0x180002dec  jns     short loc_180002E58
0x180002dee  mov     rcx, [rbp+188h]; this
0x180002df5  mov     r9d, eax; char *
0x180002df8  mov     edx, 66h ; 'f'; void *
0x180002dfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e02  mov     rcx, [rbp+188h]; this
0x180002e09  mov     r9d, esi; char *
0x180002e0c  mov     edx, 6Fh ; 'o'; void *
0x180002e11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e16  mov     rcx, [rbp+188h]; this
0x180002e1d  mov     r9d, esi; char *
0x180002e20  mov     edx, 12Eh; void *
0x180002e25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e2a  test    rdi, rdi
0x180002e2d  jz      short loc_180002E40
0x180002e2f  mov     rcx, rdi; hMutex
0x180002e32  call    cs:__imp_ReleaseMutex
0x180002e38  test    eax, eax
0x180002e3a  jz      loc_180003032
0x180002e40  mov     rcx, rbx; hObject
0x180002e43  call    cs:__imp_CloseHandle
0x180002e49  test    eax, eax
0x180002e4b  jz      loc_180003044
0x180002e51  mov     eax, esi
0x180002e53  jmp     loc_180002FED
0x180002e58  mov     rax, [rsp+280h+hObject]
0x180002e5d  lea     rcx, ds:0[rax*4]
0x180002e65  test    rcx, rcx
0x180002e68  jz      short loc_180002E78
0x180002e6a  mov     [r15], rcx
0x180002e6d  mov     eax, [rcx]
0x180002e6f  inc     eax
0x180002e71  mov     [rcx], eax
0x180002e73  jmp     loc_180002FC3
0x180002e78  mov     rdx, r14; dwBytes
0x180002e7b  mov     qword ptr [r15], 0
0x180002e82  mov     ecx, 8; dwFlags
0x180002e87  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180002e8c  mov     rsi, rax
0x180002e8f  test    rax, rax
0x180002e92  jnz     short loc_180002EB3
0x180002e94  mov     rcx, [rbp+188h]; this
0x180002e9b  mov     r14d, 8007000Eh
0x180002ea1  mov     r9d, r14d; char *
0x180002ea4  mov     edx, 14Bh; void *
0x180002ea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002eae  jmp     loc_180002F3F
0x180002eb3  xorps   xmm0, xmm0
0x180002eb6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180002ebc  test    sil, 3
0x180002ec0  jnz     loc_180003056
0x180002ec6  mov     r9, rsi
0x180002ec9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180002ece  shr     r9, 2; unsigned __int64
0x180002ed2  lea     rcx, [rsp+280h+hObject]; this
0x180002ed7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180002edc  mov     r14d, eax
0x180002edf  test    eax, eax
0x180002ee1  jns     loc_180002F7F
0x180002ee7  mov     rcx, [rbp+188h]; this
0x180002eee  mov     r9d, eax; char *
0x180002ef1  mov     edx, 14Eh; void *
0x180002ef6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002efb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180002f00  test    rcx, rcx
0x180002f03  jz      short loc_180002F13
0x180002f05  call    cs:__imp_CloseHandle
0x180002f0b  test    eax, eax
0x180002f0d  jz      loc_18000305C
0x180002f13  mov     rcx, [rsp+280h+hObject]; hObject
0x180002f18  test    rcx, rcx
0x180002f1b  jz      short loc_180002F2B
0x180002f1d  call    cs:__imp_CloseHandle
0x180002f23  test    eax, eax
0x180002f25  jz      loc_18000306E
0x180002f2b  call    cs:__imp_GetProcessHeap
0x180002f31  mov     r8, rsi; lpMem
0x180002f34  xor     edx, edx; dwFlags
0x180002f36  mov     rcx, rax; hHeap
0x180002f39  call    cs:__imp_HeapFree
0x180002f3f  mov     rcx, [rbp+188h]; this
0x180002f46  mov     r9d, r14d; char *
0x180002f49  mov     edx, 137h; void *
0x180002f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002f53  test    rdi, rdi
0x180002f56  jz      short loc_180002F69
0x180002f58  mov     rcx, rdi; hMutex
0x180002f5b  call    cs:__imp_ReleaseMutex
0x180002f61  test    eax, eax
0x180002f63  jz      loc_180003080
0x180002f69  mov     rcx, rbx; hObject
0x180002f6c  call    cs:__imp_CloseHandle
0x180002f72  test    eax, eax
0x180002f74  jz      loc_180003092
0x180002f7a  mov     eax, r14d
0x180002f7d  jmp     short loc_180002FED
0x180002f7f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180002f84  xor     edx, edx; Val
0x180002f86  mov     dword ptr [rsi], 1
0x180002f8c  lea     rcx, [rsi+22h]; void *
0x180002f90  mov     [rsi+8], rbx
0x180002f94  movdqu  xmmword ptr [rsi+10h], xmm0
0x180002f99  lea     r8d, [rdx+56h]; Size
0x180002f9d  call    memset_0
0x180002fa2  xor     edx, edx; Val
0x180002fa4  mov     word ptr [rsi+20h], 58h ; 'X'
0x180002faa  lea     rcx, [rsi+28h]; void *
0x180002fae  mov     dword ptr [rsi+24h], 1
0x180002fb5  lea     r8d, [rdx+50h]; Size
0x180002fb9  call    memset_0
0x180002fbe  xor     ebx, ebx
0x180002fc0  mov     [r15], rsi
0x180002fc3  test    rdi, rdi
0x180002fc6  jz      short loc_180002FD9
0x180002fc8  mov     rcx, rdi; hMutex
0x180002fcb  call    cs:__imp_ReleaseMutex
0x180002fd1  test    eax, eax
0x180002fd3  jz      loc_1800030A4
0x180002fd9  test    rbx, rbx
0x180002fdc  jz      short loc_180002FEB
0x180002fde  mov     rcx, rbx; hObject
0x180002fe1  call    cs:__imp_CloseHandle
0x180002fe7  test    eax, eax
0x180002fe9  jz      short loc_180003013
0x180002feb  xor     eax, eax
0x180002fed  mov     rcx, [rbp+180h+var_30]
0x180002ff4  xor     rcx, rsp; StackCookie
0x180002ff7  call    __security_check_cookie
0x180002ffc  mov     rbx, [rsp+280h+arg_10]
0x180003004  add     rsp, 260h
0x18000300b  pop     r15
0x18000300d  pop     r14
0x18000300f  pop     rdi
0x180003010  pop     rsi
0x180003011  pop     rbp
0x180003012  retn
0x180003013  mov     rcx, [rbp+188h]; this
0x18000301a  mov     edx, 0A0Bh; void *
0x18000301f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003025  mov     rcx, [rbp+188h]; this
0x18000302c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003032  mov     rcx, [rbp+188h]; this
0x180003039  mov     edx, 0A15h; void *
0x18000303e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003044  mov     rcx, [rbp+188h]; this
0x18000304b  mov     edx, 0A0Bh; void *
0x180003050  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003056  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000305c  mov     rcx, [rbp+188h]; this
0x180003063  mov     edx, 0A0Bh; void *
0x180003068  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000306e  mov     rcx, [rbp+188h]; this
0x180003075  mov     edx, 0A0Bh; void *
0x18000307a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003080  mov     rcx, [rbp+188h]; this
0x180003087  mov     edx, 0A15h; void *
0x18000308c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003092  mov     rcx, [rbp+188h]; this
0x180003099  mov     edx, 0A0Bh; void *
0x18000309e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800030a4  mov     rcx, [rbp+188h]; this
0x1800030ab  mov     edx, 0A15h; void *
0x1800030b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
