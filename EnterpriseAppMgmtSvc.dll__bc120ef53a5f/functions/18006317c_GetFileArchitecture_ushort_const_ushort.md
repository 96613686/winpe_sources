# GetFileArchitecture(ushort const *,ushort *)

- ea: `0x18006317c`
- end: `0x180063407`
- name: `?GetFileArchitecture@@YAJPEBGPEAG@Z`
- size: `651`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180062df4`

## callees

- `0x18006317c`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006322c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006327c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006322c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006327c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800633cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800633cb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006326c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800632ee`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006326c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800632ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063217`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063217`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800632c2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800632c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18006317c  mov     [rsp-8+arg_10], rbx
0x180063181  push    rbp
0x180063182  push    rsi
0x180063183  push    rdi
0x180063184  push    r13
0x180063186  push    r15
0x180063188  lea     rbp, [rsp-0B0h]
0x180063190  sub     rsp, 1B0h
0x180063197  mov     rax, cs:__security_cookie
0x18006319e  xor     rax, rsp
0x1800631a1  mov     [rbp+0D0h+var_30], rax
0x1800631a8  mov     rdi, rdx
0x1800631ab  mov     [rsp+1D0h+NumberOfBytesRead], 0
0x1800631b3  xor     edx, edx; Val
0x1800631b5  mov     rbx, rcx
0x1800631b8  lea     rcx, [rsp+1D0h+Buffer]; void *
0x1800631bd  lea     r8d, [rdx+40h]; Size
0x1800631c1  call    memset_0
0x1800631c6  xor     edx, edx; Val
0x1800631c8  lea     rcx, [rbp+0D0h+var_140]; void *
0x1800631cc  mov     r8d, 108h; Size
0x1800631d2  call    memset_0
0x1800631d7  test    rbx, rbx
0x1800631da  jz      loc_1800633DB
0x1800631e0  test    rdi, rdi
0x1800631e3  jz      loc_1800633DB
0x1800631e9  mov     r15d, 3
0x1800631ef  mov     [rsp+1D0h+hTemplateFile], 0; hTemplateFile
0x1800631f8  mov     [rsp+1D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180063200  xor     r9d, r9d; lpSecurityAttributes
0x180063203  mov     edx, 80000000h; dwDesiredAccess
0x180063208  mov     [rsp+1D0h+dwCreationDisposition], r15d; dwCreationDisposition
0x18006320d  mov     rcx, rbx; lpFileName
0x180063210  lea     r13d, [r15-2]
0x180063214  mov     r8d, r13d; dwShareMode
0x180063217  call    cs:__imp_CreateFileW
0x18006321e  nop     dword ptr [rax+rax+00h]
0x180063223  mov     rsi, rax
0x180063226  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006322a  jnz     short loc_180063250
0x18006322c  call    cs:__imp_GetLastError
0x180063233  nop     dword ptr [rax+rax+00h]
0x180063238  mov     ebx, eax
0x18006323a  test    eax, eax
0x18006323c  jle     loc_1800633D7
0x180063242  movzx   ebx, ax
0x180063245  or      ebx, 80070000h
0x18006324b  jmp     loc_1800633D7
0x180063250  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180063255  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x18006325e  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x180063264  lea     rdx, [rsp+1D0h+Buffer]; lpBuffer
0x180063269  mov     rcx, rsi; hFile
0x18006326c  call    cs:__imp_ReadFile
0x180063273  nop     dword ptr [rax+rax+00h]
0x180063278  test    eax, eax
0x18006327a  jnz     short loc_1800632A0
0x18006327c  call    cs:__imp_GetLastError
0x180063283  nop     dword ptr [rax+rax+00h]
0x180063288  mov     ebx, eax
0x18006328a  test    eax, eax
0x18006328c  jle     loc_1800633C8
0x180063292  movzx   ebx, ax
0x180063295  or      ebx, 80070000h
0x18006329b  jmp     loc_1800633C8
0x1800632a0  mov     eax, 5A4Dh
0x1800632a5  cmp     [rsp+1D0h+Buffer], ax
0x1800632aa  jz      short loc_1800632B6
0x1800632ac  mov     ebx, 800700C1h
0x1800632b1  jmp     loc_1800633C8
0x1800632b6  mov     edx, [rbp+0D0h+lDistanceToMove]; lDistanceToMove
0x1800632b9  xor     r9d, r9d; dwMoveMethod
0x1800632bc  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800632bf  mov     rcx, rsi; hFile
0x1800632c2  call    cs:__imp_SetFilePointer
0x1800632c9  nop     dword ptr [rax+rax+00h]
0x1800632ce  cmp     eax, 0FFFFFFFFh
0x1800632d1  jz      short loc_18006327C
0x1800632d3  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800632d8  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x1800632e1  mov     r8d, 108h; nNumberOfBytesToRead
0x1800632e7  lea     rdx, [rbp+0D0h+var_140]; lpBuffer
0x1800632eb  mov     rcx, rsi; hFile
0x1800632ee  call    cs:__imp_ReadFile
0x1800632f5  nop     dword ptr [rax+rax+00h]
0x1800632fa  test    eax, eax
0x1800632fc  jz      loc_18006327C
0x180063302  cmp     [rbp+0D0h+var_140], 4550h
0x180063309  jnz     loc_1800633C3
0x18006330f  movzx   ecx, [rbp+0D0h+var_E4]
0x180063313  mov     edx, 2
0x180063318  sub     ecx, r13d
0x18006331b  jz      short loc_180063337
0x18006331d  sub     ecx, r13d
0x180063320  jz      short loc_180063337
0x180063322  sub     ecx, r13d
0x180063325  jz      short loc_180063337
0x180063327  sub     ecx, edx
0x180063329  jz      loc_1800633C3
0x18006332f  cmp     ecx, edx
0x180063331  jz      loc_1800633C3
0x180063337  movzx   ecx, [rbp+0D0h+var_13C]
0x18006333b  xor     ebx, ebx
0x18006333d  mov     eax, 1C4h
0x180063342  cmp     ecx, eax
0x180063344  ja      short loc_18006337C
0x180063346  jz      short loc_180063375
0x180063348  test    ecx, ecx
0x18006334a  jz      short loc_1800633C3
0x18006334c  sub     ecx, 14Ch
0x180063352  jz      short loc_18006336E
0x180063354  sub     ecx, 16h
0x180063357  jz      short loc_180063368
0x180063359  sub     ecx, 4
0x18006335c  jz      short loc_180063368
0x18006335e  cmp     ecx, 1Eh
0x180063361  jnz     short loc_1800633C3
0x180063363  mov     [rdi], dx
0x180063366  jmp     short loc_1800633C8
0x180063368  mov     [rdi], r13w
0x18006336c  jmp     short loc_1800633C8
0x18006336e  xor     eax, eax
0x180063370  mov     [rdi], ax
0x180063373  jmp     short loc_1800633C8
0x180063375  mov     word ptr [rdi], 5
0x18006337a  jmp     short loc_1800633C8
0x18006337c  sub     ecx, 1F0h
0x180063382  jz      short loc_1800633BD
0x180063384  sub     ecx, 10h
0x180063387  jz      short loc_1800633B6
0x180063389  sub     ecx, 84h
0x18006338f  jz      short loc_1800633AF
0x180063391  sub     ecx, 83E0h
0x180063397  jz      short loc_1800633A8
0x180063399  cmp     ecx, 2400h
0x18006339f  jnz     short loc_1800633C3
0x1800633a1  mov     word ptr [rdi], 0Ch
0x1800633a6  jmp     short loc_1800633C8
0x1800633a8  mov     word ptr [rdi], 9
0x1800633ad  jmp     short loc_1800633C8
0x1800633af  mov     word ptr [rdi], 7
0x1800633b4  jmp     short loc_1800633C8
0x1800633b6  mov     word ptr [rdi], 6
0x1800633bb  jmp     short loc_1800633C8
0x1800633bd  mov     [rdi], r15w
0x1800633c1  jmp     short loc_1800633C8
0x1800633c3  mov     ebx, 80070134h
0x1800633c8  mov     rcx, rsi; hObject
0x1800633cb  call    cs:__imp_CloseHandle
0x1800633d2  nop     dword ptr [rax+rax+00h]
0x1800633d7  mov     eax, ebx
0x1800633d9  jmp     short loc_1800633E0
0x1800633db  mov     eax, 80070057h
0x1800633e0  mov     rcx, [rbp+0D0h+var_30]
0x1800633e7  xor     rcx, rsp; StackCookie
0x1800633ea  call    __security_check_cookie
0x1800633ef  mov     rbx, [rsp+1D0h+arg_10]
0x1800633f7  add     rsp, 1B0h
0x1800633fe  pop     r15
0x180063400  pop     r13
0x180063402  pop     rdi
0x180063403  pop     rsi
0x180063404  pop     rbp
0x180063405  retn
```
