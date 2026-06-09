# CFileStream::Commit(ulong)

- ea: `0x18000e4b0`
- end: `0x18000e4ce`
- name: `?Commit@CFileStream@@UEAAJK@Z`
- size: `30`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!FlushFileBuffers` at `0x18000e4b8`
- `KERNEL32!FlushFileBuffers` at `0x18000e4b8`

## pseudocode

```c
__int64 __fastcall CFileStream::Commit(HANDLE *this)
{
  return !FlushFileBuffers(this[2]) ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18000e4b0  sub     rsp, 28h
0x18000e4b4  mov     rcx, [rcx+10h]; hFile
0x18000e4b8  call    cs:__imp_FlushFileBuffers
0x18000e4be  neg     eax
0x18000e4c0  sbb     eax, eax
0x18000e4c2  not     eax
0x18000e4c4  and     eax, 80004005h
0x18000e4c9  add     rsp, 28h
0x18000e4cd  retn
```
