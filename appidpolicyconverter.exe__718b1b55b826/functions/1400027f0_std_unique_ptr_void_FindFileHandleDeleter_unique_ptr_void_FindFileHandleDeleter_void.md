# std::unique_ptr<void *,FindFileHandleDeleter>::~unique_ptr<void *,FindFileHandleDeleter>(void)

- ea: `0x1400027f0`
- end: `0x14000280b`
- name: `??1?$unique_ptr@PEAXUFindFileHandleDeleter@@@std@@QEAA@XZ`
- size: `27`
- prototype: `BOOL __fastcall(HANDLE **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140013cc5`

## callees

- `0x1400027f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400027ff`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400027ff`

## pseudocode

```c
BOOL __fastcall std::unique_ptr<void *,FindFileHandleDeleter>::~unique_ptr<void *,FindFileHandleDeleter>(HANDLE **a1)
{
  HANDLE *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return FindClose(*v1);
  return result;
}

```

## disassembly

```asm
0x1400027f0  sub     rsp, 28h
0x1400027f4  mov     rcx, [rcx]
0x1400027f7  test    rcx, rcx
0x1400027fa  jz      short loc_140002806
0x1400027fc  mov     rcx, [rcx]; hFindFile
0x1400027ff  call    cs:__imp_FindClose
0x140002805  nop
0x140002806  add     rsp, 28h
0x14000280a  retn
```
