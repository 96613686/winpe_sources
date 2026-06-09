# write_string_to_console

- ea: `0x18001a86c`
- end: `0x18001a911`
- name: `write_string_to_console`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001a914`

## callees

- `0x18001a86c`
- `0x180032370`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18001a8f2`
- `KERNEL32!WriteFile` at `0x18001a8f2`
- `KERNEL32!GetStdHandle` at `0x18001a88f`
- `KERNEL32!GetStdHandle` at `0x18001a88f`

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
0x18001a86c  push    rbx
0x18001a86e  sub     rsp, 250h
0x18001a875  mov     rax, cs:__security_cookie
0x18001a87c  xor     rax, rsp
0x18001a87f  mov     [rsp+258h+var_18], rax
0x18001a887  mov     rbx, rcx
0x18001a88a  mov     ecx, 0FFFFFFF4h; nStdHandle
0x18001a88f  call    cs:__imp_GetStdHandle
0x18001a895  mov     r10, rax
0x18001a898  lea     rdx, [rax-1]
0x18001a89c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001a8a0  ja      short loc_18001A8F8
0x18001a8a2  lea     r8, [rsp+258h+Buffer]
0x18001a8a7  xor     edx, edx
0x18001a8a9  mov     cl, [rbx]
0x18001a8ab  lea     rax, [rsp+258h+var_24]
0x18001a8b3  mov     [r8], cl
0x18001a8b6  inc     r8
0x18001a8b9  cmp     r8, rax
0x18001a8bc  jz      short loc_18001A8CA
0x18001a8be  movzx   eax, word ptr [rbx]
0x18001a8c1  add     rbx, 2
0x18001a8c5  test    ax, ax
0x18001a8c8  jnz     short loc_18001A8A9
0x18001a8ca  lea     rax, [rsp+258h+Buffer]
0x18001a8cf  mov     [rsp+258h+var_25], dl
0x18001a8d6  sub     r8d, eax
0x18001a8d9  mov     [rsp+258h+NumberOfBytesWritten], edx
0x18001a8dd  mov     [rsp+258h+lpOverlapped], rdx; lpOverlapped
0x18001a8e2  lea     r9, [rsp+258h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001a8e7  dec     r8d; nNumberOfBytesToWrite
0x18001a8ea  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x18001a8ef  mov     rcx, r10; hFile
0x18001a8f2  call    cs:__imp_WriteFile
0x18001a8f8  mov     rcx, [rsp+258h+var_18]
0x18001a900  xor     rcx, rsp; StackCookie
0x18001a903  call    __security_check_cookie
0x18001a908  add     rsp, 250h
0x18001a90f  pop     rbx
0x18001a910  retn
```
