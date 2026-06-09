# ORWriteToTempFile

- ea: `0x180030aa8`
- end: `0x180030b89`
- name: `ORWriteToTempFile`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18002c404`

## callees

- `0x18002f1cc`
- `0x180030aa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b34`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180030b24`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180030b24`

## pseudocode

```c
__int64 __fastcall ORWriteToTempFile(__int64 a1, void *a2)
{
  DWORD LastError; // edi
  _DWORD *v5; // rcx
  unsigned int v6; // r15d
  char v7; // bp
  __int64 *v8; // rsi
  DWORD v9; // r14d
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 16) )
      ORUpdateBaseBlock();
    v5 = *(_DWORD **)(a1 + 16);
    if ( v5[10] == -4096 )
    {
      return 0;
    }
    else
    {
      v6 = 0;
      v7 = 0;
      v8 = 0;
      while ( 1 )
      {
        if ( v7 )
        {
          v9 = *((_DWORD *)v8 + 9);
          v5 = (_DWORD *)v8[5];
        }
        else
        {
          v9 = 4096;
        }
        LastError = 0;
        if ( !WriteFile(a2, v5, v9, &NumberOfBytesWritten, 0) )
          LastError = GetLastError();
        if ( LastError )
          break;
        if ( v7 )
        {
          v8 = (__int64 *)*v8;
        }
        else
        {
          v8 = *(__int64 **)(a1 + 80);
          v7 = 1;
        }
        v5 = *(_DWORD **)(a1 + 16);
        v6 += v9;
        if ( v6 >= v5[10] + 4096 )
          return 0;
      }
    }
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x180030aa8  mov     [rsp+arg_8], rbx
0x180030aad  mov     [rsp+arg_10], rbp
0x180030ab2  push    rsi
0x180030ab3  push    rdi
0x180030ab4  push    r12
0x180030ab6  push    r14
0x180030ab8  push    r15
0x180030aba  sub     rsp, 30h
0x180030abe  mov     [rsp+58h+NumberOfBytesWritten], 0
0x180030ac6  mov     r12, rdx
0x180030ac9  mov     rbx, rcx
0x180030acc  test    rcx, rcx
0x180030acf  jnz     short loc_180030AD9
0x180030ad1  lea     edi, [rcx+57h]
0x180030ad4  jmp     loc_180030B6F
0x180030ad9  cmp     qword ptr [rcx+10h], 0
0x180030ade  jz      short loc_180030AE5
0x180030ae0  call    ORUpdateBaseBlock
0x180030ae5  mov     rcx, [rbx+10h]
0x180030ae9  mov     edx, 1000h
0x180030aee  mov     eax, [rcx+28h]
0x180030af1  add     eax, edx
0x180030af3  jz      short loc_180030B6D
0x180030af5  xor     r15d, r15d
0x180030af8  xor     bpl, bpl
0x180030afb  xor     esi, esi
0x180030afd  test    bpl, bpl
0x180030b00  jnz     short loc_180030B07
0x180030b02  mov     r14d, edx
0x180030b05  jmp     short loc_180030B0F
0x180030b07  mov     r14d, [rsi+24h]
0x180030b0b  mov     rcx, [rsi+28h]
0x180030b0f  mov     rdx, rcx; lpBuffer
0x180030b12  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180030b17  xor     edi, edi
0x180030b19  mov     rcx, r12; hFile
0x180030b1c  mov     r8d, r14d; nNumberOfBytesToWrite
0x180030b1f  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x180030b24  call    cs:__imp_WriteFile
0x180030b2b  nop     dword ptr [rax+rax+00h]
0x180030b30  test    eax, eax
0x180030b32  jnz     short loc_180030B42
0x180030b34  call    cs:__imp_GetLastError
0x180030b3b  nop     dword ptr [rax+rax+00h]
0x180030b40  mov     edi, eax
0x180030b42  test    edi, edi
0x180030b44  jnz     short loc_180030B6F
0x180030b46  test    bpl, bpl
0x180030b49  jz      short loc_180030B50
0x180030b4b  mov     rsi, [rsi]
0x180030b4e  jmp     short loc_180030B57
0x180030b50  mov     rsi, [rbx+50h]
0x180030b54  mov     bpl, 1
0x180030b57  mov     rcx, [rbx+10h]
0x180030b5b  mov     edx, 1000h
0x180030b60  add     r15d, r14d
0x180030b63  mov     eax, [rcx+28h]
0x180030b66  add     eax, edx
0x180030b68  cmp     r15d, eax
0x180030b6b  jb      short loc_180030AFD
0x180030b6d  xor     edi, edi
0x180030b6f  mov     rbx, [rsp+58h+arg_8]
0x180030b74  mov     eax, edi
0x180030b76  mov     rbp, [rsp+58h+arg_10]
0x180030b7b  add     rsp, 30h
0x180030b7f  pop     r15
0x180030b81  pop     r14
0x180030b83  pop     r12
0x180030b85  pop     rdi
0x180030b86  pop     rsi
0x180030b87  retn
```
