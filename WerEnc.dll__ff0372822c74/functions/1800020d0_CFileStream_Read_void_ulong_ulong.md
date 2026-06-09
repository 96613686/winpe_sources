# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x1800020d0`
- end: `0x180002108`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `56`
- prototype: `__int64 __fastcall(HANDLE *this, void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800020d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800020e1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800020e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020eb`

## pseudocode

```c
__int64 __fastcall CFileStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  signed int LastError; // eax

  v4 = 0;
  if ( !ReadFile(this[1], a2, a3, a4, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x1800020d0  push    rbx
0x1800020d2  sub     rsp, 30h
0x1800020d6  mov     rcx, [rcx+8]; hFile
0x1800020da  xor     ebx, ebx
0x1800020dc  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x1800020e1  call    cs:__imp_ReadFile
0x1800020e7  test    eax, eax
0x1800020e9  jnz     short loc_180002100
0x1800020eb  call    cs:__imp_GetLastError
0x1800020f1  mov     ebx, eax
0x1800020f3  test    eax, eax
0x1800020f5  jle     short loc_180002100
0x1800020f7  movzx   ebx, ax
0x1800020fa  or      ebx, 80070000h
0x180002100  mov     eax, ebx
0x180002102  add     rsp, 30h
0x180002106  pop     rbx
0x180002107  retn
```
