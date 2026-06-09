# CFBFileFormatCheck::VerifyUnusedDataInFileHeader(void)

- ea: `0x180007f64`
- end: `0x180008015`
- name: `?VerifyUnusedDataInFileHeader@CFBFileFormatCheck@@AEAAKXZ`
- size: `177`
- prototype: `unsigned int __fastcall(CFBFileFormatCheck *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007ed8`

## callees

- `0x180007f64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fbc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180007f8f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180007f8f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008004`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008004`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180007fb2`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180007fb2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007fd9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007fd9`

## pseudocode

```c
__int64 __fastcall CFBFileFormatCheck::VerifyUnusedDataInFileHeader(CFBFileFormatCheck *this)
{
  DWORD LastError; // ebx
  DWORD v3; // edi
  _DWORD *v4; // rbp
  unsigned int v5; // edi
  __int64 i; // rcx
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  LastError = 0;
  if ( *((_WORD *)this + 18) == 4 )
  {
    v3 = *((_DWORD *)this + 14) - 512;
    NumberOfBytesRead = 0;
    v4 = LocalAlloc(0x40u, v3);
    if ( v4 )
    {
      if ( SetFilePointerEx(*(HANDLE *)this, (LARGE_INTEGER)512LL, 0, 0)
        && ReadFile(*(HANDLE *)this, v4, v3, &NumberOfBytesRead, 0) )
      {
        if ( NumberOfBytesRead == v3 )
        {
          v5 = v3 >> 2;
          for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
          {
            if ( v4[i] )
              goto LABEL_12;
          }
        }
        else
        {
LABEL_12:
          LastError = 13;
        }
      }
      else
      {
        LastError = GetLastError();
      }
      LocalFree(v4);
    }
    else
    {
      return (DWORD)-2147024882;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180007f64  push    rbx
0x180007f66  push    rbp
0x180007f67  push    rsi
0x180007f68  push    rdi
0x180007f69  sub     rsp, 38h
0x180007f6d  xor     ebx, ebx
0x180007f6f  mov     rsi, rcx
0x180007f72  cmp     word ptr [rcx+24h], 4
0x180007f77  jnz     loc_18000800A
0x180007f7d  mov     edi, [rcx+38h]
0x180007f80  lea     ecx, [rbx+40h]; uFlags
0x180007f83  add     edi, 0FFFFFE00h
0x180007f89  mov     [rsp+58h+NumberOfBytesRead], ebx
0x180007f8d  mov     edx, edi; uBytes
0x180007f8f  call    cs:__imp_LocalAlloc
0x180007f95  mov     rbp, rax
0x180007f98  test    rax, rax
0x180007f9b  jnz     short loc_180007FA4
0x180007f9d  mov     ebx, 8007000Eh
0x180007fa2  jmp     short loc_18000800A
0x180007fa4  mov     rcx, [rsi]; hFile
0x180007fa7  xor     r9d, r9d; dwMoveMethod
0x180007faa  xor     r8d, r8d; lpNewFilePointer
0x180007fad  mov     edx, 200h; liDistanceToMove
0x180007fb2  call    cs:__imp_SetFilePointerEx
0x180007fb8  test    eax, eax
0x180007fba  jnz     short loc_180007FC6
0x180007fbc  call    cs:__imp_GetLastError
0x180007fc2  mov     ebx, eax
0x180007fc4  jmp     short loc_180008001
0x180007fc6  mov     rcx, [rsi]; hFile
0x180007fc9  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180007fce  mov     r8d, edi; nNumberOfBytesToRead
0x180007fd1  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x180007fd6  mov     rdx, rbp; lpBuffer
0x180007fd9  call    cs:__imp_ReadFile
0x180007fdf  test    eax, eax
0x180007fe1  jz      short loc_180007FBC
0x180007fe3  cmp     [rsp+58h+NumberOfBytesRead], edi
0x180007fe7  jnz     short loc_180007FFC
0x180007fe9  shr     edi, 2
0x180007fec  xor     ecx, ecx
0x180007fee  cmp     ecx, edi
0x180007ff0  jnb     short loc_180008001
0x180007ff2  cmp     [rbp+rcx*4+0], ebx
0x180007ff6  jnz     short loc_180007FFC
0x180007ff8  inc     ecx
0x180007ffa  jmp     short loc_180007FEE
0x180007ffc  mov     ebx, 0Dh
0x180008001  mov     rcx, rbp; hMem
0x180008004  call    cs:__imp_LocalFree
0x18000800a  mov     eax, ebx
0x18000800c  add     rsp, 38h
0x180008010  pop     rdi
0x180008011  pop     rsi
0x180008012  pop     rbp
0x180008013  pop     rbx
0x180008014  retn
```
