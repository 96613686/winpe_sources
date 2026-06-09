# CReaderWriterLock3::TryConvertSharedToExclusive(void)

- ea: `0x180004ab0`
- end: `0x180004ae6`
- name: `?TryConvertSharedToExclusive@CReaderWriterLock3@@QEAA_NXZ`
- size: `54`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004acb`

## pseudocode

```c
char __fastcall CReaderWriterLock3::TryConvertSharedToExclusive(CReaderWriterLock3 *this)
{
  if ( *(_DWORD *)this != 1 || _InterlockedCompareExchange((volatile signed __int32 *)this, 0x1FFFF, 1) != 1 )
    return 0;
  _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  return 1;
}

```

## disassembly

```asm
0x180004ab0  push    rbx
0x180004ab2  sub     rsp, 20h
0x180004ab6  mov     eax, [rcx]
0x180004ab8  mov     rbx, rcx
0x180004abb  cmp     eax, 1
0x180004abe  jnz     short loc_180004ADE
0x180004ac0  mov     ecx, 1FFFFh
0x180004ac5  lock cmpxchg [rbx], ecx
0x180004ac9  jnz     short loc_180004ADE
0x180004acb  call    cs:__imp_GetCurrentThreadId
0x180004ad1  and     eax, 0FFFFFFFCh
0x180004ad4  or      eax, 1
0x180004ad7  xchg    eax, [rbx+4]
0x180004ada  mov     al, 1
0x180004adc  jmp     short loc_180004AE0
0x180004ade  xor     al, al
0x180004ae0  add     rsp, 20h
0x180004ae4  pop     rbx
0x180004ae5  retn
```
