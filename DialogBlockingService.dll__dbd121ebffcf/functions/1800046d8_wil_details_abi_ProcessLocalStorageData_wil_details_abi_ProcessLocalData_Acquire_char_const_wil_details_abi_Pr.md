# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800046d8`
- end: `0x180004aa0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800058e4`

## callees

- `0x180001620`
- `0x1800020d0`
- `0x1800046d8`
- `0x180004ae4`
- `0x180004e44`
- `0x180005638`
- `0x18000627c`
- `0x180006804`
- `0x1800072b0`
- `0x18000752c`
- `0x180007d0c`
- `0x180007d1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004771`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004771`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004750`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004750`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004807`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004945`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800049b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004807`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004945`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800049b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000491c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000491c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000490e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000490e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004711`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004900`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004900`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049cb`

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
0x1800046d8  mov     [rsp-8+arg_10], rbx
0x1800046dd  push    rbp
0x1800046de  push    rsi
0x1800046df  push    rdi
0x1800046e0  push    r14
0x1800046e2  push    r15
0x1800046e4  lea     rbp, [rsp-160h]
0x1800046ec  sub     rsp, 260h
0x1800046f3  mov     rax, cs:__security_cookie
0x1800046fa  xor     rax, rsp
0x1800046fd  mov     [rbp+180h+var_30], rax
0x180004704  mov     r15, rdx
0x180004707  mov     qword ptr [rdx], 0
0x18000470e  mov     rbx, rcx
0x180004711  call    cs:__imp_GetCurrentProcessId
0x180004717  mov     r14d, 78h ; 'x'
0x18000471d  mov     [rsp+280h+var_258], rbx
0x180004722  mov     r9d, eax
0x180004725  mov     [rsp+280h+var_260], r14d; int
0x18000472a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004731  mov     edx, 104h; unsigned __int64
0x180004736  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000473b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004740  mov     r9d, 1F0001h; dwDesiredAccess
0x180004746  lea     rdx, [rsp+280h+Name]; lpName
0x18000474b  xor     r8d, r8d; dwFlags
0x18000474e  xor     ecx, ecx; lpMutexAttributes
0x180004750  call    cs:__imp_CreateMutexExW
0x180004756  mov     rbx, rax
0x180004759  test    rax, rax
0x18000475c  jnz     short loc_180004768
0x18000475e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004763  jmp     loc_1800049D7
0x180004768  xor     r8d, r8d; bAlertable
0x18000476b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000476e  mov     rcx, rbx; hHandle
0x180004771  call    cs:__imp_WaitForSingleObjectEx
0x180004777  cmp     eax, 102h
0x18000477c  jz      short loc_18000478E
0x18000477e  test    eax, 0FFFFFF7Fh
0x180004783  jnz     loc_180004A0F
0x180004789  mov     rdi, rbx
0x18000478c  jmp     short loc_180004790
0x18000478e  xor     edi, edi
0x180004790  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004795  mov     [rsp+280h+hObject], 0
0x18000479e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800047a3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800047a8  mov     esi, eax
0x1800047aa  test    eax, eax
0x1800047ac  jns     short loc_18000482D
0x1800047ae  mov     rcx, [rbp+188h]; this
0x1800047b5  lea     r8, aWil; "wil"
0x1800047bc  mov     r9d, eax; char *
0x1800047bf  mov     edx, 66h ; 'f'; void *
0x1800047c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047c9  mov     rcx, [rbp+188h]; this
0x1800047d0  lea     r8, aWil; "wil"
0x1800047d7  mov     r9d, esi; char *
0x1800047da  mov     edx, 6Fh ; 'o'; void *
0x1800047df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047e4  mov     rcx, [rbp+188h]; this
0x1800047eb  lea     r8, aWil; "wil"
0x1800047f2  mov     r9d, esi; char *
0x1800047f5  mov     edx, 12Eh; void *
0x1800047fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047ff  test    rdi, rdi
0x180004802  jz      short loc_180004815
0x180004804  mov     rcx, rdi; hMutex
0x180004807  call    cs:__imp_ReleaseMutex
0x18000480d  test    eax, eax
0x18000480f  jz      loc_180004A1C
0x180004815  mov     rcx, rbx; hObject
0x180004818  call    cs:__imp_CloseHandle
0x18000481e  test    eax, eax
0x180004820  jz      loc_180004A2E
0x180004826  mov     eax, esi
0x180004828  jmp     loc_1800049D7
0x18000482d  mov     rax, [rsp+280h+hObject]
0x180004832  lea     rcx, ds:0[rax*4]
0x18000483a  test    rcx, rcx
0x18000483d  jz      short loc_18000484D
0x18000483f  mov     [r15], rcx
0x180004842  mov     eax, [rcx]
0x180004844  inc     eax
0x180004846  mov     [rcx], eax
0x180004848  jmp     loc_1800049AD
0x18000484d  mov     rdx, r14; dwBytes
0x180004850  mov     qword ptr [r15], 0
0x180004857  mov     ecx, 8; dwFlags
0x18000485c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004861  mov     rsi, rax
0x180004864  test    rax, rax
0x180004867  jnz     short loc_18000488F
0x180004869  mov     rcx, [rbp+188h]; this
0x180004870  lea     r8, aWil; "wil"
0x180004877  mov     r14d, 8007000Eh
0x18000487d  mov     edx, 14Bh; void *
0x180004882  mov     r9d, r14d; char *
0x180004885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000488a  jmp     loc_180004922
0x18000488f  xorps   xmm0, xmm0
0x180004892  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004898  test    sil, 3
0x18000489c  jnz     loc_180004A40
0x1800048a2  mov     r9, rsi
0x1800048a5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800048aa  shr     r9, 2; unsigned __int64
0x1800048ae  lea     rcx, [rsp+280h+hObject]; this
0x1800048b3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800048b8  mov     r14d, eax
0x1800048bb  test    eax, eax
0x1800048bd  jns     loc_180004969
0x1800048c3  mov     rcx, [rbp+188h]; this
0x1800048ca  lea     r8, aWil; "wil"
0x1800048d1  mov     r9d, eax; char *
0x1800048d4  mov     edx, 14Eh; void *
0x1800048d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048de  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800048e3  test    rcx, rcx
0x1800048e6  jz      short loc_1800048F6
0x1800048e8  call    cs:__imp_CloseHandle
0x1800048ee  test    eax, eax
0x1800048f0  jz      loc_180004A46
0x1800048f6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800048fb  test    rcx, rcx
0x1800048fe  jz      short loc_18000490E
0x180004900  call    cs:__imp_CloseHandle
0x180004906  test    eax, eax
0x180004908  jz      loc_180004A58
0x18000490e  call    cs:__imp_GetProcessHeap
0x180004914  mov     r8, rsi; lpMem
0x180004917  xor     edx, edx; dwFlags
0x180004919  mov     rcx, rax; hHeap
0x18000491c  call    cs:__imp_HeapFree
0x180004922  mov     rcx, [rbp+188h]; this
0x180004929  lea     r8, aWil; "wil"
0x180004930  mov     r9d, r14d; char *
0x180004933  mov     edx, 137h; void *
0x180004938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000493d  test    rdi, rdi
0x180004940  jz      short loc_180004953
0x180004942  mov     rcx, rdi; hMutex
0x180004945  call    cs:__imp_ReleaseMutex
0x18000494b  test    eax, eax
0x18000494d  jz      loc_180004A6A
0x180004953  mov     rcx, rbx; hObject
0x180004956  call    cs:__imp_CloseHandle
0x18000495c  test    eax, eax
0x18000495e  jz      loc_180004A7C
0x180004964  mov     eax, r14d
0x180004967  jmp     short loc_1800049D7
0x180004969  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000496e  xor     edx, edx; Val
0x180004970  mov     dword ptr [rsi], 1
0x180004976  lea     rcx, [rsi+22h]; void *
0x18000497a  mov     [rsi+8], rbx
0x18000497e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004983  lea     r8d, [rdx+56h]; Size
0x180004987  call    memset_0
0x18000498c  xor     edx, edx; Val
0x18000498e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004994  lea     rcx, [rsi+28h]; void *
0x180004998  mov     dword ptr [rsi+24h], 1
0x18000499f  lea     r8d, [rdx+50h]; Size
0x1800049a3  call    memset_0
0x1800049a8  xor     ebx, ebx
0x1800049aa  mov     [r15], rsi
0x1800049ad  test    rdi, rdi
0x1800049b0  jz      short loc_1800049C3
0x1800049b2  mov     rcx, rdi; hMutex
0x1800049b5  call    cs:__imp_ReleaseMutex
0x1800049bb  test    eax, eax
0x1800049bd  jz      loc_180004A8E
0x1800049c3  test    rbx, rbx
0x1800049c6  jz      short loc_1800049D5
0x1800049c8  mov     rcx, rbx; hObject
0x1800049cb  call    cs:__imp_CloseHandle
0x1800049d1  test    eax, eax
0x1800049d3  jz      short loc_1800049FD
0x1800049d5  xor     eax, eax
0x1800049d7  mov     rcx, [rbp+180h+var_30]
0x1800049de  xor     rcx, rsp; StackCookie
0x1800049e1  call    __security_check_cookie
0x1800049e6  mov     rbx, [rsp+280h+arg_10]
0x1800049ee  add     rsp, 260h
0x1800049f5  pop     r15
0x1800049f7  pop     r14
0x1800049f9  pop     rdi
0x1800049fa  pop     rsi
0x1800049fb  pop     rbp
0x1800049fc  retn
0x1800049fd  mov     rcx, [rbp+188h]; this
0x180004a04  mov     edx, 0A0Bh; void *
0x180004a09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a0f  mov     rcx, [rbp+188h]; this
0x180004a16  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004a1c  mov     rcx, [rbp+188h]; this
0x180004a23  mov     edx, 0A15h; void *
0x180004a28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a2e  mov     rcx, [rbp+188h]; this
0x180004a35  mov     edx, 0A0Bh; void *
0x180004a3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a40  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004a46  mov     rcx, [rbp+188h]; this
0x180004a4d  mov     edx, 0A0Bh; void *
0x180004a52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a58  mov     rcx, [rbp+188h]; this
0x180004a5f  mov     edx, 0A0Bh; void *
0x180004a64  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a6a  mov     rcx, [rbp+188h]; this
0x180004a71  mov     edx, 0A15h; void *
0x180004a76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a7c  mov     rcx, [rbp+188h]; this
0x180004a83  mov     edx, 0A0Bh; void *
0x180004a88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a8e  mov     rcx, [rbp+188h]; this
0x180004a95  mov     edx, 0A15h; void *
0x180004a9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
