# CReaderWriterLock3::_TryWriteLock(long)

- ea: `0x1800053b0`
- end: `0x1800053fd`
- name: `?_TryWriteLock@CReaderWriterLock3@@AEAA_NJ@Z`
- size: `77`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005340`
- `0x1800053b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053d9`

## pseudocode

```c
char __fastcall CReaderWriterLock3::_TryWriteLock(CReaderWriterLock3 *this, int a2)
{
  signed __int32 v3; // ecx

  if ( *((_DWORD *)this + 1) )
    return CReaderWriterLock3::_TryWriteLock2(this);
  v3 = *(_DWORD *)this;
  if ( (_WORD)v3 || v3 != _InterlockedCompareExchange((volatile signed __int32 *)this, (v3 + a2) | 0xFFFF, v3) )
    return CReaderWriterLock3::_TryWriteLock2(this);
  _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  return 1;
}

```

## disassembly

```asm
0x1800053b0  push    rbx
0x1800053b2  sub     rsp, 20h
0x1800053b6  mov     eax, [rcx+4]
0x1800053b9  mov     rbx, rcx
0x1800053bc  test    eax, eax
0x1800053be  jnz     short loc_1800053F0
0x1800053c0  mov     ecx, [rcx]
0x1800053c2  test    cx, cx
0x1800053c5  jnz     short loc_1800053F0
0x1800053c7  add     edx, ecx
0x1800053c9  mov     eax, ecx
0x1800053cb  or      edx, 0FFFFh
0x1800053d1  lock cmpxchg [rbx], edx
0x1800053d5  cmp     ecx, eax
0x1800053d7  jnz     short loc_1800053F0
0x1800053d9  call    cs:__imp_GetCurrentThreadId
0x1800053df  and     eax, 0FFFFFFFCh
0x1800053e2  or      eax, 1
0x1800053e5  xchg    eax, [rbx+4]
0x1800053e8  mov     al, 1
0x1800053ea  add     rsp, 20h
0x1800053ee  pop     rbx
0x1800053ef  retn
0x1800053f0  mov     rcx, rbx; this
0x1800053f3  add     rsp, 20h
0x1800053f7  pop     rbx
0x1800053f8  jmp     ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
```
