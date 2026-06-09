# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007168`
- end: `0x180007534`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800081e4`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x180006ec8`
- `0x180007168`
- `0x18000753c`
- `0x180007840`
- `0x180007ed8`
- `0x1800088bc`
- `0x180009084`
- `0x180009a74`
- `0x180009b4c`
- `0x180009ff8`
- `0x18000a008`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007201`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007201`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800071e0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800071e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007297`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800073ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007443`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007297`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800073ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007443`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007383`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007383`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007375`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007375`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800071a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800071a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007459`

## string_xrefs

- `0x180007492`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800074b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800074d1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800074f0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007509`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007522`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  unsigned __int64 v19; // rax
  wil::details::in1diag3 *v20; // rcx
  bool v21; // r8
  _QWORD *v22; // rsi
  unsigned int v23; // r14d
  int v24; // eax
  HANDLE ProcessHeap; // rax
  const char *v26; // r9
  const char *v27; // r9
  unsigned __int64 v28; // rax
  const char *v29; // r9
  const char *v30; // r9
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v34[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v34[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v34, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v31);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v32);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v34[0]);
  if ( 4 * v34[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_24;
  }
  *a2 = 0;
  v19 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = (_QWORD *)v19;
  if ( v19 )
  {
    *(_OWORD *)v34 = 0;
    if ( (v19 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
    v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v34,
            Name,
            v21,
            v19 >> 2);
    v23 = v24;
    if ( v24 >= 0 )
    {
      v22[2] = v34[0];
      v28 = v34[1];
      *(_DWORD *)v22 = 1;
      v22[1] = v6;
      v34[0] = 0;
      v22[3] = v28;
      v34[1] = 0;
      memset_0((char *)v22 + 34, 0, 0x56u);
      *((_WORD *)v22 + 16) = 88;
      *((_DWORD *)v22 + 9) = 1;
      memset_0(v22 + 5, 0, 0x50u);
      *a2 = v22;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
      v6 = 0;
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v30);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
  }
  else
  {
    v23 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v23, v33);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return v23;
}

```

## disassembly

```asm
0x180007168  mov     [rsp-8+arg_10], rbx
0x18000716d  push    rbp
0x18000716e  push    rsi
0x18000716f  push    rdi
0x180007170  push    r14
0x180007172  push    r15
0x180007174  lea     rbp, [rsp-160h]
0x18000717c  sub     rsp, 260h
0x180007183  mov     rax, cs:__security_cookie
0x18000718a  xor     rax, rsp
0x18000718d  mov     [rbp+180h+var_30], rax
0x180007194  mov     r15, rdx
0x180007197  mov     qword ptr [rdx], 0
0x18000719e  mov     rbx, rcx
0x1800071a1  call    cs:__imp_GetCurrentProcessId
0x1800071a7  mov     r14d, 78h ; 'x'
0x1800071ad  mov     [rsp+280h+var_258], rbx
0x1800071b2  mov     r9d, eax
0x1800071b5  mov     [rsp+280h+var_260], r14d; int
0x1800071ba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800071c1  mov     edx, 104h; unsigned __int64
0x1800071c6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800071cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800071d0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800071d6  lea     rdx, [rsp+280h+Name]; lpName
0x1800071db  xor     r8d, r8d; dwFlags
0x1800071de  xor     ecx, ecx; lpMutexAttributes
0x1800071e0  call    cs:__imp_CreateMutexExW
0x1800071e6  mov     rbx, rax
0x1800071e9  test    rax, rax
0x1800071ec  jnz     short loc_1800071F8
0x1800071ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800071f3  jmp     loc_180007465
0x1800071f8  xor     r8d, r8d; bAlertable
0x1800071fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800071fe  mov     rcx, rbx; hHandle
0x180007201  call    cs:__imp_WaitForSingleObjectEx
0x180007207  cmp     eax, 102h
0x18000720c  jz      short loc_18000721E
0x18000720e  test    eax, 0FFFFFF7Fh
0x180007213  jnz     loc_1800074A4
0x180007219  mov     rdi, rbx
0x18000721c  jmp     short loc_180007220
0x18000721e  xor     edi, edi
0x180007220  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180007225  mov     [rsp+280h+var_250], 0
0x18000722e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007233  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007238  mov     esi, eax
0x18000723a  test    eax, eax
0x18000723c  jns     short loc_1800072BD
0x18000723e  mov     rcx, [rbp+188h]; this
0x180007245  lea     r8, aWil; "wil"
0x18000724c  mov     r9d, eax; char *
0x18000724f  mov     edx, 66h ; 'f'; void *
0x180007254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007259  mov     rcx, [rbp+188h]; this
0x180007260  lea     r8, aWil; "wil"
0x180007267  mov     r9d, esi; char *
0x18000726a  mov     edx, 6Fh ; 'o'; void *
0x18000726f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007274  mov     rcx, [rbp+188h]; this
0x18000727b  lea     r8, aWil; "wil"
0x180007282  mov     r9d, esi; char *
0x180007285  mov     edx, 12Eh; void *
0x18000728a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000728f  test    rdi, rdi
0x180007292  jz      short loc_1800072A5
0x180007294  mov     rcx, rdi; hMutex
0x180007297  call    cs:__imp_ReleaseMutex
0x18000729d  test    eax, eax
0x18000729f  jz      loc_1800074B1
0x1800072a5  mov     rcx, rbx; hObject
0x1800072a8  call    cs:__imp_CloseHandle
0x1800072ae  test    eax, eax
0x1800072b0  jz      loc_1800074CA
0x1800072b6  mov     eax, esi
0x1800072b8  jmp     loc_180007465
0x1800072bd  mov     rax, [rsp+280h+var_250]
0x1800072c2  lea     rcx, ds:0[rax*4]
0x1800072ca  test    rcx, rcx
0x1800072cd  jz      short loc_1800072DD
0x1800072cf  mov     [r15], rcx
0x1800072d2  mov     eax, [rcx]
0x1800072d4  inc     eax
0x1800072d6  mov     [rcx], eax
0x1800072d8  jmp     loc_18000743B
0x1800072dd  mov     rdx, r14; dwBytes
0x1800072e0  mov     qword ptr [r15], 0
0x1800072e7  mov     ecx, 8; dwFlags
0x1800072ec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800072f1  mov     rsi, rax
0x1800072f4  test    rax, rax
0x1800072f7  jnz     short loc_18000731C
0x1800072f9  mov     rcx, [rbp+188h]; this
0x180007300  lea     r8, aWil; "wil"
0x180007307  mov     r14d, 8007000Eh
0x18000730d  mov     edx, 14Bh; void *
0x180007312  mov     r9d, r14d; char *
0x180007315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000731a  jmp     short loc_180007389
0x18000731c  xorps   xmm0, xmm0
0x18000731f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180007325  test    sil, 3
0x180007329  jnz     loc_1800074E3
0x18000732f  mov     r9, rsi
0x180007332  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007337  shr     r9, 2; unsigned __int64
0x18000733b  lea     rcx, [rsp+280h+var_250]; this
0x180007340  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180007345  mov     r14d, eax
0x180007348  test    eax, eax
0x18000734a  jns     loc_1800073D3
0x180007350  mov     rcx, [rbp+188h]; this
0x180007357  lea     r8, aWil; "wil"
0x18000735e  mov     r9d, eax; char *
0x180007361  mov     edx, 14Eh; void *
0x180007366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000736b  lea     rcx, [rsp+280h+var_250]; this
0x180007370  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007375  call    cs:__imp_GetProcessHeap
0x18000737b  mov     r8, rsi; lpMem
0x18000737e  xor     edx, edx; dwFlags
0x180007380  mov     rcx, rax; hHeap
0x180007383  call    cs:__imp_HeapFree
0x180007389  mov     rcx, [rbp+188h]; this
0x180007390  lea     r8, aWil; "wil"
0x180007397  mov     r9d, r14d; char *
0x18000739a  mov     edx, 137h; void *
0x18000739f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073a4  test    rdi, rdi
0x1800073a7  jz      short loc_1800073BA
0x1800073a9  mov     rcx, rdi; hMutex
0x1800073ac  call    cs:__imp_ReleaseMutex
0x1800073b2  test    eax, eax
0x1800073b4  jz      loc_1800074E9
0x1800073ba  mov     rcx, rbx; hObject
0x1800073bd  call    cs:__imp_CloseHandle
0x1800073c3  test    eax, eax
0x1800073c5  jz      loc_180007502
0x1800073cb  mov     eax, r14d
0x1800073ce  jmp     loc_180007465
0x1800073d3  mov     rax, [rsp+280h+var_250]
0x1800073d8  lea     rcx, [rsi+22h]; void *
0x1800073dc  xor     edx, edx; Val
0x1800073de  mov     [rsi+10h], rax
0x1800073e2  mov     rax, [rsp+280h+var_250+8]
0x1800073e7  mov     dword ptr [rsi], 1
0x1800073ed  mov     [rsi+8], rbx
0x1800073f1  lea     r8d, [rdx+56h]; Size
0x1800073f5  mov     [rsp+280h+var_250], 0
0x1800073fe  mov     [rsi+18h], rax
0x180007402  mov     [rsp+280h+var_250+8], 0
0x18000740b  call    memset_0
0x180007410  xor     edx, edx; Val
0x180007412  mov     word ptr [rsi+20h], 58h ; 'X'
0x180007418  lea     rcx, [rsi+28h]; void *
0x18000741c  mov     dword ptr [rsi+24h], 1
0x180007423  lea     r8d, [rdx+50h]; Size
0x180007427  call    memset_0
0x18000742c  lea     rcx, [rsp+280h+var_250]; this
0x180007431  mov     [r15], rsi
0x180007434  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007439  xor     ebx, ebx
0x18000743b  test    rdi, rdi
0x18000743e  jz      short loc_180007451
0x180007440  mov     rcx, rdi; hMutex
0x180007443  call    cs:__imp_ReleaseMutex
0x180007449  test    eax, eax
0x18000744b  jz      loc_18000751B
0x180007451  test    rbx, rbx
0x180007454  jz      short loc_180007463
0x180007456  mov     rcx, rbx; hObject
0x180007459  call    cs:__imp_CloseHandle
0x18000745f  test    eax, eax
0x180007461  jz      short loc_18000748B
0x180007463  xor     eax, eax
0x180007465  mov     rcx, [rbp+180h+var_30]
0x18000746c  xor     rcx, rsp; StackCookie
0x18000746f  call    __security_check_cookie
0x180007474  mov     rbx, [rsp+280h+arg_10]
0x18000747c  add     rsp, 260h
0x180007483  pop     r15
0x180007485  pop     r14
0x180007487  pop     rdi
0x180007488  pop     rsi
0x180007489  pop     rbp
0x18000748a  retn
0x18000748b  mov     rcx, [rbp+188h]; this
0x180007492  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007499  mov     edx, 0A0Bh; void *
0x18000749e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800074a4  mov     rcx, [rbp+188h]; this
0x1800074ab  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800074b1  mov     rcx, [rbp+188h]; this
0x1800074b8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800074bf  mov     edx, 0A15h; void *
0x1800074c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800074ca  mov     rcx, [rbp+188h]; this
0x1800074d1  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800074d8  mov     edx, 0A0Bh; void *
0x1800074dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800074e3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800074e9  mov     rcx, [rbp+188h]; this
0x1800074f0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800074f7  mov     edx, 0A15h; void *
0x1800074fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007502  mov     rcx, [rbp+188h]; this
0x180007509  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007510  mov     edx, 0A0Bh; void *
0x180007515  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000751b  mov     rcx, [rbp+188h]; this
0x180007522  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007529  mov     edx, 0A15h; void *
0x18000752e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
