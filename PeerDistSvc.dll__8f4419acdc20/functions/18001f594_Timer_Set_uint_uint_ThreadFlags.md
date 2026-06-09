# Timer::Set(uint,uint,ThreadFlags)

- ea: `0x18001f594`
- end: `0x18001f647`
- name: `?Set@Timer@@QEAAXIIVThreadFlags@@@Z`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800bc430`
- `0x1800f4810`

## callees

- `0x180018d3c`
- `0x18001f46c`
- `0x18001f594`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001f627`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001f627`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001f5c3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001f5c3`
- `ntdll!EtwEventActivityIdControl` at `0x18001f5ea`
- `ntdll!EtwEventActivityIdControl` at `0x18001f5ea`

## string_xrefs

- `0x18001f5fa`: `CreateTimerQueue failed`
- `0x18001f631`: `CreateTimerQueueTimer`

## pseudocode

```c
BOOL __fastcall Timer::Set(HANDLE *a1, DWORD a2, __int64 a3, ULONG a4)
{
  HANDLE *v4; // rdi
  void *v8; // rax
  Timer::TimerQueue *v9; // rcx
  void *v10; // rax
  BOOL result; // eax

  v4 = a1 + 3;
  if ( a1[3] )
  {
    v8 = Timer::TimerQueue::Get((Timer::TimerQueue *)a1);
    if ( !v8 )
      goto LABEL_7;
    if ( !DeleteTimerQueueTimer(v8, *v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      SystemError::Throw(L"Timer::CancelEngine");
    *v4 = 0;
  }
  EtwEventActivityIdControl(1, a1 + 1);
  v10 = Timer::TimerQueue::Get(v9);
  if ( !v10 )
LABEL_7:
    SystemError::Throw(L"CreateTimerQueue failed");
  result = CreateTimerQueueTimer(v4, v10, Timer::TimerCallback, a1, a2, 0, a4);
  if ( !result )
    SystemError::Throw(L"CreateTimerQueueTimer");
  return result;
}

```

## disassembly

```asm
0x18001f594  push    rbx
0x18001f596  push    rbp
0x18001f597  push    rsi
0x18001f598  push    rdi
0x18001f599  sub     rsp, 48h
0x18001f59d  lea     rdi, [rcx+18h]
0x18001f5a1  mov     ebx, r9d
0x18001f5a4  cmp     qword ptr [rdi], 0
0x18001f5a8  mov     ebp, edx
0x18001f5aa  mov     rsi, rcx
0x18001f5ad  jz      short loc_18001F5E1
0x18001f5af  call    ?Get@TimerQueue@Timer@@QEAAQEAXXZ; Timer::TimerQueue::Get(void)
0x18001f5b4  test    rax, rax
0x18001f5b7  jz      short loc_18001F5FA
0x18001f5b9  mov     rdx, [rdi]; Timer
0x18001f5bc  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001f5c0  mov     rcx, rax; TimerQueue
0x18001f5c3  call    cs:__imp_DeleteTimerQueueTimer
0x18001f5c9  test    eax, eax
0x18001f5cb  jnz     short loc_18001F5DA
0x18001f5cd  lea     rcx, aTimerCanceleng; "Timer::CancelEngine"
0x18001f5d4  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x18001f5da  mov     qword ptr [rdi], 0
0x18001f5e1  lea     rdx, [rsi+8]
0x18001f5e5  mov     ecx, 1
0x18001f5ea  call    cs:__imp_EtwEventActivityIdControl
0x18001f5f0  call    ?Get@TimerQueue@Timer@@QEAAQEAXXZ; Timer::TimerQueue::Get(void)
0x18001f5f5  test    rax, rax
0x18001f5f8  jnz     short loc_18001F607
0x18001f5fa  lea     rcx, aCreatetimerque_0; "CreateTimerQueue failed"
0x18001f601  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x18001f607  mov     [rsp+68h+Flags], ebx; Flags
0x18001f60b  lea     r8, ?TimerCallback@Timer@@CAXPEAXE@Z; Callback
0x18001f612  mov     [rsp+68h+Period], 0; Period
0x18001f61a  mov     r9, rsi; Parameter
0x18001f61d  mov     rdx, rax; TimerQueue
0x18001f620  mov     [rsp+68h+DueTime], ebp; DueTime
0x18001f624  mov     rcx, rdi; phNewTimer
0x18001f627  call    cs:__imp_CreateTimerQueueTimer
0x18001f62d  test    eax, eax
0x18001f62f  jnz     short loc_18001F63E
0x18001f631  lea     rcx, aCreatetimerque; "CreateTimerQueueTimer"
0x18001f638  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x18001f63e  add     rsp, 48h
0x18001f642  pop     rdi
0x18001f643  pop     rsi
0x18001f644  pop     rbp
0x18001f645  pop     rbx
0x18001f646  retn
```
