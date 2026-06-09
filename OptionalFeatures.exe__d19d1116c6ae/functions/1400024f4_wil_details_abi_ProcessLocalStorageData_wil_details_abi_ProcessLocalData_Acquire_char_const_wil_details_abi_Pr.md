# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400024f4`
- end: `0x140002892`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14000336c`

## callees

- `0x14000187f`
- `0x1400024f4`
- `0x140002898`
- `0x140002ac0`
- `0x140003108`
- `0x140003bd8`
- `0x140003e94`
- `0x1400041f4`
- `0x140004570`
- `0x14000492c`
- `0x14000493c`
- `0x140004ba0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140002715`
- `KERNEL32!HeapFree` at `0x140002715`
- `KERNEL32!ReleaseMutex` at `0x14000260e`
- `KERNEL32!ReleaseMutex` at `0x140002737`
- `KERNEL32!ReleaseMutex` at `0x1400027a7`
- `KERNEL32!ReleaseMutex` at `0x14000260e`
- `KERNEL32!ReleaseMutex` at `0x140002737`
- `KERNEL32!ReleaseMutex` at `0x1400027a7`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000258d`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000258d`
- `KERNEL32!CloseHandle` at `0x14000261f`
- `KERNEL32!CloseHandle` at `0x1400026e1`
- `KERNEL32!CloseHandle` at `0x1400026f9`
- `KERNEL32!CloseHandle` at `0x140002748`
- `KERNEL32!CloseHandle` at `0x1400027bd`
- `KERNEL32!CloseHandle` at `0x14000261f`
- `KERNEL32!CloseHandle` at `0x1400026e1`
- `KERNEL32!CloseHandle` at `0x1400026f9`
- `KERNEL32!CloseHandle` at `0x140002748`
- `KERNEL32!CloseHandle` at `0x1400027bd`
- `KERNEL32!CreateMutexExW` at `0x14000256c`
- `KERNEL32!CreateMutexExW` at `0x14000256c`
- `KERNEL32!GetCurrentProcessId` at `0x14000252d`
- `KERNEL32!GetCurrentProcessId` at `0x14000252d`
- `KERNEL32!GetProcessHeap` at `0x140002707`
- `KERNEL32!GetProcessHeap` at `0x140002707`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
0x1400024f4  mov     [rsp-8+arg_10], rbx
0x1400024f9  push    rbp
0x1400024fa  push    rsi
0x1400024fb  push    rdi
0x1400024fc  push    r14
0x1400024fe  push    r15
0x140002500  lea     rbp, [rsp-160h]
0x140002508  sub     rsp, 260h
0x14000250f  mov     rax, cs:__security_cookie
0x140002516  xor     rax, rsp
0x140002519  mov     [rbp+180h+var_30], rax
0x140002520  mov     r15, rdx
0x140002523  mov     qword ptr [rdx], 0
0x14000252a  mov     rbx, rcx
0x14000252d  call    cs:__imp_GetCurrentProcessId
0x140002533  mov     r14d, 78h ; 'x'
0x140002539  mov     [rsp+280h+var_258], rbx
0x14000253e  mov     r9d, eax
0x140002541  mov     [rsp+280h+var_260], r14d; int
0x140002546  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000254d  mov     edx, 104h; unsigned __int64
0x140002552  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002557  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000255c  mov     r9d, 1F0001h; dwDesiredAccess
0x140002562  lea     rdx, [rsp+280h+Name]; lpName
0x140002567  xor     r8d, r8d; dwFlags
0x14000256a  xor     ecx, ecx; lpMutexAttributes
0x14000256c  call    cs:__imp_CreateMutexExW
0x140002572  mov     rbx, rax
0x140002575  test    rax, rax
0x140002578  jnz     short loc_140002584
0x14000257a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000257f  jmp     loc_1400027C9
0x140002584  xor     r8d, r8d; bAlertable
0x140002587  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000258a  mov     rcx, rbx; hHandle
0x14000258d  call    cs:__imp_WaitForSingleObjectEx
0x140002593  cmp     eax, 102h
0x140002598  jz      short loc_1400025AA
0x14000259a  test    eax, 0FFFFFF7Fh
0x14000259f  jnz     loc_140002801
0x1400025a5  mov     rdi, rbx
0x1400025a8  jmp     short loc_1400025AC
0x1400025aa  xor     edi, edi
0x1400025ac  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400025b1  mov     [rsp+280h+hObject], 0
0x1400025ba  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400025bf  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400025c4  mov     esi, eax
0x1400025c6  test    eax, eax
0x1400025c8  jns     short loc_140002634
0x1400025ca  mov     rcx, [rbp+188h]; this
0x1400025d1  mov     r9d, eax; char *
0x1400025d4  mov     edx, 66h ; 'f'; void *
0x1400025d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400025de  mov     rcx, [rbp+188h]; this
0x1400025e5  mov     r9d, esi; char *
0x1400025e8  mov     edx, 6Fh ; 'o'; void *
0x1400025ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400025f2  mov     rcx, [rbp+188h]; this
0x1400025f9  mov     r9d, esi; char *
0x1400025fc  mov     edx, 12Eh; void *
0x140002601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002606  test    rdi, rdi
0x140002609  jz      short loc_14000261C
0x14000260b  mov     rcx, rdi; hMutex
0x14000260e  call    cs:__imp_ReleaseMutex
0x140002614  test    eax, eax
0x140002616  jz      loc_14000280E
0x14000261c  mov     rcx, rbx; hObject
0x14000261f  call    cs:__imp_CloseHandle
0x140002625  test    eax, eax
0x140002627  jz      loc_140002820
0x14000262d  mov     eax, esi
0x14000262f  jmp     loc_1400027C9
0x140002634  mov     rax, [rsp+280h+hObject]
0x140002639  lea     rcx, ds:0[rax*4]
0x140002641  test    rcx, rcx
0x140002644  jz      short loc_140002654
0x140002646  mov     [r15], rcx
0x140002649  mov     eax, [rcx]
0x14000264b  inc     eax
0x14000264d  mov     [rcx], eax
0x14000264f  jmp     loc_14000279F
0x140002654  mov     rdx, r14; dwBytes
0x140002657  mov     qword ptr [r15], 0
0x14000265e  mov     ecx, 8; dwFlags
0x140002663  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002668  mov     rsi, rax
0x14000266b  test    rax, rax
0x14000266e  jnz     short loc_14000268F
0x140002670  mov     rcx, [rbp+188h]; this
0x140002677  mov     r14d, 8007000Eh
0x14000267d  mov     r9d, r14d; char *
0x140002680  mov     edx, 14Bh; void *
0x140002685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000268a  jmp     loc_14000271B
0x14000268f  xorps   xmm0, xmm0
0x140002692  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140002698  test    sil, 3
0x14000269c  jnz     loc_140002832
0x1400026a2  mov     r9, rsi
0x1400026a5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400026aa  shr     r9, 2; unsigned __int64
0x1400026ae  lea     rcx, [rsp+280h+hObject]; this
0x1400026b3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400026b8  mov     r14d, eax
0x1400026bb  test    eax, eax
0x1400026bd  jns     loc_14000275B
0x1400026c3  mov     rcx, [rbp+188h]; this
0x1400026ca  mov     r9d, eax; char *
0x1400026cd  mov     edx, 14Eh; void *
0x1400026d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400026d7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400026dc  test    rcx, rcx
0x1400026df  jz      short loc_1400026EF
0x1400026e1  call    cs:__imp_CloseHandle
0x1400026e7  test    eax, eax
0x1400026e9  jz      loc_140002838
0x1400026ef  mov     rcx, [rsp+280h+hObject]; hObject
0x1400026f4  test    rcx, rcx
0x1400026f7  jz      short loc_140002707
0x1400026f9  call    cs:__imp_CloseHandle
0x1400026ff  test    eax, eax
0x140002701  jz      loc_14000284A
0x140002707  call    cs:__imp_GetProcessHeap
0x14000270d  mov     r8, rsi; lpMem
0x140002710  xor     edx, edx; dwFlags
0x140002712  mov     rcx, rax; hHeap
0x140002715  call    cs:__imp_HeapFree
0x14000271b  mov     rcx, [rbp+188h]; this
0x140002722  mov     r9d, r14d; char *
0x140002725  mov     edx, 137h; void *
0x14000272a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000272f  test    rdi, rdi
0x140002732  jz      short loc_140002745
0x140002734  mov     rcx, rdi; hMutex
0x140002737  call    cs:__imp_ReleaseMutex
0x14000273d  test    eax, eax
0x14000273f  jz      loc_14000285C
0x140002745  mov     rcx, rbx; hObject
0x140002748  call    cs:__imp_CloseHandle
0x14000274e  test    eax, eax
0x140002750  jz      loc_14000286E
0x140002756  mov     eax, r14d
0x140002759  jmp     short loc_1400027C9
0x14000275b  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140002760  xor     edx, edx; Val
0x140002762  mov     dword ptr [rsi], 1
0x140002768  lea     rcx, [rsi+22h]; void *
0x14000276c  mov     [rsi+8], rbx
0x140002770  movdqu  xmmword ptr [rsi+10h], xmm0
0x140002775  lea     r8d, [rdx+56h]; Size
0x140002779  call    memset_0
0x14000277e  xor     edx, edx; Val
0x140002780  mov     word ptr [rsi+20h], 58h ; 'X'
0x140002786  lea     rcx, [rsi+28h]; void *
0x14000278a  mov     dword ptr [rsi+24h], 1
0x140002791  lea     r8d, [rdx+50h]; Size
0x140002795  call    memset_0
0x14000279a  xor     ebx, ebx
0x14000279c  mov     [r15], rsi
0x14000279f  test    rdi, rdi
0x1400027a2  jz      short loc_1400027B5
0x1400027a4  mov     rcx, rdi; hMutex
0x1400027a7  call    cs:__imp_ReleaseMutex
0x1400027ad  test    eax, eax
0x1400027af  jz      loc_140002880
0x1400027b5  test    rbx, rbx
0x1400027b8  jz      short loc_1400027C7
0x1400027ba  mov     rcx, rbx; hObject
0x1400027bd  call    cs:__imp_CloseHandle
0x1400027c3  test    eax, eax
0x1400027c5  jz      short loc_1400027EF
0x1400027c7  xor     eax, eax
0x1400027c9  mov     rcx, [rbp+180h+var_30]
0x1400027d0  xor     rcx, rsp; StackCookie
0x1400027d3  call    __security_check_cookie
0x1400027d8  mov     rbx, [rsp+280h+arg_10]
0x1400027e0  add     rsp, 260h
0x1400027e7  pop     r15
0x1400027e9  pop     r14
0x1400027eb  pop     rdi
0x1400027ec  pop     rsi
0x1400027ed  pop     rbp
0x1400027ee  retn
0x1400027ef  mov     rcx, [rbp+188h]; this
0x1400027f6  mov     edx, 0A0Bh; void *
0x1400027fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002801  mov     rcx, [rbp+188h]; this
0x140002808  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000280e  mov     rcx, [rbp+188h]; this
0x140002815  mov     edx, 0A15h; void *
0x14000281a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002820  mov     rcx, [rbp+188h]; this
0x140002827  mov     edx, 0A0Bh; void *
0x14000282c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002832  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002838  mov     rcx, [rbp+188h]; this
0x14000283f  mov     edx, 0A0Bh; void *
0x140002844  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000284a  mov     rcx, [rbp+188h]; this
0x140002851  mov     edx, 0A0Bh; void *
0x140002856  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000285c  mov     rcx, [rbp+188h]; this
0x140002863  mov     edx, 0A15h; void *
0x140002868  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000286e  mov     rcx, [rbp+188h]; this
0x140002875  mov     edx, 0A0Bh; void *
0x14000287a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002880  mov     rcx, [rbp+188h]; this
0x140002887  mov     edx, 0A15h; void *
0x14000288c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
