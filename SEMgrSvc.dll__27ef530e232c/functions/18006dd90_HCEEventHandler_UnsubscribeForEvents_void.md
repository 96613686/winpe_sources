# HCEEventHandler::UnsubscribeForEvents(void)

- ea: `0x18006dd90`
- end: `0x18006de57`
- name: `?UnsubscribeForEvents@HCEEventHandler@@UEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(HCEEventHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18006c18c`

## callees

- `0x18001aac8`
- `0x18001ba30`
- `0x18006dd90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006de14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006de14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006de03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006de03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006de23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006de23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18006de3c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18006de3c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18006de32`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18006de32`

## pseudocode

```c
__int64 __fastcall HCEEventHandler::UnsubscribeForEvents(HCEEventHandler *this)
{
  void *v1; // rdx
  NFCConnector **v2; // rbx
  void *v4; // rdx
  void *v5; // rdx

  v1 = (void *)*((_QWORD *)this + 15);
  v2 = (NFCConnector **)((char *)this + 80);
  if ( v1 )
  {
    NFCConnector::UnsubscribeForEvent(*v2, v1);
    *((_QWORD *)this + 15) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
  {
    NFCConnector::UnsubscribeForEvent(*v2, v4);
    *((_QWORD *)this + 16) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 17);
  if ( v5 )
  {
    NFCConnector::HCEUnsubscribeForRecv(*v2, v5);
    *((_QWORD *)this + 17) = 0;
  }
  if ( *((_QWORD *)this + 12) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *((_BYTE *)this + 200) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    SetThreadpoolWait(*((PTP_WAIT *)this + 12), 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 12), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 12));
    *((_QWORD *)this + 12) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18006dd90  mov     [rsp+arg_0], rbx
0x18006dd95  push    rdi
0x18006dd96  sub     rsp, 20h
0x18006dd9a  mov     rdx, [rcx+78h]; void *
0x18006dd9e  lea     rbx, [rcx+50h]
0x18006dda2  mov     rdi, rcx
0x18006dda5  test    rdx, rdx
0x18006dda8  jz      short loc_18006DDBA
0x18006ddaa  mov     rcx, [rbx]; this
0x18006ddad  call    ?UnsubscribeForEvent@NFCConnector@@QEAAJPEAX@Z; NFCConnector::UnsubscribeForEvent(void *)
0x18006ddb2  mov     qword ptr [rdi+78h], 0
0x18006ddba  mov     rdx, [rdi+80h]; void *
0x18006ddc1  test    rdx, rdx
0x18006ddc4  jz      short loc_18006DDD9
0x18006ddc6  mov     rcx, [rbx]; this
0x18006ddc9  call    ?UnsubscribeForEvent@NFCConnector@@QEAAJPEAX@Z; NFCConnector::UnsubscribeForEvent(void *)
0x18006ddce  mov     qword ptr [rdi+80h], 0
0x18006ddd9  mov     rdx, [rdi+88h]; void *
0x18006dde0  test    rdx, rdx
0x18006dde3  jz      short loc_18006DDF8
0x18006dde5  mov     rcx, [rbx]; this
0x18006dde8  call    ?HCEUnsubscribeForRecv@NFCConnector@@QEAAJPEAX@Z; NFCConnector::HCEUnsubscribeForRecv(void *)
0x18006dded  mov     qword ptr [rdi+88h], 0
0x18006ddf8  cmp     qword ptr [rdi+60h], 0
0x18006ddfd  jz      short loc_18006DE4A
0x18006ddff  lea     rcx, [rdi+8]; lpCriticalSection
0x18006de03  call    cs:__imp_EnterCriticalSection
0x18006de09  lea     rcx, [rdi+8]; lpCriticalSection
0x18006de0d  mov     byte ptr [rdi+0C8h], 0
0x18006de14  call    cs:__imp_LeaveCriticalSection
0x18006de1a  mov     rcx, [rdi+60h]; pwa
0x18006de1e  xor     r8d, r8d; pftTimeout
0x18006de21  xor     edx, edx; h
0x18006de23  call    cs:__imp_SetThreadpoolWait
0x18006de29  mov     rcx, [rdi+60h]; pwa
0x18006de2d  mov     edx, 1; fCancelPendingCallbacks
0x18006de32  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18006de38  mov     rcx, [rdi+60h]; pwa
0x18006de3c  call    cs:__imp_CloseThreadpoolWait
0x18006de42  mov     qword ptr [rdi+60h], 0
0x18006de4a  mov     rbx, [rsp+28h+arg_0]
0x18006de4f  xor     eax, eax
0x18006de51  add     rsp, 20h
0x18006de55  pop     rdi
0x18006de56  retn
```
