# CReaderWriterLock3::WriteLock(void)

- ea: `0x180004de0`
- end: `0x180004e3c`
- name: `?WriteLock@CReaderWriterLock3@@QEAAXXZ`
- size: `92`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `15`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002a30`
- `0x1800037e0`
- `0x1800041c0`
- `0x180004c10`
- `0x180004d90`
- `0x180030058`
- `0x180030498`
- `0x180030890`
- `0x180030b44`
- `0x180030d80`
- `0x18003104c`
- `0x180031314`
- `0x180031478`
- `0x180031cc8`
- `0x180031d50`

## callees

- `0x180004de0`
- `0x180005340`
- `0x18002f194`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e0d`

## pseudocode

```c
void __fastcall CReaderWriterLock3::WriteLock(CReaderWriterLock3 *this)
{
  signed __int32 v2; // ecx

  if ( *((_DWORD *)this + 1)
    || (v2 = *(_DWORD *)this, (_WORD)v2)
    || v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, (v2 + 0x10000) | 0xFFFF, v2) )
  {
    if ( !CReaderWriterLock3::_TryWriteLock2(this) )
      CReaderWriterLock3::_WriteLockSpin(this);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
}

```

## disassembly

```asm
0x180004de0  push    rbx
0x180004de2  sub     rsp, 20h
0x180004de6  mov     eax, [rcx+4]
0x180004de9  mov     rbx, rcx
0x180004dec  test    eax, eax
0x180004dee  jnz     short loc_180004E22
0x180004df0  mov     ecx, [rcx]
0x180004df2  test    cx, cx
0x180004df5  jnz     short loc_180004E22
0x180004df7  lea     edx, [rcx+10000h]
0x180004dfd  mov     eax, ecx
0x180004dff  or      edx, 0FFFFh
0x180004e05  lock cmpxchg [rbx], edx
0x180004e09  cmp     ecx, eax
0x180004e0b  jnz     short loc_180004E22
0x180004e0d  call    cs:__imp_GetCurrentThreadId
0x180004e13  and     eax, 0FFFFFFFCh
0x180004e16  or      eax, 1
0x180004e19  xchg    eax, [rbx+4]
0x180004e1c  add     rsp, 20h
0x180004e20  pop     rbx
0x180004e21  retn
0x180004e22  mov     rcx, rbx; this
0x180004e25  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x180004e2a  test    al, al
0x180004e2c  jnz     short loc_180004E36
0x180004e2e  mov     rcx, rbx; this
0x180004e31  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180004e36  add     rsp, 20h
0x180004e3a  pop     rbx
0x180004e3b  retn
```
