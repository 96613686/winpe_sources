# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003b08`
- end: `0x180003ed0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800049d0`

## callees

- `0x180001e20`
- `0x180002ac8`
- `0x180003b08`
- `0x180003ed8`
- `0x180004120`
- `0x180004768`
- `0x180005248`
- `0x180005524`
- `0x180005f14`
- `0x180005fcc`
- `0x18000638c`
- `0x18000639c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ba1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ba1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b80`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b80`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003de5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003de5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dfb`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
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
0x180003b08  mov     [rsp-8+arg_10], rbx
0x180003b0d  push    rbp
0x180003b0e  push    rsi
0x180003b0f  push    rdi
0x180003b10  push    r14
0x180003b12  push    r15
0x180003b14  lea     rbp, [rsp-160h]
0x180003b1c  sub     rsp, 260h
0x180003b23  mov     rax, cs:__security_cookie
0x180003b2a  xor     rax, rsp
0x180003b2d  mov     [rbp+180h+var_30], rax
0x180003b34  mov     r15, rdx
0x180003b37  mov     qword ptr [rdx], 0
0x180003b3e  mov     rbx, rcx
0x180003b41  call    cs:__imp_GetCurrentProcessId
0x180003b47  mov     r14d, 78h ; 'x'
0x180003b4d  mov     [rsp+280h+var_258], rbx
0x180003b52  mov     r9d, eax
0x180003b55  mov     [rsp+280h+var_260], r14d; int
0x180003b5a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003b61  mov     edx, 104h; unsigned __int64
0x180003b66  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b6b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003b70  mov     r9d, 1F0001h; dwDesiredAccess
0x180003b76  lea     rdx, [rsp+280h+Name]; lpName
0x180003b7b  xor     r8d, r8d; dwFlags
0x180003b7e  xor     ecx, ecx; lpMutexAttributes
0x180003b80  call    cs:__imp_CreateMutexExW
0x180003b86  mov     rbx, rax
0x180003b89  test    rax, rax
0x180003b8c  jnz     short loc_180003B98
0x180003b8e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b93  jmp     loc_180003E07
0x180003b98  xor     r8d, r8d; bAlertable
0x180003b9b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003b9e  mov     rcx, rbx; hHandle
0x180003ba1  call    cs:__imp_WaitForSingleObjectEx
0x180003ba7  cmp     eax, 102h
0x180003bac  jz      short loc_180003BBE
0x180003bae  test    eax, 0FFFFFF7Fh
0x180003bb3  jnz     loc_180003E3F
0x180003bb9  mov     rdi, rbx
0x180003bbc  jmp     short loc_180003BC0
0x180003bbe  xor     edi, edi
0x180003bc0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003bc5  mov     [rsp+280h+hObject], 0
0x180003bce  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003bd3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003bd8  mov     esi, eax
0x180003bda  test    eax, eax
0x180003bdc  jns     short loc_180003C5D
0x180003bde  mov     rcx, [rbp+188h]; this
0x180003be5  lea     r8, aWil; "wil"
0x180003bec  mov     r9d, eax; char *
0x180003bef  mov     edx, 66h ; 'f'; void *
0x180003bf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bf9  mov     rcx, [rbp+188h]; this
0x180003c00  lea     r8, aWil; "wil"
0x180003c07  mov     r9d, esi; char *
0x180003c0a  mov     edx, 6Fh ; 'o'; void *
0x180003c0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c14  mov     rcx, [rbp+188h]; this
0x180003c1b  lea     r8, aWil; "wil"
0x180003c22  mov     r9d, esi; char *
0x180003c25  mov     edx, 12Eh; void *
0x180003c2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c2f  test    rdi, rdi
0x180003c32  jz      short loc_180003C45
0x180003c34  mov     rcx, rdi; hMutex
0x180003c37  call    cs:__imp_ReleaseMutex
0x180003c3d  test    eax, eax
0x180003c3f  jz      loc_180003E4C
0x180003c45  mov     rcx, rbx; hObject
0x180003c48  call    cs:__imp_CloseHandle
0x180003c4e  test    eax, eax
0x180003c50  jz      loc_180003E5E
0x180003c56  mov     eax, esi
0x180003c58  jmp     loc_180003E07
0x180003c5d  mov     rax, [rsp+280h+hObject]
0x180003c62  lea     rcx, ds:0[rax*4]
0x180003c6a  test    rcx, rcx
0x180003c6d  jz      short loc_180003C7D
0x180003c6f  mov     [r15], rcx
0x180003c72  mov     eax, [rcx]
0x180003c74  inc     eax
0x180003c76  mov     [rcx], eax
0x180003c78  jmp     loc_180003DDD
0x180003c7d  mov     rdx, r14; dwBytes
0x180003c80  mov     qword ptr [r15], 0
0x180003c87  mov     ecx, 8; dwFlags
0x180003c8c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003c91  mov     rsi, rax
0x180003c94  test    rax, rax
0x180003c97  jnz     short loc_180003CBF
0x180003c99  mov     rcx, [rbp+188h]; this
0x180003ca0  lea     r8, aWil; "wil"
0x180003ca7  mov     r14d, 8007000Eh
0x180003cad  mov     edx, 14Bh; void *
0x180003cb2  mov     r9d, r14d; char *
0x180003cb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cba  jmp     loc_180003D52
0x180003cbf  xorps   xmm0, xmm0
0x180003cc2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003cc8  test    sil, 3
0x180003ccc  jnz     loc_180003E70
0x180003cd2  mov     r9, rsi
0x180003cd5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003cda  shr     r9, 2; unsigned __int64
0x180003cde  lea     rcx, [rsp+280h+hObject]; this
0x180003ce3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003ce8  mov     r14d, eax
0x180003ceb  test    eax, eax
0x180003ced  jns     loc_180003D99
0x180003cf3  mov     rcx, [rbp+188h]; this
0x180003cfa  lea     r8, aWil; "wil"
0x180003d01  mov     r9d, eax; char *
0x180003d04  mov     edx, 14Eh; void *
0x180003d09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d0e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003d13  test    rcx, rcx
0x180003d16  jz      short loc_180003D26
0x180003d18  call    cs:__imp_CloseHandle
0x180003d1e  test    eax, eax
0x180003d20  jz      loc_180003E76
0x180003d26  mov     rcx, [rsp+280h+hObject]; hObject
0x180003d2b  test    rcx, rcx
0x180003d2e  jz      short loc_180003D3E
0x180003d30  call    cs:__imp_CloseHandle
0x180003d36  test    eax, eax
0x180003d38  jz      loc_180003E88
0x180003d3e  call    cs:__imp_GetProcessHeap
0x180003d44  mov     r8, rsi; lpMem
0x180003d47  xor     edx, edx; dwFlags
0x180003d49  mov     rcx, rax; hHeap
0x180003d4c  call    cs:__imp_HeapFree
0x180003d52  mov     rcx, [rbp+188h]; this
0x180003d59  lea     r8, aWil; "wil"
0x180003d60  mov     r9d, r14d; char *
0x180003d63  mov     edx, 137h; void *
0x180003d68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d6d  test    rdi, rdi
0x180003d70  jz      short loc_180003D83
0x180003d72  mov     rcx, rdi; hMutex
0x180003d75  call    cs:__imp_ReleaseMutex
0x180003d7b  test    eax, eax
0x180003d7d  jz      loc_180003E9A
0x180003d83  mov     rcx, rbx; hObject
0x180003d86  call    cs:__imp_CloseHandle
0x180003d8c  test    eax, eax
0x180003d8e  jz      loc_180003EAC
0x180003d94  mov     eax, r14d
0x180003d97  jmp     short loc_180003E07
0x180003d99  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003d9e  xor     edx, edx; Val
0x180003da0  mov     dword ptr [rsi], 1
0x180003da6  lea     rcx, [rsi+22h]; void *
0x180003daa  mov     [rsi+8], rbx
0x180003dae  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003db3  lea     r8d, [rdx+56h]; Size
0x180003db7  call    memset_0
0x180003dbc  xor     edx, edx; Val
0x180003dbe  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003dc4  lea     rcx, [rsi+28h]; void *
0x180003dc8  mov     dword ptr [rsi+24h], 1
0x180003dcf  lea     r8d, [rdx+50h]; Size
0x180003dd3  call    memset_0
0x180003dd8  xor     ebx, ebx
0x180003dda  mov     [r15], rsi
0x180003ddd  test    rdi, rdi
0x180003de0  jz      short loc_180003DF3
0x180003de2  mov     rcx, rdi; hMutex
0x180003de5  call    cs:__imp_ReleaseMutex
0x180003deb  test    eax, eax
0x180003ded  jz      loc_180003EBE
0x180003df3  test    rbx, rbx
0x180003df6  jz      short loc_180003E05
0x180003df8  mov     rcx, rbx; hObject
0x180003dfb  call    cs:__imp_CloseHandle
0x180003e01  test    eax, eax
0x180003e03  jz      short loc_180003E2D
0x180003e05  xor     eax, eax
0x180003e07  mov     rcx, [rbp+180h+var_30]
0x180003e0e  xor     rcx, rsp; StackCookie
0x180003e11  call    __security_check_cookie
0x180003e16  mov     rbx, [rsp+280h+arg_10]
0x180003e1e  add     rsp, 260h
0x180003e25  pop     r15
0x180003e27  pop     r14
0x180003e29  pop     rdi
0x180003e2a  pop     rsi
0x180003e2b  pop     rbp
0x180003e2c  retn
0x180003e2d  mov     rcx, [rbp+188h]; this
0x180003e34  mov     edx, 0A0Bh; void *
0x180003e39  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e3f  mov     rcx, [rbp+188h]; this
0x180003e46  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003e4c  mov     rcx, [rbp+188h]; this
0x180003e53  mov     edx, 0A15h; void *
0x180003e58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e5e  mov     rcx, [rbp+188h]; this
0x180003e65  mov     edx, 0A0Bh; void *
0x180003e6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e70  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003e76  mov     rcx, [rbp+188h]; this
0x180003e7d  mov     edx, 0A0Bh; void *
0x180003e82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e88  mov     rcx, [rbp+188h]; this
0x180003e8f  mov     edx, 0A0Bh; void *
0x180003e94  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e9a  mov     rcx, [rbp+188h]; this
0x180003ea1  mov     edx, 0A15h; void *
0x180003ea6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003eac  mov     rcx, [rbp+188h]; this
0x180003eb3  mov     edx, 0A0Bh; void *
0x180003eb8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ebe  mov     rcx, [rbp+188h]; this
0x180003ec5  mov     edx, 0A15h; void *
0x180003eca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
