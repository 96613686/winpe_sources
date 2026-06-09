# StorageWriteFile

- ea: `0x18000c810`
- end: `0x18000c828`
- name: `StorageWriteFile`
- size: `24`
- prototype: `BOOL __fastcall(void *, const void *, DWORD, DWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c81d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c81d`

## pseudocode

```c
BOOL __fastcall StorageWriteFile(void *a1, const void *a2, DWORD a3, DWORD *a4)
{
  return WriteFile(a1, a2, a3, a4, 0);
}

```

## disassembly

```asm
0x18000c810  sub     rsp, 38h
0x18000c814  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000c81d  call    cs:__imp_WriteFile
0x18000c823  add     rsp, 38h
0x18000c827  retn
```
