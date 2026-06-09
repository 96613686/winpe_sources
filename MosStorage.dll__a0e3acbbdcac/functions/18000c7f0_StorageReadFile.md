# StorageReadFile

- ea: `0x18000c7f0`
- end: `0x18000c808`
- name: `StorageReadFile`
- size: `24`
- prototype: `BOOL __fastcall(void *, void *, DWORD, DWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c7fd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c7fd`

## pseudocode

```c
BOOL __fastcall StorageReadFile(void *a1, void *a2, DWORD a3, DWORD *a4)
{
  return ReadFile(a1, a2, a3, a4, 0);
}

```

## disassembly

```asm
0x18000c7f0  sub     rsp, 38h
0x18000c7f4  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000c7fd  call    cs:__imp_ReadFile
0x18000c803  add     rsp, 38h
0x18000c807  retn
```
