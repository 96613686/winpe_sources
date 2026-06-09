# BdeCfgpCopyBootBlock(ushort const *,ushort const *)

- ea: `0x1800084a4`
- end: `0x1800086f2`
- name: `?BdeCfgpCopyBootBlock@@YAJPEBG0@Z`
- size: `590`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007bd0`

## callees

- `0x1800084a4`
- `0x180008b00`
- `0x18000eb40`
- `0x180013582`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18000864e`
- `KERNEL32!SetFilePointer` at `0x18000864e`
- `KERNEL32!WriteFile` at `0x180008673`
- `KERNEL32!WriteFile` at `0x180008673`
- `KERNEL32!VirtualFree` at `0x1800086c6`
- `KERNEL32!VirtualFree` at `0x1800086d9`
- `KERNEL32!VirtualFree` at `0x1800086c6`
- `KERNEL32!VirtualFree` at `0x1800086d9`
- `KERNEL32!GetLastError` at `0x1800084fb`
- `KERNEL32!GetLastError` at `0x180008687`
- `KERNEL32!GetLastError` at `0x1800084fb`
- `KERNEL32!GetLastError` at `0x180008687`
- `KERNEL32!CreateFileW` at `0x1800084ec`
- `KERNEL32!CreateFileW` at `0x180008539`
- `KERNEL32!CreateFileW` at `0x1800084ec`
- `KERNEL32!CreateFileW` at `0x180008539`
- `KERNEL32!CloseHandle` at `0x18000869f`
- `KERNEL32!CloseHandle` at `0x1800086ae`
- `KERNEL32!CloseHandle` at `0x18000869f`
- `KERNEL32!CloseHandle` at `0x1800086ae`
- `KERNEL32!VirtualAlloc` at `0x180008595`
- `KERNEL32!VirtualAlloc` at `0x1800085be`
- `KERNEL32!VirtualAlloc` at `0x180008595`
- `KERNEL32!VirtualAlloc` at `0x1800085be`
- `KERNEL32!ReadFile` at `0x1800085e6`
- `KERNEL32!ReadFile` at `0x18000861c`
- `KERNEL32!ReadFile` at `0x1800085e6`
- `KERNEL32!ReadFile` at `0x18000861c`

## pseudocode

```c
__int64 __fastcall BdeCfgpCopyBootBlock(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HANDLE FileW; // r14
  signed int LastError; // eax
  unsigned int v5; // ebx
  char *v6; // rsi
  char *v7; // rbp
  HANDLE v8; // rax
  void *v9; // rdi
  signed int v10; // eax
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp+20h] BYREF

  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x20000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v5;
  }
  v6 = 0;
  v7 = 0;
  v8 = CreateFileW(a2, 0xC0000000, 3u, 0, 3u, 0x20000000u, 0);
  v9 = v8;
  if ( v8 == (HANDLE)-1LL )
    goto LABEL_18;
  if ( (int)BdeCfgpDeviceIoControl(v8, 0x90018u) < 0 )
    BdeCfgLogWarning(0x80A00037);
  v5 = BdeCfgpDeviceIoControl(v9, 0x90020u);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_20;
  v7 = (char *)VirtualAlloc(0, 0x2000u, 0x3000u, 4u);
  if ( v7 && (v6 = (char *)VirtualAlloc(0, 0x2000u, 0x3000u, 4u)) != 0 )
  {
    if ( !ReadFile(FileW, v7, 0x2000u, &NumberOfBytesRead, 0)
      || NumberOfBytesRead != 0x2000
      || !ReadFile(v9, v6, 0x2000u, &NumberOfBytesRead, 0)
      || NumberOfBytesRead != 0x2000
      || (memcpy_0(v6 + 84, v7 + 84, 0x1DACu), SetFilePointer(v9, 0, 0, 0) == -1)
      || !WriteFile(v9, v6, 0x2000u, &NumberOfBytesWritten, 0)
      || NumberOfBytesWritten != 0x2000 )
    {
LABEL_18:
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
    }
  }
  else
  {
    v5 = -2147024882;
  }
LABEL_20:
  CloseHandle(FileW);
  if ( v9 != (void *)-1LL )
    CloseHandle(v9);
  if ( v7 )
    VirtualFree(v7, 0, 0x8000u);
  if ( v6 )
    VirtualFree(v6, 0, 0x8000u);
  return v5;
}

```

## disassembly

```asm
0x1800084a4  mov     rax, rsp
0x1800084a7  mov     [rax+8], rbx
0x1800084ab  push    rbp
0x1800084ac  push    rsi
0x1800084ad  push    rdi
0x1800084ae  push    r12
0x1800084b0  push    r14
0x1800084b2  sub     rsp, 40h
0x1800084b6  mov     qword ptr [rax-38h], 0
0x1800084be  mov     edi, 3
0x1800084c3  mov     rbx, rdx
0x1800084c6  mov     dword ptr [rax+18h], 0
0x1800084cd  mov     r12d, 20000000h
0x1800084d3  mov     dword ptr [rax+20h], 0
0x1800084da  mov     [rax-40h], r12d
0x1800084de  mov     r8d, edi; dwShareMode
0x1800084e1  xor     r9d, r9d; lpSecurityAttributes
0x1800084e4  mov     [rax-48h], edi
0x1800084e7  mov     edx, 80000000h; dwDesiredAccess
0x1800084ec  call    cs:__imp_CreateFileW
0x1800084f2  mov     r14, rax
0x1800084f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800084f9  jnz     short loc_180008519
0x1800084fb  call    cs:__imp_GetLastError
0x180008501  mov     ebx, eax
0x180008503  test    eax, eax
0x180008505  jle     loc_1800086DF
0x18000850b  movzx   ebx, ax
0x18000850e  or      ebx, 80070000h
0x180008514  jmp     loc_1800086DF
0x180008519  xor     esi, esi
0x18000851b  xor     r9d, r9d; lpSecurityAttributes
0x18000851e  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x180008523  mov     r8d, edi; dwShareMode
0x180008526  mov     [rsp+68h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000852b  mov     edx, 0C0000000h; dwDesiredAccess
0x180008530  mov     rcx, rbx; lpFileName
0x180008533  mov     [rsp+68h+dwCreationDisposition], edi; dwCreationDisposition
0x180008537  xor     ebp, ebp
0x180008539  call    cs:__imp_CreateFileW
0x18000853f  mov     rdi, rax
0x180008542  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008546  jz      loc_180008687
0x18000854c  mov     edx, 90018h; unsigned int
0x180008551  mov     rcx, rax; void *
0x180008554  call    ?BdeCfgpDeviceIoControl@@YAJPEAXK@Z; BdeCfgpDeviceIoControl(void *,ulong)
0x180008559  test    eax, eax
0x18000855b  jns     short loc_180008567
0x18000855d  mov     ecx, 80A00037h; dwMessageId
0x180008562  call    BdeCfgLogWarning
0x180008567  mov     edx, 90020h; unsigned int
0x18000856c  mov     rcx, rdi; void *
0x18000856f  call    ?BdeCfgpDeviceIoControl@@YAJPEAXK@Z; BdeCfgpDeviceIoControl(void *,ulong)
0x180008574  mov     ebx, eax
0x180008576  test    eax, eax
0x180008578  js      loc_18000869C
0x18000857e  mov     r12d, 2000h
0x180008584  mov     r9d, 4; flProtect
0x18000858a  mov     edx, r12d; dwSize
0x18000858d  mov     r8d, 3000h; flAllocationType
0x180008593  xor     ecx, ecx; lpAddress
0x180008595  call    cs:__imp_VirtualAlloc
0x18000859b  mov     rbp, rax
0x18000859e  test    rax, rax
0x1800085a1  jnz     short loc_1800085AD
0x1800085a3  mov     ebx, 8007000Eh
0x1800085a8  jmp     loc_18000869C
0x1800085ad  mov     r9d, 4; flProtect
0x1800085b3  mov     r8d, 3000h; flAllocationType
0x1800085b9  mov     rdx, r12; dwSize
0x1800085bc  xor     ecx, ecx; lpAddress
0x1800085be  call    cs:__imp_VirtualAlloc
0x1800085c4  mov     rsi, rax
0x1800085c7  test    rax, rax
0x1800085ca  jz      short loc_1800085A3
0x1800085cc  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800085d4  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x1800085dd  mov     r8d, r12d; nNumberOfBytesToRead
0x1800085e0  mov     rdx, rbp; lpBuffer
0x1800085e3  mov     rcx, r14; hFile
0x1800085e6  call    cs:__imp_ReadFile
0x1800085ec  test    eax, eax
0x1800085ee  jz      loc_180008687
0x1800085f4  cmp     [rsp+68h+NumberOfBytesRead], r12d
0x1800085fc  jnz     loc_180008687
0x180008602  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000860a  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x180008613  mov     r8d, r12d; nNumberOfBytesToRead
0x180008616  mov     rdx, rsi; lpBuffer
0x180008619  mov     rcx, rdi; hFile
0x18000861c  call    cs:__imp_ReadFile
0x180008622  test    eax, eax
0x180008624  jz      short loc_180008687
0x180008626  cmp     [rsp+68h+NumberOfBytesRead], r12d
0x18000862e  jnz     short loc_180008687
0x180008630  lea     rdx, [rbp+54h]; Src
0x180008634  mov     r8d, 1DACh; Size
0x18000863a  lea     rcx, [rsi+54h]; void *
0x18000863e  call    memcpy_0
0x180008643  xor     r9d, r9d; dwMoveMethod
0x180008646  xor     r8d, r8d; lpDistanceToMoveHigh
0x180008649  xor     edx, edx; lDistanceToMove
0x18000864b  mov     rcx, rdi; hFile
0x18000864e  call    cs:__imp_SetFilePointer
0x180008654  cmp     eax, 0FFFFFFFFh
0x180008657  jz      short loc_180008687
0x180008659  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008661  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18000866a  mov     r8d, r12d; nNumberOfBytesToWrite
0x18000866d  mov     rdx, rsi; lpBuffer
0x180008670  mov     rcx, rdi; hFile
0x180008673  call    cs:__imp_WriteFile
0x180008679  test    eax, eax
0x18000867b  jz      short loc_180008687
0x18000867d  cmp     [rsp+68h+NumberOfBytesWritten], r12d
0x180008685  jz      short loc_18000869C
0x180008687  call    cs:__imp_GetLastError
0x18000868d  mov     ebx, eax
0x18000868f  test    eax, eax
0x180008691  jle     short loc_18000869C
0x180008693  movzx   ebx, ax
0x180008696  or      ebx, 80070000h
0x18000869c  mov     rcx, r14; hObject
0x18000869f  call    cs:__imp_CloseHandle
0x1800086a5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800086a9  jz      short loc_1800086B4
0x1800086ab  mov     rcx, rdi; hObject
0x1800086ae  call    cs:__imp_CloseHandle
0x1800086b4  mov     edi, 8000h
0x1800086b9  test    rbp, rbp
0x1800086bc  jz      short loc_1800086CC
0x1800086be  mov     r8d, edi; dwFreeType
0x1800086c1  xor     edx, edx; dwSize
0x1800086c3  mov     rcx, rbp; lpAddress
0x1800086c6  call    cs:__imp_VirtualFree
0x1800086cc  test    rsi, rsi
0x1800086cf  jz      short loc_1800086DF
0x1800086d1  mov     r8d, edi; dwFreeType
0x1800086d4  xor     edx, edx; dwSize
0x1800086d6  mov     rcx, rsi; lpAddress
0x1800086d9  call    cs:__imp_VirtualFree
0x1800086df  mov     eax, ebx
0x1800086e1  mov     rbx, [rsp+68h+arg_0]
0x1800086e6  add     rsp, 40h
0x1800086ea  pop     r14
0x1800086ec  pop     r12
0x1800086ee  pop     rdi
0x1800086ef  pop     rsi
0x1800086f0  pop     rbp
0x1800086f1  retn
```
