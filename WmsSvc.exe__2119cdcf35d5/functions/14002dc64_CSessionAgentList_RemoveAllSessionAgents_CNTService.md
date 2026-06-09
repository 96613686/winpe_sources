# CSessionAgentList::RemoveAllSessionAgents(CNTService *)

- ea: `0x14002dc64`
- end: `0x14002e1f7`
- name: `?RemoveAllSessionAgents@CSessionAgentList@@QEAAXPEAVCNTService@@@Z`
- size: `1427`
- prototype: `void(CSessionAgentList *__hidden this, struct CNTService *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x140027328`
- `0x14002ce90`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140004730`
- `0x140004a04`
- `0x14002d318`
- `0x14002dc64`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14005dcb8`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x14002e18d`
- `ADVAPI32!CloseServiceHandle` at `0x14002e18d`
- `ADVAPI32!ControlService` at `0x14002e0a8`
- `ADVAPI32!ControlService` at `0x14002e0a8`
- `KERNEL32!CloseHandle` at `0x14002e1b0`
- `KERNEL32!CloseHandle` at `0x14002e1b0`
- `KERNEL32!CreateThread` at `0x14002de52`
- `KERNEL32!CreateThread` at `0x14002de52`
- `KERNEL32!WaitForMultipleObjects` at `0x14002dcef`
- `KERNEL32!WaitForMultipleObjects` at `0x14002df86`
- `KERNEL32!WaitForMultipleObjects` at `0x14002dcef`
- `KERNEL32!WaitForMultipleObjects` at `0x14002df86`
- `KERNEL32!GetLastError` at `0x14002de82`
- `KERNEL32!GetLastError` at `0x14002df99`
- `KERNEL32!GetLastError` at `0x14002e0b6`
- `KERNEL32!GetLastError` at `0x14002e0c7`
- `KERNEL32!GetLastError` at `0x14002de82`
- `KERNEL32!GetLastError` at `0x14002df99`
- `KERNEL32!GetLastError` at `0x14002e0b6`
- `KERNEL32!GetLastError` at `0x14002e0c7`
- `KERNEL32!IsDebuggerPresent` at `0x14002dd61`
- `KERNEL32!IsDebuggerPresent` at `0x14002df1f`
- `KERNEL32!IsDebuggerPresent` at `0x14002dfef`
- `KERNEL32!IsDebuggerPresent` at `0x14002e116`
- `KERNEL32!IsDebuggerPresent` at `0x14002dd61`
- `KERNEL32!IsDebuggerPresent` at `0x14002df1f`
- `KERNEL32!IsDebuggerPresent` at `0x14002dfef`
- `KERNEL32!IsDebuggerPresent` at `0x14002e116`

## string_xrefs

- `0x14002dd46`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002df04`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002dfbc`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002e071`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002dc8f`: `CSessionAgentList::RemoveAllSessionAgents - Start\n`
- `0x14002dd26`: `prgThreads`
- `0x14002dd69`: `prgThreads`
- `0x14002dd32`: `CSessionAgentList::RemoveAllSessionAgents`
- `0x14002deef`: `CSessionAgentList::RemoveAllSessionAgents`
- `0x14002dfb3`: `CSessionAgentList::RemoveAllSessionAgents`
- `0x14002dee3`: `idxCurrentThread < cThreads`
- `0x14002df27`: `idxCurrentThread < cThreads`
- `0x14002de1f`: `CSessionAgentList::RemoveAllSessionAgents - Releasing Session Agent in session = %lu\n`
- `0x14002de8b`: `CSessionAgentList::RemoveAllSessionAgents - failed to create thread to release Session Agent in session = %lu, error = %lu\n`
- `0x14002df5a`: `CSessionAgentList::RemoveAllSessionAgents - waiting for session agents to terminate\n`
- `0x14002e1c5`: `CSessionAgentList::RemoveAllSessionAgents - End\n`
- `0x14002e07b`: `CSessionAgentList::StopWebLimitingDriver\n`
- `0x14002e0e1`: `CSessionAgentList::StopWebLimitingDriver`

## pseudocode

```c
void __fastcall CSessionAgentList::RemoveAllSessionAgents(CSessionAgentList *this, struct CNTService *a2)
{
  signed int v4; // ebp
  __int64 v5; // r8
  const unsigned __int16 *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  const unsigned __int16 *v9; // r9
  unsigned __int64 v10; // r12
  __int64 *v11; // rsi
  HANDLE *v12; // r14
  HANDLE *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  const unsigned __int16 *v16; // r9
  __int64 v17; // rbx
  __int64 v18; // rax
  HANDLE Thread; // rax
  DWORD v20; // eax
  __int64 v21; // rcx
  DWORD v22; // eax
  signed int LastError; // eax
  signed int v24; // ebx
  SC_HANDLE v25; // rcx
  signed int v26; // eax
  signed int v27; // ebx
  SC_HANDLE v28; // rcx
  __int64 i; // rbx
  HANDLE v30; // rcx
  __int64 v31; // [rsp+30h] [rbp-68h]
  __int64 v32; // [rsp+38h] [rbp-60h]
  PSRWLOCK v33; // [rsp+40h] [rbp-58h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-50h] BYREF

  v4 = 0;
  DEBUGMSG(L"CSessionAgentList::RemoveAllSessionAgents - Start\n");
  CAutoWriteLock::CAutoWriteLock((CAutoWriteLock *)&v33, (CSessionAgentList *)((char *)this + 32), v5, v6);
  v10 = *((int *)this + 86);
  v11 = (__int64 *)(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  if ( (__int64 *)*v11 == v11 )
  {
    v12 = 0;
LABEL_3:
    CAutoWriteLock::~CAutoWriteLock(&v33, v7, v8, v9);
    if ( v4 <= 0 )
      goto LABEL_39;
    while ( 1 )
    {
      v22 = WaitForMultipleObjects(v4, v12, 1, 0x2710u);
      if ( v22 != 258 )
        break;
      DEBUGMSG(L"CSessionAgentList::RemoveAllSessionAgents - waiting for session agents to terminate\n");
      if ( a2 )
        CNTService::SetStatus(a2, 3u);
    }
    if ( v22 == -1 )
    {
      LastError = GetLastError();
      v24 = LastError;
      if ( LastError > 0 )
        v24 = (unsigned __int16)LastError | 0x80070000;
      if ( v24 >= 0 )
        v24 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        0xB4u,
        L"CSessionAgentList::RemoveAllSessionAgents",
        L"CBRAEx",
        L"dwWait != ((DWORD)0xFFFFFFFF)",
        v24);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
          180,
          L"CSessionAgentList::RemoveAllSessionAgents",
          L"CBRAEx",
          L"dwWait != ((DWORD)0xFFFFFFFF)",
          v24);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
          180,
          L"CSessionAgentList::RemoveAllSessionAgents",
          L"CBRAEx",
          L"dwWait != ((DWORD)0xFFFFFFFF)",
          v24);
    }
    else
    {
LABEL_39:
      if ( a2 )
        CNTService::SetStatus(a2, 3u);
    }
    goto LABEL_41;
  }
  v13 = (HANDLE *)operator new(saturated_mul(v10, 8u));
  v12 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 8 * v10);
    while ( 1 )
    {
      v17 = *v11;
      if ( (__int64 *)*v11 == v11 )
        goto LABEL_3;
      if ( v4 >= (int)v10 )
      {
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
          0x83u,
          L"CSessionAgentList::RemoveAllSessionAgents",
          L"CBRAEx",
          L"idxCurrentThread < cThreads",
          -2147418113);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
            131,
            L"CSessionAgentList::RemoveAllSessionAgents",
            L"CBRAEx",
            L"idxCurrentThread < cThreads",
            -2147418113);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
            131,
            L"CSessionAgentList::RemoveAllSessionAgents",
            L"CBRAEx",
            L"idxCurrentThread < cThreads",
            -2147418113);
        goto LABEL_9;
      }
      if ( *(__int64 **)(v17 + 8) != v11 || (v18 = *(_QWORD *)v17, *(_QWORD *)(*(_QWORD *)v17 + 8LL) != v17) )
        __fastfail(3u);
      *v11 = v18;
      *(_QWORD *)(v18 + 8) = v11;
      DEBUGMSG(
        L"CSessionAgentList::RemoveAllSessionAgents - Releasing Session Agent in session = %lu\n",
        *(unsigned int *)(v17 + 16));
      Thread = CreateThread(0, 0, CSessionAgentList::s_AsyncReleaseThreadProc, *(LPVOID *)(v17 + 32), 0, 0);
      v12[v4] = Thread;
      if ( Thread )
      {
        *(_QWORD *)(v17 + 32) = 0;
        ++v4;
      }
      else
      {
        if ( a2 )
          CNTService::SetStatus(a2, 3u);
        v20 = GetLastError();
        DEBUGMSG(
          L"CSessionAgentList::RemoveAllSessionAgents - failed to create thread to release Session Agent in session = %lu, error = %lu\n",
          *(unsigned int *)(v17 + 16),
          v20);
        v21 = *(_QWORD *)(v17 + 32);
        if ( v21 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          *(_QWORD *)(v17 + 32) = 0;
        }
        if ( a2 )
          CNTService::SetStatus(a2, 3u);
      }
      CSessionAgentList::DestroySessionAgentListEntry((__int64)this, v17, 0);
    }
  }
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
    0x7Cu,
    L"CSessionAgentList::RemoveAllSessionAgents",
    L"CPR",
    L"prgThreads",
    -2147024882);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
      124,
      L"CSessionAgentList::RemoveAllSessionAgents",
      L"CPR",
      L"prgThreads",
      -2147024882);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
      124,
      L"CSessionAgentList::RemoveAllSessionAgents",
      L"CPR",
      L"prgThreads",
      -2147024882);
LABEL_9:
  CAutoWriteLock::~CAutoWriteLock(&v33, v14, v15, v16);
LABEL_41:
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  DEBUGMSG(L"CSessionAgentList::StopWebLimitingDriver\n");
  v25 = (SC_HANDLE)*((_QWORD *)this + 3);
  if ( v25 && !ControlService(v25, 1u, &ServiceStatus) && GetLastError() != 1115 )
  {
    v26 = GetLastError();
    v27 = v26;
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    if ( v27 >= 0 )
      v27 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
      0x339u,
      L"CSessionAgentList::StopWebLimitingDriver",
      L"CBRAEx",
      L"fSuccess || ::GetLastError () == 1115L",
      v27);
    if ( IsDebuggerPresent() )
    {
      LODWORD(v32) = v27;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        825,
        L"CSessionAgentList::StopWebLimitingDriver",
        L"CBRAEx",
        L"fSuccess || ::GetLastError () == 1115L",
        v32);
    }
    else
    {
      LODWORD(v31) = v27;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        825,
        L"CSessionAgentList::StopWebLimitingDriver",
        L"CBRAEx",
        L"fSuccess || ::GetLastError () == 1115L",
        v31);
    }
  }
  v28 = (SC_HANDLE)*((_QWORD *)this + 3);
  if ( v28 )
  {
    CloseServiceHandle(v28);
    *((_QWORD *)this + 3) = 0;
  }
  if ( v12 )
  {
    for ( i = 0; (int)i < (int)v10; i = (unsigned int)(i + 1) )
    {
      v30 = v12[i];
      if ( v30 )
        CloseHandle(v30);
    }
    operator delete(v12);
  }
  DEBUGMSG(L"CSessionAgentList::RemoveAllSessionAgents - End\n");
}

```

## disassembly

```asm
0x14002dc64  mov     [rsp+arg_10], rbx
0x14002dc69  mov     [rsp+arg_18], rbp
0x14002dc6e  push    rsi
0x14002dc6f  push    rdi
0x14002dc70  push    r12
0x14002dc72  push    r14
0x14002dc74  push    r15
0x14002dc76  sub     rsp, 70h
0x14002dc7a  mov     rax, cs:__security_cookie
0x14002dc81  xor     rax, rsp
0x14002dc84  mov     [rsp+98h+var_30], rax
0x14002dc89  mov     r15, rcx
0x14002dc8c  mov     rdi, rdx
0x14002dc8f  lea     rcx, aCsessionagentl_34; "CSessionAgentList::RemoveAllSessionAgen"...
0x14002dc96  xor     ebp, ebp
0x14002dc98  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002dc9d  lea     rdx, [r15+20h]; struct CSharedReaderWriterLock *
0x14002dca1  lea     rcx, [rsp+98h+var_58]; this
0x14002dca6  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x14002dcab  movsxd  r12, dword ptr [r15+158h]
0x14002dcb2  lea     rcx, [r15+8]
0x14002dcb6  mov     rax, r15
0x14002dcb9  neg     rax
0x14002dcbc  sbb     rsi, rsi
0x14002dcbf  and     rsi, rcx
0x14002dcc2  cmp     [rsi], rsi
0x14002dcc5  jnz     short loc_14002DCFF
0x14002dcc7  xor     r14d, r14d
0x14002dcca  lea     rcx, [rsp+98h+var_58]; this
0x14002dccf  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x14002dcd4  test    ebp, ebp
0x14002dcd6  jle     loc_14002E05F
0x14002dcdc  mov     ebx, 2710h
0x14002dce1  mov     r8d, 1; bWaitAll
0x14002dce7  mov     r9d, ebx; dwMilliseconds
0x14002dcea  mov     rdx, r14; lpHandles
0x14002dced  mov     ecx, ebp; nCount
0x14002dcef  call    cs:__imp_WaitForMultipleObjects
0x14002dcf5  mov     esi, 102h
0x14002dcfa  jmp     loc_14002DF8C
0x14002dcff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002dd06  mov     eax, 8
0x14002dd0b  mul     r12
0x14002dd0e  cmovb   rax, rcx
0x14002dd12  mov     rcx, rax; Size
0x14002dd15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002dd1a  mov     r14, rax
0x14002dd1d  test    rax, rax
0x14002dd20  jnz     loc_14002DDDE
0x14002dd26  lea     rax, aPrgthreads; "prgThreads"
0x14002dd2d  mov     ebx, 8007000Eh
0x14002dd32  lea     rdi, aCsessionagentl_20; "CSessionAgentList::RemoveAllSessionAgen"...
0x14002dd39  mov     dword ptr [rsp+98h+lpThreadId], ebx; int
0x14002dd3d  lea     ebp, [r14+7Ch]
0x14002dd41  mov     qword ptr [rsp+98h+dwCreationFlags], rax; unsigned __int16 *
0x14002dd46  lea     rsi, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002dd4d  mov     r8, rdi; unsigned __int16 *
0x14002dd50  mov     edx, ebp; unsigned int
0x14002dd52  lea     r9, aCpr; "CPR"
0x14002dd59  mov     rcx, rsi; unsigned __int16 *
0x14002dd5c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002dd61  call    cs:__imp_IsDebuggerPresent
0x14002dd67  test    eax, eax
0x14002dd69  lea     rax, aPrgthreads; "prgThreads"
0x14002dd70  jz      short loc_14002DDA5
0x14002dd72  mov     dword ptr [rsp+98h+var_60], ebx
0x14002dd76  mov     [rsp+98h+var_68], rax
0x14002dd7b  lea     rax, aCpr; "CPR"
0x14002dd82  mov     [rsp+98h+lpThreadId], rax
0x14002dd87  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002dd8e  mov     r9d, ebp
0x14002dd91  mov     qword ptr [rsp+98h+dwCreationFlags], rdi
0x14002dd96  mov     r8, rsi
0x14002dd99  mov     ecx, 2; unsigned __int8
0x14002dd9e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002dda3  jmp     short loc_14002DDCF
0x14002dda5  mov     dword ptr [rsp+98h+var_68], ebx
0x14002dda9  mov     [rsp+98h+lpThreadId], rax
0x14002ddae  lea     rax, aCpr; "CPR"
0x14002ddb5  mov     r9, rdi
0x14002ddb8  mov     qword ptr [rsp+98h+dwCreationFlags], rax
0x14002ddbd  mov     r8d, ebp
0x14002ddc0  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002ddc7  mov     rdx, rsi
0x14002ddca  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002ddcf  lea     rcx, [rsp+98h+var_58]; this
0x14002ddd4  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x14002ddd9  jmp     loc_14002E078
0x14002ddde  lea     r8, ds:0[r12*8]; Size
0x14002dde6  xor     edx, edx; Val
0x14002dde8  mov     rcx, r14; void *
0x14002ddeb  call    memset_0
0x14002ddf0  mov     rbx, [rsi]
0x14002ddf3  cmp     rbx, rsi
0x14002ddf6  jz      loc_14002DCCA
0x14002ddfc  cmp     ebp, r12d
0x14002ddff  jge     loc_14002DEE3
0x14002de05  cmp     [rbx+8], rsi
0x14002de09  jnz     loc_14002DEDC
0x14002de0f  mov     rax, [rbx]
0x14002de12  cmp     [rax+8], rbx
0x14002de16  jnz     loc_14002DEDC
0x14002de1c  mov     [rsi], rax
0x14002de1f  lea     rcx, aCsessionagentl_24; "CSessionAgentList::RemoveAllSessionAgen"...
0x14002de26  mov     [rax+8], rsi
0x14002de2a  mov     edx, [rbx+10h]
0x14002de2d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002de32  mov     r9, [rbx+20h]; lpParameter
0x14002de36  lea     r8, ?s_AsyncReleaseThreadProc@CSessionAgentList@@CAKPEAX@Z; lpStartAddress
0x14002de3d  xor     edx, edx; dwStackSize
0x14002de3f  mov     [rsp+98h+lpThreadId], 0; lpThreadId
0x14002de48  xor     ecx, ecx; lpThreadAttributes
0x14002de4a  mov     [rsp+98h+dwCreationFlags], 0; dwCreationFlags
0x14002de52  call    cs:__imp_CreateThread
0x14002de58  movsxd  rcx, ebp
0x14002de5b  mov     [r14+rcx*8], rax
0x14002de5f  test    rax, rax
0x14002de62  jz      short loc_14002DE70
0x14002de64  mov     qword ptr [rbx+20h], 0
0x14002de6c  inc     ebp
0x14002de6e  jmp     short loc_14002DEC9
0x14002de70  test    rdi, rdi
0x14002de73  jz      short loc_14002DE82
0x14002de75  mov     edx, 3; unsigned int
0x14002de7a  mov     rcx, rdi; this
0x14002de7d  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x14002de82  call    cs:__imp_GetLastError
0x14002de88  mov     edx, [rbx+10h]
0x14002de8b  lea     rcx, aCsessionagentl_9; "CSessionAgentList::RemoveAllSessionAgen"...
0x14002de92  mov     r8d, eax
0x14002de95  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002de9a  mov     rcx, [rbx+20h]
0x14002de9e  test    rcx, rcx
0x14002dea1  jz      short loc_14002DEB7
0x14002dea3  mov     rax, [rcx]
0x14002dea6  mov     rax, [rax+10h]
0x14002deaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002deaf  mov     qword ptr [rbx+20h], 0
0x14002deb7  test    rdi, rdi
0x14002deba  jz      short loc_14002DEC9
0x14002debc  mov     edx, 3; unsigned int
0x14002dec1  mov     rcx, rdi; this
0x14002dec4  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x14002dec9  xor     r8d, r8d
0x14002decc  mov     rdx, rbx
0x14002decf  mov     rcx, r15
0x14002ded2  call    ?DestroySessionAgentListEntry@CSessionAgentList@@AEAAJPEAUSSessionAgentListEntry@@W4EDestroySaListEntryOptions@1@@Z; CSessionAgentList::DestroySessionAgentListEntry(SSessionAgentListEntry *,CSessionAgentList::EDestroySaListEntryOptions)
0x14002ded7  jmp     loc_14002DDF0
0x14002dedc  mov     ecx, 3
0x14002dee1  int     29h; Win8: RtlFailFast(ecx)
0x14002dee3  lea     rax, aIdxcurrentthre; "idxCurrentThread < cThreads"
0x14002deea  mov     ebx, 8000FFFFh
0x14002deef  lea     rdi, aCsessionagentl_20; "CSessionAgentList::RemoveAllSessionAgen"...
0x14002def6  mov     dword ptr [rsp+98h+lpThreadId], ebx; int
0x14002defa  mov     ebp, 83h
0x14002deff  mov     qword ptr [rsp+98h+dwCreationFlags], rax; unsigned __int16 *
0x14002df04  lea     rsi, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002df0b  mov     r8, rdi; unsigned __int16 *
0x14002df0e  mov     edx, ebp; unsigned int
0x14002df10  lea     r9, aCbraex; "CBRAEx"
0x14002df17  mov     rcx, rsi; unsigned __int16 *
0x14002df1a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002df1f  call    cs:__imp_IsDebuggerPresent
0x14002df25  test    eax, eax
0x14002df27  lea     rax, aIdxcurrentthre; "idxCurrentThread < cThreads"
0x14002df2e  jz      short loc_14002DF45
0x14002df30  mov     dword ptr [rsp+98h+var_60], ebx
0x14002df34  mov     [rsp+98h+var_68], rax
0x14002df39  lea     rax, aCbraex; "CBRAEx"
0x14002df40  jmp     loc_14002DD82
0x14002df45  mov     dword ptr [rsp+98h+var_68], ebx
0x14002df49  mov     [rsp+98h+lpThreadId], rax
0x14002df4e  lea     rax, aCbraex; "CBRAEx"
0x14002df55  jmp     loc_14002DDB5
0x14002df5a  lea     rcx, aCsessionagentl_18; "CSessionAgentList::RemoveAllSessionAgen"...
0x14002df61  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002df66  test    rdi, rdi
0x14002df69  jz      short loc_14002DF78
0x14002df6b  mov     edx, 3; unsigned int
0x14002df70  mov     rcx, rdi; this
0x14002df73  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x14002df78  mov     r9d, ebx; dwMilliseconds
0x14002df7b  mov     r8d, 1; bWaitAll
0x14002df81  mov     rdx, r14; lpHandles
0x14002df84  mov     ecx, ebp; nCount
0x14002df86  call    cs:__imp_WaitForMultipleObjects
0x14002df8c  cmp     eax, esi
0x14002df8e  jz      short loc_14002DF5A
0x14002df90  cmp     eax, 0FFFFFFFFh
0x14002df93  jnz     loc_14002E05F
0x14002df99  call    cs:__imp_GetLastError
0x14002df9f  mov     ebx, eax
0x14002dfa1  test    eax, eax
0x14002dfa3  jle     short loc_14002DFAE
0x14002dfa5  movzx   ebx, ax
0x14002dfa8  or      ebx, 80070000h
0x14002dfae  mov     eax, 80004005h
0x14002dfb3  lea     rdi, aCsessionagentl_20; "CSessionAgentList::RemoveAllSessionAgen"...
0x14002dfba  test    ebx, ebx
0x14002dfbc  lea     rsi, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002dfc3  mov     ebp, 0B4h
0x14002dfc8  lea     r9, aCbraex; "CBRAEx"
0x14002dfcf  cmovns  ebx, eax
0x14002dfd2  mov     r8, rdi; unsigned __int16 *
0x14002dfd5  lea     rax, aDwwaitDword0xf; "dwWait != ((DWORD)0xFFFFFFFF)"
0x14002dfdc  mov     dword ptr [rsp+98h+lpThreadId], ebx; int
0x14002dfe0  mov     edx, ebp; unsigned int
0x14002dfe2  mov     qword ptr [rsp+98h+dwCreationFlags], rax; unsigned __int16 *
0x14002dfe7  mov     rcx, rsi; unsigned __int16 *
0x14002dfea  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002dfef  call    cs:__imp_IsDebuggerPresent
0x14002dff5  test    eax, eax
0x14002dff7  lea     rax, aDwwaitDword0xf; "dwWait != ((DWORD)0xFFFFFFFF)"
0x14002dffe  jz      short loc_14002E033
0x14002e000  mov     dword ptr [rsp+98h+var_60], ebx
0x14002e004  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002e00b  mov     [rsp+98h+var_68], rax
0x14002e010  mov     r9d, ebp
0x14002e013  lea     rax, aCbraex; "CBRAEx"
0x14002e01a  mov     r8, rsi
0x14002e01d  mov     [rsp+98h+lpThreadId], rax
0x14002e022  mov     ecx, 2; unsigned __int8
0x14002e027  mov     qword ptr [rsp+98h+dwCreationFlags], rdi
0x14002e02c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002e031  jmp     short loc_14002E078
0x14002e033  mov     dword ptr [rsp+98h+var_68], ebx
0x14002e037  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002e03e  mov     [rsp+98h+lpThreadId], rax
0x14002e043  mov     r9, rdi
0x14002e046  lea     rax, aCbraex; "CBRAEx"
0x14002e04d  mov     r8d, ebp
0x14002e050  mov     rdx, rsi
0x14002e053  mov     qword ptr [rsp+98h+dwCreationFlags], rax
0x14002e058  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002e05d  jmp     short loc_14002E078
0x14002e05f  test    rdi, rdi
0x14002e062  jz      short loc_14002E071
0x14002e064  mov     edx, 3; unsigned int
0x14002e069  mov     rcx, rdi; this
0x14002e06c  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x14002e071  lea     rsi, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002e078  xorps   xmm0, xmm0
0x14002e07b  lea     rcx, aCsessionagentl_4; "CSessionAgentList::StopWebLimitingDrive"...
0x14002e082  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x14002e087  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x14002e08c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002e091  mov     rcx, [r15+18h]; hService
0x14002e095  test    rcx, rcx
0x14002e098  jz      loc_14002E184
0x14002e09e  lea     r8, [rsp+98h+ServiceStatus]; lpServiceStatus
0x14002e0a3  mov     edx, 1; dwControl
0x14002e0a8  call    cs:__imp_ControlService
0x14002e0ae  test    eax, eax
0x14002e0b0  jnz     loc_14002E184
0x14002e0b6  call    cs:__imp_GetLastError
0x14002e0bc  cmp     eax, 45Bh
0x14002e0c1  jz      loc_14002E184
0x14002e0c7  call    cs:__imp_GetLastError
0x14002e0cd  mov     ebx, eax
0x14002e0cf  test    eax, eax
0x14002e0d1  jle     short loc_14002E0DC
0x14002e0d3  movzx   ebx, ax
0x14002e0d6  or      ebx, 80070000h
0x14002e0dc  mov     eax, 80004005h
0x14002e0e1  lea     rbp, aCsessionagentl_35; "CSessionAgentList::StopWebLimitingDrive"...
0x14002e0e8  test    ebx, ebx
0x14002e0ea  lea     r9, aCbraex; "CBRAEx"
0x14002e0f1  mov     edi, 339h
0x14002e0f6  mov     r8, rbp; unsigned __int16 *
0x14002e0f9  cmovns  ebx, eax
0x14002e0fc  mov     edx, edi; unsigned int
0x14002e0fe  lea     rax, aFsuccessGetlas_2; "fSuccess || ::GetLastError () == 1115L"
0x14002e105  mov     dword ptr [rsp+98h+lpThreadId], ebx; int
0x14002e109  mov     rcx, rsi; unsigned __int16 *
0x14002e10c  mov     qword ptr [rsp+98h+dwCreationFlags], rax; unsigned __int16 *
0x14002e111  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002e116  call    cs:__imp_IsDebuggerPresent
0x14002e11c  test    eax, eax
0x14002e11e  lea     rax, aFsuccessGetlas_2; "fSuccess || ::GetLastError () == 1115L"
0x14002e125  jz      short loc_14002E15A
0x14002e127  mov     dword ptr [rsp+98h+var_60], ebx
0x14002e12b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002e132  mov     [rsp+98h+var_68], rax
0x14002e137  mov     r9d, edi
0x14002e13a  lea     rax, aCbraex; "CBRAEx"
0x14002e141  mov     r8, rsi
0x14002e144  mov     [rsp+98h+lpThreadId], rax
0x14002e149  mov     ecx, 2; unsigned __int8
0x14002e14e  mov     qword ptr [rsp+98h+dwCreationFlags], rbp
0x14002e153  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002e158  jmp     short loc_14002E184
0x14002e15a  mov     dword ptr [rsp+98h+var_68], ebx
0x14002e15e  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002e165  mov     [rsp+98h+lpThreadId], rax
0x14002e16a  mov     r9, rbp
0x14002e16d  lea     rax, aCbraex; "CBRAEx"
0x14002e174  mov     r8d, edi
0x14002e177  mov     rdx, rsi
0x14002e17a  mov     qword ptr [rsp+98h+dwCreationFlags], rax
0x14002e17f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
  ... truncated ...
```
