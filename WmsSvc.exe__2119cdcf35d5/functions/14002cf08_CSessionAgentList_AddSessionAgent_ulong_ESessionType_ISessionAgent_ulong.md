# CSessionAgentList::AddSessionAgent(ulong,ESessionType,ISessionAgent *,ulong)

- ea: `0x14002cf08`
- end: `0x14002d1fc`
- name: `?AddSessionAgent@CSessionAgentList@@QEAAJKW4ESessionType@@PEAUISessionAgent@@K@Z`
- size: `756`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, const unsigned __int16 *, DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task`

## callers

- `0x140022820`

## callees

- `0x1400016c4`
- `0x140004730`
- `0x140004a04`
- `0x14002cf08`
- `0x14002d318`
- `0x14002d444`
- `0x14002e200`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006ea54`
- `0x14007e010`

## import_xrefs

- `KERNEL32!RegisterWaitForSingleObject` at `0x14002d19f`
- `KERNEL32!RegisterWaitForSingleObject` at `0x14002d19f`
- `KERNEL32!OpenProcess` at `0x14002d085`
- `KERNEL32!OpenProcess` at `0x14002d085`
- `KERNEL32!GetLastError` at `0x14002d098`
- `KERNEL32!GetLastError` at `0x14002d1a9`
- `KERNEL32!GetLastError` at `0x14002d098`
- `KERNEL32!GetLastError` at `0x14002d1a9`
- `KERNEL32!IsDebuggerPresent` at `0x14002cff8`
- `KERNEL32!IsDebuggerPresent` at `0x14002d0f3`
- `KERNEL32!IsDebuggerPresent` at `0x14002cff8`
- `KERNEL32!IsDebuggerPresent` at `0x14002d0f3`

## string_xrefs

- `0x14002cfd5`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002d0c8`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002cf50`: `CSessionAgentList::AddSessionAgent idSession = %lu idProcess = 0x%x eSessionType = %s\n`
- `0x14002cf8d`: `CSessionAgentList::AddSessionAgent - idSession = %lu already has a session agent; removing the old one and using the new one.\n`
- `0x14002cfdc`: `pSessionAgentListEntry`
- `0x14002cfc5`: `CSessionAgentList::AddSessionAgent`
- `0x14002d0bb`: `CSessionAgentList::AddSessionAgent`
- `0x14002d0d2`: `pSessionAgentListEntry->hProcessSessionAgent`
- `0x14002d1bd`: `CSessionAgentList::AddSessionAgent - ERROR - RegisterWaitForSingleObject failed, hr = 0x%08X.\n`

## pseudocode

```c
__int64 __fastcall CSessionAgentList::AddSessionAgent(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        const unsigned __int16 *a4,
        DWORD dwProcessId)
{
  unsigned int v8; // r15d
  unsigned __int64 v9; // r9
  const unsigned __int16 *v10; // rax
  DWORD v11; // r12d
  __int64 *v12; // rdx
  __int64 v13; // rbx
  void *v14; // rax
  void *v15; // rdi
  signed int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // r8
  const unsigned __int16 *v19; // r9
  HANDLE v20; // rax
  signed int v21; // eax
  _QWORD *v22; // rax
  signed int LastError; // eax
  PSRWLOCK v25; // [rsp+90h] [rbp+8h] BYREF

  v8 = a3;
  CAutoWriteLock::CAutoWriteLock((CAutoWriteLock *)&v25, (struct CSharedReaderWriterLock *)(a1 + 32), a3, a4);
  v10 = Utils::StringTableHelper((Utils *)v8, (unsigned int)&qword_14009C2F0, (const struct Utils::SStringMap *)7, v9);
  v11 = dwProcessId;
  DEBUGMSG(
    L"CSessionAgentList::AddSessionAgent idSession = %lu idProcess = 0x%x eSessionType = %s\n",
    a2,
    dwProcessId,
    v10);
  v12 = *(__int64 **)(a1 + 8);
  v13 = (a1 + 8) & -(__int64)(a1 != 0);
  while ( v12 != (__int64 *)v13 )
  {
    if ( *((_DWORD *)v12 + 4) == a2 )
    {
      if ( v12 )
      {
        DEBUGMSG(
          L"CSessionAgentList::AddSessionAgent - idSession = %lu already has a session agent; removing the old one and usi"
           "ng the new one.\n",
          a2);
        CSessionAgentList::RemoveSessionAgent((CSessionAgentList *)a1, a2);
      }
      break;
    }
    v12 = (__int64 *)*v12;
  }
  v14 = operator new(0x40u);
  v15 = v14;
  if ( v14 )
  {
    *((_DWORD *)v14 + 4) = a2;
    *((_DWORD *)v14 + 5) = v11;
    *((_DWORD *)v14 + 6) = v8;
    *((_QWORD *)v14 + 4) = a4;
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)a4 + 8LL))(a4);
    *((_QWORD *)v15 + 7) = a1;
    v20 = OpenProcess(0x100000u, 0, v11);
    *((_QWORD *)v15 + 5) = v20;
    if ( v20 )
    {
      v22 = *(_QWORD **)(((a1 + 8) & -(__int64)(a1 != 0)) + 8);
      if ( *v22 != v13 )
        __fastfail(3u);
      *(_QWORD *)v15 = v13;
      *((_QWORD *)v15 + 1) = v22;
      *v22 = v15;
      *(_QWORD *)(((a1 + 8) & -(__int64)(a1 != 0)) + 8) = v15;
      if ( !RegisterWaitForSingleObject(
              (PHANDLE)v15 + 6,
              *((HANDLE *)v15 + 5),
              CSessionAgentList::s_OnSessionAgentDestroyed,
              v15,
              0xFFFFFFFF,
              8u) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        DEBUGMSG(
          L"CSessionAgentList::AddSessionAgent - ERROR - RegisterWaitForSingleObject failed, hr = 0x%08X.\n",
          (unsigned int)LastError);
      }
      CSessionAgentList::IncrementSqmSessionCount(a1, v8);
      v16 = 0;
      ++*(_DWORD *)(a1 + 344);
    }
    else
    {
      v21 = GetLastError();
      v16 = v21;
      if ( v21 > 0 )
        v16 = (unsigned __int16)v21 | 0x80070000;
      if ( v16 >= 0 )
        v16 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        0x186u,
        L"CSessionAgentList::AddSessionAgent",
        L"CBRAEx",
        L"pSessionAgentListEntry->hProcessSessionAgent",
        v16);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
          390,
          L"CSessionAgentList::AddSessionAgent",
          L"CBRAEx",
          L"pSessionAgentListEntry->hProcessSessionAgent",
          v16);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
          390,
          L"CSessionAgentList::AddSessionAgent",
          L"CBRAEx",
          L"pSessionAgentListEntry->hProcessSessionAgent",
          v16);
      CSessionAgentList::DestroySessionAgentListEntry(a1, v15, 1);
    }
  }
  else
  {
    v16 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
      0x17Au,
      L"CSessionAgentList::AddSessionAgent",
      L"CPR",
      L"pSessionAgentListEntry",
      -2147024882);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        378,
        L"CSessionAgentList::AddSessionAgent",
        L"CPR",
        L"pSessionAgentListEntry",
        -2147024882);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        378,
        L"CSessionAgentList::AddSessionAgent",
        L"CPR",
        L"pSessionAgentListEntry",
        -2147024882);
  }
  CAutoWriteLock::~CAutoWriteLock(&v25, v17, v18, v19);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14002cf08  mov     rax, rsp
0x14002cf0b  push    rbx
0x14002cf0c  push    rbp
0x14002cf0d  push    rsi
0x14002cf0e  push    rdi
0x14002cf0f  push    r12
0x14002cf11  push    r13
0x14002cf13  push    r14
0x14002cf15  push    r15
0x14002cf17  sub     rsp, 48h
0x14002cf1b  mov     ebp, edx
0x14002cf1d  mov     rsi, rcx
0x14002cf20  lea     rdx, [rcx+20h]; struct CSharedReaderWriterLock *
0x14002cf24  mov     r14, r9
0x14002cf27  lea     rcx, [rax+8]; this
0x14002cf2b  mov     r15d, r8d
0x14002cf2e  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x14002cf33  mov     r8d, 7; struct Utils::SStringMap *
0x14002cf39  lea     rdx, qword_14009C2F0; unsigned int
0x14002cf40  mov     ecx, r15d; this
0x14002cf43  call    ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
0x14002cf48  mov     r12d, [rsp+88h+dwProcessId]
0x14002cf50  lea     rcx, aCsessionagentl_11; "CSessionAgentList::AddSessionAgent idSe"...
0x14002cf57  mov     r9, rax
0x14002cf5a  mov     r8d, r12d
0x14002cf5d  mov     edx, ebp
0x14002cf5f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002cf64  lea     rcx, [rsi+8]
0x14002cf68  mov     rax, rsi
0x14002cf6b  mov     rdx, [rcx]
0x14002cf6e  neg     rax
0x14002cf71  sbb     rbx, rbx
0x14002cf74  and     rbx, rcx
0x14002cf77  cmp     rdx, rbx
0x14002cf7a  jz      short loc_14002CFA3
0x14002cf7c  cmp     [rdx+10h], ebp
0x14002cf7f  jz      short loc_14002CF86
0x14002cf81  mov     rdx, [rdx]
0x14002cf84  jmp     short loc_14002CF77
0x14002cf86  test    rdx, rdx
0x14002cf89  jz      short loc_14002CFA3
0x14002cf8b  mov     edx, ebp
0x14002cf8d  lea     rcx, aCsessionagentl_6; "CSessionAgentList::AddSessionAgent - id"...
0x14002cf94  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002cf99  mov     edx, ebp; unsigned int
0x14002cf9b  mov     rcx, rsi; this
0x14002cf9e  call    ?RemoveSessionAgent@CSessionAgentList@@QEAAJK@Z; CSessionAgentList::RemoveSessionAgent(ulong)
0x14002cfa3  mov     ecx, 40h ; '@'; Size
0x14002cfa8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002cfad  mov     rdi, rax
0x14002cfb0  test    rax, rax
0x14002cfb3  jnz     loc_14002D059
0x14002cfb9  mov     ebx, 8007000Eh
0x14002cfbe  lea     r15, aCpr; "CPR"
0x14002cfc5  lea     r14, aCsessionagentl_2; "CSessionAgentList::AddSessionAgent"
0x14002cfcc  mov     [rsp+88h+dwFlags], ebx; int
0x14002cfd0  mov     edi, 17Ah
0x14002cfd5  lea     rbp, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002cfdc  lea     rsi, aPsessionagentl; "pSessionAgentListEntry"
0x14002cfe3  mov     r9, r15; unsigned __int16 *
0x14002cfe6  mov     r8, r14; unsigned __int16 *
0x14002cfe9  mov     qword ptr [rsp+88h+dwMilliseconds], rsi; unsigned __int16 *
0x14002cfee  mov     edx, edi; unsigned int
0x14002cff0  mov     rcx, rbp; unsigned __int16 *
0x14002cff3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002cff8  call    cs:__imp_IsDebuggerPresent
0x14002cffe  test    eax, eax
0x14002d000  jz      short loc_14002D031
0x14002d002  mov     [rsp+88h+var_50], ebx
0x14002d006  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002d00d  mov     [rsp+88h+var_58], rsi
0x14002d012  mov     r9d, edi
0x14002d015  mov     qword ptr [rsp+88h+dwFlags], r15
0x14002d01a  mov     r8, rbp
0x14002d01d  mov     ecx, 2; unsigned __int8
0x14002d022  mov     qword ptr [rsp+88h+dwMilliseconds], r14
0x14002d027  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002d02c  jmp     loc_14002D1DC
0x14002d031  mov     dword ptr [rsp+88h+var_58], ebx
0x14002d035  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002d03c  mov     qword ptr [rsp+88h+dwFlags], rsi
0x14002d041  mov     r9, r14
0x14002d044  mov     r8d, edi
0x14002d047  mov     qword ptr [rsp+88h+dwMilliseconds], r15
0x14002d04c  mov     rdx, rbp
0x14002d04f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002d054  jmp     loc_14002D1DC
0x14002d059  mov     [rax+10h], ebp
0x14002d05c  mov     rcx, r14
0x14002d05f  mov     [rax+14h], r12d
0x14002d063  mov     [rax+18h], r15d
0x14002d067  mov     [rax+20h], r14
0x14002d06b  mov     rax, [r14]
0x14002d06e  mov     rax, [rax+8]
0x14002d072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d077  mov     r8d, r12d; dwProcessId
0x14002d07a  mov     [rdi+38h], rsi
0x14002d07e  xor     edx, edx; bInheritHandle
0x14002d080  mov     ecx, 100000h; dwDesiredAccess
0x14002d085  call    cs:__imp_OpenProcess
0x14002d08b  mov     [rdi+28h], rax
0x14002d08f  test    rax, rax
0x14002d092  jnz     loc_14002D15F
0x14002d098  call    cs:__imp_GetLastError
0x14002d09e  mov     ebx, eax
0x14002d0a0  test    eax, eax
0x14002d0a2  jle     short loc_14002D0AD
0x14002d0a4  movzx   ebx, ax
0x14002d0a7  or      ebx, 80070000h
0x14002d0ad  mov     eax, 80004005h
0x14002d0b2  lea     r13, aCbraex; "CBRAEx"
0x14002d0b9  test    ebx, ebx
0x14002d0bb  lea     r14, aCsessionagentl_2; "CSessionAgentList::AddSessionAgent"
0x14002d0c2  mov     r15d, 186h
0x14002d0c8  lea     rbp, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002d0cf  cmovns  ebx, eax
0x14002d0d2  lea     r12, aPsessionagentl_0; "pSessionAgentListEntry->hProcessSession"...
0x14002d0d9  mov     [rsp+88h+dwFlags], ebx; int
0x14002d0dd  mov     r9, r13; unsigned __int16 *
0x14002d0e0  mov     r8, r14; unsigned __int16 *
0x14002d0e3  mov     qword ptr [rsp+88h+dwMilliseconds], r12; unsigned __int16 *
0x14002d0e8  mov     edx, r15d; unsigned int
0x14002d0eb  mov     rcx, rbp; unsigned __int16 *
0x14002d0ee  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002d0f3  call    cs:__imp_IsDebuggerPresent
0x14002d0f9  test    eax, eax
0x14002d0fb  jz      short loc_14002D129
0x14002d0fd  mov     [rsp+88h+var_50], ebx
0x14002d101  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002d108  mov     [rsp+88h+var_58], r12
0x14002d10d  mov     r9d, r15d
0x14002d110  mov     qword ptr [rsp+88h+dwFlags], r13
0x14002d115  mov     r8, rbp
0x14002d118  mov     ecx, 2; unsigned __int8
0x14002d11d  mov     qword ptr [rsp+88h+dwMilliseconds], r14
0x14002d122  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002d127  jmp     short loc_14002D14C
0x14002d129  mov     dword ptr [rsp+88h+var_58], ebx
0x14002d12d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002d134  mov     qword ptr [rsp+88h+dwFlags], r12
0x14002d139  mov     r9, r14
0x14002d13c  mov     r8d, r15d
0x14002d13f  mov     qword ptr [rsp+88h+dwMilliseconds], r13
0x14002d144  mov     rdx, rbp
0x14002d147  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002d14c  mov     r8d, 1
0x14002d152  mov     rdx, rdi
0x14002d155  mov     rcx, rsi
0x14002d158  call    ?DestroySessionAgentListEntry@CSessionAgentList@@AEAAJPEAUSSessionAgentListEntry@@W4EDestroySaListEntryOptions@1@@Z; CSessionAgentList::DestroySessionAgentListEntry(SSessionAgentListEntry *,CSessionAgentList::EDestroySaListEntryOptions)
0x14002d15d  jmp     short loc_14002D1DC
0x14002d15f  mov     rax, [rbx+8]
0x14002d163  cmp     [rax], rbx
0x14002d166  jz      short loc_14002D16F
0x14002d168  mov     ecx, 3
0x14002d16d  int     29h; Win8: RtlFailFast(ecx)
0x14002d16f  mov     [rdi], rbx
0x14002d172  lea     rcx, [rdi+30h]; phNewWaitObject
0x14002d176  mov     [rdi+8], rax
0x14002d17a  lea     r8, ?s_OnSessionAgentDestroyed@CSessionAgentList@@CAXPEAXE@Z; Callback
0x14002d181  mov     [rax], rdi
0x14002d184  mov     r9, rdi; Context
0x14002d187  mov     [rbx+8], rdi
0x14002d18b  mov     rdx, [rdi+28h]; hObject
0x14002d18f  mov     [rsp+88h+dwFlags], 8; dwFlags
0x14002d197  mov     [rsp+88h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x14002d19f  call    cs:__imp_RegisterWaitForSingleObject
0x14002d1a5  test    eax, eax
0x14002d1a7  jnz     short loc_14002D1C9
0x14002d1a9  call    cs:__imp_GetLastError
0x14002d1af  test    eax, eax
0x14002d1b1  jle     short loc_14002D1BB
0x14002d1b3  movzx   eax, ax
0x14002d1b6  or      eax, 80070000h
0x14002d1bb  mov     edx, eax
0x14002d1bd  lea     rcx, aCsessionagentl_32; "CSessionAgentList::AddSessionAgent - ER"...
0x14002d1c4  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002d1c9  mov     edx, r15d
0x14002d1cc  mov     rcx, rsi
0x14002d1cf  call    ?IncrementSqmSessionCount@CSessionAgentList@@AEAAJW4ESessionType@@@Z; CSessionAgentList::IncrementSqmSessionCount(ESessionType)
0x14002d1d4  xor     ebx, ebx
0x14002d1d6  inc     dword ptr [rsi+158h]
0x14002d1dc  lea     rcx, [rsp+88h+arg_0]; this
0x14002d1e4  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x14002d1e9  mov     eax, ebx
0x14002d1eb  add     rsp, 48h
0x14002d1ef  pop     r15
0x14002d1f1  pop     r14
0x14002d1f3  pop     r13
0x14002d1f5  pop     r12
0x14002d1f7  pop     rdi
0x14002d1f8  pop     rsi
0x14002d1f9  pop     rbp
0x14002d1fa  pop     rbx
0x14002d1fb  retn
```
