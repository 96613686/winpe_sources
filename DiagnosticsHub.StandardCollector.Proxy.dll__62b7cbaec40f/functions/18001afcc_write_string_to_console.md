# write_string_to_console

- ea: `0x18001afcc`
- end: `0x18001b071`
- name: `write_string_to_console`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001b074`

## callees

- `0x180002810`
- `0x18001afcc`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18001b052`
- `KERNEL32!WriteFile` at `0x18001b052`
- `KERNEL32!GetStdHandle` at `0x18001afef`
- `KERNEL32!GetStdHandle` at `0x18001afef`

## pseudocode

```c
int __fastcall write_string_to_console(char *a1)
{
  char *StdHandle; // rax
  void *v3; // r10
  char *v4; // r8
  __int16 v5; // ax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-228h] BYREF
  _BYTE Buffer[500]; // [rsp+40h] [rbp-218h] BYREF
  char v9; // [rsp+234h] [rbp-24h] BYREF

  StdHandle = (char *)GetStdHandle(0xFFFFFFF4);
  v3 = StdHandle;
  if ( (unsigned __int64)(StdHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v4 = Buffer;
    do
    {
      *v4++ = *a1;
      if ( v4 == &v9 )
        break;
      v5 = *(_WORD *)a1;
      a1 += 2;
    }
    while ( v5 );
    Buffer[499] = 0;
    NumberOfBytesWritten = 0;
    LODWORD(StdHandle) = WriteFile(v3, Buffer, (_DWORD)v4 - (unsigned int)Buffer - 1, &NumberOfBytesWritten, 0);
  }
  return (int)StdHandle;
}

```

## disassembly

```asm
0x18001afcc  push    rbx
0x18001afce  sub     rsp, 250h
0x18001afd5  mov     rax, cs:__security_cookie
0x18001afdc  xor     rax, rsp
0x18001afdf  mov     [rsp+258h+var_18], rax
0x18001afe7  mov     rbx, rcx
0x18001afea  mov     ecx, 0FFFFFFF4h; nStdHandle
0x18001afef  call    cs:__imp_GetStdHandle
0x18001aff5  mov     r10, rax
0x18001aff8  lea     rdx, [rax-1]
0x18001affc  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001b000  ja      short loc_18001B058
0x18001b002  lea     r8, [rsp+258h+Buffer]
0x18001b007  xor     edx, edx
0x18001b009  mov     cl, [rbx]
0x18001b00b  lea     rax, [rsp+258h+var_24]
0x18001b013  mov     [r8], cl
0x18001b016  inc     r8
0x18001b019  cmp     r8, rax
0x18001b01c  jz      short loc_18001B02A
0x18001b01e  movzx   eax, word ptr [rbx]
0x18001b021  add     rbx, 2
0x18001b025  test    ax, ax
0x18001b028  jnz     short loc_18001B009
0x18001b02a  lea     rax, [rsp+258h+Buffer]
0x18001b02f  mov     [rsp+258h+var_25], dl
0x18001b036  sub     r8d, eax
0x18001b039  mov     [rsp+258h+NumberOfBytesWritten], edx
0x18001b03d  mov     [rsp+258h+lpOverlapped], rdx; lpOverlapped
0x18001b042  lea     r9, [rsp+258h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b047  dec     r8d; nNumberOfBytesToWrite
0x18001b04a  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x18001b04f  mov     rcx, r10; hFile
0x18001b052  call    cs:__imp_WriteFile
0x18001b058  mov     rcx, [rsp+258h+var_18]
0x18001b060  xor     rcx, rsp; StackCookie
0x18001b063  call    __security_check_cookie
0x18001b068  add     rsp, 250h
0x18001b06f  pop     rbx
0x18001b070  retn
```
