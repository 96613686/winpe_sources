# GetFileArchitecture(ushort const *,ushort *)

- ea: `0x18005e3f4`
- end: `0x18005e650`
- name: `?GetFileArchitecture@@YAJPEBGPEAG@Z`
- size: `604`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18005e0b0`

## callees

- `0x18005e3f4`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e49e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e49e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e4e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e61b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e61b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005e4d8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005e548`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005e4d8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005e548`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005e48f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005e48f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18005e522`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18005e522`

## pseudocode

```c
__int64 __fastcall GetFileArchitecture(LPCWSTR lpFileName, unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  void *v5; // rsi
  signed int LastError; // eax
  unsigned int v7; // ebx
  signed int v8; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  _WORD Buffer[30]; // [rsp+50h] [rbp-B0h] BYREF
  LONG lDistanceToMove; // [rsp+8Ch] [rbp-74h]
  int v13; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v14; // [rsp+94h] [rbp-6Ch]
  __int16 v15; // [rsp+ECh] [rbp-14h]

  NumberOfBytesRead = 0;
  memset_0(Buffer, 0, 0x40u);
  memset_0(&v13, 0, 0x108u);
  if ( lpFileName && a2 )
  {
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v5 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return v7;
    }
    if ( !ReadFile(FileW, Buffer, 0x40u, &NumberOfBytesRead, 0) )
      goto LABEL_7;
    if ( Buffer[0] != 23117 )
    {
      v7 = -2147024703;
LABEL_41:
      CloseHandle(v5);
      return v7;
    }
    if ( SetFilePointer(v5, lDistanceToMove, 0, 0) == -1 || !ReadFile(v5, &v13, 0x108u, &NumberOfBytesRead, 0) )
    {
LABEL_7:
      v8 = GetLastError();
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      goto LABEL_41;
    }
    if ( v13 == 17744 && (v15 == 1 || v15 == 2 || v15 == 3 || v15 != 5 && v15 != 7) )
    {
      v7 = 0;
      if ( v14 > 0x1C4u )
      {
        switch ( v14 )
        {
          case 0x1F0u:
            *a2 = 3;
            goto LABEL_41;
          case 0x200u:
            *a2 = 6;
            goto LABEL_41;
          case 0x284u:
            *a2 = 7;
            goto LABEL_41;
          case 0x8664u:
            *a2 = 9;
            goto LABEL_41;
          case 0xAA64u:
            *a2 = 12;
            goto LABEL_41;
        }
      }
      else
      {
        if ( v14 == 452 )
        {
          *a2 = 5;
          goto LABEL_41;
        }
        if ( v14 )
        {
          switch ( v14 )
          {
            case 0x14Cu:
              *a2 = 0;
              goto LABEL_41;
            case 0x162u:
            case 0x166u:
              *a2 = 1;
              goto LABEL_41;
            case 0x184u:
              *a2 = 2;
              goto LABEL_41;
          }
        }
      }
    }
    v7 = -2147024588;
    goto LABEL_41;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18005e3f4  mov     [rsp-8+arg_10], rbx
0x18005e3f9  push    rbp
0x18005e3fa  push    rsi
0x18005e3fb  push    rdi
0x18005e3fc  push    r13
0x18005e3fe  push    r15
0x18005e400  lea     rbp, [rsp-0B0h]
0x18005e408  sub     rsp, 1B0h
0x18005e40f  mov     rax, cs:__security_cookie
0x18005e416  xor     rax, rsp
0x18005e419  mov     [rbp+0D0h+var_30], rax
0x18005e420  mov     rdi, rdx
0x18005e423  mov     [rsp+1D0h+NumberOfBytesRead], 0
0x18005e42b  xor     edx, edx; Val
0x18005e42d  mov     rbx, rcx
0x18005e430  lea     rcx, [rsp+1D0h+Buffer]; void *
0x18005e435  lea     r8d, [rdx+40h]; Size
0x18005e439  call    memset_0
0x18005e43e  xor     edx, edx; Val
0x18005e440  lea     rcx, [rbp+0D0h+var_140]; void *
0x18005e444  mov     r8d, 108h; Size
0x18005e44a  call    memset_0
0x18005e44f  test    rbx, rbx
0x18005e452  jz      loc_18005E625
0x18005e458  test    rdi, rdi
0x18005e45b  jz      loc_18005E625
0x18005e461  mov     r15d, 3
0x18005e467  mov     [rsp+1D0h+hTemplateFile], 0; hTemplateFile
0x18005e470  mov     [rsp+1D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005e478  xor     r9d, r9d; lpSecurityAttributes
0x18005e47b  mov     edx, 80000000h; dwDesiredAccess
0x18005e480  mov     [rsp+1D0h+dwCreationDisposition], r15d; dwCreationDisposition
0x18005e485  mov     rcx, rbx; lpFileName
0x18005e488  lea     r13d, [r15-2]
0x18005e48c  mov     r8d, r13d; dwShareMode
0x18005e48f  call    cs:__imp_CreateFileW
0x18005e495  mov     rsi, rax
0x18005e498  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005e49c  jnz     short loc_18005E4BC
0x18005e49e  call    cs:__imp_GetLastError
0x18005e4a4  mov     ebx, eax
0x18005e4a6  test    eax, eax
0x18005e4a8  jle     loc_18005E621
0x18005e4ae  movzx   ebx, ax
0x18005e4b1  or      ebx, 80070000h
0x18005e4b7  jmp     loc_18005E621
0x18005e4bc  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005e4c1  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x18005e4ca  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x18005e4d0  lea     rdx, [rsp+1D0h+Buffer]; lpBuffer
0x18005e4d5  mov     rcx, rsi; hFile
0x18005e4d8  call    cs:__imp_ReadFile
0x18005e4de  test    eax, eax
0x18005e4e0  jnz     short loc_18005E500
0x18005e4e2  call    cs:__imp_GetLastError
0x18005e4e8  mov     ebx, eax
0x18005e4ea  test    eax, eax
0x18005e4ec  jle     loc_18005E618
0x18005e4f2  movzx   ebx, ax
0x18005e4f5  or      ebx, 80070000h
0x18005e4fb  jmp     loc_18005E618
0x18005e500  mov     eax, 5A4Dh
0x18005e505  cmp     [rsp+1D0h+Buffer], ax
0x18005e50a  jz      short loc_18005E516
0x18005e50c  mov     ebx, 800700C1h
0x18005e511  jmp     loc_18005E618
0x18005e516  mov     edx, [rbp+0D0h+lDistanceToMove]; lDistanceToMove
0x18005e519  xor     r9d, r9d; dwMoveMethod
0x18005e51c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18005e51f  mov     rcx, rsi; hFile
0x18005e522  call    cs:__imp_SetFilePointer
0x18005e528  cmp     eax, 0FFFFFFFFh
0x18005e52b  jz      short loc_18005E4E2
0x18005e52d  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005e532  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x18005e53b  mov     r8d, 108h; nNumberOfBytesToRead
0x18005e541  lea     rdx, [rbp+0D0h+var_140]; lpBuffer
0x18005e545  mov     rcx, rsi; hFile
0x18005e548  call    cs:__imp_ReadFile
0x18005e54e  test    eax, eax
0x18005e550  jz      short loc_18005E4E2
0x18005e552  cmp     [rbp+0D0h+var_140], 4550h
0x18005e559  jnz     loc_18005E613
0x18005e55f  movzx   ecx, [rbp+0D0h+var_E4]
0x18005e563  mov     edx, 2
0x18005e568  sub     ecx, r13d
0x18005e56b  jz      short loc_18005E587
0x18005e56d  sub     ecx, r13d
0x18005e570  jz      short loc_18005E587
0x18005e572  sub     ecx, r13d
0x18005e575  jz      short loc_18005E587
0x18005e577  sub     ecx, edx
0x18005e579  jz      loc_18005E613
0x18005e57f  cmp     ecx, edx
0x18005e581  jz      loc_18005E613
0x18005e587  movzx   ecx, [rbp+0D0h+var_13C]
0x18005e58b  xor     ebx, ebx
0x18005e58d  mov     eax, 1C4h
0x18005e592  cmp     ecx, eax
0x18005e594  ja      short loc_18005E5CC
0x18005e596  jz      short loc_18005E5C5
0x18005e598  test    ecx, ecx
0x18005e59a  jz      short loc_18005E613
0x18005e59c  sub     ecx, 14Ch
0x18005e5a2  jz      short loc_18005E5BE
0x18005e5a4  sub     ecx, 16h
0x18005e5a7  jz      short loc_18005E5B8
0x18005e5a9  sub     ecx, 4
0x18005e5ac  jz      short loc_18005E5B8
0x18005e5ae  cmp     ecx, 1Eh
0x18005e5b1  jnz     short loc_18005E613
0x18005e5b3  mov     [rdi], dx
0x18005e5b6  jmp     short loc_18005E618
0x18005e5b8  mov     [rdi], r13w
0x18005e5bc  jmp     short loc_18005E618
0x18005e5be  xor     eax, eax
0x18005e5c0  mov     [rdi], ax
0x18005e5c3  jmp     short loc_18005E618
0x18005e5c5  mov     word ptr [rdi], 5
0x18005e5ca  jmp     short loc_18005E618
0x18005e5cc  sub     ecx, 1F0h
0x18005e5d2  jz      short loc_18005E60D
0x18005e5d4  sub     ecx, 10h
0x18005e5d7  jz      short loc_18005E606
0x18005e5d9  sub     ecx, 84h
0x18005e5df  jz      short loc_18005E5FF
0x18005e5e1  sub     ecx, 83E0h
0x18005e5e7  jz      short loc_18005E5F8
0x18005e5e9  cmp     ecx, 2400h
0x18005e5ef  jnz     short loc_18005E613
0x18005e5f1  mov     word ptr [rdi], 0Ch
0x18005e5f6  jmp     short loc_18005E618
0x18005e5f8  mov     word ptr [rdi], 9
0x18005e5fd  jmp     short loc_18005E618
0x18005e5ff  mov     word ptr [rdi], 7
0x18005e604  jmp     short loc_18005E618
0x18005e606  mov     word ptr [rdi], 6
0x18005e60b  jmp     short loc_18005E618
0x18005e60d  mov     [rdi], r15w
0x18005e611  jmp     short loc_18005E618
0x18005e613  mov     ebx, 80070134h
0x18005e618  mov     rcx, rsi; hObject
0x18005e61b  call    cs:__imp_CloseHandle
0x18005e621  mov     eax, ebx
0x18005e623  jmp     short loc_18005E62A
0x18005e625  mov     eax, 80070057h
0x18005e62a  mov     rcx, [rbp+0D0h+var_30]
0x18005e631  xor     rcx, rsp; StackCookie
0x18005e634  call    __security_check_cookie
0x18005e639  mov     rbx, [rsp+1D0h+arg_10]
0x18005e641  add     rsp, 1B0h
0x18005e648  pop     r15
0x18005e64a  pop     r13
0x18005e64c  pop     rdi
0x18005e64d  pop     rsi
0x18005e64e  pop     rbp
0x18005e64f  retn
```
