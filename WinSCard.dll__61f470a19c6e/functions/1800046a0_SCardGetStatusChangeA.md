# SCardGetStatusChangeA

- ea: `0x1800046a0`
- end: `0x180004c95`
- name: `SCardGetStatusChangeA`
- size: `1525`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, DWORD dwTimeout, LPSCARD_READERSTATEA rgReaderStates, DWORD cReaders)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x1800046a0`
- `0x180004ca0`
- `0x1800051b0`
- `0x180006400`
- `0x180006890`
- `0x18001991c`
- `0x180019f1c`
- `0x18001b9b8`
- `0x1800239b8`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004811`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004811`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004953`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004953`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LONG __stdcall SCardGetStatusChangeA(
        SCARDCONTEXT hContext,
        DWORD dwTimeout,
        LPSCARD_READERSTATEA rgReaderStates,
        DWORD cReaders)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v6; // rdx
  DWORD v7; // r10d
  int v8; // r11d
  int v9; // r12d
  int v10; // r8d
  unsigned int i; // eax
  bool v12; // zf
  int v13; // r10d
  int v14; // r13d
  char *v15; // rcx
  __int64 v16; // rdx
  char *v17; // rax
  __int64 v18; // rax
  const char *v19; // r9
  char *v20; // r8
  char v21; // r10
  char *v22; // rax
  CHandleList *v23; // rdi
  struct _RTL_CRITICAL_SECTION *v24; // rsi
  SCARDCONTEXT v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdi
  struct _REDIRECTION_CONTEXT *v28; // rsi
  unsigned __int64 v29; // rcx
  __int64 v30; // rsi
  DWORD v31; // eax
  unsigned __int64 v32; // rdx
  int v33; // r9d
  int v34; // r10d
  unsigned int k; // ecx
  bool v36; // zf
  int v37; // r11d
  char *v38; // rcx
  char *v39; // rax
  const char *v40; // rax
  char *v41; // r15
  __int64 v42; // r8
  char v43; // dl
  char *v44; // rax
  __int64 v46; // rdx
  unsigned __int16 *v47; // r15
  DWORD j; // esi
  const unsigned __int16 *v49; // rdx
  unsigned __int64 v50; // rdx
  int v51; // r10d
  int v52; // r11d
  int m; // r15d
  int v54; // r11d
  ulong v55; // [rsp+30h] [rbp-78h]
  ulong v56; // [rsp+38h] [rbp-70h] BYREF
  ulong pExceptionObject; // [rsp+3Ch] [rbp-6Ch] BYREF
  const int *v58; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int16 *v59; // [rsp+48h] [rbp-60h]
  int v60; // [rsp+50h] [rbp-58h]
  int v61; // [rsp+54h] [rbp-54h]
  struct _REDIRECTION_CONTEXT *v62; // [rsp+58h] [rbp-50h]
  ulong v63; // [rsp+60h] [rbp-48h] BYREF
  char *v64; // [rsp+68h] [rbp-40h]

  CurrentThreadId = GetCurrentThreadId();
  v7 = CurrentThreadId;
  v8 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v8 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    dword_180045874 = 0;
    v9 = -1;
    goto LABEL_17;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread != -2
    && *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) == CurrentThreadId )
  {
    v9 = -1;
  }
  else
  {
    v9 = -1;
    v10 = -1;
    for ( i = 0; ; ++i )
    {
      v12 = i == 32;
      if ( i >= 0x20 )
        break;
      v6 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
      if ( (_DWORD)v6 == v7 )
      {
        v8 = i;
        `WppTraceIndent'::`2'::idxCurrentThread = i;
        v12 = i == 32;
        break;
      }
      if ( v10 == -1 && !(_DWORD)v6 )
        v10 = i;
    }
    if ( v12 )
    {
      if ( v10 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_36;
      }
      v8 = v10;
      `WppTraceIndent'::`2'::idxCurrentThread = v10;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v10) = v7;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v10 + 1) = 0;
    }
  }
  if ( v8 >= 0 )
  {
LABEL_17:
    v13 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v8 + 1);
    goto LABEL_18;
  }
LABEL_36:
  v13 = 0;
LABEL_18:
  v14 = 0;
  v62 = 0;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  v15 = (char *)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v13 >= 1 )
  {
    while ( !(unsigned int)StringCbCatA(v15, v6, "..") && v52 + 1 <= v51 )
      ;
    v15 = (char *)WPP_GLOBAL_Control;
  }
  v16 = 256;
  v17 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v17 )
  {
    ++v17;
    if ( !--v16 )
      goto LABEL_28;
  }
  v18 = 2147483646;
  v19 = ">";
  v20 = (char *)&`wil::SetLastError'::`5'::depth - v16;
  do
  {
    if ( !v18 )
      break;
    v21 = *v19;
    if ( !*v19 )
      break;
    ++v19;
    *v20++ = v21;
    --v18;
    --v16;
  }
  while ( v16 );
  v22 = v20 - 1;
  if ( v16 )
    v22 = v20;
  *v22 = 0;
LABEL_28:
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v15 != (char *)&WPP_GLOBAL_Control && (v15[28] & 2) != 0 && (unsigned __int8)v15[25] >= 5u )
    WPP_SF_s(*((_QWORD *)v15 + 2), 10, WPP_b9891d3101073fd7de822d6ffb5eb0dd_Traceguids);
  try
  {
    v23 = g_phlContexts;
    v24 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    v64 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    if ( HIBYTE(hContext) != *((_BYTE *)v23 + 8)
      || *((_DWORD *)v23 + 4) <= (hContext & 0x7FFFFFFF)
      || (v25 = 16 * (hContext & 0x7FFFFFFF),
          v26 = *((_QWORD *)v23 + 3),
          ((*(_DWORD *)(v25 + v26 + 8) ^ HIDWORD(hContext)) & 0xFFFFFF) != 0) )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v27 = *(_QWORD *)(v25 + v26);
    LeaveCriticalSection(v24);
    if ( *(_DWORD *)(v27 + 16) )
    {
      v56 = -2146435042;
      throw &v56;
    }
    v28 = *(struct _REDIRECTION_CONTEXT **)(v27 + 136);
    v62 = v28;
    v29 = *(_QWORD *)(v27 + 128);
    if ( v29 )
    {
      v14 = RedirectedSCardGetStatusChangeA(v29, dwTimeout, rgReaderStates, cReaders);
      if ( v14 == -2146435054 )
        SetStartedEventWhenSCardSubsytemIsStarted(v28);
    }
    else
    {
      v58 = &CBuffer::`vftable';
      v47 = 0;
      v59 = 0;
      v60 = 0;
      v61 = 0;
      for ( j = 0; j < cReaders; ++j )
      {
        MStrAdd((struct CBuffer *)&v58, rgReaderStates[(unsigned __int64)j].szReader);
        v47 = v59;
      }
      v49 = &WideCharStr;
      if ( v61 )
        v49 = v47;
      CSCardUserContext::GetStatusChange(
        (CSCardUserContext *)v27,
        v49,
        (struct SCARD_READERSTATEW *)rgReaderStates,
        cReaders,
        dwTimeout);
      v58 = &CBuffer::`vftable';
      if ( v47 )
        operator delete(v47, v50);
      v59 = 0;
      v60 = 0;
      v61 = 0;
    }
  }
  catch ( ulong v63 )
  {
    v55 = v63;
    if ( v63 == -2146435054 && v62 )
      ResetEvent(*((HANDLE *)v62 + 16));
    v14 = v55;
    v9 = -1;
  }
  catch ( ... )
  {
    v14 = -2146435068;
    v9 = -1;
  }
  v30 = 256;
  v31 = GetCurrentThreadId();
  v34 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v34 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v31;
    dword_180045874 = 0;
    goto LABEL_59;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v31 )
  {
    for ( k = 0; ; ++k )
    {
      v36 = k == 32;
      if ( k >= 0x20 )
        break;
      v32 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)k);
      if ( (_DWORD)v32 == v31 )
      {
        v34 = k;
        `WppTraceIndent'::`2'::idxCurrentThread = k;
        v36 = k == 32;
        break;
      }
      if ( v9 == -1 && !(_DWORD)v32 )
        v9 = k;
    }
    if ( v36 )
    {
      if ( v9 == -1 )
      {
        v34 = -2;
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_75;
      }
      v34 = v9;
      `WppTraceIndent'::`2'::idxCurrentThread = v9;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v9) = v31;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v9 + 1) = 0;
    }
  }
  if ( v34 >= 0 )
  {
LABEL_59:
    v37 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v34 + 1);
    goto LABEL_60;
  }
LABEL_75:
  v37 = 0;
LABEL_60:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  v38 = (char *)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v37 >= 1 )
  {
    for ( m = 1; m <= v54; ++m )
    {
      if ( (unsigned int)StringCbCatA(v38, v32, "..") )
        break;
    }
    v38 = (char *)WPP_GLOBAL_Control;
  }
  v39 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v39 )
  {
    ++v39;
    if ( !--v30 )
      goto LABEL_70;
  }
  v40 = "<";
  v41 = (char *)&`wil::SetLastError'::`5'::depth - v30;
  v42 = 2147483646;
  do
  {
    if ( !v42 )
      break;
    v43 = *v40;
    if ( !*v40 )
      break;
    ++v40;
    *v41++ = v43;
    --v42;
    --v30;
  }
  while ( v30 );
  v44 = v41 - 1;
  if ( v30 )
    v44 = v41;
  *v44 = 0;
LABEL_70:
  if ( v34 >= 0 )
  {
    v46 = 8LL * v34;
    v12 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v46 + 4))-- == 1;
    if ( v12 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v46) = 0;
  }
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v38 != (char *)&WPP_GLOBAL_Control && (v38[28] & 2) != 0 && (unsigned __int8)v38[25] >= 5u )
    WPP_SF_sd(*((_QWORD *)v38 + 2), 11, (unsigned int)WPP_b9891d3101073fd7de822d6ffb5eb0dd_Traceguids, v33, v14);
  return v14;
}

```

## disassembly

```asm
0x1800046a0  mov     [rsp+arg_18], r9d
0x1800046a5  mov     [rsp+arg_10], r8
0x1800046aa  mov     [rsp+arg_8], edx
0x1800046ae  push    rbx
0x1800046af  push    rsi
0x1800046b0  push    rdi
0x1800046b1  push    r12
0x1800046b3  push    r13
0x1800046b5  push    r14
0x1800046b7  push    r15
0x1800046b9  sub     rsp, 70h
0x1800046bd  mov     r15, rcx
0x1800046c0  call    cs:__imp_GetCurrentThreadId
0x1800046c6  mov     r10d, eax
0x1800046c9  movsxd  r11, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800046d0  lea     rbx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800046d7  cmp     r11d, 0FFFFFFFFh
0x1800046db  jz      loc_18000486A
0x1800046e1  cmp     r11d, 0FFFFFFFEh
0x1800046e5  jz      short loc_1800046ED
0x1800046e7  cmp     [rbx+r11*8], eax
0x1800046eb  jz      short loc_180004749
0x1800046ed  mov     r12d, 0FFFFFFFFh
0x1800046f3  mov     r8d, r12d
0x1800046f6  xor     eax, eax
0x1800046f8  cmp     eax, 20h ; ' '
0x1800046fb  jnb     short loc_180004725
0x1800046fd  movsxd  rcx, eax
0x180004700  mov     edx, [rbx+rcx*8]
0x180004703  cmp     edx, r10d
0x180004706  jz      short loc_180004719
0x180004708  cmp     r8d, r12d
0x18000470b  jz      short loc_180004711
0x18000470d  inc     eax
0x18000470f  jmp     short loc_1800046F8
0x180004711  test    edx, edx
0x180004713  cmovz   r8d, eax
0x180004717  jmp     short loc_18000470D
0x180004719  mov     r11d, eax
0x18000471c  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180004722  cmp     eax, 20h ; ' '
0x180004725  jnz     short loc_18000474F
0x180004727  xor     ecx, ecx
0x180004729  cmp     r8d, r12d
0x18000472c  jz      loc_18000488D
0x180004732  mov     r11d, r8d
0x180004735  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r8d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000473c  movsxd  rax, r8d
0x18000473f  mov     [rbx+rax*8], r10d
0x180004743  mov     [rbx+rax*8+4], ecx
0x180004747  jmp     short loc_180004751
0x180004749  mov     r12d, 0FFFFFFFFh
0x18000474f  xor     ecx, ecx
0x180004751  test    r11d, r11d
0x180004754  js      loc_180004897
0x18000475a  movsxd  rax, r11d
0x18000475d  inc     dword ptr [rbx+rax*8+4]
0x180004761  mov     r10d, [rbx+rax*8+4]
0x180004766  mov     r13d, ecx
0x180004769  mov     [rsp+0A8h+var_50], rcx
0x18000476e  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180004775  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x18000477c  test    byte ptr [rcx+1Ch], 2
0x180004780  jnz     loc_180004BCD
0x180004786  mov     edx, 100h
0x18000478b  lea     r14, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180004792  mov     rax, r14
0x180004795  cmp     byte ptr [rax], 0
0x180004798  jnz     loc_1800048CD
0x18000479e  mov     eax, 7FFFFFFEh
0x1800047a3  lea     r9, asc_1800382D0; ">"
0x1800047aa  lea     r8, ?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800047b1  sub     r8, rdx
0x1800047b4  test    rdx, rdx
0x1800047b7  jz      short loc_1800047D9
0x1800047b9  test    rax, rax
0x1800047bc  jz      short loc_1800047D9
0x1800047be  movzx   r10d, byte ptr [r9]
0x1800047c2  test    r10b, r10b
0x1800047c5  jz      short loc_1800047D9
0x1800047c7  inc     r9
0x1800047ca  mov     [r8], r10b
0x1800047cd  inc     r8
0x1800047d0  dec     rax
0x1800047d3  sub     rdx, 1
0x1800047d7  jnz     short loc_1800047B9
0x1800047d9  lea     rax, [r8-1]
0x1800047dd  test    rdx, rdx
0x1800047e0  cmovnz  rax, r8
0x1800047e4  mov     byte ptr [rax], 0
0x1800047e7  mov     cs:?WPP_pszIndent@@3PEADEA, r14; char * WPP_pszIndent
0x1800047ee  lea     rax, WPP_GLOBAL_Control
0x1800047f5  cmp     rcx, rax
0x1800047f8  jnz     loc_18000489F
0x1800047fe  mov     rdi, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180004805  lea     rsi, [rdi+20h]
0x180004809  mov     [rsp+0A8h+var_40], rsi
0x18000480e  mov     rcx, rsi; lpCriticalSection
0x180004811  call    cs:__imp_EnterCriticalSection
0x180004817  nop
0x180004818  mov     rax, r15
0x18000481b  shr     rax, 38h
0x18000481f  cmp     al, [rdi+8]
0x180004822  jnz     short loc_180004850
0x180004824  mov     eax, r15d
0x180004827  btr     eax, 1Fh
0x18000482b  cmp     [rdi+10h], eax
0x18000482e  jbe     short loc_180004850
0x180004830  mov     edx, eax
0x180004832  shl     rdx, 4
0x180004836  mov     rax, [rdi+18h]
0x18000483a  shr     r15, 20h
0x18000483e  xor     r15d, [rdx+rax+8]
0x180004843  test    r15d, 0FFFFFFh
0x18000484a  jz      loc_1800048DF
0x180004850  mov     [rsp+0A8h+pExceptionObject], 6
0x180004858  lea     rdx, _TI1K; pThrowInfo
0x18000485f  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180004864  call    _CxxThrowException_0
0x18000486a  xor     ecx, ecx
0x18000486c  mov     r11d, ecx
0x18000486f  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180004875  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r10d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000487c  mov     cs:dword_180045874, ecx
0x180004882  mov     r12d, 0FFFFFFFFh
0x180004888  jmp     loc_18000475A
0x18000488d  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, 0FFFFFFFEh; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180004897  mov     r10d, ecx
0x18000489a  jmp     loc_180004766
0x18000489f  test    byte ptr [rcx+1Ch], 2
0x1800048a3  jz      loc_1800047FE
0x1800048a9  cmp     byte ptr [rcx+19h], 5
0x1800048ad  jb      loc_1800047FE
0x1800048b3  mov     edx, 0Ah
0x1800048b8  lea     r8, WPP_b9891d3101073fd7de822d6ffb5eb0dd_Traceguids
0x1800048bf  mov     rcx, [rcx+10h]
0x1800048c3  call    WPP_SF_s
0x1800048c8  jmp     loc_1800047FE
0x1800048cd  inc     rax
0x1800048d0  sub     rdx, 1
0x1800048d4  jnz     loc_180004795
0x1800048da  jmp     loc_1800047E7
0x1800048df  mov     rdi, [rdx+rax]
0x1800048e3  mov     rcx, rsi; lpCriticalSection
0x1800048e6  call    cs:__imp_LeaveCriticalSection
0x1800048ec  cmp     dword ptr [rdi+10h], 0
0x1800048f0  jnz     loc_180004C0A
0x1800048f6  mov     rsi, [rdi+88h]
0x1800048fd  mov     [rsp+0A8h+var_50], rsi
0x180004902  mov     rcx, [rdi+80h]; unsigned __int64
0x180004909  test    rcx, rcx
0x18000490c  jz      loc_180004AF6
0x180004912  mov     r9d, [rsp+0A8h+arg_18]; unsigned int
0x18000491a  mov     r8, [rsp+0A8h+arg_10]; struct SCARD_READERSTATEA *
0x180004922  mov     edx, [rsp+0A8h+arg_8]; unsigned int
0x180004929  call    ?RedirectedSCardGetStatusChangeA@@YAJ_KKPEAUSCARD_READERSTATEA@@K@Z; RedirectedSCardGetStatusChangeA(unsigned __int64,ulong,SCARD_READERSTATEA *,ulong)
0x18000492e  mov     r13d, eax
0x180004931  mov     [rsp+0A8h+var_78], eax
0x180004935  cmp     eax, 80100012h
0x18000493a  jz      loc_180004C23
0x180004940  mov     esi, 100h
0x180004945  lea     r15, ?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000494c  lea     rdi, WPP_GLOBAL_Control
0x180004953  call    cs:__imp_GetCurrentThreadId
0x180004959  mov     r8d, eax
0x18000495c  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180004963  cmp     r10d, 0FFFFFFFFh
0x180004967  jz      loc_180004A52
0x18000496d  cmp     r10d, 0FFFFFFFEh
0x180004971  jz      short loc_180004979
0x180004973  cmp     [rbx+r10*8], eax
0x180004977  jz      short loc_1800049B4
0x180004979  xor     ecx, ecx
0x18000497b  nop     dword ptr [rax+rax+00h]
0x180004980  cmp     ecx, 20h ; ' '
0x180004983  jnb     short loc_1800049AE
0x180004985  movsxd  rax, ecx
0x180004988  mov     edx, [rbx+rax*8]; unsigned __int64
0x18000498b  cmp     edx, r8d
0x18000498e  jz      short loc_1800049A2
0x180004990  cmp     r12d, 0FFFFFFFFh
0x180004994  jz      short loc_18000499A
0x180004996  inc     ecx
0x180004998  jmp     short loc_180004980
0x18000499a  test    edx, edx
0x18000499c  cmovz   r12d, ecx
0x1800049a0  jmp     short loc_180004996
0x1800049a2  mov     r10d, ecx
0x1800049a5  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800049ab  cmp     ecx, 20h ; ' '
0x1800049ae  jz      loc_180004A9F
0x1800049b4  test    r10d, r10d
0x1800049b7  js      loc_180004A7C
0x1800049bd  movsxd  rax, r10d
0x1800049c0  mov     r11d, [rbx+rax*8+4]
0x1800049c5  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x1800049cc  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x1800049d3  test    byte ptr [rcx+1Ch], 2
0x1800049d7  jnz     loc_180004C50
0x1800049dd  mov     rax, r14
0x1800049e0  cmp     byte ptr [rax], 0
0x1800049e3  jnz     loc_180004BBB
0x1800049e9  lea     rax, asc_1800382CC; "<"
0x1800049f0  sub     r15, rsi
0x1800049f3  test    rsi, rsi
0x1800049f6  jz      short loc_180004A1C
0x1800049f8  mov     r8d, 7FFFFFFEh
0x1800049fe  test    r8, r8
0x180004a01  jz      short loc_180004A1C
0x180004a03  movzx   edx, byte ptr [rax]
0x180004a06  test    dl, dl
0x180004a08  jz      short loc_180004A1C
0x180004a0a  inc     rax
0x180004a0d  mov     [r15], dl
0x180004a10  inc     r15
0x180004a13  dec     r8
0x180004a16  sub     rsi, 1
0x180004a1a  jnz     short loc_1800049FE
0x180004a1c  lea     rax, [r15-1]
0x180004a20  test    rsi, rsi
0x180004a23  cmovnz  rax, r15
0x180004a27  mov     byte ptr [rax], 0
0x180004a2a  test    r10d, r10d
0x180004a2d  jns     short loc_180004A84
0x180004a2f  mov     cs:?WPP_pszIndent@@3PEADEA, r14; char * WPP_pszIndent
0x180004a36  cmp     rcx, rdi
0x180004a39  jnz     loc_180004AC3
0x180004a3f  mov     eax, r13d
0x180004a42  add     rsp, 70h
0x180004a46  pop     r15
0x180004a48  pop     r14
0x180004a4a  pop     r13
0x180004a4c  pop     r12
0x180004a4e  pop     rdi
0x180004a4f  pop     rsi
0x180004a50  pop     rbx
0x180004a51  retn
0x180004a52  xor     r10d, r10d
0x180004a55  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r10d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180004a5c  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r8d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180004a63  mov     cs:dword_180045874, r10d
0x180004a6a  jmp     loc_1800049BD
0x180004a6f  mov     r10d, 0FFFFFFFEh
0x180004a75  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r10d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180004a7c  xor     r11d, r11d
0x180004a7f  jmp     loc_1800049C5
0x180004a84  movsxd  rax, r10d
0x180004a87  lea     rdx, ds:0[rax*8]
0x180004a8f  sub     dword ptr [rdx+rbx+4], 1
0x180004a94  jnz     short loc_180004A2F
0x180004a96  mov     dword ptr [rdx+rbx], 0
0x180004a9d  jmp     short loc_180004A2F
0x180004a9f  cmp     r12d, 0FFFFFFFFh
0x180004aa3  jz      short loc_180004A6F
0x180004aa5  mov     r10d, r12d
0x180004aa8  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r12d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180004aaf  movsxd  rax, r12d
0x180004ab2  mov     [rbx+rax*8], r8d
0x180004ab6  mov     dword ptr [rbx+rax*8+4], 0
0x180004abe  jmp     loc_1800049B4
0x180004ac3  test    byte ptr [rcx+1Ch], 2
0x180004ac7  jz      loc_180004A3F
0x180004acd  cmp     byte ptr [rcx+19h], 5
0x180004ad1  jb      loc_180004A3F
0x180004ad7  mov     edx, 0Bh
0x180004adc  mov     [rsp+0A8h+var_88], r13d
0x180004ae1  lea     r8, WPP_b9891d3101073fd7de822d6ffb5eb0dd_Traceguids
0x180004ae8  mov     rcx, [rcx+10h]
0x180004aec  call    WPP_SF_sd
0x180004af1  jmp     loc_180004A3F
0x180004af6  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180004afd  mov     [rsp+0A8h+var_68], rax
0x180004b02  xor     r15d, r15d
0x180004b05  mov     [rsp+0A8h+var_60], r15
0x180004b0a  mov     [rsp+0A8h+var_58], r15d
0x180004b0f  mov     [rsp+0A8h+var_54], r15d
0x180004b14  mov     [rsp+0A8h+var_74], r15d
0x180004b19  xor     esi, esi
0x180004b1b  mov     [rsp+0A8h+var_74], esi
0x180004b1f  mov     eax, [rsp+0A8h+arg_18]
0x180004b26  cmp     esi, eax
0x180004b28  jnb     short loc_180004B53
0x180004b2a  mov     edx, esi
0x180004b2c  shl     rdx, 6
0x180004b30  mov     rax, [rsp+0A8h+arg_10]
0x180004b38  mov     rdx, [rdx+rax]; char *
0x180004b3c  lea     rcx, [rsp+0A8h+var_68]; struct CBuffer *
0x180004b41  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBD@Z; MStrAdd(CBuffer &,char const *)
0x180004b46  inc     esi
0x180004b48  mov     [rsp+0A8h+var_74], esi
0x180004b4c  mov     r15, [rsp+0A8h+var_60]
0x180004b51  jmp     short loc_180004B1F
0x180004b53  lea     rdx, WideCharStr
0x180004b5a  cmp     [rsp+0A8h+var_54], 0
0x180004b5f  cmova   rdx, r15; unsigned __int16 *
0x180004b63  mov     r10d, [rsp+0A8h+arg_8]
0x180004b6b  mov     [rsp+0A8h+var_88], r10d; unsigned int
0x180004b70  mov     r9d, eax; unsigned int
0x180004b73  mov     r8, [rsp+0A8h+arg_10]; struct SCARD_READERSTATEW *
0x180004b7b  mov     rcx, rdi; this
  ... truncated ...
```
