# CReaderWriterLock3::IsWriteLocked(void)

- ea: `0x180003c90`
- end: `0x180003caf`
- name: `?IsWriteLocked@CReaderWriterLock3@@QEBA_NXZ`
- size: `31`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c70`
- `0x180003d00`
- `0x180003d30`
- `0x1800041c0`
- `0x180004c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c99`

## pseudocode

```c
bool __fastcall CReaderWriterLock3::IsWriteLocked(CReaderWriterLock3 *this)
{
  int v1; // ebx

  v1 = *((_DWORD *)this + 1);
  return ((v1 ^ GetCurrentThreadId()) & 0xFFFFFFFC) == 0;
}

```

## disassembly

```asm
0x180003c90  push    rbx
0x180003c92  sub     rsp, 20h
0x180003c96  mov     ebx, [rcx+4]
0x180003c99  call    cs:__imp_GetCurrentThreadId
0x180003c9f  xor     eax, ebx
0x180003ca1  test    eax, 0FFFFFFFCh
0x180003ca6  setz    al
0x180003ca9  add     rsp, 20h
0x180003cad  pop     rbx
0x180003cae  retn
```
