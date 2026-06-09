# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800066b8`
- end: `0x180006a85`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180008634`

## callees

- `0x180004410`
- `0x18000526c`
- `0x1800066b8`
- `0x180007620`
- `0x180007dd0`
- `0x1800083cc`
- `0x180009368`
- `0x18000a814`
- `0x18000b254`
- `0x18000b3cc`
- `0x18000baf4`
- `0x18000bb04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800067e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006925`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006995`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800067e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006925`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006995`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006730`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006730`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006751`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006751`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800066f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800066f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069ab`

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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x1800066b8  mov     [rsp-8+arg_10], rbx
0x1800066bd  push    rbp
0x1800066be  push    rsi
0x1800066bf  push    rdi
0x1800066c0  push    r14
0x1800066c2  push    r15
0x1800066c4  lea     rbp, [rsp-160h]
0x1800066cc  sub     rsp, 260h
0x1800066d3  mov     rax, cs:__security_cookie
0x1800066da  xor     rax, rsp
0x1800066dd  mov     [rbp+180h+var_30], rax
0x1800066e4  mov     r15, rdx
0x1800066e7  mov     qword ptr [rdx], 0
0x1800066ee  mov     rbx, rcx
0x1800066f1  call    cs:__imp_GetCurrentProcessId
0x1800066f7  mov     r14d, 78h ; 'x'
0x1800066fd  mov     [rsp+280h+var_258], rbx
0x180006702  mov     r9d, eax
0x180006705  mov     [rsp+280h+var_260], r14d; int
0x18000670a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006711  mov     edx, 104h; unsigned __int64
0x180006716  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000671b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006720  mov     r9d, 1F0001h; dwDesiredAccess
0x180006726  lea     rdx, [rsp+280h+Name]; lpName
0x18000672b  xor     r8d, r8d; dwFlags
0x18000672e  xor     ecx, ecx; lpMutexAttributes
0x180006730  call    cs:__imp_CreateMutexExW
0x180006736  mov     rbx, rax
0x180006739  test    rax, rax
0x18000673c  jnz     short loc_180006748
0x18000673e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006743  jmp     loc_1800069B7
0x180006748  xor     r8d, r8d; bAlertable
0x18000674b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000674e  mov     rcx, rbx; hHandle
0x180006751  call    cs:__imp_WaitForSingleObjectEx
0x180006757  cmp     eax, 102h
0x18000675c  jz      short loc_18000676E
0x18000675e  test    eax, 0FFFFFF7Fh
0x180006763  jnz     loc_1800069EF
0x180006769  mov     rdi, rbx
0x18000676c  jmp     short loc_180006770
0x18000676e  xor     edi, edi
0x180006770  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006775  mov     [rsp+280h+hObject], 0
0x18000677e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006783  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006788  mov     esi, eax
0x18000678a  test    eax, eax
0x18000678c  jns     short loc_18000680D
0x18000678e  mov     rcx, [rbp+188h]; this
0x180006795  lea     r8, aWil; "wil"
0x18000679c  mov     r9d, eax; char *
0x18000679f  mov     edx, 66h ; 'f'; void *
0x1800067a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067a9  mov     rcx, [rbp+188h]; this
0x1800067b0  lea     r8, aWil; "wil"
0x1800067b7  mov     r9d, esi; char *
0x1800067ba  mov     edx, 6Fh ; 'o'; void *
0x1800067bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067c4  mov     rcx, [rbp+188h]; this
0x1800067cb  lea     r8, aWil; "wil"
0x1800067d2  mov     r9d, esi; char *
0x1800067d5  mov     edx, 12Eh; void *
0x1800067da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067df  test    rdi, rdi
0x1800067e2  jz      short loc_1800067F5
0x1800067e4  mov     rcx, rdi; hMutex
0x1800067e7  call    cs:__imp_ReleaseMutex
0x1800067ed  test    eax, eax
0x1800067ef  jz      loc_180006A01
0x1800067f5  mov     rcx, rbx; hObject
0x1800067f8  call    cs:__imp_CloseHandle
0x1800067fe  test    eax, eax
0x180006800  jz      loc_180006A13
0x180006806  mov     eax, esi
0x180006808  jmp     loc_1800069B7
0x18000680d  mov     rax, [rsp+280h+hObject]
0x180006812  lea     rcx, ds:0[rax*4]
0x18000681a  test    rcx, rcx
0x18000681d  jz      short loc_18000682D
0x18000681f  mov     [r15], rcx
0x180006822  mov     eax, [rcx]
0x180006824  inc     eax
0x180006826  mov     [rcx], eax
0x180006828  jmp     loc_18000698D
0x18000682d  mov     rdx, r14; dwBytes
0x180006830  mov     qword ptr [r15], 0
0x180006837  mov     ecx, 8; dwFlags
0x18000683c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006841  mov     rsi, rax
0x180006844  test    rax, rax
0x180006847  jnz     short loc_18000686F
0x180006849  mov     rcx, [rbp+188h]; this
0x180006850  lea     r8, aWil; "wil"
0x180006857  mov     r14d, 8007000Eh
0x18000685d  mov     edx, 14Bh; void *
0x180006862  mov     r9d, r14d; char *
0x180006865  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000686a  jmp     loc_180006902
0x18000686f  xorps   xmm0, xmm0
0x180006872  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006878  test    sil, 3
0x18000687c  jnz     loc_180006A25
0x180006882  mov     r9, rsi
0x180006885  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000688a  shr     r9, 2; unsigned __int64
0x18000688e  lea     rcx, [rsp+280h+hObject]; this
0x180006893  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006898  mov     r14d, eax
0x18000689b  test    eax, eax
0x18000689d  jns     loc_180006949
0x1800068a3  mov     rcx, [rbp+188h]; this
0x1800068aa  lea     r8, aWil; "wil"
0x1800068b1  mov     r9d, eax; char *
0x1800068b4  mov     edx, 14Eh; void *
0x1800068b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800068be  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800068c3  test    rcx, rcx
0x1800068c6  jz      short loc_1800068D6
0x1800068c8  call    cs:__imp_CloseHandle
0x1800068ce  test    eax, eax
0x1800068d0  jz      loc_180006A2B
0x1800068d6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800068db  test    rcx, rcx
0x1800068de  jz      short loc_1800068EE
0x1800068e0  call    cs:__imp_CloseHandle
0x1800068e6  test    eax, eax
0x1800068e8  jz      loc_180006A3D
0x1800068ee  call    cs:__imp_GetProcessHeap
0x1800068f4  mov     r8, rsi; lpMem
0x1800068f7  xor     edx, edx; dwFlags
0x1800068f9  mov     rcx, rax; hHeap
0x1800068fc  call    cs:__imp_HeapFree
0x180006902  mov     rcx, [rbp+188h]; this
0x180006909  lea     r8, aWil; "wil"
0x180006910  mov     r9d, r14d; char *
0x180006913  mov     edx, 137h; void *
0x180006918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000691d  test    rdi, rdi
0x180006920  jz      short loc_180006933
0x180006922  mov     rcx, rdi; hMutex
0x180006925  call    cs:__imp_ReleaseMutex
0x18000692b  test    eax, eax
0x18000692d  jz      loc_180006A4F
0x180006933  mov     rcx, rbx; hObject
0x180006936  call    cs:__imp_CloseHandle
0x18000693c  test    eax, eax
0x18000693e  jz      loc_180006A61
0x180006944  mov     eax, r14d
0x180006947  jmp     short loc_1800069B7
0x180006949  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000694e  xor     edx, edx; Val
0x180006950  mov     dword ptr [rsi], 1
0x180006956  lea     rcx, [rsi+22h]; void *
0x18000695a  mov     [rsi+8], rbx
0x18000695e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180006963  lea     r8d, [rdx+56h]; Size
0x180006967  call    memset_0
0x18000696c  xor     edx, edx; Val
0x18000696e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180006974  lea     rcx, [rsi+28h]; void *
0x180006978  mov     dword ptr [rsi+24h], 1
0x18000697f  lea     r8d, [rdx+50h]; Size
0x180006983  call    memset_0
0x180006988  xor     ebx, ebx
0x18000698a  mov     [r15], rsi
0x18000698d  test    rdi, rdi
0x180006990  jz      short loc_1800069A3
0x180006992  mov     rcx, rdi; hMutex
0x180006995  call    cs:__imp_ReleaseMutex
0x18000699b  test    eax, eax
0x18000699d  jz      loc_180006A73
0x1800069a3  test    rbx, rbx
0x1800069a6  jz      short loc_1800069B5
0x1800069a8  mov     rcx, rbx; hObject
0x1800069ab  call    cs:__imp_CloseHandle
0x1800069b1  test    eax, eax
0x1800069b3  jz      short loc_1800069DD
0x1800069b5  xor     eax, eax
0x1800069b7  mov     rcx, [rbp+180h+var_30]
0x1800069be  xor     rcx, rsp; StackCookie
0x1800069c1  call    __security_check_cookie
0x1800069c6  mov     rbx, [rsp+280h+arg_10]
0x1800069ce  add     rsp, 260h
0x1800069d5  pop     r15
0x1800069d7  pop     r14
0x1800069d9  pop     rdi
0x1800069da  pop     rsi
0x1800069db  pop     rbp
0x1800069dc  retn
0x1800069dd  mov     rcx, [rbp+188h]; this
0x1800069e4  mov     edx, 0A0Bh; void *
0x1800069e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800069ef  mov     rcx, [rbp+188h]; this
0x1800069f6  mov     edx, 0E01h; void *
0x1800069fb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006a01  mov     rcx, [rbp+188h]; this
0x180006a08  mov     edx, 0A15h; void *
0x180006a0d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a13  mov     rcx, [rbp+188h]; this
0x180006a1a  mov     edx, 0A0Bh; void *
0x180006a1f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a25  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006a2b  mov     rcx, [rbp+188h]; this
0x180006a32  mov     edx, 0A0Bh; void *
0x180006a37  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a3d  mov     rcx, [rbp+188h]; this
0x180006a44  mov     edx, 0A0Bh; void *
0x180006a49  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a4f  mov     rcx, [rbp+188h]; this
0x180006a56  mov     edx, 0A15h; void *
0x180006a5b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a61  mov     rcx, [rbp+188h]; this
0x180006a68  mov     edx, 0A0Bh; void *
0x180006a6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a73  mov     rcx, [rbp+188h]; this
0x180006a7a  mov     edx, 0A15h; void *
0x180006a7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
