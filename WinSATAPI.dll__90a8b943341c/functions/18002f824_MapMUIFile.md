# MapMUIFile

- ea: `0x18002f824`
- end: `0x18002f91f`
- name: `MapMUIFile`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180010ac8`
- `0x18002fa04`

## callees

- `0x18002f824`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f8fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f8fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f8a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f8d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f8a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f8d5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002f88f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002f88f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002f8c3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002f8c3`
- `KERNEL32!CreateFileW` at `0x18002f861`
- `KERNEL32!CreateFileW` at `0x18002f861`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  DWORD v3; // ebx
  HANDLE FileW; // rax
  void *v5; // rdi
  HANDLE FileMappingW; // rsi
  unsigned __int64 v7; // rbx

  v3 = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      LOBYTE(v3) = a3 != 0;
      return LoadLibraryExW(a1, 0, v3);
    }
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v5 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v5);
      if ( FileMappingW )
      {
        v7 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v7 | 1) & -(__int64)(v7 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002f824  mov     rax, rsp
0x18002f827  mov     [rax+8], rbx
0x18002f82b  mov     [rax+10h], rsi
0x18002f82f  push    rdi
0x18002f830  sub     rsp, 40h
0x18002f834  xor     ebx, ebx
0x18002f836  test    rcx, rcx
0x18002f839  jz      loc_18002F90C
0x18002f83f  test    edx, edx
0x18002f841  jz      loc_18002F8F3
0x18002f847  mov     [rax-18h], rbx
0x18002f84b  lea     r8d, [rbx+5]; dwShareMode
0x18002f84f  mov     [rax-20h], ebx
0x18002f852  xor     r9d, r9d; lpSecurityAttributes
0x18002f855  mov     edx, 80000000h; dwDesiredAccess
0x18002f85a  mov     dword ptr [rax-28h], 3
0x18002f861  call    cs:__imp_CreateFileW
0x18002f868  nop     dword ptr [rax+rax+00h]
0x18002f86d  mov     rdi, rax
0x18002f870  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f874  jz      loc_18002F90C
0x18002f87a  mov     [rsp+48h+lpName], rbx; lpName
0x18002f87f  lea     r8d, [rbx+8]; flProtect
0x18002f883  xor     r9d, r9d; dwMaximumSizeHigh
0x18002f886  mov     [rsp+48h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x18002f88a  xor     edx, edx; lpFileMappingAttributes
0x18002f88c  mov     rcx, rax; hFile
0x18002f88f  call    cs:__imp_CreateFileMappingW
0x18002f896  nop     dword ptr [rax+rax+00h]
0x18002f89b  mov     rcx, rdi; hObject
0x18002f89e  mov     rsi, rax
0x18002f8a1  call    cs:__imp_CloseHandle
0x18002f8a8  nop     dword ptr [rax+rax+00h]
0x18002f8ad  test    rsi, rsi
0x18002f8b0  jz      short loc_18002F90C
0x18002f8b2  xor     r9d, r9d; dwFileOffsetLow
0x18002f8b5  mov     qword ptr [rsp+48h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x18002f8ba  xor     r8d, r8d; dwFileOffsetHigh
0x18002f8bd  lea     edx, [rbx+1]; dwDesiredAccess
0x18002f8c0  mov     rcx, rsi; hFileMappingObject
0x18002f8c3  call    cs:__imp_MapViewOfFile
0x18002f8ca  nop     dword ptr [rax+rax+00h]
0x18002f8cf  mov     rcx, rsi; hObject
0x18002f8d2  mov     rbx, rax
0x18002f8d5  call    cs:__imp_CloseHandle
0x18002f8dc  nop     dword ptr [rax+rax+00h]
0x18002f8e1  mov     rcx, rbx
0x18002f8e4  or      rcx, 1; lpLibFileName
0x18002f8e8  neg     rbx
0x18002f8eb  sbb     rax, rax
0x18002f8ee  and     rax, rcx
0x18002f8f1  jmp     short loc_18002F90E
0x18002f8f3  test    r8d, r8d
0x18002f8f6  setnz   bl
0x18002f8f9  xor     edx, edx; hFile
0x18002f8fb  mov     r8d, ebx; dwFlags
0x18002f8fe  call    cs:__imp_LoadLibraryExW
0x18002f905  nop     dword ptr [rax+rax+00h]
0x18002f90a  jmp     short loc_18002F90E
0x18002f90c  xor     eax, eax
0x18002f90e  mov     rbx, [rsp+48h+arg_0]
0x18002f913  mov     rsi, [rsp+48h+arg_8]
0x18002f918  add     rsp, 40h
0x18002f91c  pop     rdi
0x18002f91d  retn
```
