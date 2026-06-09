# CReaderWriterLock3::_TryWriteLock2(void)

- ea: `0x180005340`
- end: `0x18000536c`
- name: `?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ`
- size: `44`
- prototype: `char __fastcall(CReaderWriterLock3 *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ca0`
- `0x180004de0`
- `0x1800053b0`
- `0x18002ecf4`

## callees

- `0x180005340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005349`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005349`

## pseudocode

```c
char __fastcall CReaderWriterLock3::_TryWriteLock2(CReaderWriterLock3 *this)
{
  if ( (*((_DWORD *)this + 1) & 0xFFFFFFFC) != (GetCurrentThreadId() & 0xFFFFFFFC) )
    return 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 1);
  return 1;
}

```

## disassembly

```asm
0x180005340  push    rbx
0x180005342  sub     rsp, 20h
0x180005346  mov     rbx, rcx
0x180005349  call    cs:__imp_GetCurrentThreadId
0x18000534f  mov     edx, [rbx+4]
0x180005352  and     eax, 0FFFFFFFCh
0x180005355  and     edx, 0FFFFFFFCh
0x180005358  cmp     edx, eax
0x18000535a  jnz     short loc_180005364
0x18000535c  lock inc dword ptr [rbx+4]
0x180005360  mov     al, 1
0x180005362  jmp     short loc_180005366
0x180005364  xor     al, al
0x180005366  add     rsp, 20h
0x18000536a  pop     rbx
0x18000536b  retn
```
