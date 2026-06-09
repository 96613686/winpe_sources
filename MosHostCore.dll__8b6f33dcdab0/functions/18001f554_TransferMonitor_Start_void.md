# TransferMonitor::Start(void)

- ea: `0x18001f554`
- end: `0x18001f647`
- name: `?Start@TransferMonitor@@QEAAJXZ`
- size: `243`
- prototype: `__int64 __fastcall(TransferMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800166a8`
- `0x18001d224`

## callees

- `0x18001f554`
- `0x1800226dc`
- `0x180022754`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f56d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f56d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f62f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f62f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001f5e2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001f5e2`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001f5a0`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001f5a0`
- `ZTrace_Maps!ZTraceHelper` at `0x18001f61f`
- `ZTrace_Maps!ZTraceHelper` at `0x18001f61f`

## string_xrefs

- `0x18001f5ff`: `[MosHost] Warning: tried to Start() while already started`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TransferMonitor::Start(TransferMonitor *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v3; // eax
  int v4; // r8d
  unsigned int v5; // ebx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( *((_BYTE *)this + 136) )
  {
    ZTraceHelper(2, "TransferMonitor::Start", 51, this, "[MosHost] Warning: tried to Start() while already started");
  }
  else
  {
    v3 = TimerQueue::Initialize((TransferMonitor *)((char *)this + 64));
    if ( v3 < 0 )
    {
      v4 = 35;
LABEL_4:
      v5 = ZTraceReportPropagation(v3, "TransferMonitor::Start", v4, this);
      goto LABEL_10;
    }
    v3 = TimerQueue::QueueTimer(
           (HANDLE *)this + 8,
           lambda_56f9094f29f565b311ab40e9ab869f48_::_lambda_invoker_cdecl_,
           this,
           0x493E0u,
           0x493E0u);
    if ( v3 < 0 )
    {
      v4 = 40;
      goto LABEL_4;
    }
    *((_BYTE *)this + 136) = 1;
    QueryUnbiasedInterruptTime((PULONGLONG)this + 18);
    *((_QWORD *)this + 19) = 0;
    *((_DWORD *)this + 40) = 0;
  }
  v5 = 0;
LABEL_10:
  if ( v2 )
    LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x18001f554  mov     [rsp+arg_8], rbx
0x18001f559  mov     [rsp+arg_10], rsi
0x18001f55e  push    rdi
0x18001f55f  sub     rsp, 30h
0x18001f563  mov     rbx, rcx
0x18001f566  lea     rdi, [rcx+60h]
0x18001f56a  mov     rcx, rdi; lpCriticalSection
0x18001f56d  call    cs:__imp_EnterCriticalSection
0x18001f573  mov     [rsp+38h+arg_0], rdi
0x18001f578  cmp     byte ptr [rbx+88h], 0
0x18001f57f  jnz     short loc_18001F5FF
0x18001f581  lea     rcx, [rbx+40h]; this
0x18001f585  call    ?Initialize@TimerQueue@@QEAAJXZ; TimerQueue::Initialize(void)
0x18001f58a  test    eax, eax
0x18001f58c  jns     short loc_18001F5AA
0x18001f58e  mov     r8d, 23h ; '#'
0x18001f594  mov     r9, rbx
0x18001f597  lea     rdx, aTransfermonito_0; "TransferMonitor::Start"
0x18001f59e  mov     ecx, eax
0x18001f5a0  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001f5a6  mov     ebx, eax
0x18001f5a8  jmp     short loc_18001F627
0x18001f5aa  mov     r9d, 493E0h; unsigned int
0x18001f5b0  mov     [rsp+38h+var_18], r9d; unsigned int
0x18001f5b5  mov     r8, rbx; void *
0x18001f5b8  lea     rdx, _lambda_56f9094f29f565b311ab40e9ab869f48____lambda_invoker_cdecl_; void (*)(void *)
0x18001f5bf  lea     rcx, [rbx+40h]; this
0x18001f5c3  call    ?QueueTimer@TimerQueue@@QEAAJP6AXPEAX@Z0KK@Z; TimerQueue::QueueTimer(void (*)(void *),void *,ulong,ulong)
0x18001f5c8  test    eax, eax
0x18001f5ca  jns     short loc_18001F5D4
0x18001f5cc  mov     r8d, 28h ; '('
0x18001f5d2  jmp     short loc_18001F594
0x18001f5d4  mov     byte ptr [rbx+88h], 1
0x18001f5db  lea     rcx, [rbx+90h]; UnbiasedTime
0x18001f5e2  call    cs:__imp_QueryUnbiasedInterruptTime
0x18001f5e8  mov     qword ptr [rbx+98h], 0
0x18001f5f3  mov     dword ptr [rbx+0A0h], 0
0x18001f5fd  jmp     short loc_18001F625
0x18001f5ff  lea     rax, aMoshostWarning; "[MosHost] Warning: tried to Start() whi"...
0x18001f606  mov     qword ptr [rsp+38h+var_18], rax
0x18001f60b  mov     r9, rbx
0x18001f60e  mov     r8d, 33h ; '3'
0x18001f614  lea     rdx, aTransfermonito_0; "TransferMonitor::Start"
0x18001f61b  lea     ecx, [r8-31h]
0x18001f61f  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001f625  xor     ebx, ebx
0x18001f627  test    rdi, rdi
0x18001f62a  jz      short loc_18001F635
0x18001f62c  mov     rcx, rdi; lpCriticalSection
0x18001f62f  call    cs:__imp_LeaveCriticalSection
0x18001f635  mov     eax, ebx
0x18001f637  mov     rbx, [rsp+38h+arg_8]
0x18001f63c  mov     rsi, [rsp+38h+arg_10]
0x18001f641  add     rsp, 30h
0x18001f645  pop     rdi
0x18001f646  retn
```
