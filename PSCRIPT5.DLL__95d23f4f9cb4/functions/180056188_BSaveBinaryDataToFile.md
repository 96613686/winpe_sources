# BSaveBinaryDataToFile

- ea: `0x180056188`
- end: `0x18005623e`
- name: `BSaveBinaryDataToFile`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800564d8`

## callees

- `0x180054518`
- `0x180056188`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180056203`
- `KERNEL32!WriteFile` at `0x180056203`
- `KERNEL32!CreateFileW` at `0x1800561d6`
- `KERNEL32!CreateFileW` at `0x1800561d6`
- `KERNEL32!CloseHandle` at `0x180056224`
- `KERNEL32!CloseHandle` at `0x180056224`
- `KERNEL32!LocalFree` at `0x18005622d`
- `KERNEL32!LocalFree` at `0x18005622d`

## pseudocode

```c
_BOOL8 __fastcall BSaveBinaryDataToFile(__int64 a1, const wchar_t *a2)
{
  BOOL v3; // ebx
  const WCHAR *FilenameWithExtName; // rax
  WCHAR *v5; // rdi
  HANDLE FileW; // rax
  void *v7; // rsi
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  v3 = 0;
  FilenameWithExtName = (const WCHAR *)GenerateFilenameWithExtName(a2);
  v5 = (WCHAR *)FilenameWithExtName;
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
0x180056188  mov     rax, rsp
0x18005618b  push    rbx
0x18005618c  push    rbp
0x18005618d  push    rsi
0x18005618e  push    rdi
0x18005618f  sub     rsp, 48h
0x180056193  mov     rbp, rcx
0x180056196  mov     dword ptr [rax+18h], 0
0x18005619d  mov     rcx, rdx; pszSrc
0x1800561a0  xor     ebx, ebx
0x1800561a2  call    GenerateFilenameWithExtName
0x1800561a7  mov     rdi, rax
0x1800561aa  test    rax, rax
0x1800561ad  jz      loc_180056233
0x1800561b3  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x1800561b8  xor     r9d, r9d; lpSecurityAttributes
0x1800561bb  mov     [rsp+68h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x1800561c3  xor     r8d, r8d; dwShareMode
0x1800561c6  mov     edx, 40000000h; dwDesiredAccess
0x1800561cb  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x1800561d3  mov     rcx, rax; lpFileName
0x1800561d6  call    cs:__imp_CreateFileW
0x1800561dc  mov     rsi, rax
0x1800561df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800561e3  jz      short loc_18005622A
0x1800561e5  mov     r8d, [rbp+410h]; nNumberOfBytesToWrite
0x1800561ec  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800561f4  mov     rdx, [rbp+400h]; lpBuffer
0x1800561fb  mov     rcx, rax; hFile
0x1800561fe  mov     qword ptr [rsp+68h+dwCreationDisposition], rbx; lpOverlapped
0x180056203  call    cs:__imp_WriteFile
0x180056209  test    eax, eax
0x18005620b  jz      short loc_180056221
0x18005620d  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x180056214  cmp     [rbp+410h], eax
0x18005621a  jnz     short loc_180056221
0x18005621c  mov     ebx, 1
0x180056221  mov     rcx, rsi; hObject
0x180056224  call    cs:__imp_CloseHandle
0x18005622a  mov     rcx, rdi; hMem
0x18005622d  call    cs:__imp_LocalFree
0x180056233  mov     eax, ebx
0x180056235  add     rsp, 48h
0x180056239  pop     rdi
0x18005623a  pop     rsi
0x18005623b  pop     rbp
0x18005623c  pop     rbx
0x18005623d  retn
```
