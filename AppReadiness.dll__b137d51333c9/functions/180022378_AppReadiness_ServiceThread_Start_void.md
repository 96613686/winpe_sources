# AppReadiness::ServiceThread::Start(void)

- ea: `0x180022378`
- end: `0x180022479`
- name: `?Start@ServiceThread@AppReadiness@@QEAAXXZ`
- size: `257`
- prototype: `void __fastcall(AppReadiness::ServiceThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800221a4`

## callees

- `0x180022378`
- `0x180027a4c`
- `0x1800369d4`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800223d3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800223dd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800223d3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800223dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022468`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022468`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002240b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002240b`

## string_xrefs

- `0x18002239b`: `AppReadiness::ServiceThread::Start`
- `0x180022432`: `AppReadiness::ServiceThread::Start`
- `0x1800223a7`: `!m_threadHandle.IsValid()`
- `0x18002238c`: `onecoreuap\shell\appreadiness\src\core\servicethread.cpp`
- `0x180022423`: `onecoreuap\shell\appreadiness\src\core\servicethread.cpp`
- `0x18002243e`: `ResultFromWin32Handle(CreateThread(nullptr, 0, &ServiceThread::StaticThreadProc, this, 0, &threadId), m_threadHandle.GetAddressOf())`

## pseudocode

```c
void __fastcall AppReadiness::ServiceThread::Start(AppReadiness::ServiceThread *this)
{
  HANDLE v2; // rax
  int v3; // edx
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  DWORD ThreadId; // [rsp+70h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 5) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      -2147019873,
      "!m_threadHandle.IsValid()",
      "AppReadiness::ServiceThread::Start",
      "onecoreuap\\shell\\appreadiness\\src\\core\\servicethread.cpp",
      35);
    throw (Windows::HResultException *)pExceptionObject;
  }
  ResetEvent(*((HANDLE *)this + 1));
  ResetEvent(*((HANDLE *)this + 3));
  ThreadId = 0;
  v2 = CreateThread(0, 0, AppReadiness::ServiceThread::StaticThreadProc, this, 0, &ThreadId);
  v3 = ResultFromWin32Handle(v2, (void **)this + 5);
  if ( v3 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v3,
      "ResultFromWin32Handle(CreateThread(nullptr, 0, &ServiceThread::StaticThreadProc, this, 0, &threadId), m_threadHand"
      "le.GetAddressOf())",
      "AppReadiness::ServiceThread::Start",
      "onecoreuap\\shell\\appreadiness\\src\\core\\servicethread.cpp",
      40);
    throw (Windows::HResultException *)pExceptionObject;
  }
  WaitForSingleObject(*((HANDLE *)this + 3), 0xFFFFFFFF);
}

```

## disassembly

```asm
0x180022378  mov     [rsp+arg_8], rbx
0x18002237d  push    rdi
0x18002237e  sub     rsp, 60h
0x180022382  cmp     qword ptr [rcx+28h], 0
0x180022387  mov     rbx, rcx
0x18002238a  jz      short loc_1800223CF
0x18002238c  lea     rax, aOnecoreuapShel_7; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180022393  mov     dword ptr [rsp+68h+lpThreadId], 23h ; '#'; int
0x18002239b  lea     r9, aAppreadinessSe; "AppReadiness::ServiceThread::Start"
0x1800223a2  mov     qword ptr [rsp+68h+dwCreationFlags], rax; char *
0x1800223a7  lea     r8, aMThreadhandleI; "!m_threadHandle.IsValid()"
0x1800223ae  mov     edx, 8007139Fh; int
0x1800223b3  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800223b8  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800223bd  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800223c4  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800223c9  call    _CxxThrowException_0
0x1800223cf  mov     rcx, [rcx+8]; hEvent
0x1800223d3  call    cs:__imp_ResetEvent
0x1800223d9  mov     rcx, [rbx+18h]; hEvent
0x1800223dd  call    cs:__imp_ResetEvent
0x1800223e3  lea     rax, [rsp+68h+ThreadId]
0x1800223e8  mov     [rsp+68h+ThreadId], 0
0x1800223f0  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x1800223f5  lea     r8, ?StaticThreadProc@ServiceThread@AppReadiness@@CAKPEAX@Z; lpStartAddress
0x1800223fc  mov     r9, rbx; lpParameter
0x1800223ff  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x180022407  xor     edx, edx; dwStackSize
0x180022409  xor     ecx, ecx; lpThreadAttributes
0x18002240b  call    cs:__imp_CreateThread
0x180022411  mov     rcx, rax; void *
0x180022414  lea     rdx, [rbx+28h]; void **
0x180022418  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x18002241d  mov     edx, eax; int
0x18002241f  test    eax, eax
0x180022421  jns     short loc_180022461
0x180022423  lea     rax, aOnecoreuapShel_7; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002242a  mov     dword ptr [rsp+68h+lpThreadId], 28h ; '('; int
0x180022432  lea     r9, aAppreadinessSe; "AppReadiness::ServiceThread::Start"
0x180022439  mov     qword ptr [rsp+68h+dwCreationFlags], rax; char *
0x18002243e  lea     r8, aResultfromwin3; "ResultFromWin32Handle(CreateThread(null"...
0x180022445  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18002244a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002244f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180022456  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002245b  call    _CxxThrowException_0
0x180022461  mov     rcx, [rbx+18h]; hHandle
0x180022465  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180022468  call    cs:__imp_WaitForSingleObject
0x18002246e  mov     rbx, [rsp+68h+arg_8]
0x180022473  add     rsp, 60h
0x180022477  pop     rdi
0x180022478  retn
```
