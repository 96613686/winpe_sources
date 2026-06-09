# operator delete(void *)

- ea: `0x18000e3cc`
- end: `0x18000e3d3`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000ef40`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000e3cc`

## pseudocode

```c
// attributes: thunk
HLOCAL __stdcall operator delete(HLOCAL hMem)
{
  return LocalFree(hMem);
}

```

## disassembly

```asm
0x18000e3cc  jmp     cs:__imp_LocalFree
```
