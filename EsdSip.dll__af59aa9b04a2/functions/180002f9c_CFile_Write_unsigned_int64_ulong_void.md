# CFile::Write(unsigned __int64,ulong,void *)

- ea: `0x180002f9c`
- end: `0x180003019`
- name: `?Write@CFile@@QEBA_N_KKPEAX@Z`
- size: `125`
- prototype: `bool(CFile *__hidden this, unsigned __int64, unsigned int, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001dc0`
- `0x180002210`

## callees

- `0x180002f9c`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180002fe8`
- `KERNEL32!WriteFile` at `0x180002fe8`
- `KERNEL32!SetLastError` at `0x180002ffd`
- `KERNEL32!SetLastError` at `0x180002ffd`
- `KERNEL32!SetFilePointerEx` at `0x180002fbe`
- `KERNEL32!SetFilePointerEx` at `0x180002fbe`

## pseudocode

```c
char __fastcall CFile::Write(HANDLE *this, LARGE_INTEGER a2, DWORD a3, void *a4)
{
  HANDLE v7; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  if ( !SetFilePointerEx(this[1], a2, 0, 0) )
    return 0;
  v7 = this[1];
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v7, a4, a3, &NumberOfBytesWritten, 0) )
    return 0;
  if ( NumberOfBytesWritten != a3 )
  {
    SetLastError(0xDu);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180002f9c  mov     [rsp+arg_8], rbx
0x180002fa1  mov     [rsp+arg_10], rsi
0x180002fa6  push    rdi
0x180002fa7  sub     rsp, 30h
0x180002fab  mov     rsi, r9
0x180002fae  mov     ebx, r8d
0x180002fb1  mov     rdi, rcx
0x180002fb4  xor     r9d, r9d; dwMoveMethod
0x180002fb7  mov     rcx, [rcx+8]; hFile
0x180002fbb  xor     r8d, r8d; lpNewFilePointer
0x180002fbe  call    cs:__imp_SetFilePointerEx
0x180002fc4  test    eax, eax
0x180002fc6  jz      short loc_180003003
0x180002fc8  mov     rcx, [rdi+8]; hFile
0x180002fcc  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002fd1  mov     r8d, ebx; nNumberOfBytesToWrite
0x180002fd4  mov     [rsp+38h+NumberOfBytesWritten], 0
0x180002fdc  mov     rdx, rsi; lpBuffer
0x180002fdf  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180002fe8  call    cs:__imp_WriteFile
0x180002fee  test    eax, eax
0x180002ff0  jz      short loc_180003003
0x180002ff2  cmp     [rsp+38h+NumberOfBytesWritten], ebx
0x180002ff6  jz      short loc_180003015
0x180002ff8  mov     ecx, 0Dh; dwErrCode
0x180002ffd  call    cs:__imp_SetLastError
0x180003003  xor     al, al
0x180003005  mov     rbx, [rsp+38h+arg_8]
0x18000300a  mov     rsi, [rsp+38h+arg_10]
0x18000300f  add     rsp, 30h
0x180003013  pop     rdi
0x180003014  retn
0x180003015  mov     al, 1
0x180003017  jmp     short loc_180003005
```
