# TiffOpenFile

- ea: `0x180008c80`
- end: `0x180008f72`
- name: `TiffOpenFile`
- size: `754`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, HANDLE *, unsigned int *, void *, _WORD *lpBuffer)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800069c0`
- `0x180008420`

## callees

- `0x180008c80`
- `0x180009a7c`
- `0x180009aa4`
- `0x180012ad4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008d25`
- `KERNEL32!GetLastError` at `0x180008d62`
- `KERNEL32!GetLastError` at `0x180008e06`
- `KERNEL32!GetLastError` at `0x180008e7d`
- `KERNEL32!GetLastError` at `0x180008ed7`
- `KERNEL32!GetLastError` at `0x180008d25`
- `KERNEL32!GetLastError` at `0x180008d62`
- `KERNEL32!GetLastError` at `0x180008e06`
- `KERNEL32!GetLastError` at `0x180008e7d`
- `KERNEL32!GetLastError` at `0x180008ed7`
- `KERNEL32!SetFilePointer` at `0x180008e73`
- `KERNEL32!SetFilePointer` at `0x180008e73`
- `KERNEL32!SetLastError` at `0x180008f59`
- `KERNEL32!SetLastError` at `0x180008f59`
- `KERNEL32!ReadFile` at `0x180008dfc`
- `KERNEL32!ReadFile` at `0x180008ecd`
- `KERNEL32!ReadFile` at `0x180008dfc`
- `KERNEL32!ReadFile` at `0x180008ecd`
- `KERNEL32!GetFileSize` at `0x180008d4a`
- `KERNEL32!GetFileSize` at `0x180008d4a`
- `KERNEL32!CloseHandle` at `0x180008f41`
- `KERNEL32!CloseHandle` at `0x180008f41`

## pseudocode

```c
__int64 __fastcall TiffOpenFile(LPCWSTR lpFileName, HANDLE *a2, unsigned int *a3, void *a4, _WORD *lpBuffer)
{
  void *File; // rax
  __int64 v10; // rbx
  DWORD v11; // eax
  DWORD FileSize; // eax
  _WORD *v14; // r15
  DWORD LastError; // eax
  DWORD v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // edx
  unsigned int v22; // edi
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+10h] BYREF

  NumberOfBytesRead = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  File = (void *)InternalSafeCreateFile(lpFileName, 0xC0000000, 0, 3u, 0);
  *a2 = File;
  if ( File != (void *)-1LL )
  {
    FileSize = GetFileSize(File, 0);
    v14 = lpBuffer;
    *a3 = FileSize;
    if ( FileSize == -1 )
    {
      LastError = GetLastError();
      v16 = LastError;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v18 = 29;
      goto LABEL_16;
    }
    if ( FileSize <= 8 )
    {
      v16 = 1392;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v20 = 30;
      goto LABEL_46;
    }
    if ( ReadFile(*a2, a4, 8u, &NumberOfBytesRead, 0) )
    {
      if ( *(_WORD *)a4 != 18761 || *((_WORD *)a4 + 1) != 42 || (v21 = *((_DWORD *)a4 + 1), v21 < 8) || v21 > *a3 )
      {
        v16 = 1392;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_47;
        }
        v20 = 32;
LABEL_46:
        WPP_SF_(v19[2], v20, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
        goto LABEL_47;
      }
      if ( SetFilePointer(*a2, v21, 0, 0) == -1 )
      {
        LastError = GetLastError();
        v16 = LastError;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_47;
        }
        v18 = 33;
      }
      else
      {
        if ( ReadFile(*a2, v14, 2u, &NumberOfBytesRead, 0) )
          return 1;
        LastError = GetLastError();
        v16 = LastError;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_47:
          v22 = 0;
          if ( *a2 != (HANDLE)-1LL )
          {
            CloseHandle(*a2);
            *a2 = (HANDLE)-1LL;
          }
          *a3 = 0;
          *v14 = 0;
          SetLastError(v16);
          return v22;
        }
        v18 = 34;
      }
    }
    else
    {
      LastError = GetLastError();
      v16 = LastError;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v18 = 31;
    }
LABEL_16:
    WPP_SF_d(v17[2], v18, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, LastError);
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v11 = GetLastError();
    WPP_SF_d(v10, 28, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x180008c80  mov     rax, rsp
0x180008c83  push    rbx
0x180008c84  push    rbp
0x180008c85  push    rsi
0x180008c86  push    rdi
0x180008c87  push    r12
0x180008c89  push    r13
0x180008c8b  push    r14
0x180008c8d  push    r15
0x180008c8f  sub     rsp, 48h
0x180008c93  mov     rbx, r9
0x180008c96  mov     dword ptr [rax+10h], 0
0x180008c9d  mov     r14, r8
0x180008ca0  mov     rsi, rdx
0x180008ca3  mov     rdi, rcx
0x180008ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cad  lea     r12, WPP_GLOBAL_Control
0x180008cb4  lea     r13, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008cbb  mov     ebp, 2
0x180008cc0  cmp     rcx, r12
0x180008cc3  jz      short loc_180008CE0
0x180008cc5  test    [rcx+1Ch], bpl
0x180008cc9  jz      short loc_180008CE0
0x180008ccb  cmp     byte ptr [rcx+19h], 5
0x180008ccf  jb      short loc_180008CE0
0x180008cd1  mov     rcx, [rcx+10h]
0x180008cd5  lea     edx, [rbp+19h]
0x180008cd8  mov     r8, r13
0x180008cdb  call    WPP_SF_
0x180008ce0  mov     [rsp+88h+var_60], 0; int
0x180008ce8  xor     r8d, r8d; dwShareMode
0x180008ceb  mov     edx, 0C0000000h; dwDesiredAccess
0x180008cf0  mov     dword ptr [rsp+88h+lpOverlapped], 3; DWORD
0x180008cf8  mov     rcx, rdi; lpFileName
0x180008cfb  call    InternalSafeCreateFile
0x180008d00  mov     [rsi], rax
0x180008d03  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008d07  jnz     short loc_180008D45
0x180008d09  mov     rbx, cs:WPP_GLOBAL_Control
0x180008d10  cmp     rbx, r12
0x180008d13  jz      short loc_180008D3E
0x180008d15  test    [rbx+1Ch], bpl
0x180008d19  jz      short loc_180008D3E
0x180008d1b  cmp     [rbx+19h], bpl
0x180008d1f  jb      short loc_180008D3E
0x180008d21  mov     rbx, [rbx+10h]
0x180008d25  call    cs:__imp_GetLastError
0x180008d2b  mov     edx, 1Ch
0x180008d30  mov     r8, r13
0x180008d33  mov     r9d, eax
0x180008d36  mov     rcx, rbx
0x180008d39  call    WPP_SF_d
0x180008d3e  xor     eax, eax
0x180008d40  jmp     loc_180008F61
0x180008d45  xor     edx, edx; lpFileSizeHigh
0x180008d47  mov     rcx, rax; hFile
0x180008d4a  call    cs:__imp_GetFileSize
0x180008d50  mov     r15, [rsp+88h+lpBuffer]
0x180008d58  or      edi, 0FFFFFFFFh
0x180008d5b  mov     [r14], eax
0x180008d5e  cmp     eax, edi
0x180008d60  jnz     short loc_180008DA7
0x180008d62  call    cs:__imp_GetLastError
0x180008d68  mov     ebx, eax
0x180008d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d71  cmp     rcx, r12
0x180008d74  jz      loc_180008F36
0x180008d7a  test    [rcx+1Ch], bpl
0x180008d7e  jz      loc_180008F36
0x180008d84  cmp     [rcx+19h], bpl
0x180008d88  jb      loc_180008F36
0x180008d8e  mov     edx, 1Dh
0x180008d93  mov     rcx, [rcx+10h]
0x180008d97  mov     r9d, eax
0x180008d9a  mov     r8, r13
0x180008d9d  call    WPP_SF_d
0x180008da2  jmp     loc_180008F36
0x180008da7  cmp     eax, 8
0x180008daa  ja      short loc_180008DDF
0x180008dac  mov     ebx, 570h
0x180008db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008db8  cmp     rcx, r12
0x180008dbb  jz      loc_180008F36
0x180008dc1  test    [rcx+1Ch], bpl
0x180008dc5  jz      loc_180008F36
0x180008dcb  cmp     [rcx+19h], bpl
0x180008dcf  jb      loc_180008F36
0x180008dd5  mov     edx, 1Eh
0x180008dda  jmp     loc_180008F2A
0x180008ddf  mov     rcx, [rsi]; hFile
0x180008de2  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180008dea  mov     r8d, 8; nNumberOfBytesToRead
0x180008df0  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x180008df9  mov     rdx, rbx; lpBuffer
0x180008dfc  call    cs:__imp_ReadFile
0x180008e02  test    eax, eax
0x180008e04  jnz     short loc_180008E3C
0x180008e06  call    cs:__imp_GetLastError
0x180008e0c  mov     ebx, eax
0x180008e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e15  cmp     rcx, r12
0x180008e18  jz      loc_180008F36
0x180008e1e  test    [rcx+1Ch], bpl
0x180008e22  jz      loc_180008F36
0x180008e28  cmp     [rcx+19h], bpl
0x180008e2c  jb      loc_180008F36
0x180008e32  mov     edx, 1Fh
0x180008e37  jmp     loc_180008D93
0x180008e3c  mov     eax, 4949h
0x180008e41  cmp     [rbx], ax
0x180008e44  jnz     loc_180008F08
0x180008e4a  cmp     word ptr [rbx+2], 2Ah ; '*'
0x180008e4f  jnz     loc_180008F08
0x180008e55  mov     edx, [rbx+4]; lDistanceToMove
0x180008e58  cmp     edx, 8
0x180008e5b  jb      loc_180008F08
0x180008e61  cmp     edx, [r14]
0x180008e64  ja      loc_180008F08
0x180008e6a  mov     rcx, [rsi]; hFile
0x180008e6d  xor     r9d, r9d; dwMoveMethod
0x180008e70  xor     r8d, r8d; lpDistanceToMoveHigh
0x180008e73  call    cs:__imp_SetFilePointer
0x180008e79  cmp     eax, edi
0x180008e7b  jnz     short loc_180008EB3
0x180008e7d  call    cs:__imp_GetLastError
0x180008e83  mov     ebx, eax
0x180008e85  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e8c  cmp     rcx, r12
0x180008e8f  jz      loc_180008F36
0x180008e95  test    [rcx+1Ch], bpl
0x180008e99  jz      loc_180008F36
0x180008e9f  cmp     [rcx+19h], bpl
0x180008ea3  jb      loc_180008F36
0x180008ea9  mov     edx, 21h ; '!'
0x180008eae  jmp     loc_180008D93
0x180008eb3  mov     rcx, [rsi]; hFile
0x180008eb6  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180008ebe  mov     r8d, ebp; nNumberOfBytesToRead
0x180008ec1  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x180008eca  mov     rdx, r15; lpBuffer
0x180008ecd  call    cs:__imp_ReadFile
0x180008ed3  test    eax, eax
0x180008ed5  jnz     short loc_180008F01
0x180008ed7  call    cs:__imp_GetLastError
0x180008edd  mov     ebx, eax
0x180008edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ee6  cmp     rcx, r12
0x180008ee9  jz      short loc_180008F36
0x180008eeb  test    [rcx+1Ch], bpl
0x180008eef  jz      short loc_180008F36
0x180008ef1  cmp     [rcx+19h], bpl
0x180008ef5  jb      short loc_180008F36
0x180008ef7  mov     edx, 22h ; '"'
0x180008efc  jmp     loc_180008D93
0x180008f01  mov     edi, 1
0x180008f06  jmp     short loc_180008F5F
0x180008f08  mov     ebx, 570h
0x180008f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f14  cmp     rcx, r12
0x180008f17  jz      short loc_180008F36
0x180008f19  test    [rcx+1Ch], bpl
0x180008f1d  jz      short loc_180008F36
0x180008f1f  cmp     [rcx+19h], bpl
0x180008f23  jb      short loc_180008F36
0x180008f25  mov     edx, 20h ; ' '
0x180008f2a  mov     rcx, [rcx+10h]
0x180008f2e  mov     r8, r13
0x180008f31  call    WPP_SF_
0x180008f36  xor     edi, edi
0x180008f38  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180008f3c  jz      short loc_180008F4E
0x180008f3e  mov     rcx, [rsi]; hObject
0x180008f41  call    cs:__imp_CloseHandle
0x180008f47  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180008f4e  xor     ecx, ecx
0x180008f50  mov     [r14], edi
0x180008f53  mov     [r15], cx
0x180008f57  mov     ecx, ebx; dwErrCode
0x180008f59  call    cs:__imp_SetLastError
0x180008f5f  mov     eax, edi
0x180008f61  add     rsp, 48h
0x180008f65  pop     r15
0x180008f67  pop     r14
0x180008f69  pop     r13
0x180008f6b  pop     r12
0x180008f6d  pop     rdi
0x180008f6e  pop     rsi
0x180008f6f  pop     rbp
0x180008f70  pop     rbx
0x180008f71  retn
```
