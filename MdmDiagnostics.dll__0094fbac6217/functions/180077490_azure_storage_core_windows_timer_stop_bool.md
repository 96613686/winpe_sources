# azure::storage::core::windows_timer::stop(bool)

- ea: `0x180077490`
- end: `0x1800774e2`
- name: `?stop@windows_timer@core@storage@azure@@QEAAX_N@Z`
- size: `82`
- prototype: `void __fastcall(azure::storage::core::windows_timer *__hidden this, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007f200`

## callees

- `0x180077490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800774b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800774b7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800774ad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800774cd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800774ad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800774cd`

## pseudocode

```c
void __fastcall azure::storage::core::windows_timer::stop(HANDLE *this, unsigned __int8 a2)
{
  __int64 v3; // rdi

  v3 = a2 ^ 1LL;
  if ( !DeleteTimerQueueTimer(0, *this, (HANDLE)(v3 - 1)) )
  {
    while ( GetLastError() != 997 && !DeleteTimerQueueTimer(0, *this, (HANDLE)(v3 - 1)) )
      ;
  }
}

```

## disassembly

```asm
0x180077490  mov     [rsp+arg_0], rbx
0x180077495  push    rdi
0x180077496  sub     rsp, 20h
0x18007749a  movzx   edi, dl
0x18007749d  mov     rbx, rcx
0x1800774a0  mov     rdx, [rcx]; Timer
0x1800774a3  xor     rdi, 1
0x1800774a7  xor     ecx, ecx; TimerQueue
0x1800774a9  lea     r8, [rdi-1]; CompletionEvent
0x1800774ad  call    cs:__imp_DeleteTimerQueueTimer
0x1800774b3  test    eax, eax
0x1800774b5  jnz     short loc_1800774D7
0x1800774b7  call    cs:__imp_GetLastError
0x1800774bd  cmp     eax, 3E5h
0x1800774c2  jz      short loc_1800774D7
0x1800774c4  mov     rdx, [rbx]; Timer
0x1800774c7  lea     r8, [rdi-1]; CompletionEvent
0x1800774cb  xor     ecx, ecx; TimerQueue
0x1800774cd  call    cs:__imp_DeleteTimerQueueTimer
0x1800774d3  test    eax, eax
0x1800774d5  jz      short loc_1800774B7
0x1800774d7  mov     rbx, [rsp+28h+arg_0]
0x1800774dc  add     rsp, 20h
0x1800774e0  pop     rdi
0x1800774e1  retn
```
