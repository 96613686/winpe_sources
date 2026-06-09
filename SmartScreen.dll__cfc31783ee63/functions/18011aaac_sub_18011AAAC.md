# sub_18011AAAC

- ea: `0x18011aaac`
- end: `0x18011aafe`
- name: `sub_18011AAAC`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1801187c8`

## callees

- `0x18011aaac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011aae2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011aae2`

## pseudocode

```c
__int64 sub_18011AAAC()
{
  char *FileW; // rax
  unsigned int v1; // ebx

  FileW = (char *)hObject;
  v1 = 0;
  if ( hObject == (HANDLE)-2LL )
  {
    FileW = (char *)CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    hObject = FileW;
  }
  LOBYTE(v1) = FileW + 1 != 0;
  return v1;
}

```

## disassembly

```asm
0x18011aaac  push    rbx
0x18011aaae  sub     rsp, 40h
0x18011aab2  mov     rax, cs:hObject
0x18011aab9  xor     ebx, ebx
0x18011aabb  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18011aabf  jnz     short loc_18011AAEF
0x18011aac1  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18011aac6  lea     r8d, [rbx+3]; dwShareMode
0x18011aaca  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18011aace  lea     rcx, FileName; "CONOUT$"
0x18011aad5  xor     r9d, r9d; lpSecurityAttributes
0x18011aad8  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18011aadd  mov     edx, 40000000h; dwDesiredAccess
0x18011aae2  call    cs:CreateFileW
0x18011aae8  mov     cs:hObject, rax
0x18011aaef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011aaf3  setnz   bl
0x18011aaf6  mov     eax, ebx
0x18011aaf8  add     rsp, 40h
0x18011aafc  pop     rbx
0x18011aafd  retn
```
