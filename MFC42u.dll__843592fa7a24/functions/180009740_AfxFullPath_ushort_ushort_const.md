# AfxFullPath(ushort *,ushort const *)

- ea: `0x180009740`
- end: `0x180009905`
- name: `?AfxFullPath@@YAHPEAGPEBG@Z`
- size: `453`
- prototype: `__int64 __fastcall(wchar_t *Source, LPCWSTR lpFileName)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800095c0`
- `0x180009910`
- `0x18002caa0`
- `0x18003a5a0`
- `0x1800626f0`
- `0x180094c70`
- `0x180094f40`

## callees

- `0x180009740`
- `0x180019290`
- `0x180038520`
- `0x1800d1f92`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800097a5`
- `msvcrt!wcsncpy_s` at `0x1800097a5`
- `msvcrt!wcscpy_s` at `0x1800098c8`
- `msvcrt!wcscpy_s` at `0x1800098c8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000978f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000978f`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180009831`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180009831`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000987d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000987d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000988c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000988c`
- `KERNEL32!lstrlenW` at `0x1800098a5`
- `KERNEL32!lstrlenW` at `0x1800098a5`
- `USER32!CharUpperW` at `0x180009855`
- `USER32!CharUpperW` at `0x180009855`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AfxFullPath(wchar_t *Source, LPCWSTR lpFileName)
{
  DWORD FullPathNameW; // eax
  unsigned int v6; // esi
  char v7; // al
  HANDLE FirstFileW; // rax
  int v9; // eax
  __int64 v10; // rdx
  DWORD FileSystemFlags; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpRootPathName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD MaximumComponentLength; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp-A8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  FilePart = 0;
  FullPathNameW = GetFullPathNameW(lpFileName, 0x104u, Source, &FilePart);
  if ( !FullPathNameW )
  {
    wcsncpy_s(Source, 0x104u, lpFileName, 0xFFFFFFFFFFFFFFFFuLL);
    return 0;
  }
  if ( FullPathNameW >= 0x104 )
    return 0;
  lpRootPathName = _afxPchNil;
  AfxGetRoot(Source, (struct CString *)&lpRootPathName);
  v6 = 1;
  if ( *((int *)lpRootPathName - 2) < 1
    || *lpRootPathName != 92
    || *((int *)lpRootPathName - 2) <= 1
    || lpRootPathName[1] != 92 )
  {
    FileSystemFlags = 0;
    MaximumComponentLength = 0;
    if ( !GetVolumeInformationW(lpRootPathName, 0, 0, 0, &MaximumComponentLength, &FileSystemFlags, 0, 0) )
    {
      CString::~CString((CString *)&lpRootPathName);
      return 0;
    }
    v7 = FileSystemFlags;
    if ( (FileSystemFlags & 2) == 0 )
    {
      CharUpperW(Source);
      v7 = FileSystemFlags;
    }
    if ( (v7 & 4) == 0 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        FindClose(FirstFileW);
        if ( FilePart
          && FilePart > Source
          && (v9 = lstrlenW(FindFileData.cFileName), v10 = FilePart - Source, (int)v10 + v9 < 260) )
        {
          wcscpy_s(FilePart, 260 - (int)v10, FindFileData.cFileName);
        }
        else
        {
          v6 = 0;
        }
      }
    }
  }
  CString::~CString((CString *)&lpRootPathName);
  return v6;
}

```

## disassembly

```asm
0x180009740  mov     [rsp-8+arg_10], rbx
0x180009745  mov     [rsp-8+arg_18], rsi
0x18000974a  push    rbp
0x18000974b  push    rdi
0x18000974c  push    r14
0x18000974e  lea     rbp, [rsp-1C0h]
0x180009756  sub     rsp, 2C0h
0x18000975d  mov     rax, cs:__security_cookie
0x180009764  xor     rax, rsp
0x180009767  mov     [rbp+1D0h+var_20], rax
0x18000976e  mov     r14, rdx
0x180009771  mov     rdi, rcx
0x180009774  mov     [rsp+2D0h+FilePart], 0
0x18000977d  lea     r9, [rsp+2D0h+FilePart]; lpFilePart
0x180009782  mov     r8, rcx; lpBuffer
0x180009785  mov     ebx, 104h
0x18000978a  mov     edx, ebx; nBufferLength
0x18000978c  mov     rcx, r14; lpFileName
0x18000978f  call    cs:__imp_GetFullPathNameW
0x180009795  test    eax, eax
0x180009797  jnz     short loc_1800097B2
0x180009799  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000979d  mov     r8, r14; Source
0x1800097a0  mov     edx, ebx; SizeInWords
0x1800097a2  mov     rcx, rdi; Destination
0x1800097a5  call    cs:__imp_wcsncpy_s
0x1800097ab  xor     eax, eax
0x1800097ad  jmp     loc_1800098DE
0x1800097b2  cmp     eax, ebx
0x1800097b4  jnb     short loc_1800097AB
0x1800097b6  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800097bd  mov     [rsp+2D0h+lpRootPathName], rax
0x1800097c2  lea     rdx, [rsp+2D0h+lpRootPathName]; this
0x1800097c7  mov     rcx, rdi; Source
0x1800097ca  call    ?AfxGetRoot@@YAXPEBGAEAVCString@@@Z; AfxGetRoot(ushort const *,CString &)
0x1800097cf  mov     rcx, [rsp+2D0h+lpRootPathName]; lpRootPathName
0x1800097d4  mov     esi, 1
0x1800097d9  cmp     [rcx-8], esi
0x1800097dc  jl      short loc_1800097F4
0x1800097de  cmp     word ptr [rcx], 5Ch ; '\'
0x1800097e2  jnz     short loc_1800097F4
0x1800097e4  cmp     [rcx-8], esi
0x1800097e7  jle     short loc_1800097F4
0x1800097e9  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1800097ee  jz      loc_1800098D2
0x1800097f4  mov     [rsp+2D0h+FileSystemFlags], 0
0x1800097fc  mov     [rsp+2D0h+MaximumComponentLength], 0
0x180009804  mov     [rsp+2D0h+nFileSystemNameSize], 0; nFileSystemNameSize
0x18000980c  mov     [rsp+2D0h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x180009815  lea     rax, [rsp+2D0h+FileSystemFlags]
0x18000981a  mov     [rsp+2D0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18000981f  lea     rax, [rsp+2D0h+MaximumComponentLength]
0x180009824  mov     [rsp+2D0h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x180009829  xor     r9d, r9d; lpVolumeSerialNumber
0x18000982c  xor     r8d, r8d; nVolumeNameSize
0x18000982f  xor     edx, edx; lpVolumeNameBuffer
0x180009831  call    cs:__imp_GetVolumeInformationW
0x180009837  test    eax, eax
0x180009839  jnz     short loc_18000984A
0x18000983b  lea     rcx, [rsp+2D0h+lpRootPathName]; this
0x180009840  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180009845  jmp     loc_1800097AB
0x18000984a  mov     eax, [rsp+2D0h+FileSystemFlags]
0x18000984e  test    al, 2
0x180009850  jnz     short loc_18000985F
0x180009852  mov     rcx, rdi; lpsz
0x180009855  call    cs:__imp_CharUpperW
0x18000985b  mov     eax, [rsp+2D0h+FileSystemFlags]
0x18000985f  test    al, 4
0x180009861  jnz     short loc_1800098D2
0x180009863  xor     edx, edx; Val
0x180009865  mov     r8d, 250h; Size
0x18000986b  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x180009870  call    memset_0
0x180009875  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x18000987a  mov     rcx, r14; lpFileName
0x18000987d  call    cs:__imp_FindFirstFileW
0x180009883  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009887  jz      short loc_1800098D2
0x180009889  mov     rcx, rax; hFindFile
0x18000988c  call    cs:__imp_FindClose
0x180009892  mov     rax, [rsp+2D0h+FilePart]
0x180009897  test    rax, rax
0x18000989a  jz      short loc_1800098D0
0x18000989c  cmp     rax, rdi
0x18000989f  jbe     short loc_1800098D0
0x1800098a1  lea     rcx, [rbp+1D0h+FindFileData.cFileName]; lpString
0x1800098a5  call    cs:__imp_lstrlenW
0x1800098ab  mov     rcx, [rsp+2D0h+FilePart]; Destination
0x1800098b0  mov     rdx, rcx
0x1800098b3  sub     rdx, rdi
0x1800098b6  sar     rdx, 1
0x1800098b9  add     eax, edx
0x1800098bb  cmp     eax, ebx
0x1800098bd  jge     short loc_1800098D0
0x1800098bf  sub     ebx, edx
0x1800098c1  movsxd  rdx, ebx; SizeInWords
0x1800098c4  lea     r8, [rbp+1D0h+FindFileData.cFileName]; Source
0x1800098c8  call    cs:__imp_wcscpy_s
0x1800098ce  jmp     short loc_1800098D2
0x1800098d0  xor     esi, esi
0x1800098d2  lea     rcx, [rsp+2D0h+lpRootPathName]; this
0x1800098d7  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800098dc  mov     eax, esi
0x1800098de  mov     rcx, [rbp+1D0h+var_20]
0x1800098e5  xor     rcx, rsp; StackCookie
0x1800098e8  call    __security_check_cookie
0x1800098ed  lea     r11, [rsp+2D0h+var_10]
0x1800098f5  mov     rbx, [r11+30h]
0x1800098f9  mov     rsi, [r11+38h]
0x1800098fd  mov     rsp, r11
0x180009900  pop     r14
0x180009902  pop     rdi
0x180009903  pop     rbp
0x180009904  retn
```
