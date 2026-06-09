# TimerQueue::Initialize(void)

- ea: `0x1800226dc`
- end: `0x18002274e`
- name: `?Initialize@TimerQueue@@QEAAJXZ`
- size: `114`
- prototype: `__int64 __fastcall(TimerQueue *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180016d3c`
- `0x18001edb0`
- `0x18001f554`

## callees

- `0x1800226dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226fe`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800226f0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800226f0`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18002272b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18002272b`

## pseudocode

```c
__int64 __fastcall TimerQueue::Initialize(TimerQueue *this)
{
  unsigned int v1; // edi
  HANDLE TimerQueue; // rax
  signed int LastError; // eax

  v1 = 0;
  if ( !*(_QWORD *)this )
  {
    TimerQueue = CreateTimerQueue();
    *(_QWORD *)this = TimerQueue;
    if ( TimerQueue )
    {
      if ( *((_QWORD *)this + 1) != *((_QWORD *)this + 2) )
        __int2c();
    }
    else
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
      return (unsigned int)ZTraceReportOrigination(LastError, "TimerQueue::Initialize", 40, this);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800226dc  mov     [rsp+arg_0], rbx
0x1800226e1  push    rdi
0x1800226e2  sub     rsp, 20h
0x1800226e6  xor     edi, edi
0x1800226e8  mov     rbx, rcx
0x1800226eb  cmp     [rcx], rdi
0x1800226ee  jnz     short loc_180022741
0x1800226f0  call    cs:__imp_CreateTimerQueue
0x1800226f6  mov     [rbx], rax
0x1800226f9  test    rax, rax
0x1800226fc  jnz     short loc_180022735
0x1800226fe  call    cs:__imp_GetLastError
0x180022704  test    eax, eax
0x180022706  jz      short loc_180022714
0x180022708  jle     short loc_180022719
0x18002270a  movzx   eax, ax
0x18002270d  or      eax, 80070000h
0x180022712  jmp     short loc_180022719
0x180022714  mov     eax, 80390004h
0x180022719  mov     r9, rbx
0x18002271c  lea     rdx, aTimerqueueInit; "TimerQueue::Initialize"
0x180022723  mov     r8d, 28h ; '('
0x180022729  mov     ecx, eax
0x18002272b  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180022731  mov     edi, eax
0x180022733  jmp     short loc_180022741
0x180022735  mov     rax, [rbx+10h]
0x180022739  cmp     [rbx+8], rax
0x18002273d  jz      short loc_180022741
0x18002273f  int     2Ch; Windows NT - assertion failure
0x180022741  mov     rbx, [rsp+28h+arg_0]
0x180022746  mov     eax, edi
0x180022748  add     rsp, 20h
0x18002274c  pop     rdi
0x18002274d  retn
```
