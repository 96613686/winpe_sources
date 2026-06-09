# CWorkerThread::Start(void)

- ea: `0x140060820`
- end: `0x140060bd9`
- name: `?Start@CWorkerThread@@UEAAJXZ`
- size: `953`
- prototype: `__int64 __fastcall(CWorkerThread *__hidden this)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140009778`
- `0x14000b980`
- `0x140035ec0`
- `0x14006a730`
- `0x14006e19c`
- `0x14006e81c`

## callees

- `0x140004730`
- `0x140004a04`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140060820`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140060a4f`
- `KERNEL32!CloseHandle` at `0x140060baf`
- `KERNEL32!CloseHandle` at `0x140060a4f`
- `KERNEL32!CloseHandle` at `0x140060baf`
- `KERNEL32!GetThreadId` at `0x140060b85`
- `KERNEL32!GetThreadId` at `0x140060b85`
- `KERNEL32!CreateThread` at `0x140060a7c`
- `KERNEL32!CreateThread` at `0x140060a7c`
- `KERNEL32!WaitForSingleObject` at `0x140060ab9`
- `KERNEL32!WaitForSingleObject` at `0x140060ab9`
- `KERNEL32!ResetEvent` at `0x1400609fb`
- `KERNEL32!ResetEvent` at `0x1400609fb`
- `KERNEL32!CreateEventW` at `0x140060923`
- `KERNEL32!CreateEventW` at `0x140060a0b`
- `KERNEL32!CreateEventW` at `0x140060923`
- `KERNEL32!CreateEventW` at `0x140060a0b`
- `KERNEL32!GetLastError` at `0x140060936`
- `KERNEL32!GetLastError` at `0x140060a1a`
- `KERNEL32!GetLastError` at `0x140060a8b`
- `KERNEL32!GetLastError` at `0x140060ac7`
- `KERNEL32!GetLastError` at `0x140060936`
- `KERNEL32!GetLastError` at `0x140060a1a`
- `KERNEL32!GetLastError` at `0x140060a8b`
- `KERNEL32!GetLastError` at `0x140060ac7`
- `KERNEL32!IsDebuggerPresent` at `0x140060894`
- `KERNEL32!IsDebuggerPresent` at `0x140060991`
- `KERNEL32!IsDebuggerPresent` at `0x140060b49`
- `KERNEL32!IsDebuggerPresent` at `0x140060894`
- `KERNEL32!IsDebuggerPresent` at `0x140060991`
- `KERNEL32!IsDebuggerPresent` at `0x140060b49`

## string_xrefs

- `0x14006085c`: `m_eThreadStatus == WTTS_Stopped`
- `0x140060872`: `CWorkerThread::Start`
- `0x14006096d`: `CWorkerThread::Start`
- `0x140060af2`: `CWorkerThread::Start`
- `0x140060885`: `termsrv\wms\src\common\srcutils\workerthread.cpp`
- `0x140060982`: `termsrv\wms\src\common\srcutils\workerthread.cpp`
- `0x140060b07`: `termsrv\wms\src\common\srcutils\workerthread.cpp`
- `0x14006094b`: `m_hThreadKillEvent`
- `0x140060a2f`: `m_hThreadStarted`
- `0x140060aa0`: `m_hThread`
- `0x140060ae6`: ` - thread failed to start.`
- `0x140060b95`: `CWorkerThread::Start - %s thread started:  id = 0x%X  obj = 0x%X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkerThread::Start(CWorkerThread *this, __int64 a2, __int64 a3, const unsigned __int16 *a4)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  const unsigned __int16 *v7; // r9
  signed int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  const unsigned __int16 *v11; // r9
  void *v12; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  const unsigned __int16 *v15; // r13
  unsigned int v16; // r12d
  HANDLE v17; // rax
  signed int v18; // eax
  char *v19; // rcx
  HANDLE Thread; // rax
  signed int v21; // eax
  signed int v22; // eax
  DWORD ThreadId; // eax
  char *v24; // rcx
  int v26; // [rsp+30h] [rbp-38h]
  signed int v27; // [rsp+30h] [rbp-38h]
  signed int v28; // [rsp+30h] [rbp-38h]
  int v29; // [rsp+38h] [rbp-30h]
  signed int v30; // [rsp+38h] [rbp-30h]
  signed int v31; // [rsp+38h] [rbp-30h]
  PSRWLOCK v32; // [rsp+70h] [rbp+8h] BYREF

  CAutoWriteLock::CAutoWriteLock((CAutoWriteLock *)&v32, (CWorkerThread *)((char *)this + 48), a3, a4);
  if ( *((_DWORD *)this + 10) != 3 )
  {
    v8 = -2147418113;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
      0x3Au,
      L"CWorkerThread::Start",
      L"CBRAEx",
      L"m_eThreadStatus == WTTS_Stopped",
      -2147418113);
    if ( IsDebuggerPresent() )
    {
      v29 = -2147418113;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
        58,
        L"CWorkerThread::Start",
        L"CBRAEx",
        L"m_eThreadStatus == WTTS_Stopped",
        v29);
    }
    else
    {
      v26 = -2147418113;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
        58,
        L"CWorkerThread::Start",
        L"CBRAEx",
        L"m_eThreadStatus == WTTS_Stopped",
        v26);
    }
    CAutoWriteLock::~CAutoWriteLock(&v32, v9, v10, v11);
    goto LABEL_39;
  }
  *((_DWORD *)this + 10) = 0;
  CAutoWriteLock::~CAutoWriteLock(&v32, v5, v6, v7);
  v12 = (void *)*((_QWORD *)this + 3);
  if ( v12 )
  {
    ResetEvent(v12);
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 3) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v15 = L"m_hThreadKillEvent";
      v16 = 71;
LABEL_11:
      if ( v8 >= 0 )
        v8 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
        v16,
        L"CWorkerThread::Start",
        L"CBRAEx",
        v15,
        v8);
      if ( IsDebuggerPresent() )
      {
        v30 = v8;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
          v16,
          L"CWorkerThread::Start",
          L"CBRAEx",
          v15,
          v30);
      }
      else
      {
        v27 = v8;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
          v16,
          L"CWorkerThread::Start",
          L"CBRAEx",
          v15,
          v27);
      }
      goto LABEL_39;
    }
    *((_DWORD *)this + 11) = 1;
  }
  v17 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 4) = v17;
  if ( !v17 )
  {
    v18 = GetLastError();
    v8 = v18;
    if ( v18 > 0 )
      v8 = (unsigned __int16)v18 | 0x80070000;
    v15 = L"m_hThreadStarted";
    v16 = 80;
    goto LABEL_11;
  }
  v19 = (char *)*((_QWORD *)this + 2);
  if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v19);
    *((_QWORD *)this + 2) = 0;
  }
  Thread = CreateThread(0, 0, CWorkerThread::s_ThreadProc, this, 0, 0);
  *((_QWORD *)this + 2) = Thread;
  if ( !Thread )
  {
    v21 = GetLastError();
    v8 = v21;
    if ( v21 > 0 )
      v8 = (unsigned __int16)v21 | 0x80070000;
    v15 = L"m_hThread";
    v16 = 86;
    goto LABEL_11;
  }
  if ( WaitForSingleObject(*((HANDLE *)this + 4), 0xFFFFFFFF) )
  {
    v22 = GetLastError();
    v8 = v22;
    if ( v22 > 0 )
      v8 = (unsigned __int16)v22 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
      89,
      L"CWorkerThread::Start",
      L" - thread failed to start.");
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
      0x59u,
      L"CWorkerThread::Start",
      L"CBRLAEx",
      L"dwWait == ((((DWORD )0x00000000L) ) + 0 )",
      v8);
    if ( IsDebuggerPresent() )
    {
      v31 = v8;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
        89,
        L"CWorkerThread::Start",
        L"CBRLAEx",
        L"dwWait == ((((DWORD )0x00000000L) ) + 0 )",
        v31);
    }
    else
    {
      v28 = v8;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
        89,
        L"CWorkerThread::Start",
        L"CBRLAEx",
        L"dwWait == ((((DWORD )0x00000000L) ) + 0 )",
        v28);
    }
  }
  else
  {
    v8 = 0;
    ThreadId = GetThreadId(*((HANDLE *)this + 2));
    DEBUGMSG(
      L"CWorkerThread::Start - %s thread started:  id = 0x%X  obj = 0x%X\n",
      *((_QWORD *)this + 1),
      ThreadId,
      this);
  }
LABEL_39:
  v24 = (char *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v24);
    *((_QWORD *)this + 4) = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140060820  mov     [rsp+arg_8], rbx
0x140060825  mov     [rsp+arg_10], rbp
0x14006082a  push    rsi
0x14006082b  push    r12
0x14006082d  push    r13
0x14006082f  push    r14
0x140060831  push    r15
0x140060833  sub     rsp, 40h
0x140060837  mov     rsi, rcx
0x14006083a  lea     rdx, [rcx+30h]; struct CSharedReaderWriterLock *
0x14006083e  lea     rcx, [rsp+68h+arg_0]; this
0x140060843  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x140060848  nop
0x140060849  cmp     dword ptr [rsi+28h], 3
0x14006084d  jz      loc_1400608FD
0x140060853  mov     ebx, 8000FFFFh
0x140060858  mov     dword ptr [rsp+68h+lpThreadId], ebx; int
0x14006085c  lea     r13, aMEthreadstatus; "m_eThreadStatus == WTTS_Stopped"
0x140060863  mov     qword ptr [rsp+68h+dwCreationFlags], r13; unsigned __int16 *
0x140060868  lea     r15, aCbraex; "CBRAEx"
0x14006086f  mov     r9, r15; unsigned __int16 *
0x140060872  lea     r14, aCworkerthreadS_1; "CWorkerThread::Start"
0x140060879  mov     r8, r14; unsigned __int16 *
0x14006087c  mov     r12d, 3Ah ; ':'
0x140060882  mov     edx, r12d; unsigned int
0x140060885  lea     rbp, aTermsrvWmsSrcC_12; "termsrv\\wms\\src\\common\\srcutils\\wo"...
0x14006088c  mov     rcx, rbp; unsigned __int16 *
0x14006088f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140060894  call    cs:__imp_IsDebuggerPresent
0x14006089a  test    eax, eax
0x14006089c  jz      short loc_1400608CA
0x14006089e  mov     [rsp+68h+var_30], ebx
0x1400608a2  mov     [rsp+68h+var_38], r13
0x1400608a7  mov     [rsp+68h+lpThreadId], r15
0x1400608ac  mov     qword ptr [rsp+68h+dwCreationFlags], r14
0x1400608b1  mov     r9d, r12d
0x1400608b4  mov     r8, rbp
0x1400608b7  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400608be  lea     ecx, [r12-38h]; unsigned __int8
0x1400608c3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400608c8  jmp     short loc_1400608EE
0x1400608ca  mov     dword ptr [rsp+68h+var_38], ebx
0x1400608ce  mov     [rsp+68h+lpThreadId], r13
0x1400608d3  mov     qword ptr [rsp+68h+dwCreationFlags], r15
0x1400608d8  mov     r9, r14
0x1400608db  mov     r8d, r12d
0x1400608de  mov     rdx, rbp
0x1400608e1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400608e8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400608ed  nop
0x1400608ee  lea     rcx, [rsp+68h+arg_0]; this
0x1400608f3  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x1400608f8  jmp     loc_140060BA1
0x1400608fd  mov     dword ptr [rsi+28h], 0
0x140060904  lea     rcx, [rsp+68h+arg_0]; this
0x140060909  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x14006090e  mov     rcx, [rsi+18h]; hEvent
0x140060912  test    rcx, rcx
0x140060915  jnz     loc_1400609FB
0x14006091b  xor     r9d, r9d; lpName
0x14006091e  xor     r8d, r8d; bInitialState
0x140060921  xor     edx, edx; bManualReset
0x140060923  call    cs:__imp_CreateEventW
0x140060929  mov     [rsi+18h], rax
0x14006092d  test    rax, rax
0x140060930  jnz     loc_1400609F2
0x140060936  call    cs:__imp_GetLastError
0x14006093c  mov     ebx, eax
0x14006093e  test    eax, eax
0x140060940  jle     short loc_14006094B
0x140060942  movzx   ebx, ax
0x140060945  or      ebx, 80070000h
0x14006094b  lea     r13, aMHthreadkillev; "m_hThreadKillEvent"
0x140060952  mov     r12d, 47h ; 'G'
0x140060958  test    ebx, ebx
0x14006095a  mov     eax, 80004005h
0x14006095f  cmovns  ebx, eax
0x140060962  mov     dword ptr [rsp+68h+lpThreadId], ebx; int
0x140060966  lea     r15, aCbraex; "CBRAEx"
0x14006096d  lea     r14, aCworkerthreadS_1; "CWorkerThread::Start"
0x140060974  mov     qword ptr [rsp+68h+dwCreationFlags], r13; unsigned __int16 *
0x140060979  mov     r9, r15; unsigned __int16 *
0x14006097c  mov     r8, r14; unsigned __int16 *
0x14006097f  mov     edx, r12d; unsigned int
0x140060982  lea     rbp, aTermsrvWmsSrcC_12; "termsrv\\wms\\src\\common\\srcutils\\wo"...
0x140060989  mov     rcx, rbp; unsigned __int16 *
0x14006098c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140060991  call    cs:__imp_IsDebuggerPresent
0x140060997  test    eax, eax
0x140060999  jz      short loc_1400609CA
0x14006099b  mov     [rsp+68h+var_30], ebx
0x14006099f  mov     [rsp+68h+var_38], r13
0x1400609a4  mov     [rsp+68h+lpThreadId], r15
0x1400609a9  mov     r9d, r12d
0x1400609ac  mov     qword ptr [rsp+68h+dwCreationFlags], r14
0x1400609b1  mov     r8, rbp
0x1400609b4  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400609bb  mov     ecx, 2; unsigned __int8
0x1400609c0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400609c5  jmp     loc_140060BA1
0x1400609ca  mov     dword ptr [rsp+68h+var_38], ebx
0x1400609ce  mov     [rsp+68h+lpThreadId], r13
0x1400609d3  mov     qword ptr [rsp+68h+dwCreationFlags], r15
0x1400609d8  mov     r8d, r12d
0x1400609db  mov     r9, r14
0x1400609de  mov     rdx, rbp
0x1400609e1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400609e8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400609ed  jmp     loc_140060BA1
0x1400609f2  mov     dword ptr [rsi+2Ch], 1
0x1400609f9  jmp     short loc_140060A01
0x1400609fb  call    cs:__imp_ResetEvent
0x140060a01  xor     r9d, r9d; lpName
0x140060a04  xor     r8d, r8d; bInitialState
0x140060a07  xor     edx, edx; bManualReset
0x140060a09  xor     ecx, ecx; lpEventAttributes
0x140060a0b  call    cs:__imp_CreateEventW
0x140060a11  mov     [rsi+20h], rax
0x140060a15  test    rax, rax
0x140060a18  jnz     short loc_140060A41
0x140060a1a  call    cs:__imp_GetLastError
0x140060a20  mov     ebx, eax
0x140060a22  test    eax, eax
0x140060a24  jle     short loc_140060A2F
0x140060a26  movzx   ebx, ax
0x140060a29  or      ebx, 80070000h
0x140060a2f  lea     r13, aMHthreadstarte; "m_hThreadStarted"
0x140060a36  mov     r12d, 50h ; 'P'
0x140060a3c  jmp     loc_140060958
0x140060a41  mov     rcx, [rsi+10h]; hObject
0x140060a45  lea     rax, [rcx-1]
0x140060a49  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140060a4d  ja      short loc_140060A5D
0x140060a4f  call    cs:__imp_CloseHandle
0x140060a55  mov     qword ptr [rsi+10h], 0
0x140060a5d  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x140060a66  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x140060a6e  mov     r9, rsi; lpParameter
0x140060a71  lea     r8, ?s_ThreadProc@CWorkerThread@@KAKPEAX@Z; lpStartAddress
0x140060a78  xor     edx, edx; dwStackSize
0x140060a7a  xor     ecx, ecx; lpThreadAttributes
0x140060a7c  call    cs:__imp_CreateThread
0x140060a82  mov     [rsi+10h], rax
0x140060a86  test    rax, rax
0x140060a89  jnz     short loc_140060AB2
0x140060a8b  call    cs:__imp_GetLastError
0x140060a91  mov     ebx, eax
0x140060a93  test    eax, eax
0x140060a95  jle     short loc_140060AA0
0x140060a97  movzx   ebx, ax
0x140060a9a  or      ebx, 80070000h
0x140060aa0  lea     r13, aMHthread; "m_hThread"
0x140060aa7  mov     r12d, 56h ; 'V'
0x140060aad  jmp     loc_140060958
0x140060ab2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140060ab5  mov     rcx, [rsi+20h]; hHandle
0x140060ab9  call    cs:__imp_WaitForSingleObject
0x140060abf  test    eax, eax
0x140060ac1  jz      loc_140060B7F
0x140060ac7  call    cs:__imp_GetLastError
0x140060acd  mov     ebx, eax
0x140060acf  test    eax, eax
0x140060ad1  jle     short loc_140060ADC
0x140060ad3  movzx   ebx, ax
0x140060ad6  or      ebx, 80070000h
0x140060adc  mov     eax, 80004005h
0x140060ae1  test    ebx, ebx
0x140060ae3  cmovns  ebx, eax
0x140060ae6  lea     rax, aThreadFailedTo; " - thread failed to start."
0x140060aed  mov     [rsp+68h+lpThreadId], rax
0x140060af2  lea     r14, aCworkerthreadS_1; "CWorkerThread::Start"
0x140060af9  mov     qword ptr [rsp+68h+dwCreationFlags], r14
0x140060afe  mov     r15d, 59h ; 'Y'
0x140060b04  mov     r9d, r15d
0x140060b07  lea     rbp, aTermsrvWmsSrcC_12; "termsrv\\wms\\src\\common\\srcutils\\wo"...
0x140060b0e  mov     r8, rbp
0x140060b11  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140060b18  lea     ecx, [r15-55h]; unsigned __int8
0x140060b1c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140060b21  mov     dword ptr [rsp+68h+lpThreadId], ebx; int
0x140060b25  lea     r12, aDwwaitDword0x0; "dwWait == ((((DWORD )0x00000000L) ) + 0"...
0x140060b2c  mov     qword ptr [rsp+68h+dwCreationFlags], r12; unsigned __int16 *
0x140060b31  lea     r13, aCbrlaex; "CBRLAEx"
0x140060b38  mov     r9, r13; unsigned __int16 *
0x140060b3b  mov     r8, r14; unsigned __int16 *
0x140060b3e  mov     edx, r15d; unsigned int
0x140060b41  mov     rcx, rbp; unsigned __int16 *
0x140060b44  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140060b49  call    cs:__imp_IsDebuggerPresent
0x140060b4f  test    eax, eax
0x140060b51  jz      short loc_140060B69
0x140060b53  mov     [rsp+68h+var_30], ebx
0x140060b57  mov     [rsp+68h+var_38], r12
0x140060b5c  mov     [rsp+68h+lpThreadId], r13
0x140060b61  mov     r9d, r15d
0x140060b64  jmp     loc_1400609AC
0x140060b69  mov     dword ptr [rsp+68h+var_38], ebx
0x140060b6d  mov     [rsp+68h+lpThreadId], r12
0x140060b72  mov     qword ptr [rsp+68h+dwCreationFlags], r13
0x140060b77  mov     r8d, r15d
0x140060b7a  jmp     loc_1400609DB
0x140060b7f  xor     ebx, ebx
0x140060b81  mov     rcx, [rsi+10h]; Thread
0x140060b85  call    cs:__imp_GetThreadId
0x140060b8b  mov     r9, rsi
0x140060b8e  mov     r8d, eax
0x140060b91  mov     rdx, [rsi+8]
0x140060b95  lea     rcx, aCworkerthreadS_3; "CWorkerThread::Start - %s thread starte"...
0x140060b9c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140060ba1  mov     rcx, [rsi+20h]; hObject
0x140060ba5  lea     rdx, [rcx-1]
0x140060ba9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140060bad  ja      short loc_140060BBD
0x140060baf  call    cs:__imp_CloseHandle
0x140060bb5  mov     qword ptr [rsi+20h], 0
0x140060bbd  mov     eax, ebx
0x140060bbf  lea     r11, [rsp+68h+var_28]
0x140060bc4  mov     rbx, [r11+38h]
0x140060bc8  mov     rbp, [r11+40h]
0x140060bcc  mov     rsp, r11
0x140060bcf  pop     r15
0x140060bd1  pop     r14
0x140060bd3  pop     r13
0x140060bd5  pop     r12
0x140060bd7  pop     rsi
0x140060bd8  retn
```
