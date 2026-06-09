# CWorkerThread::Stop(void)

- ea: `0x140060be0`
- end: `0x140060d8f`
- name: `?Stop@CWorkerThread@@UEAAJXZ`
- size: `431`
- prototype: `__int64 __fastcall(CWorkerThread *__hidden this)`
- caller_count: `8`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140029ec0`
- `0x140035ec0`
- `0x1400607b4`
- `0x1400607e0`
- `0x140069f84`
- `0x14006a8e0`
- `0x14006cb40`
- `0x140077ad0`

## callees

- `0x140004730`
- `0x140004a04`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x140060be0`
- `0x140060de8`

## import_xrefs

- `KERNEL32!TerminateThread` at `0x140060c84`
- `KERNEL32!TerminateThread` at `0x140060c84`
- `KERNEL32!CloseHandle` at `0x140060c46`
- `KERNEL32!CloseHandle` at `0x140060d52`
- `KERNEL32!CloseHandle` at `0x140060d6e`
- `KERNEL32!CloseHandle` at `0x140060c46`
- `KERNEL32!CloseHandle` at `0x140060d52`
- `KERNEL32!CloseHandle` at `0x140060d6e`
- `KERNEL32!GetThreadId` at `0x140060c61`
- `KERNEL32!GetThreadId` at `0x140060c61`
- `KERNEL32!SetEvent` at `0x140060c1b`
- `KERNEL32!SetEvent` at `0x140060c1b`
- `KERNEL32!IsDebuggerPresent` at `0x140060cb9`
- `KERNEL32!IsDebuggerPresent` at `0x140060cb9`

## string_xrefs

- `0x140060cad`: `termsrv\wms\src\common\srcutils\workerthread.cpp`
- `0x140060cdf`: `termsrv\wms\src\common\srcutils\workerthread.cpp`
- `0x140060d0c`: `termsrv\wms\src\common\srcutils\workerthread.cpp`
- `0x140060c9e`: `CWorkerThread::Stop`
- `0x140060c71`: `CWorkerThread::Stop - %s thread failed to stop gracefully; calling TerminateThread():  id = 0x%X  obj = 0x%X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkerThread::Stop(CWorkerThread *this, __int64 a2, __int64 a3, const unsigned __int16 *a4)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  const unsigned __int16 *v7; // r9
  char *v8; // rcx
  void *v9; // rcx
  DWORD ThreadId; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  const unsigned __int16 *v13; // r9
  char *v14; // rcx
  char *v15; // rcx
  PSRWLOCK v17; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 3) )
    {
      CAutoWriteLock::CAutoWriteLock((CAutoWriteLock *)&v17, (CWorkerThread *)((char *)this + 48), a3, a4);
      *((_DWORD *)this + 10) = 2;
      SetEvent(*((HANDLE *)this + 3));
      CAutoWriteLock::~CAutoWriteLock(&v17, v5, v6, v7);
      if ( (int)CWorkerThread::WaitForThreadToStop(this) >= 0 )
      {
        v8 = (char *)*((_QWORD *)this + 2);
        if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(v8);
          *((_QWORD *)this + 2) = 0;
        }
      }
    }
  }
  v9 = (void *)*((_QWORD *)this + 2);
  if ( v9 )
  {
    ThreadId = GetThreadId(v9);
    DEBUGMSG(
      L"CWorkerThread::Stop - %s thread failed to stop gracefully; calling TerminateThread():  id = 0x%X  obj = 0x%X\n",
      *((_QWORD *)this + 1),
      ThreadId,
      this);
    if ( !TerminateThread(*((HANDLE *)this + 2), 0xFFFFFFFF) )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
        0xBDu,
        L"CWorkerThread::Stop",
        a4,
        L"fSuccess");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
          189,
          L"CWorkerThread::Stop",
          L"ASSERT",
          L"fSuccess");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\common\\srcutils\\workerthread.cpp",
          189,
          L"CWorkerThread::Stop",
          L"ASSERT",
          L"fSuccess");
    }
  }
  CAutoWriteLock::CAutoWriteLock((CAutoWriteLock *)&v17, (CWorkerThread *)((char *)this + 48), a3, a4);
  *((_DWORD *)this + 10) = 3;
  CAutoWriteLock::~CAutoWriteLock(&v17, v11, v12, v13);
  if ( *((_DWORD *)this + 11) )
  {
    v14 = (char *)*((_QWORD *)this + 3);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v14);
      *((_QWORD *)this + 3) = 0;
    }
  }
  v15 = (char *)*((_QWORD *)this + 2);
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v15);
    *((_QWORD *)this + 2) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140060be0  mov     [rsp+arg_8], rbx
0x140060be5  mov     [rsp+arg_10], r14
0x140060bea  push    r15
0x140060bec  sub     rsp, 40h
0x140060bf0  mov     rbx, rcx
0x140060bf3  cmp     qword ptr [rcx+10h], 0
0x140060bf8  jz      short loc_140060C54
0x140060bfa  cmp     qword ptr [rcx+18h], 0
0x140060bff  jz      short loc_140060C54
0x140060c01  lea     rdx, [rcx+30h]; struct CSharedReaderWriterLock *
0x140060c05  lea     rcx, [rsp+48h+arg_0]; this
0x140060c0a  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x140060c0f  nop
0x140060c10  mov     dword ptr [rbx+28h], 2
0x140060c17  mov     rcx, [rbx+18h]; hEvent
0x140060c1b  call    cs:__imp_SetEvent
0x140060c21  nop
0x140060c22  lea     rcx, [rsp+48h+arg_0]; this
0x140060c27  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x140060c2c  mov     rcx, rbx; this
0x140060c2f  call    ?WaitForThreadToStop@CWorkerThread@@QEAAJXZ; CWorkerThread::WaitForThreadToStop(void)
0x140060c34  test    eax, eax
0x140060c36  js      short loc_140060C54
0x140060c38  mov     rcx, [rbx+10h]; hObject
0x140060c3c  lea     rax, [rcx-1]
0x140060c40  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140060c44  ja      short loc_140060C54
0x140060c46  call    cs:__imp_CloseHandle
0x140060c4c  mov     qword ptr [rbx+10h], 0
0x140060c54  mov     rcx, [rbx+10h]; Thread
0x140060c58  test    rcx, rcx
0x140060c5b  jz      loc_140060D1F
0x140060c61  call    cs:__imp_GetThreadId
0x140060c67  mov     r9, rbx
0x140060c6a  mov     r8d, eax
0x140060c6d  mov     rdx, [rbx+8]
0x140060c71  lea     rcx, aCworkerthreadS_2; "CWorkerThread::Stop - %s thread failed "...
0x140060c78  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140060c7d  or      edx, 0FFFFFFFFh; dwExitCode
0x140060c80  mov     rcx, [rbx+10h]; hThread
0x140060c84  call    cs:__imp_TerminateThread
0x140060c8a  test    eax, eax
0x140060c8c  jnz     loc_140060D1F
0x140060c92  lea     r15, aFsuccess; "fSuccess"
0x140060c99  mov     [rsp+48h+var_28], r15; unsigned __int16 *
0x140060c9e  lea     r14, aCworkerthreadS_0; "CWorkerThread::Stop"
0x140060ca5  mov     r8, r14; unsigned __int16 *
0x140060ca8  mov     edx, 0BDh; unsigned int
0x140060cad  lea     rcx, aTermsrvWmsSrcC_12; "termsrv\\wms\\src\\common\\srcutils\\wo"...
0x140060cb4  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140060cb9  call    cs:__imp_IsDebuggerPresent
0x140060cbf  test    eax, eax
0x140060cc1  lea     rax, aAssert; "ASSERT"
0x140060cc8  jz      short loc_140060CF9
0x140060cca  mov     [rsp+48h+var_18], r15
0x140060ccf  mov     [rsp+48h+var_20], rax
0x140060cd4  mov     [rsp+48h+var_28], r14
0x140060cd9  mov     r9d, 0BDh
0x140060cdf  lea     r8, aTermsrvWmsSrcC_12; "termsrv\\wms\\src\\common\\srcutils\\wo"...
0x140060ce6  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140060ced  mov     ecx, 2; unsigned __int8
0x140060cf2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140060cf7  jmp     short loc_140060D1F
0x140060cf9  mov     [rsp+48h+var_20], r15
0x140060cfe  mov     [rsp+48h+var_28], rax
0x140060d03  mov     r9, r14
0x140060d06  mov     r8d, 0BDh
0x140060d0c  lea     rdx, aTermsrvWmsSrcC_12; "termsrv\\wms\\src\\common\\srcutils\\wo"...
0x140060d13  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140060d1a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140060d1f  lea     rdx, [rbx+30h]; struct CSharedReaderWriterLock *
0x140060d23  lea     rcx, [rsp+48h+arg_0]; this
0x140060d28  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x140060d2d  mov     dword ptr [rbx+28h], 3
0x140060d34  lea     rcx, [rsp+48h+arg_0]; this
0x140060d39  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x140060d3e  cmp     dword ptr [rbx+2Ch], 0
0x140060d42  jz      short loc_140060D60
0x140060d44  mov     rcx, [rbx+18h]; hObject
0x140060d48  lea     rax, [rcx-1]
0x140060d4c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140060d50  ja      short loc_140060D60
0x140060d52  call    cs:__imp_CloseHandle
0x140060d58  mov     qword ptr [rbx+18h], 0
0x140060d60  mov     rcx, [rbx+10h]; hObject
0x140060d64  lea     rax, [rcx-1]
0x140060d68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140060d6c  ja      short loc_140060D7C
0x140060d6e  call    cs:__imp_CloseHandle
0x140060d74  mov     qword ptr [rbx+10h], 0
0x140060d7c  xor     eax, eax
0x140060d7e  mov     rbx, [rsp+48h+arg_8]
0x140060d83  mov     r14, [rsp+48h+arg_10]
0x140060d88  add     rsp, 40h
0x140060d8c  pop     r15
0x140060d8e  retn
```
