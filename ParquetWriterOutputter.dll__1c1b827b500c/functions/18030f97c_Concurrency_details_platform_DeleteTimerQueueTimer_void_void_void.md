# Concurrency::details::platform::__DeleteTimerQueueTimer(void *,void *,void *)

- ea: `0x18030f97c`
- end: `0x18030f9d9`
- name: `?__DeleteTimerQueueTimer@platform@details@Concurrency@@YAXPEAX00@Z`
- size: `93`
- prototype: `void __fastcall(HANDLE TimerQueue, HANDLE Timer, HANDLE CompletionEvent, void *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18030d9c0`
- `0x18030e630`
- `0x18030e830`
- `0x18030e9e0`
- `0x180316930`

## callees

- `0x18030f97c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18030f9b1`
- `KERNEL32!GetLastError` at `0x18030f9b1`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18030f9a7`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18030f9a7`

## pseudocode

```c
void __fastcall Concurrency::details::platform::__DeleteTimerQueueTimer(
        HANDLE TimerQueue,
        HANDLE Timer,
        HANDLE CompletionEvent,
        void *a4)
{
  int i; // ebx

  for ( i = 16; i > 0; --i )
  {
    if ( DeleteTimerQueueTimer(TimerQueue, Timer, CompletionEvent) )
      break;
    if ( GetLastError() == 997 )
      break;
  }
}

```

## disassembly

```asm
0x18030f97c  mov     [rsp+arg_0], rbx
0x18030f981  mov     [rsp+arg_8], rbp
0x18030f986  mov     [rsp+arg_10], rsi
0x18030f98b  push    rdi
0x18030f98c  sub     rsp, 20h
0x18030f990  mov     rdi, r8
0x18030f993  mov     rsi, rdx
0x18030f996  mov     rbp, rcx
0x18030f999  mov     ebx, 10h
0x18030f99e  mov     r8, rdi; CompletionEvent
0x18030f9a1  mov     rdx, rsi; Timer
0x18030f9a4  mov     rcx, rbp; TimerQueue
0x18030f9a7  call    cs:__imp_DeleteTimerQueueTimer
0x18030f9ad  test    eax, eax
0x18030f9af  jnz     short loc_18030F9C4
0x18030f9b1  call    cs:__imp_GetLastError
0x18030f9b7  cmp     eax, 3E5h
0x18030f9bc  jz      short loc_18030F9C4
0x18030f9be  dec     ebx
0x18030f9c0  test    ebx, ebx
0x18030f9c2  jg      short loc_18030F99E
0x18030f9c4  mov     rbx, [rsp+28h+arg_0]
0x18030f9c9  mov     rbp, [rsp+28h+arg_8]
0x18030f9ce  mov     rsi, [rsp+28h+arg_10]
0x18030f9d3  add     rsp, 20h
0x18030f9d7  pop     rdi
0x18030f9d8  retn
```
