# IsPEImage

- ea: `0x1800033f4`
- end: `0x1800035ed`
- name: `IsPEImage`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800038cc`

## callees

- `0x180003194`
- `0x1800033f4`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800034c8`
- `KERNEL32!ReadFile` at `0x180003570`
- `KERNEL32!ReadFile` at `0x1800034c8`
- `KERNEL32!ReadFile` at `0x180003570`
- `KERNEL32!CreateFileW` at `0x18000342b`
- `KERNEL32!CreateFileW` at `0x18000342b`
- `KERNEL32!GetLastError` at `0x18000343f`
- `KERNEL32!GetLastError` at `0x180003472`
- `KERNEL32!GetLastError` at `0x1800034d2`
- `KERNEL32!GetLastError` at `0x180003523`
- `KERNEL32!GetLastError` at `0x18000357a`
- `KERNEL32!GetLastError` at `0x18000343f`
- `KERNEL32!GetLastError` at `0x180003472`
- `KERNEL32!GetLastError` at `0x1800034d2`
- `KERNEL32!GetLastError` at `0x180003523`
- `KERNEL32!GetLastError` at `0x18000357a`
- `KERNEL32!CloseHandle` at `0x1800035bd`
- `KERNEL32!CloseHandle` at `0x1800035cc`
- `KERNEL32!CloseHandle` at `0x1800035bd`
- `KERNEL32!CloseHandle` at `0x1800035cc`
- `KERNEL32!SetFilePointer` at `0x180003467`
- `KERNEL32!SetFilePointer` at `0x180003518`
- `KERNEL32!SetFilePointer` at `0x180003467`
- `KERNEL32!SetFilePointer` at `0x180003518`

## pseudocode

```c
signed int __fastcall IsPEImage(const WCHAR *a1, _DWORD *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  void *v5; // rdi
  signed int result; // eax
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  int v11; // [rsp+44h] [rbp-24h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-20h]
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF
  LONG Buffer; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  *a2 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x10000000u, 0);
  v5 = FileW;
  hObject = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    if ( SetFilePointer(FileW, 60, 0, 0) == -1 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      Buffer = 0;
      NumberOfBytesRead = 0;
      if ( ReadFile(v5, &Buffer, 4u, &NumberOfBytesRead, 0) )
      {
        if ( NumberOfBytesRead >= 4 )
        {
          if ( SetFilePointer(v5, Buffer, 0, 0) == -1 )
          {
            v9 = GetLastError();
            v3 = v9;
            if ( v9 > 0 )
              v3 = (unsigned __int16)v9 | 0x80070000;
          }
          else
          {
            v11 = 0;
            NumberOfBytesRead = 0;
            if ( ReadFile(v5, &v11, 4u, &NumberOfBytesRead, 0) )
            {
              if ( NumberOfBytesRead >= 4 )
              {
                if ( v11 == 17744 )
                  *a2 = 1;
              }
              else
              {
                v3 = -2147418113;
              }
            }
            else
            {
              v10 = GetLastError();
              v3 = v10;
              if ( v10 > 0 )
                v3 = (unsigned __int16)v10 | 0x80070000;
            }
          }
        }
        else
        {
          v3 = -2147418113;
        }
      }
      else
      {
        v8 = GetLastError();
        v3 = v8;
        if ( v8 > 0 )
          v3 = (unsigned __int16)v8 | 0x80070000;
      }
    }
    CloseHandle(v5);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800033f4  mov     rax, rsp
0x1800033f7  mov     [rax+10h], rdx
0x1800033fb  mov     [rax+8], rcx
0x1800033ff  push    rbx
0x180003400  push    rsi
0x180003401  push    rdi
0x180003402  sub     rsp, 50h
0x180003406  mov     rsi, rdx
0x180003409  xor     ebx, ebx
0x18000340b  mov     [rdx], ebx
0x18000340d  mov     [rax-38h], rbx
0x180003411  mov     dword ptr [rax-40h], 10000000h
0x180003418  mov     dword ptr [rax-48h], 3
0x18000341f  xor     r9d, r9d; lpSecurityAttributes
0x180003422  mov     edx, 80000000h; dwDesiredAccess
0x180003427  lea     r8d, [rbx+1]; dwShareMode
0x18000342b  call    cs:__imp_CreateFileW
0x180003431  mov     rdi, rax
0x180003434  mov     [rsp+68h+hObject], rax
0x180003439  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000343d  jnz     short loc_18000345A
0x18000343f  call    cs:__imp_GetLastError
0x180003445  test    eax, eax
0x180003447  jle     loc_1800035E5
0x18000344d  movzx   eax, ax
0x180003450  or      eax, 80070000h
0x180003455  jmp     loc_1800035E5
0x18000345a  xor     r9d, r9d; dwMoveMethod
0x18000345d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180003460  lea     edx, [r9+3Ch]; lDistanceToMove
0x180003464  mov     rcx, rdi; hFile
0x180003467  call    cs:__imp_SetFilePointer
0x18000346d  cmp     eax, 0FFFFFFFFh
0x180003470  jnz     short loc_180003490
0x180003472  call    cs:__imp_GetLastError
0x180003478  mov     ebx, eax
0x18000347a  test    eax, eax
0x18000347c  jle     short loc_180003487
0x18000347e  movzx   ebx, ax
0x180003481  or      ebx, 80070000h
0x180003487  mov     [rsp+68h+var_28], ebx
0x18000348b  jmp     loc_1800035BA
0x180003490  mov     [rsp+68h+Buffer], 0
0x18000349b  mov     [rsp+68h+NumberOfBytesRead], 0
0x1800034a6  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800034af  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800034b7  mov     r8d, 4; nNumberOfBytesToRead
0x1800034bd  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x1800034c5  mov     rcx, rdi; hFile
0x1800034c8  call    cs:__imp_ReadFile
0x1800034ce  test    eax, eax
0x1800034d0  jnz     short loc_1800034F0
0x1800034d2  call    cs:__imp_GetLastError
0x1800034d8  mov     ebx, eax
0x1800034da  test    eax, eax
0x1800034dc  jle     short loc_1800034E7
0x1800034de  movzx   ebx, ax
0x1800034e1  or      ebx, 80070000h
0x1800034e7  mov     [rsp+68h+var_28], ebx
0x1800034eb  jmp     loc_1800035BA
0x1800034f0  cmp     [rsp+68h+NumberOfBytesRead], 4
0x1800034f8  jnb     short loc_180003508
0x1800034fa  mov     ebx, 8000FFFFh
0x1800034ff  mov     [rsp+68h+var_28], ebx
0x180003503  jmp     loc_1800035BA
0x180003508  xor     r9d, r9d; dwMoveMethod
0x18000350b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000350e  mov     edx, [rsp+68h+Buffer]; lDistanceToMove
0x180003515  mov     rcx, rdi; hFile
0x180003518  call    cs:__imp_SetFilePointer
0x18000351e  cmp     eax, 0FFFFFFFFh
0x180003521  jnz     short loc_18000353E
0x180003523  call    cs:__imp_GetLastError
0x180003529  mov     ebx, eax
0x18000352b  test    eax, eax
0x18000352d  jle     short loc_180003538
0x18000352f  movzx   ebx, ax
0x180003532  or      ebx, 80070000h
0x180003538  mov     [rsp+68h+var_28], ebx
0x18000353c  jmp     short loc_1800035BA
0x18000353e  mov     [rsp+68h+var_24], 0
0x180003546  mov     [rsp+68h+NumberOfBytesRead], 0
0x180003551  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18000355a  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180003562  mov     r8d, 4; nNumberOfBytesToRead
0x180003568  lea     rdx, [rsp+68h+var_24]; lpBuffer
0x18000356d  mov     rcx, rdi; hFile
0x180003570  call    cs:__imp_ReadFile
0x180003576  test    eax, eax
0x180003578  jnz     short loc_180003595
0x18000357a  call    cs:__imp_GetLastError
0x180003580  mov     ebx, eax
0x180003582  test    eax, eax
0x180003584  jle     short loc_18000358F
0x180003586  movzx   ebx, ax
0x180003589  or      ebx, 80070000h
0x18000358f  mov     [rsp+68h+var_28], ebx
0x180003593  jmp     short loc_1800035BA
0x180003595  cmp     [rsp+68h+NumberOfBytesRead], 4
0x18000359d  jnb     short loc_1800035AA
0x18000359f  mov     ebx, 8000FFFFh
0x1800035a4  mov     [rsp+68h+var_28], ebx
0x1800035a8  jmp     short loc_1800035BA
0x1800035aa  cmp     [rsp+68h+var_24], 4550h
0x1800035b2  jnz     short loc_1800035BA
0x1800035b4  mov     dword ptr [rsi], 1
0x1800035ba  mov     rcx, rdi; hObject
0x1800035bd  call    cs:__imp_CloseHandle
0x1800035c3  mov     eax, ebx
0x1800035c5  jmp     short loc_1800035E5
0x1800035c7  mov     rcx, [rsp+68h+hObject]; hObject
0x1800035cc  call    cs:__imp_CloseHandle
0x1800035d2  mov     rcx, [rsp+68h+arg_0]
0x1800035d7  call    HasExecutableExtension
0x1800035dc  mov     rcx, [rsp+68h+arg_8]
0x1800035e1  mov     [rcx], eax
0x1800035e3  xor     eax, eax
0x1800035e5  add     rsp, 50h
0x1800035e9  pop     rdi
0x1800035ea  pop     rsi
0x1800035eb  pop     rbx
0x1800035ec  retn
0x18000745c  push    rbp
0x18000745e  sub     rsp, 40h
0x180007462  mov     rbp, rdx
0x180007465  mov     rax, [rcx]
0x180007468  xor     ecx, ecx
0x18000746a  cmp     dword ptr [rax], 0C0000006h
0x180007470  setz    cl
0x180007473  mov     eax, ecx
0x180007475  add     rsp, 40h
0x180007479  pop     rbp
0x18000747a  retn
```
