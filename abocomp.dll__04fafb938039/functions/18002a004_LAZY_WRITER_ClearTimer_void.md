# LAZY_WRITER::ClearTimer(void)

- ea: `0x18002a004`
- end: `0x18002a068`
- name: `?ClearTimer@LAZY_WRITER@@QEAAXXZ`
- size: `100`
- prototype: `void __fastcall(LAZY_WRITER *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dde0`
- `0x18002a070`
- `0x18002a2b0`

## callees

- `0x180001f90`
- `0x18002a004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a032`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002a01b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002a01b`

## pseudocode

```c
void __fastcall LAZY_WRITER::ClearTimer(LAZY_WRITER *this)
{
  void *v1; // rdx
  signed int LastError; // eax

  v1 = (void *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    if ( !DeleteTimerQueueTimer(0, v1, 0) && GetLastError() != 997 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ABO_MAPPER_LOG::WriteLogEntry(
        (HANDLE *)g_pAboLog,
        L"Timer Deletion operation failed with Error = %X",
        (unsigned int)LastError);
    }
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18002a004  push    rbx
0x18002a006  sub     rsp, 20h
0x18002a00a  mov     rdx, [rcx+8]; Timer
0x18002a00e  mov     rbx, rcx
0x18002a011  test    rdx, rdx
0x18002a014  jz      short loc_18002A062
0x18002a016  xor     r8d, r8d; CompletionEvent
0x18002a019  xor     ecx, ecx; TimerQueue
0x18002a01b  call    cs:__imp_DeleteTimerQueueTimer
0x18002a021  test    eax, eax
0x18002a023  jnz     short loc_18002A05A
0x18002a025  call    cs:__imp_GetLastError
0x18002a02b  cmp     eax, 3E5h
0x18002a030  jz      short loc_18002A05A
0x18002a032  call    cs:__imp_GetLastError
0x18002a038  test    eax, eax
0x18002a03a  jle     short loc_18002A044
0x18002a03c  movzx   eax, ax
0x18002a03f  or      eax, 80070000h
0x18002a044  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002a04b  lea     rdx, aTimerDeletionO; "Timer Deletion operation failed with Er"...
0x18002a052  mov     r8d, eax
0x18002a055  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002a05a  mov     qword ptr [rbx+8], 0
0x18002a062  add     rsp, 20h
0x18002a066  pop     rbx
0x18002a067  retn
```
