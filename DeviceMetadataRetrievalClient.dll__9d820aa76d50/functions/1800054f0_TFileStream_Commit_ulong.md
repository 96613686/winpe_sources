# TFileStream::Commit(ulong)

- ea: `0x1800054f0`
- end: `0x1800054f6`
- name: `?Commit@TFileStream@@UEAAJK@Z`
- size: `6`
- prototype: `__int64 __fastcall(TFileStream *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall TFileStream::Commit(TFileStream *this)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800054f0  mov     eax, 80004001h
0x1800054f5  retn
```
