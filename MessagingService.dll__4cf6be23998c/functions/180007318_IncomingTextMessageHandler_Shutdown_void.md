# IncomingTextMessageHandler::Shutdown(void)

- ea: `0x180007318`
- end: `0x180007406`
- name: `?Shutdown@IncomingTextMessageHandler@@QEAAXXZ`
- size: `238`
- prototype: `void __fastcall(IncomingTextMessageHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006c30`

## callees

- `0x18000108c`
- `0x180007128`
- `0x180007318`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007337`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007337`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073ed`

## pseudocode

```c
void __fastcall IncomingTextMessageHandler::Shutdown(IncomingTextMessageHandler *this)
{
  IncomingMessageRegistrationEvent *v2; // rcx
  IncomingTextMessageHandler *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF

  EnterCriticalSection(&IncomingTextMessageHandler::sm_instanceLock);
  v2 = (IncomingMessageRegistrationEvent *)*((_QWORD *)this + 5);
  if ( v2 )
    tlx::_delete<IncomingMessageRegistrationEvent>(v2);
  *((_QWORD *)this + 5) = 0;
  v3 = IncomingTextMessageHandler::sm_incomingTextMessageHandler;
  if ( IncomingTextMessageHandler::sm_incomingTextMessageHandler )
  {
    IncomingTextMessageHandler::sm_incomingTextMessageHandler = 0;
    (*(void (__fastcall **)(IncomingTextMessageHandler *))(*(_QWORD *)v3 + 8LL))(v3);
  }
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    *((_QWORD *)this + 3) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = *((_QWORD *)this + 4);
  if ( v5 )
  {
    *((_QWORD *)this + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( (unsigned int)dword_180013018 > 4 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&word_18001050A, 0, 0, 2u, &v6);
  LeaveCriticalSection(&IncomingTextMessageHandler::sm_instanceLock);
}

```

## disassembly

```asm
0x180007318  push    rbx
0x18000731a  sub     rsp, 60h
0x18000731e  mov     rax, cs:__security_cookie
0x180007325  xor     rax, rsp
0x180007328  mov     [rsp+68h+var_18], rax
0x18000732d  mov     rbx, rcx
0x180007330  lea     rcx, ?sm_instanceLock@IncomingTextMessageHandler@@0Vrecursive_mutex@utl@@A; lpCriticalSection
0x180007337  call    cs:__imp_EnterCriticalSection
0x18000733d  mov     rcx, [rbx+28h]
0x180007341  test    rcx, rcx
0x180007344  jz      short loc_18000734B
0x180007346  call    ??$_delete@VIncomingMessageRegistrationEvent@@@tlx@@YAXPEAVIncomingMessageRegistrationEvent@@@Z; tlx::_delete<IncomingMessageRegistrationEvent>(IncomingMessageRegistrationEvent *)
0x18000734b  mov     qword ptr [rbx+28h], 0
0x180007353  mov     rcx, cs:?sm_incomingTextMessageHandler@IncomingTextMessageHandler@@0V?$CComPtr@VIncomingTextMessageHandler@@@ATL@@A; ATL::CComPtr<IncomingTextMessageHandler> IncomingTextMessageHandler::sm_incomingTextMessageHandler
0x18000735a  test    rcx, rcx
0x18000735d  jz      short loc_180007376
0x18000735f  mov     cs:?sm_incomingTextMessageHandler@IncomingTextMessageHandler@@0V?$CComPtr@VIncomingTextMessageHandler@@@ATL@@A, 0; ATL::CComPtr<IncomingTextMessageHandler> IncomingTextMessageHandler::sm_incomingTextMessageHandler
0x18000736a  mov     rax, [rcx]
0x18000736d  mov     rax, [rax+8]
0x180007371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007376  mov     rcx, [rbx+18h]
0x18000737a  test    rcx, rcx
0x18000737d  jz      short loc_180007393
0x18000737f  mov     qword ptr [rbx+18h], 0
0x180007387  mov     rax, [rcx]
0x18000738a  mov     rax, [rax+10h]
0x18000738e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007393  mov     rcx, [rbx+20h]
0x180007397  test    rcx, rcx
0x18000739a  jz      short loc_1800073B0
0x18000739c  mov     qword ptr [rbx+20h], 0
0x1800073a4  mov     rax, [rcx]
0x1800073a7  mov     rax, [rax+10h]
0x1800073ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b0  mov     eax, cs:dword_180013018
0x1800073b6  cmp     eax, 4
0x1800073b9  jbe     short loc_1800073E6
0x1800073bb  lea     rax, [rsp+68h+var_38]
0x1800073c0  xor     r9d, r9d; int
0x1800073c3  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x1800073c8  lea     rdx, word_18001050A; int
0x1800073cf  xor     r8d, r8d; int
0x1800073d2  mov     [rsp+68h+var_48], 2; ULONG
0x1800073da  lea     rcx, dword_180013018; int
0x1800073e1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800073e6  lea     rcx, ?sm_instanceLock@IncomingTextMessageHandler@@0Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800073ed  call    cs:__imp_LeaveCriticalSection
0x1800073f3  mov     rcx, [rsp+68h+var_18]
0x1800073f8  xor     rcx, rsp; StackCookie
0x1800073fb  call    __security_check_cookie
0x180007400  add     rsp, 60h
0x180007404  pop     rbx
0x180007405  retn
```
