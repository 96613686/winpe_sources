# CGenerate::WriteToFileUnicode(ushort const *)

- ea: `0x14000ae8c`
- end: `0x14000af1c`
- name: `?WriteToFileUnicode@CGenerate@@AEAAJPEBG@Z`
- size: `144`
- prototype: `__int64 __fastcall(HANDLE *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x14000a460`
- `0x14000a614`
- `0x14000c5b0`

## callees

- `0x14000ae8c`

## import_xrefs

- `msvcrt!wcslen` at `0x14000aeb7`
- `msvcrt!wcslen` at `0x14000aeb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aee0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aee0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000aed6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000aed6`

## pseudocode

```c
__int64 __fastcall CGenerate::WriteToFileUnicode(HANDLE *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  DWORD v5; // edi
  BOOL v6; // eax
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  if ( (char *)this[13] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && a2 )
  {
    v4 = 0;
    NumberOfBytesWritten = 0;
    v5 = 2 * wcslen(a2);
    v6 = WriteFile(this[13], a2, v5, &NumberOfBytesWritten, 0);
    try
    {
      if ( v6 )
      {
        if ( v5 != NumberOfBytesWritten )
          v4 = -2147467259;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    catch ( ... )
    {
      NumberOfBytesWritten = -2147418113;
      return (unsigned int)-2147418113;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x14000ae8c  push    rbx
0x14000ae8e  push    rsi
0x14000ae8f  push    rdi
0x14000ae90  push    r14
0x14000ae92  sub     rsp, 38h
0x14000ae96  mov     rsi, rdx
0x14000ae99  mov     r14, rcx
0x14000ae9c  mov     rax, [rcx+68h]
0x14000aea0  dec     rax
0x14000aea3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000aea7  ja      short loc_14000AF0B
0x14000aea9  test    rdx, rdx
0x14000aeac  jz      short loc_14000AF0B
0x14000aeae  xor     ebx, ebx
0x14000aeb0  mov     [rsp+58h+NumberOfBytesWritten], ebx
0x14000aeb4  mov     rcx, rdx; String
0x14000aeb7  call    cs:__imp_wcslen
0x14000aebd  mov     rdi, rax
0x14000aec0  add     edi, edi
0x14000aec2  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x14000aec7  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000aecc  mov     r8d, edi; nNumberOfBytesToWrite
0x14000aecf  mov     rdx, rsi; lpBuffer
0x14000aed2  mov     rcx, [r14+68h]; hFile
0x14000aed6  call    cs:__imp_WriteFile
0x14000aedc  test    eax, eax
0x14000aede  jnz     short loc_14000AEF7
0x14000aee0  call    cs:__imp_GetLastError
0x14000aee6  mov     ebx, eax
0x14000aee8  test    eax, eax
0x14000aeea  jle     short loc_14000AF03
0x14000aeec  movzx   ebx, ax
0x14000aeef  or      ebx, 80070000h
0x14000aef5  jmp     short loc_14000AF03
0x14000aef7  mov     eax, 80004005h
0x14000aefc  cmp     edi, [rsp+58h+NumberOfBytesWritten]
0x14000af00  cmovnz  ebx, eax
0x14000af03  jmp     short loc_14000AF10
0x14000af05  mov     ebx, [rsp+58h+NumberOfBytesWritten]
0x14000af09  jmp     short loc_14000AF10
0x14000af0b  mov     ebx, 80070057h
0x14000af10  mov     eax, ebx
0x14000af12  add     rsp, 38h
0x14000af16  pop     r14
0x14000af18  pop     rdi
0x14000af19  pop     rsi
0x14000af1a  pop     rbx
0x14000af1b  retn
```
