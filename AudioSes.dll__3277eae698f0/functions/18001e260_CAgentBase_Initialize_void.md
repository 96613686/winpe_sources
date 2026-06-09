# CAgentBase::Initialize(void)

- ea: `0x18001e260`
- end: `0x18001e34d`
- name: `?Initialize@CAgentBase@@IEAAJXZ`
- size: `237`
- prototype: `__int64 __fastcall(CAgentBase *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e558`
- `0x18001e8ac`

## callees

- `0x18000e7a0`
- `0x18001ddbc`
- `0x18001e260`
- `0x180078fe8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18001e28d`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18001e28d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e321`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e321`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001e2ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001e2ab`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e2ef`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e2ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e308`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e308`

## pseudocode

```c
__int64 __fastcall CAgentBase::Initialize(CAgentBase *this)
{
  __int64 result; // rax
  HANDLE WaitableTimer; // rax
  HANDLE Event; // rax
  void *v5; // rbx
  HANDLE Thread; // rax
  unsigned int Error; // edi
  unsigned int v8; // ebx
  _QWORD Parameter[2]; // [rsp+30h] [rbp-28h] BYREF
  int v10; // [rsp+40h] [rbp-18h]
  int v11; // [rsp+44h] [rbp-14h]
  HANDLE v12; // [rsp+60h] [rbp+8h] BYREF

  result = ATL::CComSafeDeleteCriticalSection::Init((CAgentBase *)((char *)this + 8));
  if ( (int)result >= 0 )
  {
    WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x100002u);
    *((_QWORD *)this + 8) = WaitableTimer;
    if ( WaitableTimer )
    {
      Event = CreateEventExW(0, 0, 1u, 0x100002u);
      v12 = Event;
      v5 = Event;
      if ( Event )
      {
        Parameter[1] = Event;
        Parameter[0] = this;
        v10 = -2147418113;
        v11 = 0;
        Thread = CreateThread(0, 0, CAgentBase::AgentThreadStart, Parameter, 0, 0);
        *((_QWORD *)this + 9) = Thread;
        if ( !Thread || WaitForSingleObject(v5, 0xFFFFFFFF) )
          Error = ATL::AtlHresultFromLastError();
        else
          Error = v10;
        CloseHandle(v5);
        return Error;
      }
      else
      {
        v8 = ATL::AtlHresultFromLastError();
        ATL::CHandle::~CHandle((ATL::CHandle *)&v12);
        return v8;
      }
    }
    else
    {
      return ATL::AtlHresultFromLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e260  mov     [rsp+arg_8], rbx
0x18001e265  push    rdi
0x18001e266  sub     rsp, 50h
0x18001e26a  mov     rdi, rcx
0x18001e26d  add     rcx, 8; this
0x18001e271  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001e276  test    eax, eax
0x18001e278  js      loc_18001E310
0x18001e27e  mov     ebx, 100002h
0x18001e283  xor     r8d, r8d; dwFlags
0x18001e286  mov     r9d, ebx; dwDesiredAccess
0x18001e289  xor     edx, edx; lpTimerName
0x18001e28b  xor     ecx, ecx; lpTimerAttributes
0x18001e28d  call    cs:__imp_CreateWaitableTimerExW
0x18001e293  mov     [rdi+40h], rax
0x18001e297  test    rax, rax
0x18001e29a  jz      loc_18001E331
0x18001e2a0  xor     edx, edx; lpName
0x18001e2a2  mov     r9d, ebx; dwDesiredAccess
0x18001e2a5  xor     ecx, ecx; lpEventAttributes
0x18001e2a7  lea     r8d, [rdx+1]; dwFlags
0x18001e2ab  call    cs:__imp_CreateEventExW
0x18001e2b1  mov     [rsp+58h+arg_0], rax
0x18001e2b6  mov     rbx, rax
0x18001e2b9  test    rax, rax
0x18001e2bc  jz      short loc_18001E338
0x18001e2be  mov     [rsp+58h+var_20], rax
0x18001e2c3  lea     r9, [rsp+58h+Parameter]; lpParameter
0x18001e2c8  xor     eax, eax
0x18001e2ca  mov     [rsp+58h+Parameter], rdi
0x18001e2cf  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18001e2d4  lea     r8, ?AgentThreadStart@CAgentBase@@CAKPEAX@Z; lpStartAddress
0x18001e2db  xor     edx, edx; dwStackSize
0x18001e2dd  mov     [rsp+58h+dwCreationFlags], eax; dwCreationFlags
0x18001e2e1  xor     ecx, ecx; lpThreadAttributes
0x18001e2e3  mov     [rsp+58h+var_18], 8000FFFFh
0x18001e2eb  mov     [rsp+58h+var_14], eax
0x18001e2ef  call    cs:__imp_CreateThread
0x18001e2f5  mov     [rdi+48h], rax
0x18001e2f9  test    rax, rax
0x18001e2fc  jnz     short loc_18001E31B
0x18001e2fe  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001e303  mov     edi, eax
0x18001e305  mov     rcx, rbx; hObject
0x18001e308  call    cs:__imp_CloseHandle
0x18001e30e  mov     eax, edi
0x18001e310  mov     rbx, [rsp+58h+arg_8]
0x18001e315  add     rsp, 50h
0x18001e319  pop     rdi
0x18001e31a  retn
0x18001e31b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001e31e  mov     rcx, rbx; hHandle
0x18001e321  call    cs:__imp_WaitForSingleObject
0x18001e327  test    eax, eax
0x18001e329  jnz     short loc_18001E2FE
0x18001e32b  mov     edi, [rsp+58h+var_18]
0x18001e32f  jmp     short loc_18001E305
0x18001e331  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001e336  jmp     short loc_18001E310
0x18001e338  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001e33d  lea     rcx, [rsp+58h+arg_0]; this
0x18001e342  mov     ebx, eax
0x18001e344  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18001e349  mov     eax, ebx
0x18001e34b  jmp     short loc_18001E310
```
