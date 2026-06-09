# CIOPort::ProcessItems(CThreadState *)

- ea: `0x180148d00`
- end: `0x18014942a`
- name: `?ProcessItems@CIOPort@@IEAA?AW4eThreadNextStep@@PEAUCThreadState@@@Z`
- size: `1834`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180149430`

## callees

- `0x18000b7dc`
- `0x18001373c`
- `0x180131760`
- `0x180148690`
- `0x1801489b0`
- `0x180148c20`
- `0x180148d00`
- `0x18014ad0c`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18014920b`
- `KERNEL32!EnterCriticalSection` at `0x18014920b`
- `KERNEL32!LeaveCriticalSection` at `0x180149262`
- `KERNEL32!LeaveCriticalSection` at `0x180149262`
- `KERNEL32!GetLastError` at `0x180148ee9`
- `KERNEL32!GetLastError` at `0x180148ee9`
- `KERNEL32!GetCurrentThreadId` at `0x180148d45`
- `KERNEL32!GetCurrentThreadId` at `0x180148e70`
- `KERNEL32!GetCurrentThreadId` at `0x180149026`
- `KERNEL32!GetCurrentThreadId` at `0x180149106`
- `KERNEL32!GetCurrentThreadId` at `0x1801491ec`
- `KERNEL32!GetCurrentThreadId` at `0x1801492b0`
- `KERNEL32!GetCurrentThreadId` at `0x180148d45`
- `KERNEL32!GetCurrentThreadId` at `0x180148e70`
- `KERNEL32!GetCurrentThreadId` at `0x180149026`
- `KERNEL32!GetCurrentThreadId` at `0x180149106`
- `KERNEL32!GetCurrentThreadId` at `0x1801491ec`
- `KERNEL32!GetCurrentThreadId` at `0x1801492b0`
- `KERNEL32!FlsGetValue` at `0x180148d37`
- `KERNEL32!FlsGetValue` at `0x180148e62`
- `KERNEL32!FlsGetValue` at `0x180149018`
- `KERNEL32!FlsGetValue` at `0x1801490f8`
- `KERNEL32!FlsGetValue` at `0x1801492a2`
- `KERNEL32!FlsGetValue` at `0x180148d37`
- `KERNEL32!FlsGetValue` at `0x180148e62`
- `KERNEL32!FlsGetValue` at `0x180149018`
- `KERNEL32!FlsGetValue` at `0x1801490f8`
- `KERNEL32!FlsGetValue` at `0x1801492a2`
- `KERNEL32!FlsSetValue` at `0x180148d5d`
- `KERNEL32!FlsSetValue` at `0x180148e88`
- `KERNEL32!FlsSetValue` at `0x18014903e`
- `KERNEL32!FlsSetValue` at `0x18014911e`
- `KERNEL32!FlsSetValue` at `0x1801492c8`
- `KERNEL32!FlsSetValue` at `0x180148d5d`
- `KERNEL32!FlsSetValue` at `0x180148e88`
- `KERNEL32!FlsSetValue` at `0x18014903e`
- `KERNEL32!FlsSetValue` at `0x18014911e`
- `KERNEL32!FlsSetValue` at `0x1801492c8`
- `KERNEL32!GetThreadIOPendingFlag` at `0x180148dda`
- `KERNEL32!GetThreadIOPendingFlag` at `0x180148f90`
- `KERNEL32!GetThreadIOPendingFlag` at `0x180148dda`
- `KERNEL32!GetThreadIOPendingFlag` at `0x180148f90`
- `KERNEL32!GetCurrentThread` at `0x180148dcd`
- `KERNEL32!GetCurrentThread` at `0x180148f83`
- `KERNEL32!GetCurrentThread` at `0x180148dcd`
- `KERNEL32!GetCurrentThread` at `0x180148f83`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180148ed8`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180148ed8`

## pseudocode

```c
__int64 __fastcall CIOPort::ProcessItems(__int64 a1, PVOID a2)
{
  __int64 v2; // rdi
  PVOID Value; // rsi
  struct CThreadState *v6; // r14
  __int64 v7; // rcx
  DWORD v8; // edx
  unsigned int v9; // eax
  signed int v10; // eax
  HANDLE CurrentThread; // rax
  signed __int64 v12; // rax
  unsigned int v13; // edx
  signed __int64 v14; // rtt
  char v15; // al
  __int64 v16; // rdi
  PVOID v17; // rsi
  struct CThreadState *v18; // r14
  void *v19; // rcx
  BOOL QueuedCompletionStatus; // edi
  DWORD v21; // esi
  unsigned __int64 v22; // r8
  LPOVERLAPPED v23; // rdx
  HANDLE v24; // rax
  signed __int64 v25; // rax
  unsigned int v26; // edx
  signed __int64 v27; // rtt
  char v28; // al
  __int64 v29; // rdi
  PVOID v30; // rsi
  struct CThreadState *v31; // r14
  int v32; // eax
  __int64 v33; // rdi
  int v34; // r15d
  PVOID v35; // r14
  struct CThreadState *v36; // rsi
  unsigned int v37; // eax
  unsigned int v38; // edi
  __int64 v39; // r15
  DWORD CurrentThreadId; // edi
  struct TpSListNode *v41; // rsi
  __int64 v42; // rdi
  __int64 v44; // rdi
  PVOID v45; // r14
  struct CThreadState *v46; // rsi
  int v47; // eax
  DWORD dwMilliseconds[2]; // [rsp+20h] [rbp-49h]
  BOOL IOIsPending; // [rsp+30h] [rbp-39h] BYREF
  signed __int64 v51; // [rsp+38h] [rbp-31h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int64 CompletionKey; // [rsp+48h] [rbp-21h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v55[16]; // [rsp+58h] [rbp-11h] BYREF
  BOOL *p_IOIsPending; // [rsp+68h] [rbp-1h]
  __int64 v57; // [rsp+70h] [rbp+7h]
  BOOL *v58; // [rsp+78h] [rbp+Fh]
  __int64 v59; // [rsp+80h] [rbp+17h]

  v2 = *(_QWORD *)(a1 + 8);
  Value = FlsGetValue(*(_DWORD *)(v2 + 40));
  if ( !Value && GetCurrentThreadId() == Mso::Threadpool::details::vdwTidMain )
  {
    v6 = *(struct CThreadState **)(v2 + 72);
    if ( FlsSetValue(*(_DWORD *)(v2 + 40), v6) )
    {
      if ( CThreadManager::GetThreadState((CThreadManager *)v2) == v6 )
        Value = *(PVOID *)(v2 + 72);
      else
        MsoShipAssertTagProc(507553630);
    }
  }
  if ( Value != a2 )
    MsoShipAssertTagProc(507553820);
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v7 = *(_QWORD *)(a1 + 16);
        v8 = -1;
        v9 = ((unsigned int)v7 >> 19) & 0x7FF;
        if ( (int)v7 < 0 && v9 )
          --v9;
        v10 = v9 - (((unsigned int)v7 >> 12) & 0x7F) - 4;
        if ( v10 > 0 )
        {
          if ( (unsigned int)v10 > 4 )
          {
            IOIsPending = 0;
            CurrentThread = GetCurrentThread();
            if ( !GetThreadIOPendingFlag(CurrentThread, &IOIsPending) || !IOIsPending )
            {
              _m_prefetchw((const void *)(a1 + 16));
              v12 = *(_QWORD *)(a1 + 16);
              while ( 1 )
              {
                v51 = v12;
                v13 = ((unsigned int)v12 >> 19) & 0x7FF;
                if ( (int)v12 < 0 && v13 )
                  --v13;
                if ( (int)(v13 - (((unsigned int)v12 >> 12) & 0x7F) - 4) <= 0 )
                  break;
                LODWORD(v51) = v12 & 0xC007FFFF | (((((unsigned int)v12 >> 19) - 1) & 0x7FF) << 19);
                v14 = v12;
                v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 16), v51, v12);
                if ( v14 == v12 )
                {
                  v15 = 1;
                  goto LABEL_23;
                }
              }
              v15 = 0;
LABEL_23:
              if ( v15 )
                return 0;
            }
            v16 = *(_QWORD *)(a1 + 8);
            v17 = FlsGetValue(*(_DWORD *)(v16 + 40));
            if ( !v17 && GetCurrentThreadId() == Mso::Threadpool::details::vdwTidMain )
            {
              v18 = *(struct CThreadState **)(v16 + 72);
              if ( FlsSetValue(*(_DWORD *)(v16 + 40), v18) )
              {
                if ( CThreadManager::GetThreadState((CThreadManager *)v16) == v18 )
                  v17 = *(PVOID *)(v16 + 72);
                else
                  MsoShipAssertTagProc(507553630);
              }
            }
            if ( v17 != a2 )
              MsoShipAssertTagProc(507553822);
          }
          v8 = 6000;
        }
        v19 = *(void **)(a1 + 128);
        NumberOfBytesTransferred = 0;
        CompletionKey = 0;
        Overlapped = 0;
        QueuedCompletionStatus = GetQueuedCompletionStatus(
                                   v19,
                                   &NumberOfBytesTransferred,
                                   &CompletionKey,
                                   &Overlapped,
                                   v8);
        v21 = QueuedCompletionStatus ? 0 : GetLastError();
        v22 = CompletionKey;
        v23 = Overlapped;
        if ( QueuedCompletionStatus || Overlapped )
          break;
        if ( (Microsoft_Office_ThreadpoolEnableBits & 0x20) != 0 )
        {
          LODWORD(v51) = NumberOfBytesTransferred;
          IOIsPending = CompletionKey;
          p_IOIsPending = &IOIsPending;
          v57 = 4;
          v58 = (BOOL *)&v51;
          v59 = 4;
          McGenEventWrite_EventWriteTransfer(
            guidProviderOfficeThreadpool_Context,
            TPPortPacketReceivedFailure,
            CompletionKey,
            3,
            v55);
          v22 = CompletionKey;
        }
        if ( v22 )
          MsoShipAssertTagProc(507553813);
        if ( v21 != 258 )
          MsoShipAssertTagProc(507553812);
        IOIsPending = 0;
        v24 = GetCurrentThread();
        if ( !GetThreadIOPendingFlag(v24, &IOIsPending) || !IOIsPending )
        {
          _m_prefetchw((const void *)(a1 + 16));
          v25 = *(_QWORD *)(a1 + 16);
          while ( 1 )
          {
            v51 = v25;
            v26 = ((unsigned int)v25 >> 19) & 0x7FF;
            if ( (int)v25 < 0 && v26 )
              --v26;
            if ( (int)(v26 - (((unsigned int)v25 >> 12) & 0x7F) - 4) <= 0 )
              break;
            LODWORD(v51) = v25 & 0xC007FFFF | (((((unsigned int)v25 >> 19) - 1) & 0x7FF) << 19);
            v27 = v25;
            v25 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 16), v51, v25);
            if ( v27 == v25 )
            {
              v28 = 1;
              goto LABEL_53;
            }
          }
          v28 = 0;
LABEL_53:
          if ( v28 )
            return 0;
        }
        v29 = *(_QWORD *)(a1 + 8);
        v30 = FlsGetValue(*(_DWORD *)(v29 + 40));
        if ( !v30 && GetCurrentThreadId() == Mso::Threadpool::details::vdwTidMain )
        {
          v31 = *(struct CThreadState **)(v29 + 72);
          if ( FlsSetValue(*(_DWORD *)(v29 + 40), v31) )
          {
            if ( CThreadManager::GetThreadState((CThreadManager *)v29) == v31 )
              v30 = *(PVOID *)(v29 + 72);
            else
              MsoShipAssertTagProc(507553630);
          }
        }
        if ( v30 != a2 )
          MsoShipAssertTagProc(507553822);
      }
      if ( CompletionKey < 4 )
        break;
      if ( !Overlapped )
      {
        MsoShipAssertTagProc(507553809);
        v22 = CompletionKey;
        v23 = Overlapped;
      }
      if ( (Microsoft_Office_ThreadpoolEnableBits & 0x10) != 0 )
      {
        IOIsPending = NumberOfBytesTransferred;
        LODWORD(v51) = v22;
        p_IOIsPending = (BOOL *)&v51;
        v57 = 4;
        v58 = &IOIsPending;
        v59 = 4;
        McGenEventWrite_EventWriteTransfer(guidProviderOfficeThreadpool_Context, TPPortPacketReceivedIO, v22, 3, v55);
        v22 = CompletionKey;
        v23 = Overlapped;
      }
      dwMilliseconds[0] = v21;
      v32 = CIOPort::ProcessPortCallback(a1, v23, v22, NumberOfBytesTransferred, *(_QWORD *)dwMilliseconds, a2);
      v33 = *(_QWORD *)(a1 + 8);
      v34 = v32;
      v35 = FlsGetValue(*(_DWORD *)(v33 + 40));
      if ( !v35 && GetCurrentThreadId() == Mso::Threadpool::details::vdwTidMain )
      {
        v36 = *(struct CThreadState **)(v33 + 72);
        if ( FlsSetValue(*(_DWORD *)(v33 + 40), v36) )
        {
          if ( CThreadManager::GetThreadState((CThreadManager *)v33) == v36 )
            v35 = *(PVOID *)(v33 + 72);
          else
            MsoShipAssertTagProc(507553630);
        }
      }
      if ( v35 != a2 )
        MsoShipAssertTagProc(507553805);
      if ( v34 != 1 )
      {
        if ( !v34 )
          return 0;
        while ( 1 )
        {
LABEL_80:
          v39 = 0;
          if ( *(_BYTE *)(a1 + 268) )
          {
            CurrentThreadId = GetCurrentThreadId();
            if ( CurrentThreadId == *(_DWORD *)(a1 + 168) )
            {
              ++*(_DWORD *)(a1 + 172);
            }
            else
            {
              EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
              *(_DWORD *)(a1 + 168) = CurrentThreadId;
              *(_DWORD *)(a1 + 172) = 1;
            }
          }
          v41 = *(struct TpSListNode **)(a1 + 144);
          v42 = *(_QWORD *)v41;
          if ( *(_QWORD *)v41 )
          {
            v39 = *(_QWORD *)(v42 + 24);
            *(_QWORD *)(a1 + 144) = v42;
          }
          if ( *(_BYTE *)(a1 + 268) )
          {
            if ( (*(_DWORD *)(a1 + 172))-- == 1 )
            {
              *(_DWORD *)(a1 + 168) = 0;
              LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
            }
          }
          if ( v42 )
          {
            CTpFreeList::Push(*(CTpFreeList **)(a1 + 160), v41);
            if ( v39 )
            {
              (*(void (__fastcall **)(__int64, PVOID))(*(_QWORD *)v39 + 240LL))(v39, a2);
              v44 = *(_QWORD *)(a1 + 8);
              v45 = FlsGetValue(*(_DWORD *)(v44 + 40));
              if ( !v45 && GetCurrentThreadId() == Mso::Threadpool::details::vdwTidMain )
              {
                v46 = *(struct CThreadState **)(v44 + 72);
                if ( FlsSetValue(*(_DWORD *)(v44 + 40), v46) )
                {
                  if ( CThreadManager::GetThreadState((CThreadManager *)v44) == v46 )
                    v45 = *(PVOID *)(v44 + 72);
                  else
                    MsoShipAssertTagProc(507553630);
                }
              }
              if ( v45 != a2 )
                MsoShipAssertTagProc(507553792);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            }
          }
          v47 = CIOPort::AfterCallback(a1, a2);
          if ( v47 == 1 )
            break;
          if ( !v47 )
            return 0;
        }
      }
    }
    if ( (Microsoft_Office_ThreadpoolEnableBits & 0x10) != 0 )
    {
      IOIsPending = NumberOfBytesTransferred;
      LODWORD(v51) = CompletionKey;
      p_IOIsPending = (BOOL *)&v51;
      v57 = 4;
      v58 = &IOIsPending;
      v59 = 4;
      McGenEventWrite_EventWriteTransfer(
        guidProviderOfficeThreadpool_Context,
        TPPortPacketReceivedWorker,
        CompletionKey,
        3,
        v55);
      v22 = CompletionKey;
      v23 = Overlapped;
    }
    v37 = CIOPort::BeforeProcessingWorker(a1, v23, v22, a2);
    v38 = v37;
  }
  while ( v37 == 1 );
  if ( v37 == 2 )
    goto LABEL_80;
  if ( v37 && v37 != 3 )
    MsoShipAssertTagProc(507553798);
  return v38;
}

```

## disassembly

```asm
0x180148d00  mov     [rsp-8+arg_10], rbx
0x180148d05  push    rbp
0x180148d06  push    rsi
0x180148d07  push    rdi
0x180148d08  push    r12
0x180148d0a  push    r13
0x180148d0c  push    r14
0x180148d0e  push    r15
0x180148d10  lea     rbp, [rsp-27h]
0x180148d15  sub     rsp, 90h
0x180148d1c  mov     rax, cs:__security_cookie
0x180148d23  xor     rax, rsp
0x180148d26  mov     [rbp+57h+var_38], rax
0x180148d2a  mov     rdi, [rcx+8]
0x180148d2e  mov     rbx, rcx
0x180148d31  mov     r12, rdx
0x180148d34  mov     ecx, [rdi+28h]; dwFlsIndex
0x180148d37  call    cs:__imp_FlsGetValue
0x180148d3d  mov     rsi, rax
0x180148d40  test    rax, rax
0x180148d43  jnz     short loc_180148D7C
0x180148d45  call    cs:__imp_GetCurrentThreadId
0x180148d4b  cmp     eax, cs:?vdwTidMain@details@Threadpool@Mso@@3KA; ulong Mso::Threadpool::details::vdwTidMain
0x180148d51  jnz     short loc_180148D7C
0x180148d53  mov     r14, [rdi+48h]
0x180148d57  mov     ecx, [rdi+28h]; dwFlsIndex
0x180148d5a  mov     rdx, r14; lpFlsData
0x180148d5d  call    cs:__imp_FlsSetValue
0x180148d63  test    eax, eax
0x180148d65  jz      short loc_180148D7C
0x180148d67  mov     rcx, rdi; this
0x180148d6a  call    ?GetThreadState@CThreadManager@@QEBAPEAUCThreadState@@XZ; CThreadManager::GetThreadState(void)
0x180148d6f  cmp     rax, r14
0x180148d72  jnz     loc_18014936D
0x180148d78  mov     rsi, [rdi+48h]
0x180148d7c  cmp     rsi, r12
0x180148d7f  jnz     loc_18014937C
0x180148d85  xor     r13d, r13d
0x180148d88  nop     dword ptr [rax+rax+00000000h]
0x180148d90  mov     rcx, [rbx+10h]
0x180148d94  mov     edx, 0FFFFFFFFh
0x180148d99  mov     eax, ecx
0x180148d9b  shr     eax, 13h
0x180148d9e  and     eax, 7FFh
0x180148da3  test    ecx, ecx
0x180148da5  jns     short loc_180148DAD
0x180148da7  test    eax, eax
0x180148da9  jz      short loc_180148DAD
0x180148dab  dec     eax
0x180148dad  shr     ecx, 0Ch
0x180148db0  and     ecx, 7Fh
0x180148db3  sub     eax, ecx
0x180148db5  sub     eax, 4
0x180148db8  test    eax, eax
0x180148dba  jle     loc_180148EB5
0x180148dc0  cmp     eax, 4
0x180148dc3  jbe     loc_180148EB0
0x180148dc9  mov     [rbp+57h+IOIsPending], r13d
0x180148dcd  call    cs:__imp_GetCurrentThread
0x180148dd3  mov     rcx, rax; hThread
0x180148dd6  lea     rdx, [rbp+57h+IOIsPending]; lpIOIsPending
0x180148dda  call    cs:__imp_GetThreadIOPendingFlag
0x180148de0  test    eax, eax
0x180148de2  jz      short loc_180148DEA
0x180148de4  cmp     [rbp+57h+IOIsPending], r13d
0x180148de8  jnz     short loc_180148E5B
0x180148dea  prefetchw byte ptr [rbx+10h]
0x180148dee  mov     rax, [rbx+10h]
0x180148df2  mov     [rbp+57h+var_88], rax
0x180148df6  mov     r8d, dword ptr [rbp+57h+var_88]
0x180148dfa  mov     r9d, r8d
0x180148dfd  shr     r9d, 13h
0x180148e01  mov     edx, r9d
0x180148e04  and     edx, 7FFh
0x180148e0a  test    r8d, r8d
0x180148e0d  jns     short loc_180148E15
0x180148e0f  test    edx, edx
0x180148e11  jz      short loc_180148E15
0x180148e13  dec     edx
0x180148e15  mov     ecx, r8d
0x180148e18  shr     ecx, 0Ch
0x180148e1b  and     ecx, 7Fh
0x180148e1e  sub     edx, ecx
0x180148e20  sub     edx, 4
0x180148e23  test    edx, edx
0x180148e25  jle     short loc_180148E51
0x180148e27  lea     ecx, [r9-1]
0x180148e2b  and     r8d, 0C007FFFFh
0x180148e32  and     ecx, 7FFh
0x180148e38  shl     ecx, 13h
0x180148e3b  or      ecx, r8d
0x180148e3e  mov     dword ptr [rbp+57h+var_88], ecx
0x180148e41  mov     rcx, [rbp+57h+var_88]
0x180148e45  lock cmpxchg [rbx+10h], rcx
0x180148e4b  jnz     short loc_180148DF2
0x180148e4d  mov     al, 1
0x180148e4f  jmp     short loc_180148E53
0x180148e51  xor     al, al
0x180148e53  test    al, al
0x180148e55  jnz     loc_18014931C
0x180148e5b  mov     rdi, [rbx+8]
0x180148e5f  mov     ecx, [rdi+28h]; dwFlsIndex
0x180148e62  call    cs:__imp_FlsGetValue
0x180148e68  mov     rsi, rax
0x180148e6b  test    rax, rax
0x180148e6e  jnz     short loc_180148EA7
0x180148e70  call    cs:__imp_GetCurrentThreadId
0x180148e76  cmp     eax, cs:?vdwTidMain@details@Threadpool@Mso@@3KA; ulong Mso::Threadpool::details::vdwTidMain
0x180148e7c  jnz     short loc_180148EA7
0x180148e7e  mov     r14, [rdi+48h]
0x180148e82  mov     ecx, [rdi+28h]; dwFlsIndex
0x180148e85  mov     rdx, r14; lpFlsData
0x180148e88  call    cs:__imp_FlsSetValue
0x180148e8e  test    eax, eax
0x180148e90  jz      short loc_180148EA7
0x180148e92  mov     rcx, rdi; this
0x180148e95  call    ?GetThreadState@CThreadManager@@QEBAPEAUCThreadState@@XZ; CThreadManager::GetThreadState(void)
0x180148e9a  cmp     rax, r14
0x180148e9d  jnz     loc_18014938B
0x180148ea3  mov     rsi, [rdi+48h]
0x180148ea7  cmp     rsi, r12
0x180148eaa  jnz     loc_18014939A
0x180148eb0  mov     edx, 1770h
0x180148eb5  mov     rcx, [rbx+80h]; CompletionPort
0x180148ebc  lea     r9, [rbp+57h+Overlapped]; lpOverlapped
0x180148ec0  mov     [rsp+0C0h+dwMilliseconds], edx; dwMilliseconds
0x180148ec4  lea     r8, [rbp+57h+CompletionKey]; lpCompletionKey
0x180148ec8  lea     rdx, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180148ecc  mov     [rbp+57h+NumberOfBytesTransferred], r13d
0x180148ed0  mov     [rbp+57h+CompletionKey], r13
0x180148ed4  mov     [rbp+57h+Overlapped], r13
0x180148ed8  call    cs:__imp_GetQueuedCompletionStatus
0x180148ede  mov     edi, eax
0x180148ee0  test    eax, eax
0x180148ee2  jz      short loc_180148EE9
0x180148ee4  mov     esi, r13d
0x180148ee7  jmp     short loc_180148EF1
0x180148ee9  call    cs:__imp_GetLastError
0x180148eef  mov     esi, eax
0x180148ef1  mov     r8, [rbp+57h+CompletionKey]
0x180148ef5  mov     rdx, [rbp+57h+Overlapped]
0x180148ef9  cmp     r8, 4
0x180148efd  setnb   cl
0x180148f00  test    edi, edi
0x180148f02  jnz     loc_18014906B
0x180148f08  test    rdx, rdx
0x180148f0b  jnz     loc_18014906B
0x180148f11  test    cs:Microsoft_Office_ThreadpoolEnableBits, 20h
0x180148f18  jz      short loc_180148F6A
0x180148f1a  mov     eax, [rbp+57h+NumberOfBytesTransferred]
0x180148f1d  lea     rdx, TPPortPacketReceivedFailure
0x180148f24  mov     dword ptr [rbp+57h+var_88], eax
0x180148f27  lea     rcx, guidProviderOfficeThreadpool_Context
0x180148f2e  lea     rax, [rbp+57h+IOIsPending]
0x180148f32  mov     [rbp+57h+IOIsPending], r8d
0x180148f36  mov     [rbp+57h+var_58], rax
0x180148f3a  mov     r9d, 3
0x180148f40  lea     rax, [rbp+57h+var_88]
0x180148f44  mov     [rbp+57h+var_50], 4
0x180148f4c  mov     [rbp+57h+var_48], rax
0x180148f50  lea     rax, [rbp+57h+var_68]
0x180148f54  mov     qword ptr [rsp+0C0h+dwMilliseconds], rax
0x180148f59  mov     [rbp+57h+var_40], 4
0x180148f61  call    McGenEventWrite_EventWriteTransfer
0x180148f66  mov     r8, [rbp+57h+CompletionKey]
0x180148f6a  test    r8, r8
0x180148f6d  jnz     loc_1801493A9
0x180148f73  cmp     esi, 102h
0x180148f79  jnz     loc_1801493B8
0x180148f7f  mov     [rbp+57h+IOIsPending], r13d
0x180148f83  call    cs:__imp_GetCurrentThread
0x180148f89  mov     rcx, rax; hThread
0x180148f8c  lea     rdx, [rbp+57h+IOIsPending]; lpIOIsPending
0x180148f90  call    cs:__imp_GetThreadIOPendingFlag
0x180148f96  test    eax, eax
0x180148f98  jz      short loc_180148FA0
0x180148f9a  cmp     [rbp+57h+IOIsPending], r13d
0x180148f9e  jnz     short loc_180149011
0x180148fa0  prefetchw byte ptr [rbx+10h]
0x180148fa4  mov     rax, [rbx+10h]
0x180148fa8  mov     [rbp+57h+var_88], rax
0x180148fac  mov     r8d, dword ptr [rbp+57h+var_88]
0x180148fb0  mov     r9d, r8d
0x180148fb3  shr     r9d, 13h
0x180148fb7  mov     edx, r9d
0x180148fba  and     edx, 7FFh
0x180148fc0  test    r8d, r8d
0x180148fc3  jns     short loc_180148FCB
0x180148fc5  test    edx, edx
0x180148fc7  jz      short loc_180148FCB
0x180148fc9  dec     edx
0x180148fcb  mov     ecx, r8d
0x180148fce  shr     ecx, 0Ch
0x180148fd1  and     ecx, 7Fh
0x180148fd4  sub     edx, ecx
0x180148fd6  sub     edx, 4
0x180148fd9  test    edx, edx
0x180148fdb  jle     short loc_180149007
0x180148fdd  lea     ecx, [r9-1]
0x180148fe1  and     r8d, 0C007FFFFh
0x180148fe8  and     ecx, 7FFh
0x180148fee  shl     ecx, 13h
0x180148ff1  or      ecx, r8d
0x180148ff4  mov     dword ptr [rbp+57h+var_88], ecx
0x180148ff7  mov     rcx, [rbp+57h+var_88]
0x180148ffb  lock cmpxchg [rbx+10h], rcx
0x180149001  jnz     short loc_180148FA8
0x180149003  mov     al, 1
0x180149005  jmp     short loc_180149009
0x180149007  xor     al, al
0x180149009  test    al, al
0x18014900b  jnz     loc_18014931C
0x180149011  mov     rdi, [rbx+8]
0x180149015  mov     ecx, [rdi+28h]; dwFlsIndex
0x180149018  call    cs:__imp_FlsGetValue
0x18014901e  mov     rsi, rax
0x180149021  test    rax, rax
0x180149024  jnz     short loc_18014905D
0x180149026  call    cs:__imp_GetCurrentThreadId
0x18014902c  cmp     eax, cs:?vdwTidMain@details@Threadpool@Mso@@3KA; ulong Mso::Threadpool::details::vdwTidMain
0x180149032  jnz     short loc_18014905D
0x180149034  mov     r14, [rdi+48h]
0x180149038  mov     ecx, [rdi+28h]; dwFlsIndex
0x18014903b  mov     rdx, r14; lpFlsData
0x18014903e  call    cs:__imp_FlsSetValue
0x180149044  test    eax, eax
0x180149046  jz      short loc_18014905D
0x180149048  mov     rcx, rdi; this
0x18014904b  call    ?GetThreadState@CThreadManager@@QEBAPEAUCThreadState@@XZ; CThreadManager::GetThreadState(void)
0x180149050  cmp     rax, r14
0x180149053  jnz     loc_1801493C7
0x180149059  mov     rsi, [rdi+48h]
0x18014905d  cmp     rsi, r12
0x180149060  jnz     loc_18014935E
0x180149066  jmp     loc_180148D90
0x18014906b  test    cl, cl
0x18014906d  jz      loc_18014915E
0x180149073  test    rdx, rdx
0x180149076  jz      loc_1801493D6
0x18014907c  test    cs:Microsoft_Office_ThreadpoolEnableBits, 10h
0x180149083  jz      short loc_1801490D9
0x180149085  mov     eax, [rbp+57h+NumberOfBytesTransferred]
0x180149088  lea     rdx, TPPortPacketReceivedIO
0x18014908f  mov     [rbp+57h+IOIsPending], eax
0x180149092  lea     rcx, guidProviderOfficeThreadpool_Context
0x180149099  lea     rax, [rbp+57h+var_88]
0x18014909d  mov     dword ptr [rbp+57h+var_88], r8d
0x1801490a1  mov     [rbp+57h+var_58], rax
0x1801490a5  mov     r9d, 3
0x1801490ab  lea     rax, [rbp+57h+IOIsPending]
0x1801490af  mov     [rbp+57h+var_50], 4
0x1801490b7  mov     [rbp+57h+var_48], rax
0x1801490bb  lea     rax, [rbp+57h+var_68]
0x1801490bf  mov     qword ptr [rsp+0C0h+dwMilliseconds], rax
0x1801490c4  mov     [rbp+57h+var_40], 4
0x1801490cc  call    McGenEventWrite_EventWriteTransfer
0x1801490d1  mov     r8, [rbp+57h+CompletionKey]
0x1801490d5  mov     rdx, [rbp+57h+Overlapped]
0x1801490d9  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x1801490dd  mov     rcx, rbx
0x1801490e0  mov     [rsp+0C0h+var_98], r12
0x1801490e5  mov     [rsp+0C0h+dwMilliseconds], esi
0x1801490e9  call    ?ProcessPortCallback@CIOPort@@IEAA?AW4eThreadNextStep@@PEAU_OVERLAPPED@@_KKKPEAUCThreadState@@@Z; CIOPort::ProcessPortCallback(_OVERLAPPED *,unsigned __int64,ulong,ulong,CThreadState *)
0x1801490ee  mov     rdi, [rbx+8]
0x1801490f2  mov     r15d, eax
0x1801490f5  mov     ecx, [rdi+28h]; dwFlsIndex
0x1801490f8  call    cs:__imp_FlsGetValue
0x1801490fe  mov     r14, rax
0x180149101  test    rax, rax
0x180149104  jnz     short loc_18014913D
0x180149106  call    cs:__imp_GetCurrentThreadId
0x18014910c  cmp     eax, cs:?vdwTidMain@details@Threadpool@Mso@@3KA; ulong Mso::Threadpool::details::vdwTidMain
0x180149112  jnz     short loc_18014913D
0x180149114  mov     rsi, [rdi+48h]
0x180149118  mov     ecx, [rdi+28h]; dwFlsIndex
0x18014911b  mov     rdx, rsi; lpFlsData
0x18014911e  call    cs:__imp_FlsSetValue
0x180149124  test    eax, eax
0x180149126  jz      short loc_18014913D
0x180149128  mov     rcx, rdi; this
0x18014912b  call    ?GetThreadState@CThreadManager@@QEBAPEAUCThreadState@@XZ; CThreadManager::GetThreadState(void)
0x180149130  cmp     rax, rsi
0x180149133  jnz     loc_1801493ED
0x180149139  mov     r14, [rdi+48h]
0x18014913d  cmp     r14, r12
0x180149140  jnz     loc_1801493FC
0x180149146  cmp     r15d, 1
0x18014914a  jz      loc_180148D90
0x180149150  test    r15d, r15d
0x180149153  jz      loc_18014931C
0x180149159  jmp     loc_1801491E0
0x18014915e  test    cs:Microsoft_Office_ThreadpoolEnableBits, 10h
0x180149165  jz      short loc_1801491BB
0x180149167  mov     eax, [rbp+57h+NumberOfBytesTransferred]
0x18014916a  lea     rdx, TPPortPacketReceivedWorker
0x180149171  mov     [rbp+57h+IOIsPending], eax
0x180149174  lea     rcx, guidProviderOfficeThreadpool_Context
0x18014917b  lea     rax, [rbp+57h+var_88]
0x18014917f  mov     dword ptr [rbp+57h+var_88], r8d
0x180149183  mov     [rbp+57h+var_58], rax
  ... truncated ...
```
