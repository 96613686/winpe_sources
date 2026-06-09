# TimerQueue::CancelAll(void)

- ea: `0x180022658`
- end: `0x1800226d5`
- name: `?CancelAll@TimerQueue@@QEAAJXZ`
- size: `125`
- prototype: `__int64 __fastcall(TimerQueue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b79c`
- `0x18001d224`

## callees

- `0x180022658`
- `0x1800228bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022685`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002267b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002267b`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800226b2`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800226b2`

## pseudocode

```c
__int64 __fastcall TimerQueue::CancelAll(TimerQueue *this)
{
  HANDLE **v1; // rbp
  HANDLE **i; // rbx
  signed int LastError; // eax

  v1 = (HANDLE **)*((_QWORD *)this + 2);
  for ( i = (HANDLE **)*((_QWORD *)this + 1); i != v1; ++i )
  {
    if ( !DeleteTimerQueueTimer(*(HANDLE *)this, **i, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      ZTraceReportIgnore(LastError, "TimerQueue::CancelAll", 101, this);
    }
  }
  std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::clear((char *)this + 8);
  return 0;
}

```

## disassembly

```asm
0x180022658  push    rbx
0x18002265a  push    rbp
0x18002265b  push    rsi
0x18002265c  push    rdi
0x18002265d  sub     rsp, 28h
0x180022661  mov     rbp, [rcx+10h]
0x180022665  mov     rsi, rcx
0x180022668  mov     rbx, [rcx+8]
0x18002266c  jmp     short loc_1800226BC
0x18002266e  mov     rdx, [rbx]
0x180022671  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180022675  mov     rcx, [rsi]; TimerQueue
0x180022678  mov     rdx, [rdx]; Timer
0x18002267b  call    cs:__imp_DeleteTimerQueueTimer
0x180022681  test    eax, eax
0x180022683  jnz     short loc_1800226B8
0x180022685  call    cs:__imp_GetLastError
0x18002268b  test    eax, eax
0x18002268d  jz      short loc_18002269B
0x18002268f  jle     short loc_1800226A0
0x180022691  movzx   eax, ax
0x180022694  or      eax, 80070000h
0x180022699  jmp     short loc_1800226A0
0x18002269b  mov     eax, 80390004h
0x1800226a0  mov     r9, rsi
0x1800226a3  lea     rdx, aTimerqueueCanc; "TimerQueue::CancelAll"
0x1800226aa  mov     r8d, 65h ; 'e'
0x1800226b0  mov     ecx, eax
0x1800226b2  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800226b8  add     rbx, 8
0x1800226bc  cmp     rbx, rbp
0x1800226bf  jnz     short loc_18002266E
0x1800226c1  lea     rcx, [rsi+8]
0x1800226c5  call    ?clear@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::clear(void)
0x1800226ca  xor     eax, eax
0x1800226cc  add     rsp, 28h
0x1800226d0  pop     rdi
0x1800226d1  pop     rsi
0x1800226d2  pop     rbp
0x1800226d3  pop     rbx
0x1800226d4  retn
```
