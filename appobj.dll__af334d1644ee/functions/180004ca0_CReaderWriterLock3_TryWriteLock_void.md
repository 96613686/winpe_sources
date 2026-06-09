# CReaderWriterLock3::TryWriteLock(void)

- ea: `0x180004ca0`
- end: `0x180004cf3`
- name: `?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ`
- size: `83`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004ca0`
- `0x180005340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ccd`

## pseudocode

```c
char __fastcall CReaderWriterLock3::TryWriteLock(CReaderWriterLock3 *this)
{
  signed __int32 v2; // ecx

  if ( *((_DWORD *)this + 1) )
    return CReaderWriterLock3::_TryWriteLock2(this) != 0;
  v2 = *(_DWORD *)this;
  if ( (_WORD)v2 || v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, (v2 + 0x10000) | 0xFFFF, v2) )
    return CReaderWriterLock3::_TryWriteLock2(this) != 0;
  _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  return 1;
}

```

## disassembly

```asm
0x180004ca0  push    rbx
0x180004ca2  sub     rsp, 20h
0x180004ca6  mov     eax, [rcx+4]
0x180004ca9  mov     rbx, rcx
0x180004cac  test    eax, eax
0x180004cae  jnz     short loc_180004CE0
0x180004cb0  mov     ecx, [rcx]
0x180004cb2  test    cx, cx
0x180004cb5  jnz     short loc_180004CE0
0x180004cb7  lea     edx, [rcx+10000h]
0x180004cbd  mov     eax, ecx
0x180004cbf  or      edx, 0FFFFh
0x180004cc5  lock cmpxchg [rbx], edx
0x180004cc9  cmp     ecx, eax
0x180004ccb  jnz     short loc_180004CE0
0x180004ccd  call    cs:__imp_GetCurrentThreadId
0x180004cd3  and     eax, 0FFFFFFFCh
0x180004cd6  or      eax, 1
0x180004cd9  xchg    eax, [rbx+4]
0x180004cdc  mov     al, 1
0x180004cde  jmp     short loc_180004CED
0x180004ce0  mov     rcx, rbx; this
0x180004ce3  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x180004ce8  test    al, al
0x180004cea  setnz   al
0x180004ced  add     rsp, 20h
0x180004cf1  pop     rbx
0x180004cf2  retn
```
