# FileSystemDirectoryNode::QueryFileSystemNodeType(void)

- ea: `0x180010340`
- end: `0x180010355`
- name: `?QueryFileSystemNodeType@FileSystemDirectoryNode@@UEAA?AV?$NamedEnum@W4FileSystemNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x180010340`: `FileSystemNodeType_Directory`

## pseudocode

```c
__int64 __fastcall FileSystemDirectoryNode::QueryFileSystemNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 3;
  *(_QWORD *)(a2 + 8) = L"FileSystemNodeType_Directory";
  return a2;
}

```

## disassembly

```asm
0x180010340  lea     rax, aFilesystemnode; "FileSystemNodeType_Directory"
0x180010347  mov     dword ptr [rdx], 3
0x18001034d  mov     [rdx+8], rax
0x180010351  mov     rax, rdx
0x180010354  retn
```
