# MosStorageEnsureMapDataDirectory(ushort const *,bool)

- ea: `0x180008680`
- end: `0x180008688`
- name: `?MosStorageEnsureMapDataDirectory@@YAJPEBG_N@Z`
- size: `8`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008690`

## pseudocode

```c
__int64 __fastcall MosStorageEnsureMapDataDirectory(const unsigned __int16 *a1, char a2)
{
  return MosStorageEnsureMapDataDirectoryAndKeepFileHandle(a1, a2, 0);
}

```

## disassembly

```asm
0x180008680  xor     r8d, r8d; void **
0x180008683  jmp     ?MosStorageEnsureMapDataDirectoryAndKeepFileHandle@@YAJPEBG_NPEAPEAX@Z; MosStorageEnsureMapDataDirectoryAndKeepFileHandle(ushort const *,bool,void * *)
```
