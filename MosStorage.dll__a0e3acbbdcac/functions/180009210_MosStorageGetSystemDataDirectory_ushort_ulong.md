# MosStorageGetSystemDataDirectory(ushort *,ulong)

- ea: `0x180009210`
- end: `0x180009215`
- name: `?MosStorageGetSystemDataDirectory@@YAJPEAGK@Z`
- size: `5`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007bd4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall MosStorageGetSystemDataDirectory(unsigned __int16 *a1, size_t a2)
{
  return GetInternalMosCacheDirectory(a1, a2);
}

```

## disassembly

```asm
0x180009210  jmp     GetInternalMosCacheDirectory
```
