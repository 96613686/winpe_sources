# MapMUIFile

- ea: `0x14008b7e0`
- end: `0x14008b8c4`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x14008b90c`
- `0x14008ba20`

## callees

- `0x14008b7e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14008b823`
- `KERNEL32!CreateFileW` at `0x14008b823`
- `KERNEL32!CloseHandle` at `0x14008b85f`
- `KERNEL32!CloseHandle` at `0x14008b88c`
- `KERNEL32!CloseHandle` at `0x14008b85f`
- `KERNEL32!CloseHandle` at `0x14008b88c`
- `KERNEL32!CreateFileMappingW` at `0x14008b853`
- `KERNEL32!CreateFileMappingW` at `0x14008b853`
- `KERNEL32!LoadLibraryExW` at `0x14008b8af`
- `KERNEL32!LoadLibraryExW` at `0x14008b8af`
- `KERNEL32!MapViewOfFile` at `0x14008b880`
- `KERNEL32!MapViewOfFile` at `0x14008b880`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  HANDLE FileMappingW; // rdi
  unsigned __int64 v6; // rbx

  if ( a1 )
  {
    if ( !a2 )
      return LoadLibraryExW(a1, 0, a3 != 0);
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v4);
      if ( FileMappingW )
      {
        v6 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v6 | 1) & -(__int64)(v6 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14008b7e0  mov     [rsp+arg_0], rbx
0x14008b7e5  push    rdi
0x14008b7e6  sub     rsp, 40h
0x14008b7ea  mov     eax, r8d
0x14008b7ed  test    rcx, rcx
0x14008b7f0  jz      loc_14008B8B7
0x14008b7f6  test    edx, edx
0x14008b7f8  jz      loc_14008B8A4
0x14008b7fe  xor     r9d, r9d; lpSecurityAttributes
0x14008b801  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14008b80a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14008b812  mov     edx, 80000000h; dwDesiredAccess
0x14008b817  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14008b81f  lea     r8d, [r9+5]; dwShareMode
0x14008b823  call    cs:__imp_CreateFileW
0x14008b829  mov     rbx, rax
0x14008b82c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008b830  jz      loc_14008B8B7
0x14008b836  xor     r9d, r9d; dwMaximumSizeHigh
0x14008b839  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x14008b842  xor     edx, edx; lpFileMappingAttributes
0x14008b844  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x14008b84c  mov     rcx, rax; hFile
0x14008b84f  lea     r8d, [r9+8]; flProtect
0x14008b853  call    cs:__imp_CreateFileMappingW
0x14008b859  mov     rcx, rbx; hObject
0x14008b85c  mov     rdi, rax
0x14008b85f  call    cs:__imp_CloseHandle
0x14008b865  test    rdi, rdi
0x14008b868  jz      short loc_14008B8B7
0x14008b86a  xor     r9d, r9d; dwFileOffsetLow
0x14008b86d  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x14008b876  xor     r8d, r8d; dwFileOffsetHigh
0x14008b879  mov     rcx, rdi; hFileMappingObject
0x14008b87c  lea     edx, [r9+1]; dwDesiredAccess
0x14008b880  call    cs:__imp_MapViewOfFile
0x14008b886  mov     rcx, rdi; hObject
0x14008b889  mov     rbx, rax
0x14008b88c  call    cs:__imp_CloseHandle
0x14008b892  mov     rcx, rbx
0x14008b895  or      rcx, 1; lpLibFileName
0x14008b899  neg     rbx
0x14008b89c  sbb     rax, rax
0x14008b89f  and     rax, rcx
0x14008b8a2  jmp     short loc_14008B8B9
0x14008b8a4  xor     r8d, r8d
0x14008b8a7  test    eax, eax
0x14008b8a9  setnz   r8b; dwFlags
0x14008b8ad  xor     edx, edx; hFile
0x14008b8af  call    cs:__imp_LoadLibraryExW
0x14008b8b5  jmp     short loc_14008B8B9
0x14008b8b7  xor     eax, eax
0x14008b8b9  mov     rbx, [rsp+48h+arg_0]
0x14008b8be  add     rsp, 40h
0x14008b8c2  pop     rdi
0x14008b8c3  retn
```
