# BfspFileExists

- ea: `0x140002b7c`
- end: `0x140002b9f`
- name: `BfspFileExists`
- size: `35`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140009fd4`
- `0x14000b57c`
- `0x14000c8d8`
- `0x14000cc78`
- `0x14000cfc0`
- `0x14000d3c4`
- `0x14000d494`
- `0x14000fca0`

## callees

- `0x140002b7c`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x140002b84`
- `KERNEL32!GetFileAttributesW` at `0x140002b84`

## pseudocode

```c
__int64 __fastcall BfspFileExists(const WCHAR *a1)
{
  unsigned int v1; // ebx
  DWORD FileAttributesW; // eax

  v1 = 0;
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW != -1 )
    return (FileAttributesW & 0x50) == 0;
  return v1;
}

```

## disassembly

```asm
0x140002b7c  push    rbx
0x140002b7e  sub     rsp, 20h
0x140002b82  xor     ebx, ebx
0x140002b84  call    cs:__imp_GetFileAttributesW
0x140002b8a  cmp     eax, 0FFFFFFFFh
0x140002b8d  jz      short loc_140002B97
0x140002b8f  test    al, 50h
0x140002b91  lea     eax, [rbx+1]
0x140002b94  cmovz   ebx, eax
0x140002b97  mov     eax, ebx
0x140002b99  add     rsp, 20h
0x140002b9d  pop     rbx
0x140002b9e  retn
```
