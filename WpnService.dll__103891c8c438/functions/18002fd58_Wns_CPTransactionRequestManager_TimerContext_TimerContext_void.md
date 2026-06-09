# Wns::CPTransactionRequestManager::TimerContext::~TimerContext(void)

- ea: `0x18002fd58`
- end: `0x18002fd86`
- name: `??1TimerContext@CPTransactionRequestManager@Wns@@UEAA@XZ`
- size: `46`
- prototype: `void __fastcall(Wns::CPTransactionRequestManager::TimerContext *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ff50`

## callees

- `0x18002fd58`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002fd7b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002fd7b`

## pseudocode

```c
void __fastcall Wns::CPTransactionRequestManager::TimerContext::~TimerContext(
        Wns::CPTransactionRequestManager::TimerContext *this)
{
  void *v1; // rdx

  v1 = (void *)*((_QWORD *)this + 3);
  *(_QWORD *)this = &Wns::CPTransactionRequestManager::TimerContext::`vftable';
  if ( v1 != (void *)-1LL )
    DeleteTimerQueueTimer(*(HANDLE *)(*((_QWORD *)this + 1) + 72LL), v1, 0);
}

```

## disassembly

```asm
0x18002fd58  sub     rsp, 28h
0x18002fd5c  mov     rdx, [rcx+18h]; Timer
0x18002fd60  lea     rax, ??_7TimerContext@CPTransactionRequestManager@Wns@@6B@; const Wns::CPTransactionRequestManager::TimerContext::`vftable'
0x18002fd67  mov     [rcx], rax
0x18002fd6a  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18002fd6e  jz      short loc_18002FD81
0x18002fd70  mov     rcx, [rcx+8]
0x18002fd74  xor     r8d, r8d; CompletionEvent
0x18002fd77  mov     rcx, [rcx+48h]; TimerQueue
0x18002fd7b  call    cs:__imp_DeleteTimerQueueTimer
0x18002fd81  add     rsp, 28h
0x18002fd85  retn
```
