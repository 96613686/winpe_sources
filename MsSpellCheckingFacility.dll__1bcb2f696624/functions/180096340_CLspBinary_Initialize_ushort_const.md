# CLspBinary::Initialize(ushort const *)

- ea: `0x180096340`
- end: `0x180096419`
- name: `?Initialize@CLspBinary@@UEAAHPEBG@Z`
- size: `217`
- prototype: `__int64 __fastcall(CLspBinary *__hidden this, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180005b20`
- `0x180095fb8`
- `0x180096340`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800963d3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800963d3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800963ae`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800963ae`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800963e8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800963e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180096381`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180096381`

## pseudocode

```c
__int64 __fastcall CLspBinary::Initialize(HANDLE *this, LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  HANDLE FileMappingW; // rax
  LPVOID v6; // rax

  CLspBinary::Clear((CLspBinary *)this);
  *((_BYTE *)this + 76) = 1;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  this[3] = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    this[4] = FileMappingW;
    if ( FileMappingW )
    {
      v6 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      this[1] = v6;
      if ( v6 )
      {
        *((_DWORD *)this + 4) = GetFileSize(this[3], 0);
        TString<CArray<unsigned short,CArrayAllocator_malloc>>::operator=(this + 5);
        return 1;
      }
    }
    CLspBinary::Clear((CLspBinary *)this);
  }
  return 0;
}

```

## disassembly

```asm
0x180096340  mov     [rsp+arg_0], rbx
0x180096345  push    rdi
0x180096346  sub     rsp, 40h
0x18009634a  mov     rdi, rdx
0x18009634d  mov     rbx, rcx
0x180096350  call    ?Clear@CLspBinary@@AEAAXXZ; CLspBinary::Clear(void)
0x180096355  xor     r9d, r9d; lpSecurityAttributes
0x180096358  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180096361  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180096369  mov     edx, 80000000h; dwDesiredAccess
0x18009636e  mov     rcx, rdi; lpFileName
0x180096371  mov     byte ptr [rbx+4Ch], 1
0x180096375  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18009637d  lea     r8d, [r9+1]; dwShareMode
0x180096381  call    cs:__imp_CreateFileW
0x180096387  mov     [rbx+18h], rax
0x18009638b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009638f  jz      short loc_18009640C
0x180096391  xor     r9d, r9d; dwMaximumSizeHigh
0x180096394  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18009639d  xor     edx, edx; lpFileMappingAttributes
0x18009639f  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800963a7  mov     rcx, rax; hFile
0x1800963aa  lea     r8d, [r9+2]; flProtect
0x1800963ae  call    cs:__imp_CreateFileMappingW
0x1800963b4  mov     [rbx+20h], rax
0x1800963b8  test    rax, rax
0x1800963bb  jz      short loc_180096404
0x1800963bd  xor     r9d, r9d; dwFileOffsetLow
0x1800963c0  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800963c9  xor     r8d, r8d; dwFileOffsetHigh
0x1800963cc  mov     rcx, rax; hFileMappingObject
0x1800963cf  lea     edx, [r9+4]; dwDesiredAccess
0x1800963d3  call    cs:__imp_MapViewOfFile
0x1800963d9  mov     [rbx+8], rax
0x1800963dd  test    rax, rax
0x1800963e0  jz      short loc_180096404
0x1800963e2  mov     rcx, [rbx+18h]; hFile
0x1800963e6  xor     edx, edx; lpFileSizeHigh
0x1800963e8  call    cs:__imp_GetFileSize
0x1800963ee  lea     rcx, [rbx+28h]
0x1800963f2  mov     rdx, rdi
0x1800963f5  mov     [rbx+10h], eax
0x1800963f8  call    ??4?$TString@V?$CArray@GVCArrayAllocator_malloc@@@@@@QEAAAEBV0@PEBG@Z; TString<CArray<ushort,CArrayAllocator_malloc>>::operator=(ushort const *)
0x1800963fd  mov     eax, 1
0x180096402  jmp     short loc_18009640E
0x180096404  mov     rcx, rbx; this
0x180096407  call    ?Clear@CLspBinary@@AEAAXXZ; CLspBinary::Clear(void)
0x18009640c  xor     eax, eax
0x18009640e  mov     rbx, [rsp+48h+arg_0]
0x180096413  add     rsp, 40h
0x180096417  pop     rdi
0x180096418  retn
```
