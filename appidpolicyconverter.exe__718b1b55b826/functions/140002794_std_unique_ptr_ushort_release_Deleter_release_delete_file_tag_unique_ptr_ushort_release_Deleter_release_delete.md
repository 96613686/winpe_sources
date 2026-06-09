# std::unique_ptr<ushort,release::Deleter<release::delete_file_tag>>::~unique_ptr<ushort,release::Deleter<release::delete_file_tag>>(void)

- ea: `0x140002794`
- end: `0x1400027ac`
- name: `??1?$unique_ptr@GU?$Deleter@Udelete_file_tag@release@@@release@@@std@@QEAA@XZ`
- size: `24`
- prototype: `BOOL __fastcall(const WCHAR **)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140013e8e`

## callees

- `0x140002794`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400027a0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400027a0`

## pseudocode

```c
BOOL __fastcall std::unique_ptr<unsigned short,release::Deleter<release::delete_file_tag>>::~unique_ptr<unsigned short,release::Deleter<release::delete_file_tag>>(
        const WCHAR **a1)
{
  const WCHAR *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return DeleteFileW(v1);
  return result;
}

```

## disassembly

```asm
0x140002794  sub     rsp, 28h
0x140002798  mov     rcx, [rcx]; lpFileName
0x14000279b  test    rcx, rcx
0x14000279e  jz      short loc_1400027A7
0x1400027a0  call    cs:__imp_DeleteFileW
0x1400027a6  nop
0x1400027a7  add     rsp, 28h
0x1400027ab  retn
```
