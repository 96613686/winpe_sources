# FileSystemDirectoryContentsEnumerator::Reset(void)

- ea: `0x18001039c`
- end: `0x1800103c1`
- name: `?Reset@FileSystemDirectoryContentsEnumerator@@QEAAXXZ`
- size: `37`
- prototype: `void __fastcall(FileSystemDirectoryContentsEnumerator *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010068`
- `0x180010120`
- `0x1800103d0`

## callees

- `0x18001039c`

## import_xrefs

- `KERNEL32!FindClose` at `0x1800103ae`
- `KERNEL32!FindClose` at `0x1800103ae`

## pseudocode

```c
void __fastcall FileSystemDirectoryContentsEnumerator::Reset(HANDLE *this)
{
  if ( *this != (HANDLE)-1LL )
  {
    FindClose(*this);
    *this = (HANDLE)-1LL;
  }
}

```

## disassembly

```asm
0x18001039c  push    rbx
0x18001039e  sub     rsp, 20h
0x1800103a2  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800103a6  mov     rbx, rcx
0x1800103a9  jz      short loc_1800103BB
0x1800103ab  mov     rcx, [rcx]; hFindFile
0x1800103ae  call    cs:__imp_FindClose
0x1800103b4  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800103bb  add     rsp, 20h
0x1800103bf  pop     rbx
0x1800103c0  retn
```
