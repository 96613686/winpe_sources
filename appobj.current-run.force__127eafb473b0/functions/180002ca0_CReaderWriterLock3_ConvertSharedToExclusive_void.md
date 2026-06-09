# CReaderWriterLock3::ConvertSharedToExclusive(void)

- ea: `0x180002ca0`
- end: `0x180002ce5`
- name: `?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ`
- size: `69`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002c50`

## callees

- `0x180002ca0`
- `0x180004290`
- `0x18002f194`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cbb`

## pseudocode

```c
void __fastcall CReaderWriterLock3::ConvertSharedToExclusive(CReaderWriterLock3 *this)
{
  if ( *(_DWORD *)this == 1 && _InterlockedCompareExchange((volatile signed __int32 *)this, 0x1FFFF, 1) == 1 )
  {
    _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
  else
  {
    CReaderWriterLock3::ReadUnlock(this);
    CReaderWriterLock3::_WriteLockSpin(this);
  }
}

```

## disassembly

```asm
0x180002ca0  push    rbx
0x180002ca2  sub     rsp, 20h
0x180002ca6  mov     eax, [rcx]
0x180002ca8  mov     rbx, rcx
0x180002cab  cmp     eax, 1
0x180002cae  jnz     short loc_180002CD0
0x180002cb0  mov     ecx, 1FFFFh
0x180002cb5  lock cmpxchg [rbx], ecx
0x180002cb9  jnz     short loc_180002CD0
0x180002cbb  call    cs:__imp_GetCurrentThreadId
0x180002cc1  and     eax, 0FFFFFFFCh
0x180002cc4  or      eax, 1
0x180002cc7  xchg    eax, [rbx+4]
0x180002cca  add     rsp, 20h
0x180002cce  pop     rbx
0x180002ccf  retn
0x180002cd0  mov     rcx, rbx; this
0x180002cd3  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180002cd8  mov     rcx, rbx; this
0x180002cdb  add     rsp, 20h
0x180002cdf  pop     rbx
0x180002ce0  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
```
