# CFile::Read(ulong,void *)

- ea: `0x180002da0`
- end: `0x180002df4`
- name: `?Read@CFile@@QEBA_NKPEAX@Z`
- size: `84`
- prototype: `bool(CFile *__hidden this, unsigned int, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002dfc`
- `0x180002edc`

## callees

- `0x180002da0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180002dcb`
- `KERNEL32!ReadFile` at `0x180002dcb`
- `KERNEL32!SetLastError` at `0x180002de4`
- `KERNEL32!SetLastError` at `0x180002de4`

## pseudocode

```c
char __fastcall CFile::Read(CFile *this, DWORD a2, void *a3)
{
  void *v3; // rcx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  v3 = (void *)*((_QWORD *)this + 1);
  NumberOfBytesRead = 0;
  if ( !ReadFile(v3, a3, a2, &NumberOfBytesRead, 0) )
    return 0;
  if ( NumberOfBytesRead != a2 )
  {
    SetLastError(0xDu);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180002da0  push    rbx
0x180002da2  sub     rsp, 30h
0x180002da6  mov     rcx, [rcx+8]; hFile
0x180002daa  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180002daf  mov     rax, r8
0x180002db2  mov     [rsp+38h+NumberOfBytesRead], 0
0x180002dba  mov     r8d, edx; nNumberOfBytesToRead
0x180002dbd  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180002dc6  mov     ebx, edx
0x180002dc8  mov     rdx, rax; lpBuffer
0x180002dcb  call    cs:__imp_ReadFile
0x180002dd1  test    eax, eax
0x180002dd3  jnz     short loc_180002DD9
0x180002dd5  xor     al, al
0x180002dd7  jmp     short loc_180002DEE
0x180002dd9  cmp     [rsp+38h+NumberOfBytesRead], ebx
0x180002ddd  jz      short loc_180002DEC
0x180002ddf  mov     ecx, 0Dh; dwErrCode
0x180002de4  call    cs:__imp_SetLastError
0x180002dea  jmp     short loc_180002DD5
0x180002dec  mov     al, 1
0x180002dee  add     rsp, 30h
0x180002df2  pop     rbx
0x180002df3  retn
```
