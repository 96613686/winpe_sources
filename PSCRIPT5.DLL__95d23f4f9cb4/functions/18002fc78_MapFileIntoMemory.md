# MapFileIntoMemory

- ea: `0x18002fc78`
- end: `0x18002fd79`
- name: `MapFileIntoMemory`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18005b53c`

## callees

- `0x18002fc78`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18002fd2c`
- `KERNEL32!MapViewOfFile` at `0x18002fd2c`
- `KERNEL32!CreateFileMappingW` at `0x18002fd08`
- `KERNEL32!CreateFileMappingW` at `0x18002fd08`
- `KERNEL32!GetFileSize` at `0x18002fcde`
- `KERNEL32!GetFileSize` at `0x18002fcde`
- `KERNEL32!CreateFileW` at `0x18002fcc5`
- `KERNEL32!CreateFileW` at `0x18002fcc5`
- `KERNEL32!CloseHandle` at `0x18002fd38`
- `KERNEL32!CloseHandle` at `0x18002fd4d`
- `KERNEL32!CloseHandle` at `0x18002fd38`
- `KERNEL32!CloseHandle` at `0x18002fd4d`

## pseudocode

```c
__int64 __fastcall MapFileIntoMemory(const WCHAR *a1, __int64 a2, DWORD *a3, HANDLE *a4)
{
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  void *v10; // rsi

  if ( !a4 )
  {
LABEL_10:
    if ( a2 )
      *(_QWORD *)a2 = 0;
    return *(_QWORD *)a2;
  }
  if ( !a2 )
    goto LABEL_8;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  *a4 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_8;
  if ( a3 )
  {
    FileSize = GetFileSize(FileW, 0);
    *a3 = FileSize;
    if ( FileSize == -1 )
      goto LABEL_8;
  }
  FileMappingW = CreateFileMappingW(*a4, 0, 2u, 0, 0, 0);
  v10 = FileMappingW;
  if ( !FileMappingW || (*(_QWORD *)a2 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v10), !*(_QWORD *)a2) )
  {
LABEL_8:
    if ( *a4 != (HANDLE)-1LL )
    {
      CloseHandle(*a4);
      *a4 = (HANDLE)-1LL;
    }
    goto LABEL_10;
  }
  return *(_QWORD *)a2;
}

```

## disassembly

```asm
0x18002fc78  mov     rax, rsp
0x18002fc7b  mov     [rax+8], rbx
0x18002fc7f  mov     [rax+10h], rsi
0x18002fc83  push    rdi
0x18002fc84  sub     rsp, 40h
0x18002fc88  mov     rdi, r9
0x18002fc8b  mov     rsi, r8
0x18002fc8e  mov     rbx, rdx
0x18002fc91  test    r9, r9
0x18002fc94  jz      loc_18002FD5A
0x18002fc9a  test    rdx, rdx
0x18002fc9d  jz      loc_18002FD44
0x18002fca3  mov     qword ptr [rax-18h], 0
0x18002fcab  xor     r9d, r9d; lpSecurityAttributes
0x18002fcae  mov     dword ptr [rax-20h], 100080h
0x18002fcb5  mov     edx, 80000000h; dwDesiredAccess
0x18002fcba  mov     dword ptr [rax-28h], 3
0x18002fcc1  lea     r8d, [r9+1]; dwShareMode
0x18002fcc5  call    cs:__imp_CreateFileW
0x18002fccb  mov     [rdi], rax
0x18002fcce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fcd2  jz      short loc_18002FD44
0x18002fcd4  test    rsi, rsi
0x18002fcd7  jz      short loc_18002FCEB
0x18002fcd9  xor     edx, edx; lpFileSizeHigh
0x18002fcdb  mov     rcx, rax; hFile
0x18002fcde  call    cs:__imp_GetFileSize
0x18002fce4  mov     [rsi], eax
0x18002fce6  cmp     eax, 0FFFFFFFFh
0x18002fce9  jz      short loc_18002FD44
0x18002fceb  mov     rcx, [rdi]; hFile
0x18002fcee  xor     r9d, r9d; dwMaximumSizeHigh
0x18002fcf1  mov     [rsp+48h+lpName], 0; lpName
0x18002fcfa  xor     edx, edx; lpFileMappingAttributes
0x18002fcfc  mov     [rsp+48h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18002fd04  lea     r8d, [r9+2]; flProtect
0x18002fd08  call    cs:__imp_CreateFileMappingW
0x18002fd0e  mov     rsi, rax
0x18002fd11  test    rax, rax
0x18002fd14  jz      short loc_18002FD44
0x18002fd16  xor     r9d, r9d; dwFileOffsetLow
0x18002fd19  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18002fd22  xor     r8d, r8d; dwFileOffsetHigh
0x18002fd25  mov     rcx, rax; hFileMappingObject
0x18002fd28  lea     edx, [r9+4]; dwDesiredAccess
0x18002fd2c  call    cs:__imp_MapViewOfFile
0x18002fd32  mov     rcx, rsi; hObject
0x18002fd35  mov     [rbx], rax
0x18002fd38  call    cs:__imp_CloseHandle
0x18002fd3e  cmp     qword ptr [rbx], 0
0x18002fd42  jnz     short loc_18002FD66
0x18002fd44  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18002fd48  jz      short loc_18002FD5A
0x18002fd4a  mov     rcx, [rdi]; hObject
0x18002fd4d  call    cs:__imp_CloseHandle
0x18002fd53  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18002fd5a  test    rbx, rbx
0x18002fd5d  jz      short loc_18002FD66
0x18002fd5f  mov     qword ptr [rbx], 0
0x18002fd66  mov     rax, [rbx]
0x18002fd69  mov     rbx, [rsp+48h+arg_0]
0x18002fd6e  mov     rsi, [rsp+48h+arg_8]
0x18002fd73  add     rsp, 40h
0x18002fd77  pop     rdi
0x18002fd78  retn
```
