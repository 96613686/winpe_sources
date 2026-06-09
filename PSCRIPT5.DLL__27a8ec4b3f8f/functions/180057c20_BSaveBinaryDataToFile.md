# BSaveBinaryDataToFile

- ea: `0x180057c20`
- end: `0x180057cef`
- name: `BSaveBinaryDataToFile`
- size: `207`
- prototype: `_BOOL8 __fastcall(__int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800581bc`

## callees

- `0x180055ed4`
- `0x180057c20`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180057ca1`
- `KERNEL32!WriteFile` at `0x180057ca1`
- `KERNEL32!CreateFileW` at `0x180057c6e`
- `KERNEL32!CreateFileW` at `0x180057c6e`
- `KERNEL32!CloseHandle` at `0x180057cc8`
- `KERNEL32!CloseHandle` at `0x180057cc8`
- `KERNEL32!LocalFree` at `0x180057cd7`
- `KERNEL32!LocalFree` at `0x180057cd7`

## pseudocode

```c
_BOOL8 __fastcall BSaveBinaryDataToFile(__int64 a1, const wchar_t *a2)
{
  BOOL v3; // ebx
  wchar_t *FilenameWithExtName; // rax
  wchar_t *v5; // rdi
  HANDLE FileW; // rax
  void *v7; // rsi
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  v3 = 0;
  FilenameWithExtName = GenerateFilenameWithExtName(a2);
  v5 = FilenameWithExtName;
  if ( FilenameWithExtName )
  {
    FileW = CreateFileW(FilenameWithExtName, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
    v7 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      if ( WriteFile(FileW, *(LPCVOID *)(a1 + 1024), *(_DWORD *)(a1 + 1040), &NumberOfBytesWritten, 0) )
        v3 = *(_DWORD *)(a1 + 1040) == NumberOfBytesWritten;
      CloseHandle(v7);
    }
    LocalFree(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180057c20  mov     rax, rsp
0x180057c23  push    rbx
0x180057c24  push    rbp
0x180057c25  push    rsi
0x180057c26  push    rdi
0x180057c27  sub     rsp, 48h
0x180057c2b  mov     rbp, rcx
0x180057c2e  mov     dword ptr [rax+18h], 0
0x180057c35  mov     rcx, rdx; pszSrc
0x180057c38  xor     ebx, ebx
0x180057c3a  call    GenerateFilenameWithExtName
0x180057c3f  mov     rdi, rax
0x180057c42  test    rax, rax
0x180057c45  jz      loc_180057CE3
0x180057c4b  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x180057c50  xor     r9d, r9d; lpSecurityAttributes
0x180057c53  mov     [rsp+68h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180057c5b  xor     r8d, r8d; dwShareMode
0x180057c5e  mov     edx, 40000000h; dwDesiredAccess
0x180057c63  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x180057c6b  mov     rcx, rax; lpFileName
0x180057c6e  call    cs:__imp_CreateFileW
0x180057c75  nop     dword ptr [rax+rax+00h]
0x180057c7a  mov     rsi, rax
0x180057c7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180057c81  jz      short loc_180057CD4
0x180057c83  mov     r8d, [rbp+410h]; nNumberOfBytesToWrite
0x180057c8a  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180057c92  mov     rdx, [rbp+400h]; lpBuffer
0x180057c99  mov     rcx, rax; hFile
0x180057c9c  mov     qword ptr [rsp+68h+dwCreationDisposition], rbx; lpOverlapped
0x180057ca1  call    cs:__imp_WriteFile
0x180057ca8  nop     dword ptr [rax+rax+00h]
0x180057cad  test    eax, eax
0x180057caf  jz      short loc_180057CC5
0x180057cb1  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x180057cb8  cmp     [rbp+410h], eax
0x180057cbe  jnz     short loc_180057CC5
0x180057cc0  mov     ebx, 1
0x180057cc5  mov     rcx, rsi; hObject
0x180057cc8  call    cs:__imp_CloseHandle
0x180057ccf  nop     dword ptr [rax+rax+00h]
0x180057cd4  mov     rcx, rdi; hMem
0x180057cd7  call    cs:__imp_LocalFree
0x180057cde  nop     dword ptr [rax+rax+00h]
0x180057ce3  mov     eax, ebx
0x180057ce5  add     rsp, 48h
0x180057ce9  pop     rdi
0x180057cea  pop     rsi
0x180057ceb  pop     rbp
0x180057cec  pop     rbx
0x180057ced  retn
```
