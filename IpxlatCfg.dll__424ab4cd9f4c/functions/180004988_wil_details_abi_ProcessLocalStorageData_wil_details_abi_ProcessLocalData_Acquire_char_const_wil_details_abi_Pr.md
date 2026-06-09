# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004988`
- end: `0x180004d32`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `938`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800061c0`

## callees

- `0x180001d40`
- `0x180002a28`
- `0x180004988`
- `0x180005114`
- `0x180005638`
- `0x180005f58`
- `0x180006c38`
- `0x1800083b4`
- `0x180008ea8`
- `0x18000930c`
- `0x180009bbc`
- `0x180009bcc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ab3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ab3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ba9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ba9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800049c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800049c1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004a00`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004a00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004a21`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004a21`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004aa2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004bcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004aa2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004bcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c3b`

## string_xrefs

- `0x180004c9c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  __int64 v17; // r8
  const char *v18; // r9
  __int64 v19; // r8
  const char *v20; // r9
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rax
  wil::details::in1diag3 *v23; // rcx
  unsigned int v24; // r8d
  _QWORD *v25; // rsi
  unsigned int v26; // r14d
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
      wil::details::in1diag3::FailFast_Unexpected(
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v45);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
    return v14;
  }
  v21 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_28;
  }
  *a2 = 0;
  v22 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v25 = (_QWORD *)v22;
  if ( v22 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v22 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v24,
            v22 >> 2);
    v26 = v28;
    if ( v28 >= 0 )
    {
      v39 = *(_OWORD *)hObject;
      *(_DWORD *)v25 = 1;
      v25[1] = v6;
      *((_OWORD *)v25 + 1) = v39;
      memset_0((char *)v25 + 34, 0, 0x56u);
      *((_WORD *)v25 + 16) = 88;
      *((_DWORD *)v25 + 9) = 1;
      memset_0(v25 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v25;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
  }
  else
  {
    v26 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v26, v46);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return v26;
}

```

## disassembly

```asm
0x180004988  mov     [rsp-8+arg_10], rbx
0x18000498d  push    rbp
0x18000498e  push    rsi
0x18000498f  push    rdi
0x180004990  push    r14
0x180004992  push    r15
0x180004994  lea     rbp, [rsp-160h]
0x18000499c  sub     rsp, 260h
0x1800049a3  mov     rax, cs:__security_cookie
0x1800049aa  xor     rax, rsp
0x1800049ad  mov     [rbp+180h+var_30], rax
0x1800049b4  mov     r15, rdx
0x1800049b7  mov     qword ptr [rdx], 0
0x1800049be  mov     rbx, rcx
0x1800049c1  call    cs:__imp_GetCurrentProcessId
0x1800049c7  mov     r14d, 78h ; 'x'
0x1800049cd  mov     [rsp+280h+var_258], rbx
0x1800049d2  mov     r9d, eax
0x1800049d5  mov     [rsp+280h+var_260], r14d; int
0x1800049da  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800049e1  mov     edx, 104h; unsigned __int64
0x1800049e6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800049eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800049f0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800049f6  lea     rdx, [rsp+280h+Name]; lpName
0x1800049fb  xor     r8d, r8d; dwFlags
0x1800049fe  xor     ecx, ecx; lpMutexAttributes
0x180004a00  call    cs:__imp_CreateMutexExW
0x180004a06  mov     rbx, rax
0x180004a09  test    rax, rax
0x180004a0c  jnz     short loc_180004A18
0x180004a0e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004a13  jmp     loc_180004C5D
0x180004a18  xor     r8d, r8d; bAlertable
0x180004a1b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004a1e  mov     rcx, rbx; hHandle
0x180004a21  call    cs:__imp_WaitForSingleObjectEx
0x180004a27  cmp     eax, 102h
0x180004a2c  jz      short loc_180004A3E
0x180004a2e  test    eax, 0FFFFFF7Fh
0x180004a33  jnz     loc_180004C95
0x180004a39  mov     rdi, rbx
0x180004a3c  jmp     short loc_180004A40
0x180004a3e  xor     edi, edi
0x180004a40  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004a45  mov     [rsp+280h+hObject], 0
0x180004a4e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004a53  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004a58  mov     esi, eax
0x180004a5a  test    eax, eax
0x180004a5c  jns     short loc_180004AC8
0x180004a5e  mov     rcx, [rbp+188h]; this
0x180004a65  mov     r9d, eax; char *
0x180004a68  mov     edx, 66h ; 'f'; void *
0x180004a6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a72  mov     rcx, [rbp+188h]; this
0x180004a79  mov     r9d, esi; char *
0x180004a7c  mov     edx, 6Fh ; 'o'; void *
0x180004a81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a86  mov     rcx, [rbp+188h]; this
0x180004a8d  mov     r9d, esi; char *
0x180004a90  mov     edx, 12Eh; void *
0x180004a95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a9a  test    rdi, rdi
0x180004a9d  jz      short loc_180004AB0
0x180004a9f  mov     rcx, rdi; hMutex
0x180004aa2  call    cs:__imp_ReleaseMutex
0x180004aa8  test    eax, eax
0x180004aaa  jz      loc_180004CAE
0x180004ab0  mov     rcx, rbx; hObject
0x180004ab3  call    cs:__imp_CloseHandle
0x180004ab9  test    eax, eax
0x180004abb  jz      loc_180004CC0
0x180004ac1  mov     eax, esi
0x180004ac3  jmp     loc_180004C5D
0x180004ac8  mov     rax, [rsp+280h+hObject]
0x180004acd  lea     rcx, ds:0[rax*4]
0x180004ad5  test    rcx, rcx
0x180004ad8  jz      short loc_180004AE8
0x180004ada  mov     [r15], rcx
0x180004add  mov     eax, [rcx]
0x180004adf  inc     eax
0x180004ae1  mov     [rcx], eax
0x180004ae3  jmp     loc_180004C33
0x180004ae8  mov     rdx, r14; dwBytes
0x180004aeb  mov     qword ptr [r15], 0
0x180004af2  mov     ecx, 8; dwFlags
0x180004af7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004afc  mov     rsi, rax
0x180004aff  test    rax, rax
0x180004b02  jnz     short loc_180004B23
0x180004b04  mov     rcx, [rbp+188h]; this
0x180004b0b  mov     r14d, 8007000Eh
0x180004b11  mov     r9d, r14d; char *
0x180004b14  mov     edx, 14Bh; void *
0x180004b19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b1e  jmp     loc_180004BAF
0x180004b23  xorps   xmm0, xmm0
0x180004b26  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004b2c  test    sil, 3
0x180004b30  jnz     loc_180004CD2
0x180004b36  mov     r9, rsi
0x180004b39  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004b3e  shr     r9, 2; unsigned __int64
0x180004b42  lea     rcx, [rsp+280h+hObject]; this
0x180004b47  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004b4c  mov     r14d, eax
0x180004b4f  test    eax, eax
0x180004b51  jns     loc_180004BEF
0x180004b57  mov     rcx, [rbp+188h]; this
0x180004b5e  mov     r9d, eax; char *
0x180004b61  mov     edx, 14Eh; void *
0x180004b66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b6b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004b70  test    rcx, rcx
0x180004b73  jz      short loc_180004B83
0x180004b75  call    cs:__imp_CloseHandle
0x180004b7b  test    eax, eax
0x180004b7d  jz      loc_180004CD8
0x180004b83  mov     rcx, [rsp+280h+hObject]; hObject
0x180004b88  test    rcx, rcx
0x180004b8b  jz      short loc_180004B9B
0x180004b8d  call    cs:__imp_CloseHandle
0x180004b93  test    eax, eax
0x180004b95  jz      loc_180004CEA
0x180004b9b  call    cs:__imp_GetProcessHeap
0x180004ba1  mov     r8, rsi; lpMem
0x180004ba4  xor     edx, edx; dwFlags
0x180004ba6  mov     rcx, rax; hHeap
0x180004ba9  call    cs:__imp_HeapFree
0x180004baf  mov     rcx, [rbp+188h]; this
0x180004bb6  mov     r9d, r14d; char *
0x180004bb9  mov     edx, 137h; void *
0x180004bbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004bc3  test    rdi, rdi
0x180004bc6  jz      short loc_180004BD9
0x180004bc8  mov     rcx, rdi; hMutex
0x180004bcb  call    cs:__imp_ReleaseMutex
0x180004bd1  test    eax, eax
0x180004bd3  jz      loc_180004CFC
0x180004bd9  mov     rcx, rbx; hObject
0x180004bdc  call    cs:__imp_CloseHandle
0x180004be2  test    eax, eax
0x180004be4  jz      loc_180004D0E
0x180004bea  mov     eax, r14d
0x180004bed  jmp     short loc_180004C5D
0x180004bef  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004bf4  xor     edx, edx; Val
0x180004bf6  mov     dword ptr [rsi], 1
0x180004bfc  lea     rcx, [rsi+22h]; void *
0x180004c00  mov     [rsi+8], rbx
0x180004c04  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004c09  lea     r8d, [rdx+56h]; Size
0x180004c0d  call    memset_0
0x180004c12  xor     edx, edx; Val
0x180004c14  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004c1a  lea     rcx, [rsi+28h]; void *
0x180004c1e  mov     dword ptr [rsi+24h], 1
0x180004c25  lea     r8d, [rdx+50h]; Size
0x180004c29  call    memset_0
0x180004c2e  xor     ebx, ebx
0x180004c30  mov     [r15], rsi
0x180004c33  test    rdi, rdi
0x180004c36  jz      short loc_180004C49
0x180004c38  mov     rcx, rdi; hMutex
0x180004c3b  call    cs:__imp_ReleaseMutex
0x180004c41  test    eax, eax
0x180004c43  jz      loc_180004D20
0x180004c49  test    rbx, rbx
0x180004c4c  jz      short loc_180004C5B
0x180004c4e  mov     rcx, rbx; hObject
0x180004c51  call    cs:__imp_CloseHandle
0x180004c57  test    eax, eax
0x180004c59  jz      short loc_180004C83
0x180004c5b  xor     eax, eax
0x180004c5d  mov     rcx, [rbp+180h+var_30]
0x180004c64  xor     rcx, rsp; StackCookie
0x180004c67  call    __security_check_cookie
0x180004c6c  mov     rbx, [rsp+280h+arg_10]
0x180004c74  add     rsp, 260h
0x180004c7b  pop     r15
0x180004c7d  pop     r14
0x180004c7f  pop     rdi
0x180004c80  pop     rsi
0x180004c81  pop     rbp
0x180004c82  retn
0x180004c83  mov     rcx, [rbp+188h]; this
0x180004c8a  mov     edx, 0A0Bh; void *
0x180004c8f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c95  mov     rcx, [rbp+188h]; this
0x180004c9c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004ca3  mov     edx, 0E01h; void *
0x180004ca8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004cae  mov     rcx, [rbp+188h]; this
0x180004cb5  mov     edx, 0A15h; void *
0x180004cba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004cc0  mov     rcx, [rbp+188h]; this
0x180004cc7  mov     edx, 0A0Bh; void *
0x180004ccc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004cd2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004cd8  mov     rcx, [rbp+188h]; this
0x180004cdf  mov     edx, 0A0Bh; void *
0x180004ce4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004cea  mov     rcx, [rbp+188h]; this
0x180004cf1  mov     edx, 0A0Bh; void *
0x180004cf6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004cfc  mov     rcx, [rbp+188h]; this
0x180004d03  mov     edx, 0A15h; void *
0x180004d08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d0e  mov     rcx, [rbp+188h]; this
0x180004d15  mov     edx, 0A0Bh; void *
0x180004d1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d20  mov     rcx, [rbp+188h]; this
0x180004d27  mov     edx, 0A15h; void *
0x180004d2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
