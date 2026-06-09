# SocketIoMonitor::Cleanup(void)

- ea: `0x180002380`
- end: `0x180002424`
- name: `?Cleanup@SocketIoMonitor@@UEAAXXZ`
- size: `164`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180001e90`

## callees

- `0x180002380`
- `0x180002430`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000241d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800023df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800023df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000239e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000239e`
- `WS2_32!WSACloseEvent` at `0x1800023c2`
- `WS2_32!WSACloseEvent` at `0x1800023c2`

## pseudocode

```c
void __fastcall SocketIoMonitor::Cleanup(struct _RTL_CRITICAL_SECTION *this)
{
  struct _TP_WAIT *SpinCount; // rcx
  HANDLE LockSemaphore; // rcx
  struct _TP_WAIT *v4; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax

  SpinCount = (struct _TP_WAIT *)this[6].SpinCount;
  if ( SpinCount )
    WaitForThreadpoolWaitCallbacks(SpinCount, 1);
  SharedSocket::Cleanup((SharedSocket *)this);
  EnterCriticalSection(this + 1);
  LockSemaphore = this[6].LockSemaphore;
  if ( LockSemaphore )
  {
    WSACloseEvent(LockSemaphore);
    this[6].LockSemaphore = 0;
  }
  v4 = (struct _TP_WAIT *)this[6].SpinCount;
  if ( v4 )
  {
    CloseThreadpoolWait(v4);
    this[6].SpinCount = 0;
  }
  if ( LOBYTE(this[7].DebugInfo) )
  {
    DebugInfo = this->DebugInfo;
    LOBYTE(this[7].DebugInfo) = 0;
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))DebugInfo->CriticalSection)(this);
  }
  LeaveCriticalSection(this + 1);
}

```

## disassembly

```asm
0x180002380  mov     [rsp+arg_0], rbx
0x180002385  push    rdi
0x180002386  sub     rsp, 20h
0x18000238a  mov     rbx, rcx
0x18000238d  mov     rcx, [rcx+110h]; pwa
0x180002394  test    rcx, rcx
0x180002397  jz      short loc_1800023A4
0x180002399  mov     edx, 1; fCancelPendingCallbacks
0x18000239e  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800023a4  mov     rcx, rbx; this
0x1800023a7  call    ?Cleanup@SharedSocket@@UEAAXXZ; SharedSocket::Cleanup(void)
0x1800023ac  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800023b0  call    cs:__imp_EnterCriticalSection
0x1800023b6  mov     rcx, [rbx+108h]; hEvent
0x1800023bd  test    rcx, rcx
0x1800023c0  jz      short loc_1800023D3
0x1800023c2  call    cs:__imp_WSACloseEvent
0x1800023c8  mov     qword ptr [rbx+108h], 0
0x1800023d3  mov     rcx, [rbx+110h]; pwa
0x1800023da  test    rcx, rcx
0x1800023dd  jz      short loc_1800023F0
0x1800023df  call    cs:__imp_CloseThreadpoolWait
0x1800023e5  mov     qword ptr [rbx+110h], 0
0x1800023f0  cmp     byte ptr [rbx+118h], 0
0x1800023f7  jz      short loc_18000240F
0x1800023f9  mov     rax, [rbx]
0x1800023fc  mov     rcx, rbx
0x1800023ff  mov     byte ptr [rbx+118h], 0
0x180002406  mov     rax, [rax+8]
0x18000240a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240f  lea     rcx, [rbx+28h]
0x180002413  mov     rbx, [rsp+28h+arg_0]
0x180002418  add     rsp, 20h
0x18000241c  pop     rdi
0x18000241d  jmp     cs:__imp_LeaveCriticalSection
```
