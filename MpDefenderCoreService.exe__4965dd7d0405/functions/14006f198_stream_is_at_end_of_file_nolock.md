# stream_is_at_end_of_file_nolock

- ea: `0x14006f198`
- end: `0x14006f220`
- name: `stream_is_at_end_of_file_nolock`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14006f220`

## callees

- `0x14006f198`
- `0x140073efc`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x14006f1ff`
- `KERNEL32!GetFileSizeEx` at `0x14006f1ff`
- `KERNEL32!SetFilePointerEx` at `0x14006f1e7`
- `KERNEL32!SetFilePointerEx` at `0x14006f1e7`

## pseudocode

```c
bool __fastcall stream_is_at_end_of_file_nolock(__int64 a1)
{
  void *osfhandle; // rax
  void *v3; // rbx
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp+8h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+38h] [rbp+10h] BYREF

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
0x14006f198  push    rbx
0x14006f19a  sub     rsp, 20h
0x14006f19e  mov     edx, [rcx+14h]
0x14006f1a1  nop
0x14006f1a2  shr     edx, 3
0x14006f1a5  test    dl, 1
0x14006f1a8  jz      short loc_14006F1AE
0x14006f1aa  mov     al, 1
0x14006f1ac  jmp     short loc_14006F21A
0x14006f1ae  mov     eax, [rcx+14h]
0x14006f1b1  nop
0x14006f1b2  test    al, 0C0h
0x14006f1b4  jz      short loc_14006F1BF
0x14006f1b6  mov     rax, [rcx+8]
0x14006f1ba  cmp     [rcx], rax
0x14006f1bd  jz      short loc_14006F218
0x14006f1bf  mov     ecx, [rcx+18h]; FileHandle
0x14006f1c2  nop
0x14006f1c3  call    _get_osfhandle
0x14006f1c8  mov     rbx, rax
0x14006f1cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006f1cf  jz      short loc_14006F218
0x14006f1d1  and     qword ptr [rsp+28h+NewFilePointer], 0
0x14006f1d7  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x14006f1dc  mov     r9d, 1; dwMoveMethod
0x14006f1e2  xor     edx, edx; liDistanceToMove
0x14006f1e4  mov     rcx, rax; hFile
0x14006f1e7  call    cs:__imp_SetFilePointerEx
0x14006f1ed  test    eax, eax
0x14006f1ef  jz      short loc_14006F218
0x14006f1f1  and     qword ptr [rsp+28h+FileSize], 0
0x14006f1f7  lea     rdx, [rsp+28h+FileSize]; lpFileSize
0x14006f1fc  mov     rcx, rbx; hFile
0x14006f1ff  call    cs:__imp_GetFileSizeEx
0x14006f205  test    eax, eax
0x14006f207  jz      short loc_14006F218
0x14006f209  mov     rax, qword ptr [rsp+28h+FileSize]
0x14006f20e  cmp     qword ptr [rsp+28h+NewFilePointer], rax
0x14006f213  setz    al
0x14006f216  jmp     short loc_14006F21A
0x14006f218  xor     al, al
0x14006f21a  add     rsp, 20h
0x14006f21e  pop     rbx
0x14006f21f  retn
```
