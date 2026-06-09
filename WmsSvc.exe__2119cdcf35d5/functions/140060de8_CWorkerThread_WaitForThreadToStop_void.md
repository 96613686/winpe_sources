# CWorkerThread::WaitForThreadToStop(void)

- ea: `0x140060de8`
- end: `0x140060f8d`
- name: `?WaitForThreadToStop@CWorkerThread@@QEAAJXZ`
- size: `421`
- prototype: `__int64 __fastcall(CWorkerThread *__hidden this)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140009778`
- `0x14000b980`
- `0x140045844`
- `0x140060be0`
- `0x14006e19c`
- `0x14006e81c`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140060de8`

## import_xrefs

- `KERNEL32!GetThreadId` at `0x140060e08`
- `KERNEL32!GetThreadId` at `0x140060ec2`
- `KERNEL32!GetThreadId` at `0x140060f62`
- `KERNEL32!GetThreadId` at `0x140060e08`
- `KERNEL32!GetThreadId` at `0x140060ec2`
- `KERNEL32!GetThreadId` at `0x140060f62`
- `KERNEL32!GetCurrentThreadId` at `0x140060e10`
- `KERNEL32!GetCurrentThreadId` at `0x140060e10`
- `KERNEL32!WaitForSingleObject` at `0x140060ee5`
- `KERNEL32!WaitForSingleObject` at `0x140060ee5`
- `KERNEL32!GetLastError` at `0x140060eef`
- `KERNEL32!GetLastError` at `0x140060eef`
- `KERNEL32!IsDebuggerPresent` at `0x140060e5d`
- `KERNEL32!IsDebuggerPresent` at `0x140060e5d`

## string_xrefs

- `0x140060e3d`: `termsrv\wms\src\common\srcutils\workerthread.cpp`
- `0x140060f06`: `termsrv\wms\src\common\srcutils\workerthread.cpp`
- `0x140060e36`: `CWorkerThread::WaitForThreadToStop`
- `0x140060f12`: `CWorkerThread::WaitForThreadToStop`
- `0x140060e23`: `::GetThreadId (m_hThread) != GetCurrentThreadId()`
- `0x140060ecc`: `CWorkerThread::WaitForThreadToStop - Waiting for %s thread to stop:  id = 0x%X  obj = 0x%X\n`
- `0x140060f23`: ` - thread failed to stop.`
- `0x140060f6c`: `CWorkerThread::WaitForThreadToStop - %s thread stopped:  id = 0x%X  obj = 0x%X\n`

## pseudocode

```c
__int64 __fastcall CWorkerThread::WaitForThreadToStop(CWorkerThread *this)
{
  void *v2; // rcx
  unsigned int v3; // ebx
  DWORD ThreadId; // ebx
  const unsigned __int16 *v5; // r14
  const unsigned __int16 *v6; // r15
  unsigned int v7; // ebp
  DWORD v8; // eax
  signed int LastError; // eax
  DWORD v10; // eax

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    ThreadId = GetThreadId(v2);
    if ( ThreadId == GetCurrentThreadId() )
    {
      v3 = -2147418113;
      v5 = L"::GetThreadId (m_hThread) != GetCurrentThreadId()";
      v6 = L"CBRAEx";
      v7 = 234;
    }
    else
    {
      v8 = GetThreadId(*((HANDLE *)this + 2));
      DEBUGMSG(
        L"CWorkerThread::WaitForThreadToStop - Waiting for %s thread to stop:  id = 0x%X  obj = 0x%X\n",
        *((_QWORD *)this + 1),
        v8,
        this);
      if ( !WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF) )
      {
        v3 = 0;
        v10 = GetThreadId(*((HANDLE *)this + 2));
        DEBUGMSG(
          L"CWorkerThread::WaitForThreadToStop - %s thread stopped:  id = 0x%X  obj = 0x%X\n",
          *((_QWORD *)this + 1),
          v10,
          this);
        return v3;
      }
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (v3 & 0x80000000) == 0 )
        v3 = -2147467259;
      v7 = 243;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
        243,
        L"CWorkerThread::WaitForThreadToStop",
        L" - thread failed to stop.");
      v5 = L"dwWait == ((((DWORD )0x00000000L) ) + 0 )";
      v6 = L"CBRLAEx";
    }
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
      v7,
      L"CWorkerThread::WaitForThreadToStop",
      v6,
      v5,
      v3);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
        v7,
        L"CWorkerThread::WaitForThreadToStop",
        v6,
        v5,
        v3);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
        v7,
        L"CWorkerThread::WaitForThreadToStop",
        v6,
        v5,
        v3);
  }
  else
  {
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x140060de8  push    rbx
0x140060dea  push    rbp
0x140060deb  push    rsi
0x140060dec  push    rdi
0x140060ded  push    r14
0x140060def  push    r15
0x140060df1  sub     rsp, 48h
0x140060df5  mov     rdi, rcx
0x140060df8  mov     rcx, [rcx+10h]; Thread
0x140060dfc  test    rcx, rcx
0x140060dff  jnz     short loc_140060E08
0x140060e01  xor     ebx, ebx
0x140060e03  jmp     loc_140060F7E
0x140060e08  call    cs:__imp_GetThreadId
0x140060e0e  mov     ebx, eax
0x140060e10  call    cs:__imp_GetCurrentThreadId
0x140060e16  cmp     ebx, eax
0x140060e18  jnz     loc_140060EBE
0x140060e1e  mov     ebx, 8000FFFFh
0x140060e23  lea     r14, aGetthreadidMHt; "::GetThreadId (m_hThread) != GetCurrent"...
0x140060e2a  lea     r15, aCbraex; "CBRAEx"
0x140060e31  mov     ebp, 0EAh
0x140060e36  lea     rsi, aCworkerthreadW_1; "CWorkerThread::WaitForThreadToStop"
0x140060e3d  lea     rdi, aTermsrvWmsSrcC_12; "termsrv\\wms\\src\\common\\srcutils\\wo"...
0x140060e44  mov     [rsp+78h+var_50], ebx; int
0x140060e48  mov     edx, ebp; unsigned int
0x140060e4a  mov     r8, rsi; unsigned __int16 *
0x140060e4d  mov     [rsp+78h+var_58], r14; unsigned __int16 *
0x140060e52  mov     r9, r15; unsigned __int16 *
0x140060e55  mov     rcx, rdi; unsigned __int16 *
0x140060e58  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140060e5d  call    cs:__imp_IsDebuggerPresent
0x140060e63  test    eax, eax
0x140060e65  jz      short loc_140060E96
0x140060e67  mov     [rsp+78h+var_40], ebx
0x140060e6b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140060e72  mov     [rsp+78h+var_48], r14
0x140060e77  mov     r9d, ebp
0x140060e7a  mov     qword ptr [rsp+78h+var_50], r15
0x140060e7f  mov     r8, rdi
0x140060e82  mov     ecx, 2; unsigned __int8
0x140060e87  mov     [rsp+78h+var_58], rsi
0x140060e8c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140060e91  jmp     loc_140060F7E
0x140060e96  mov     dword ptr [rsp+78h+var_48], ebx
0x140060e9a  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140060ea1  mov     qword ptr [rsp+78h+var_50], r14
0x140060ea6  mov     r9, rsi
0x140060ea9  mov     r8d, ebp
0x140060eac  mov     [rsp+78h+var_58], r15
0x140060eb1  mov     rdx, rdi
0x140060eb4  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140060eb9  jmp     loc_140060F7E
0x140060ebe  mov     rcx, [rdi+10h]; Thread
0x140060ec2  call    cs:__imp_GetThreadId
0x140060ec8  mov     rdx, [rdi+8]
0x140060ecc  lea     rcx, aCworkerthreadW_0; "CWorkerThread::WaitForThreadToStop - Wa"...
0x140060ed3  mov     r8d, eax
0x140060ed6  mov     r9, rdi
0x140060ed9  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140060ede  mov     rcx, [rdi+10h]; hHandle
0x140060ee2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140060ee5  call    cs:__imp_WaitForSingleObject
0x140060eeb  test    eax, eax
0x140060eed  jz      short loc_140060F5C
0x140060eef  call    cs:__imp_GetLastError
0x140060ef5  mov     ebx, eax
0x140060ef7  test    eax, eax
0x140060ef9  jle     short loc_140060F04
0x140060efb  movzx   ebx, ax
0x140060efe  or      ebx, 80070000h
0x140060f04  test    ebx, ebx
0x140060f06  lea     rdi, aTermsrvWmsSrcC_12; "termsrv\\wms\\src\\common\\srcutils\\wo"...
0x140060f0d  mov     eax, 80004005h
0x140060f12  lea     rsi, aCworkerthreadW_1; "CWorkerThread::WaitForThreadToStop"
0x140060f19  cmovns  ebx, eax
0x140060f1c  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140060f23  lea     rax, aThreadFailedTo_0; " - thread failed to stop."
0x140060f2a  mov     ebp, 0F3h
0x140060f2f  mov     qword ptr [rsp+78h+var_50], rax
0x140060f34  mov     r9d, ebp
0x140060f37  mov     r8, rdi
0x140060f3a  mov     [rsp+78h+var_58], rsi
0x140060f3f  mov     ecx, 4; unsigned __int8
0x140060f44  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140060f49  lea     r14, aDwwaitDword0x0; "dwWait == ((((DWORD )0x00000000L) ) + 0"...
0x140060f50  lea     r15, aCbrlaex; "CBRLAEx"
0x140060f57  jmp     loc_140060E44
0x140060f5c  mov     rcx, [rdi+10h]; Thread
0x140060f60  xor     ebx, ebx
0x140060f62  call    cs:__imp_GetThreadId
0x140060f68  mov     rdx, [rdi+8]
0x140060f6c  lea     rcx, aCworkerthreadW; "CWorkerThread::WaitForThreadToStop - %s"...
0x140060f73  mov     r8d, eax
0x140060f76  mov     r9, rdi
0x140060f79  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140060f7e  mov     eax, ebx
0x140060f80  add     rsp, 48h
0x140060f84  pop     r15
0x140060f86  pop     r14
0x140060f88  pop     rdi
0x140060f89  pop     rsi
0x140060f8a  pop     rbp
0x140060f8b  pop     rbx
0x140060f8c  retn
```
