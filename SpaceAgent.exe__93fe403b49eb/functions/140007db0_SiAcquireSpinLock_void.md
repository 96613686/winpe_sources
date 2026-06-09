# SiAcquireSpinLock(void * *)

- ea: `0x140007db0`
- end: `0x140007dde`
- name: `?SiAcquireSpinLock@@YAXPEAPEAX@Z`
- size: `46`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400082e4`
- `0x140008574`

## callees

- `0x140007db0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140007db4`
- `KERNEL32!GetCurrentThreadId` at `0x140007db4`

## pseudocode

```c
void __fastcall SiAcquireSpinLock(void **a1)
{
  signed __int64 CurrentThreadId; // rcx

  CurrentThreadId = GetCurrentThreadId();
  while ( _InterlockedCompareExchange64((volatile signed __int64 *)&Lock, CurrentThreadId, 0) )
  {
    do
      _mm_pause();
    while ( Lock );
  }
}

```

## disassembly

```asm
0x140007db0  sub     rsp, 28h
0x140007db4  call    cs:__imp_GetCurrentThreadId
0x140007dba  mov     ecx, eax
0x140007dbc  jmp     short loc_140007DCC
0x140007dbe  pause
0x140007dc0  mov     rax, cs:?Lock@@3PEAXEA; void * Lock
0x140007dc7  test    rax, rax
0x140007dca  jnz     short loc_140007DBE
0x140007dcc  xor     eax, eax
0x140007dce  lock cmpxchg cs:?Lock@@3PEAXEA, rcx; void * Lock
0x140007dd7  jnz     short loc_140007DBE
0x140007dd9  add     rsp, 28h
0x140007ddd  retn
```
