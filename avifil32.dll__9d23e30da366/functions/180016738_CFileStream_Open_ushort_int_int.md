# CFileStream::Open(ushort *,int,int)

- ea: `0x180016738`
- end: `0x180016923`
- name: `?Open@CFileStream@@QEAAHPEAGHH@Z`
- size: `491`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, LPCWSTR lpFileName, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180014744`

## callees

- `0x180001460`
- `0x180016510`
- `0x180016738`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800168a3`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800168a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800167bc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800167bc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800167f0`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800167f0`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800168ea`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800168ea`

## pseudocode

```c
__int64 __fastcall CFileStream::Open(CFileStream *this, LPCWSTR lpFileName, int a3, int a4)
{
  HANDLE FileW; // rax
  WCHAR v8; // dx
  WCHAR *v9; // rax
  WCHAR *v10; // rcx
  WCHAR i; // dx
  DWORD FileSize; // eax
  LPWSTR FilePart; // [rsp+40h] [rbp-C0h] BYREF
  DWORD TotalNumberOfClusters; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD SectorsPerCluster[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v19[262]; // [rsp+64h] [rbp-9Ch] BYREF

  if ( *((_DWORD *)this + 94) )
    return 0;
  *((_DWORD *)this + 98) = a3;
  FileW = CreateFileW(lpFileName, a3 != 0 ? -1073741824 : 0x80000000, a3 == 0, 0, 4u, 0x60000000u, 0);
  *((_QWORD *)this + 48) = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  FilePart = 0;
  Buffer[0] = 0;
  GetFullPathNameW(lpFileName, 0x104u, Buffer, &FilePart);
  if ( Buffer[0] == 92 && Buffer[1] == 92 )
  {
    v8 = v19[0];
    v9 = v19;
    FilePart = v19;
    if ( v19[0] )
    {
      v9 = v19;
      do
      {
        FilePart = ++v9;
        v10 = v9;
        if ( v8 == 92 )
          break;
        v8 = *v9;
      }
      while ( *v9 );
    }
    else
    {
      v10 = v19;
    }
  }
  else
  {
    v9 = Buffer;
    FilePart = Buffer;
    v10 = Buffer;
  }
  for ( i = *v9; i; i = *v10 )
  {
    FilePart = ++v10;
    if ( i == 92 )
    {
      *v10 = 0;
      break;
    }
  }
  SectorsPerCluster[0] = 0;
  NumberOfFreeClusters = 0;
  TotalNumberOfClusters = 0;
  if ( !GetDiskFreeSpaceW(Buffer, SectorsPerCluster, (LPDWORD)this, &NumberOfFreeClusters, &TotalNumberOfClusters) )
    *(_DWORD *)this = 2048;
  *((_DWORD *)this + 94) = 1;
  if ( !(unsigned int)CFileStream::EnsureBuffersValid(this) )
    return 0;
  *((_DWORD *)this + 91) = 0;
  *((_DWORD *)this + 93) = 0;
  if ( a4 )
    FileSize = 0;
  else
    FileSize = GetFileSize(*((HANDLE *)this + 48), 0);
  *((_DWORD *)this + 95) = FileSize;
  return 1;
}

```

## disassembly

```asm
0x180016738  mov     [rsp-8+arg_10], rbx
0x18001673d  mov     [rsp-8+arg_18], rsi
0x180016742  push    rbp
0x180016743  push    rdi
0x180016744  push    r14
0x180016746  lea     rbp, [rsp-180h]
0x18001674e  sub     rsp, 280h
0x180016755  mov     rax, cs:__security_cookie
0x18001675c  xor     rax, rsp
0x18001675f  mov     [rbp+190h+var_20], rax
0x180016766  xor     r14d, r14d
0x180016769  mov     esi, r9d
0x18001676c  mov     eax, r8d
0x18001676f  mov     rdi, rdx
0x180016772  mov     rbx, rcx
0x180016775  cmp     [rcx+178h], r14d
0x18001677c  jnz     loc_1800168FA
0x180016782  test    eax, eax
0x180016784  mov     [rcx+188h], eax
0x18001678a  mov     r8d, r14d
0x18001678d  mov     [rsp+290h+hTemplateFile], r14; hTemplateFile
0x180016792  setz    r8b; dwShareMode
0x180016796  mov     [rsp+290h+dwFlagsAndAttributes], 60000000h; dwFlagsAndAttributes
0x18001679e  neg     eax
0x1800167a0  mov     [rsp+290h+dwCreationDisposition], 4; dwCreationDisposition
0x1800167a8  mov     rcx, rdi; lpFileName
0x1800167ab  sbb     edx, edx
0x1800167ad  xor     r9d, r9d; lpSecurityAttributes
0x1800167b0  and     edx, 40000000h
0x1800167b6  add     edx, 80000000h; dwDesiredAccess
0x1800167bc  call    cs:__imp_CreateFileW
0x1800167c2  mov     [rbx+180h], rax
0x1800167c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800167cd  jz      loc_1800168FA
0x1800167d3  lea     r9, [rsp+290h+FilePart]; lpFilePart
0x1800167d8  mov     [rsp+290h+FilePart], r14
0x1800167dd  lea     r8, [rsp+290h+Buffer]; lpBuffer
0x1800167e2  mov     [rsp+290h+Buffer], r14w
0x1800167e8  mov     edx, 104h; nBufferLength
0x1800167ed  mov     rcx, rdi; lpFileName
0x1800167f0  call    cs:__imp_GetFullPathNameW
0x1800167f6  mov     r8w, 5Ch ; '\'
0x1800167fb  cmp     [rsp+290h+Buffer], r8w
0x180016801  jnz     short loc_180016847
0x180016803  cmp     [rsp+290h+var_22E], r8w
0x180016809  jnz     short loc_180016847
0x18001680b  movzx   edx, [rsp+290h+var_22C]
0x180016810  lea     rax, [rsp+290h+var_22C]
0x180016815  mov     [rsp+290h+FilePart], rax
0x18001681a  test    dx, dx
0x18001681d  jz      short loc_180016840
0x18001681f  lea     rax, [rsp+290h+var_22C]
0x180016824  add     rax, 2
0x180016828  mov     [rsp+290h+FilePart], rax
0x18001682d  mov     rcx, rax
0x180016830  cmp     dx, r8w
0x180016834  jz      short loc_180016856
0x180016836  movzx   edx, word ptr [rax]
0x180016839  test    dx, dx
0x18001683c  jnz     short loc_180016824
0x18001683e  jmp     short loc_180016856
0x180016840  lea     rcx, [rsp+290h+var_22C]
0x180016845  jmp     short loc_180016856
0x180016847  lea     rax, [rsp+290h+Buffer]
0x18001684c  mov     [rsp+290h+FilePart], rax
0x180016851  lea     rcx, [rsp+290h+Buffer]
0x180016856  movzx   edx, word ptr [rax]
0x180016859  jmp     short loc_18001686D
0x18001685b  add     rcx, 2
0x18001685f  mov     [rsp+290h+FilePart], rcx
0x180016864  cmp     dx, r8w
0x180016868  jz      short loc_180016874
0x18001686a  movzx   edx, word ptr [rcx]
0x18001686d  test    dx, dx
0x180016870  jnz     short loc_18001685B
0x180016872  jmp     short loc_180016878
0x180016874  mov     [rcx], r14w
0x180016878  lea     rax, [rsp+290h+TotalNumberOfClusters]
0x18001687d  mov     [rsp+290h+SectorsPerCluster], r14d
0x180016882  lea     r9, [rsp+290h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x180016887  mov     qword ptr [rsp+290h+dwCreationDisposition], rax; lpTotalNumberOfClusters
0x18001688c  mov     r8, rbx; lpBytesPerSector
0x18001688f  mov     [rsp+290h+NumberOfFreeClusters], r14d
0x180016894  lea     rdx, [rsp+290h+SectorsPerCluster]; lpSectorsPerCluster
0x180016899  mov     [rsp+290h+TotalNumberOfClusters], r14d
0x18001689e  lea     rcx, [rsp+290h+Buffer]; lpRootPathName
0x1800168a3  call    cs:__imp_GetDiskFreeSpaceW
0x1800168a9  test    eax, eax
0x1800168ab  jnz     short loc_1800168B3
0x1800168ad  mov     dword ptr [rbx], 800h
0x1800168b3  mov     edi, 1
0x1800168b8  mov     rcx, rbx; this
0x1800168bb  mov     [rbx+178h], edi
0x1800168c1  call    ?EnsureBuffersValid@CFileStream@@AEAAHXZ; CFileStream::EnsureBuffersValid(void)
0x1800168c6  test    eax, eax
0x1800168c8  jz      short loc_1800168FA
0x1800168ca  mov     [rbx+16Ch], r14d
0x1800168d1  mov     [rbx+174h], r14d
0x1800168d8  test    esi, esi
0x1800168da  jz      short loc_1800168E1
0x1800168dc  mov     eax, r14d
0x1800168df  jmp     short loc_1800168F0
0x1800168e1  mov     rcx, [rbx+180h]; hFile
0x1800168e8  xor     edx, edx; lpFileSizeHigh
0x1800168ea  call    cs:__imp_GetFileSize
0x1800168f0  mov     [rbx+17Ch], eax
0x1800168f6  mov     eax, edi
0x1800168f8  jmp     short loc_1800168FC
0x1800168fa  xor     eax, eax
0x1800168fc  mov     rcx, [rbp+190h+var_20]
0x180016903  xor     rcx, rsp; StackCookie
0x180016906  call    __security_check_cookie
0x18001690b  lea     r11, [rsp+290h+var_10]
0x180016913  mov     rbx, [r11+30h]
0x180016917  mov     rsi, [r11+38h]
0x18001691b  mov     rsp, r11
0x18001691e  pop     r14
0x180016920  pop     rdi
0x180016921  pop     rbp
0x180016922  retn
```
