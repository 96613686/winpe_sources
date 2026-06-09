# stream_is_at_end_of_file_nolock

- ea: `0x18005cc70`
- end: `0x18005ccf8`
- name: `stream_is_at_end_of_file_nolock`
- size: `136`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18005c8d4`
- `0x18005c9a0`
- `0x18005ccf8`
- `0x18005cdc4`

## callees

- `0x180014d78`
- `0x18005cc70`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x18005ccd7`
- `KERNEL32!GetFileSizeEx` at `0x18005ccd7`
- `KERNEL32!SetFilePointerEx` at `0x18005ccbf`
- `KERNEL32!SetFilePointerEx` at `0x18005ccbf`

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
0x18005cc70  push    rbx
0x18005cc72  sub     rsp, 20h
0x18005cc76  mov     edx, [rcx+14h]
0x18005cc79  nop
0x18005cc7a  shr     edx, 3
0x18005cc7d  test    dl, 1
0x18005cc80  jz      short loc_18005CC86
0x18005cc82  mov     al, 1
0x18005cc84  jmp     short loc_18005CCF2
0x18005cc86  mov     eax, [rcx+14h]
0x18005cc89  nop
0x18005cc8a  test    al, 0C0h
0x18005cc8c  jz      short loc_18005CC97
0x18005cc8e  mov     rax, [rcx+8]
0x18005cc92  cmp     [rcx], rax
0x18005cc95  jz      short loc_18005CCF0
0x18005cc97  mov     ecx, [rcx+18h]; FileHandle
0x18005cc9a  nop
0x18005cc9b  call    _get_osfhandle
0x18005cca0  mov     rbx, rax
0x18005cca3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005cca7  jz      short loc_18005CCF0
0x18005cca9  and     qword ptr [rsp+28h+NewFilePointer], 0
0x18005ccaf  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x18005ccb4  mov     r9d, 1; dwMoveMethod
0x18005ccba  xor     edx, edx; liDistanceToMove
0x18005ccbc  mov     rcx, rax; hFile
0x18005ccbf  call    cs:__imp_SetFilePointerEx
0x18005ccc5  test    eax, eax
0x18005ccc7  jz      short loc_18005CCF0
0x18005ccc9  and     qword ptr [rsp+28h+FileSize], 0
0x18005cccf  lea     rdx, [rsp+28h+FileSize]; lpFileSize
0x18005ccd4  mov     rcx, rbx; hFile
0x18005ccd7  call    cs:__imp_GetFileSizeEx
0x18005ccdd  test    eax, eax
0x18005ccdf  jz      short loc_18005CCF0
0x18005cce1  mov     rax, qword ptr [rsp+28h+FileSize]
0x18005cce6  cmp     qword ptr [rsp+28h+NewFilePointer], rax
0x18005cceb  setz    al
0x18005ccee  jmp     short loc_18005CCF2
0x18005ccf0  xor     al, al
0x18005ccf2  add     rsp, 20h
0x18005ccf6  pop     rbx
0x18005ccf7  retn
```
