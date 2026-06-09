# TimerQueue::Uninitialize(void)

- ea: `0x180022884`
- end: `0x1800228b4`
- name: `?Uninitialize@TimerQueue@@QEAAXXZ`
- size: `48`
- prototype: `void __fastcall(TimerQueue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d870`
- `0x18001eec4`
- `0x18001f650`
- `0x1800225f8`

## callees

- `0x180022884`
- `0x1800228bc`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180022899`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180022899`

## pseudocode

```c
void __fastcall TimerQueue::Uninitialize(TimerQueue *this)
{
  void *v2; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    DeleteTimerQueueEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *(_QWORD *)this = 0;
  }
  std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::clear((__int64 *)this + 1);
}

```

## disassembly

```asm
0x180022884  push    rbx
0x180022886  sub     rsp, 20h
0x18002288a  mov     rbx, rcx
0x18002288d  mov     rcx, [rcx]; TimerQueue
0x180022890  test    rcx, rcx
0x180022893  jz      short loc_1800228A6
0x180022895  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180022899  call    cs:__imp_DeleteTimerQueueEx
0x18002289f  mov     qword ptr [rbx], 0
0x1800228a6  lea     rcx, [rbx+8]
0x1800228aa  add     rsp, 20h
0x1800228ae  pop     rbx
0x1800228af  jmp     ?clear@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::clear(void)
```
