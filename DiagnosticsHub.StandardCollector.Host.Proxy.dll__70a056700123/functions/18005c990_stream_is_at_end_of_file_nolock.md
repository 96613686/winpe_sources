# stream_is_at_end_of_file_nolock

- ea: `0x18005c990`
- end: `0x18005ca18`
- name: `stream_is_at_end_of_file_nolock`
- size: `136`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18005c5f4`
- `0x18005c6c0`
- `0x18005ca18`
- `0x18005cae4`

## callees

- `0x180014618`
- `0x18005c990`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x18005c9f7`
- `KERNEL32!GetFileSizeEx` at `0x18005c9f7`
- `KERNEL32!SetFilePointerEx` at `0x18005c9df`
- `KERNEL32!SetFilePointerEx` at `0x18005c9df`

## pseudocode

```c
bool __fastcall stream_is_at_end_of_file_nolock(__int64 a1)
{
  void *osfhandle; // rax
  void *v3; // rbx
  LARGE_INTEGER FileSize; // [rsp+30h] [rbp+8h] BYREF
  LARGE_INTEGER NewFilePointer; // [rsp+38h] [rbp+10h] BYREF

  if ( (*(_DWORD *)(a1 + 20) & 8) != 0 )
    return 1;
  if ( (*(_DWORD *)(a1 + 20) & 0xC0) != 0 && *(_QWORD *)a1 == *(_QWORD *)(a1 + 8) )
    return 0;
  osfhandle = (void *)get_osfhandle(*(_DWORD *)(a1 + 24));
  v3 = osfhandle;
  if ( osfhandle == (void *)-1LL )
    return 0;
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(osfhandle, 0, &NewFilePointer, 1u) )
    return 0;
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(v3, &FileSize) )
    return 0;
  return NewFilePointer.QuadPart == FileSize.QuadPart;
}

```

## disassembly

```asm
0x18005c990  push    rbx
0x18005c992  sub     rsp, 20h
0x18005c996  mov     edx, [rcx+14h]
0x18005c999  nop
0x18005c99a  shr     edx, 3
0x18005c99d  test    dl, 1
0x18005c9a0  jz      short loc_18005C9A6
0x18005c9a2  mov     al, 1
0x18005c9a4  jmp     short loc_18005CA12
0x18005c9a6  mov     eax, [rcx+14h]
0x18005c9a9  nop
0x18005c9aa  test    al, 0C0h
0x18005c9ac  jz      short loc_18005C9B7
0x18005c9ae  mov     rax, [rcx+8]
0x18005c9b2  cmp     [rcx], rax
0x18005c9b5  jz      short loc_18005CA10
0x18005c9b7  mov     ecx, [rcx+18h]; FileHandle
0x18005c9ba  nop
0x18005c9bb  call    _get_osfhandle
0x18005c9c0  mov     rbx, rax
0x18005c9c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005c9c7  jz      short loc_18005CA10
0x18005c9c9  and     qword ptr [rsp+28h+NewFilePointer], 0
0x18005c9cf  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x18005c9d4  mov     r9d, 1; dwMoveMethod
0x18005c9da  xor     edx, edx; liDistanceToMove
0x18005c9dc  mov     rcx, rax; hFile
0x18005c9df  call    cs:__imp_SetFilePointerEx
0x18005c9e5  test    eax, eax
0x18005c9e7  jz      short loc_18005CA10
0x18005c9e9  and     qword ptr [rsp+28h+FileSize], 0
0x18005c9ef  lea     rdx, [rsp+28h+FileSize]; lpFileSize
0x18005c9f4  mov     rcx, rbx; hFile
0x18005c9f7  call    cs:__imp_GetFileSizeEx
0x18005c9fd  test    eax, eax
0x18005c9ff  jz      short loc_18005CA10
0x18005ca01  mov     rax, qword ptr [rsp+28h+FileSize]
0x18005ca06  cmp     qword ptr [rsp+28h+NewFilePointer], rax
0x18005ca0b  setz    al
0x18005ca0e  jmp     short loc_18005CA12
0x18005ca10  xor     al, al
0x18005ca12  add     rsp, 20h
0x18005ca16  pop     rbx
0x18005ca17  retn
```
