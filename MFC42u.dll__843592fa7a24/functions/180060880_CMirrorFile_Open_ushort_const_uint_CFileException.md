# CMirrorFile::Open(ushort const *,uint,CFileException *)

- ea: `0x180060880`
- end: `0x180060ad2`
- name: `?Open@CMirrorFile@@UEAAHPEBGIPEAVCFileException@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(CMirrorFile *__hidden this, const unsigned __int16 *, unsigned int, struct CFileException *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009910`
- `0x18000a760`
- `0x18000b3a0`
- `0x18000ce50`
- `0x18000d960`
- `0x180019290`
- `0x180038520`
- `0x18003a120`
- `0x18003a5a0`
- `0x180060280`
- `0x180060880`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!free` at `0x180060a8b`
- `msvcrt!free` at `0x180060a8b`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800609f0`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800609f0`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180060a1c`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180060a1c`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x18006093c`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x18006093c`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180060a82`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180060a82`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180060a43`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180060a70`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180060a43`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180060a70`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall CMirrorFile::Open(HANDLE *this, wchar_t *a2, unsigned int a3, struct CFileException *a4)
{
  LPCWSTR *v8; // r14
  DWORD v9; // ebx
  __int64 TempName; // rax
  void *v11; // rbx
  DWORD NumberOfFreeClusters; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpRootPathName; // [rsp+38h] [rbp-C8h] BYREF
  DWORD BytesPerSector; // [rsp+40h] [rbp-C0h] BYREF
  DWORD SectorsPerCluster[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD TotalNumberOfClusters[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v19[24]; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+78h] [rbp-88h]

  v8 = (LPCWSTR *)(this + 4);
  CString::Empty((CString *)(this + 4));
  if ( (a3 & 0x1000) != 0 && (unsigned int)CFile::GetStatus(a2, (struct CFileStatus *)v19) )
  {
    lpRootPathName = _afxPchNil;
    AfxGetRoot(a2, (struct CString *)&lpRootPathName);
    SectorsPerCluster[0] = 0;
    BytesPerSector = 0;
    NumberOfFreeClusters = 0;
    TotalNumberOfClusters[0] = 0;
    v9 = 0;
    if ( GetDiskFreeSpaceW(
           lpRootPathName,
           SectorsPerCluster,
           &BytesPerSector,
           &NumberOfFreeClusters,
           TotalNumberOfClusters) )
    {
      v9 = SectorsPerCluster[0] * BytesPerSector * NumberOfFreeClusters;
    }
    if ( v9 > 2 * v20 )
    {
      TempName = CMirrorFile::GetTempName(v18, a2, 1);
      CString::operator=(v8, TempName);
      CString::~CString((CString *)v18);
    }
    CString::~CString((CString *)&lpRootPathName);
  }
  if ( *((_DWORD *)*v8 - 2) && CFile::Open((CFile *)this, *v8, a3, a4) )
  {
    CString::operator=(this + 3, a2);
    lpRootPathName = 0;
    *(_QWORD *)SectorsPerCluster = 0;
    *(_QWORD *)TotalNumberOfClusters = 0;
    if ( GetFileTime(
           this[1],
           (LPFILETIME)&lpRootPathName,
           (LPFILETIME)SectorsPerCluster,
           (LPFILETIME)TotalNumberOfClusters) )
    {
      AfxTimeToFileTime((const struct CTime *)v19, (LPFILETIME)&lpRootPathName);
      SetFileTime(
        this[1],
        (const FILETIME *)&lpRootPathName,
        (const FILETIME *)SectorsPerCluster,
        (const FILETIME *)TotalNumberOfClusters);
    }
    NumberOfFreeClusters = 0;
    if ( GetFileSecurityW(a2, 4u, 0, 0, &NumberOfFreeClusters) )
    {
      v11 = operator new(NumberOfFreeClusters);
      if ( GetFileSecurityW(a2, 4u, v11, NumberOfFreeClusters, &NumberOfFreeClusters) )
        SetFileSecurityW(*v8, 4u, v11);
      free(v11);
    }
    return 1;
  }
  else
  {
    CString::Empty((CString *)v8);
    return CFile::Open((CFile *)this, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x180060880  push    rbp
0x180060882  push    rbx
0x180060883  push    rsi
0x180060884  push    rdi
0x180060885  push    r12
0x180060887  push    r14
0x180060889  push    r15
0x18006088b  lea     rbp, [rsp-1A0h]
0x180060893  sub     rsp, 2A0h
0x18006089a  mov     rax, cs:__security_cookie
0x1800608a1  xor     rax, rsp
0x1800608a4  mov     [rbp+1D0h+var_40], rax
0x1800608ab  mov     r12, r9
0x1800608ae  mov     r15d, r8d
0x1800608b1  mov     rdi, rdx
0x1800608b4  mov     rsi, rcx
0x1800608b7  lea     r14, [rcx+20h]
0x1800608bb  mov     rcx, r14; this
0x1800608be  call    ?Empty@CString@@QEAAXXZ; CString::Empty(void)
0x1800608c3  bt      r15d, 0Ch
0x1800608c8  jnb     loc_180060993
0x1800608ce  lea     rdx, [rsp+2D0h+var_270]; struct CFileStatus *
0x1800608d3  mov     rcx, rdi; lpFileName
0x1800608d6  call    ?GetStatus@CFile@@SAHPEBGAEAUCFileStatus@@@Z; CFile::GetStatus(ushort const *,CFileStatus &)
0x1800608db  test    eax, eax
0x1800608dd  jz      loc_180060993
0x1800608e3  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800608ea  mov     [rsp+2D0h+lpRootPathName], rax
0x1800608ef  lea     rdx, [rsp+2D0h+lpRootPathName]; this
0x1800608f4  mov     rcx, rdi; Source
0x1800608f7  call    ?AfxGetRoot@@YAXPEBGAEAVCString@@@Z; AfxGetRoot(ushort const *,CString &)
0x1800608fc  mov     [rsp+2D0h+SectorsPerCluster], 0
0x180060904  mov     [rsp+2D0h+BytesPerSector], 0
0x18006090c  mov     [rsp+2D0h+NumberOfFreeClusters], 0
0x180060914  mov     [rsp+2D0h+TotalNumberOfClusters], 0
0x18006091c  xor     ebx, ebx
0x18006091e  lea     rax, [rsp+2D0h+TotalNumberOfClusters]
0x180060923  mov     [rsp+2D0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x180060928  lea     r9, [rsp+2D0h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x18006092d  lea     r8, [rsp+2D0h+BytesPerSector]; lpBytesPerSector
0x180060932  lea     rdx, [rsp+2D0h+SectorsPerCluster]; lpSectorsPerCluster
0x180060937  mov     rcx, [rsp+2D0h+lpRootPathName]; lpRootPathName
0x18006093c  call    cs:__imp_GetDiskFreeSpaceW
0x180060942  test    eax, eax
0x180060944  jz      short loc_180060954
0x180060946  mov     ebx, [rsp+2D0h+NumberOfFreeClusters]
0x18006094a  imul    ebx, [rsp+2D0h+BytesPerSector]
0x18006094f  imul    ebx, [rsp+2D0h+SectorsPerCluster]
0x180060954  mov     eax, [rsp+2D0h+var_258]
0x180060958  add     eax, eax
0x18006095a  cmp     ebx, eax
0x18006095c  jbe     short loc_180060989
0x18006095e  mov     r8d, 1
0x180060964  mov     rdx, rdi
0x180060967  lea     rcx, [rsp+2D0h+var_278]
0x18006096c  call    ?GetTempName@CMirrorFile@@SA?AVCString@@PEBGH@Z; CMirrorFile::GetTempName(ushort const *,int)
0x180060971  nop
0x180060972  mov     rdx, rax
0x180060975  mov     rcx, r14
0x180060978  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18006097d  nop
0x18006097e  lea     rcx, [rsp+2D0h+var_278]; this
0x180060983  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180060988  nop
0x180060989  lea     rcx, [rsp+2D0h+lpRootPathName]; this
0x18006098e  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180060993  mov     rdx, [r14]; unsigned __int16 *
0x180060996  cmp     dword ptr [rdx-8], 0
0x18006099a  jz      loc_180060A98
0x1800609a0  mov     r9, r12; struct CFileException *
0x1800609a3  mov     r8d, r15d; unsigned int
0x1800609a6  mov     rcx, rsi; this
0x1800609a9  call    ?Open@CFile@@UEAAHPEBGIPEAVCFileException@@@Z; CFile::Open(ushort const *,uint,CFileException *)
0x1800609ae  test    eax, eax
0x1800609b0  jz      loc_180060A98
0x1800609b6  lea     rcx, [rsi+18h]
0x1800609ba  mov     rdx, rdi
0x1800609bd  call    ??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800609c2  mov     [rsp+2D0h+lpRootPathName], 0
0x1800609cb  mov     qword ptr [rsp+2D0h+SectorsPerCluster], 0
0x1800609d4  mov     qword ptr [rsp+2D0h+TotalNumberOfClusters], 0
0x1800609dd  lea     r9, [rsp+2D0h+TotalNumberOfClusters]; lpLastWriteTime
0x1800609e2  lea     r8, [rsp+2D0h+SectorsPerCluster]; lpLastAccessTime
0x1800609e7  lea     rdx, [rsp+2D0h+lpRootPathName]; lpCreationTime
0x1800609ec  mov     rcx, [rsi+8]; hFile
0x1800609f0  call    cs:__imp_GetFileTime
0x1800609f6  test    eax, eax
0x1800609f8  jz      short loc_180060A22
0x1800609fa  lea     rdx, [rsp+2D0h+lpRootPathName]; lpFileTime
0x1800609ff  lea     rcx, [rsp+2D0h+var_270]; this
0x180060a04  call    ?AfxTimeToFileTime@@YAXAEBVCTime@@PEAU_FILETIME@@@Z; AfxTimeToFileTime(CTime const &,_FILETIME *)
0x180060a09  lea     r9, [rsp+2D0h+TotalNumberOfClusters]; lpLastWriteTime
0x180060a0e  lea     r8, [rsp+2D0h+SectorsPerCluster]; lpLastAccessTime
0x180060a13  lea     rdx, [rsp+2D0h+lpRootPathName]; lpCreationTime
0x180060a18  mov     rcx, [rsi+8]; hFile
0x180060a1c  call    cs:__imp_SetFileTime
0x180060a22  mov     [rsp+2D0h+NumberOfFreeClusters], 0
0x180060a2a  lea     rax, [rsp+2D0h+NumberOfFreeClusters]
0x180060a2f  mov     [rsp+2D0h+lpTotalNumberOfClusters], rax; lpnLengthNeeded
0x180060a34  xor     r9d, r9d; nLength
0x180060a37  xor     r8d, r8d; pSecurityDescriptor
0x180060a3a  lea     esi, [r9+4]
0x180060a3e  mov     edx, esi; RequestedInformation
0x180060a40  mov     rcx, rdi; lpFileName
0x180060a43  call    cs:__imp_GetFileSecurityW
0x180060a49  test    eax, eax
0x180060a4b  jz      short loc_180060A91
0x180060a4d  mov     ecx, [rsp+2D0h+NumberOfFreeClusters]; Size
0x180060a51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060a56  mov     rbx, rax
0x180060a59  lea     rax, [rsp+2D0h+NumberOfFreeClusters]
0x180060a5e  mov     [rsp+2D0h+lpTotalNumberOfClusters], rax; lpnLengthNeeded
0x180060a63  mov     r9d, [rsp+2D0h+NumberOfFreeClusters]; nLength
0x180060a68  mov     r8, rbx; pSecurityDescriptor
0x180060a6b  mov     edx, esi; RequestedInformation
0x180060a6d  mov     rcx, rdi; lpFileName
0x180060a70  call    cs:__imp_GetFileSecurityW
0x180060a76  test    eax, eax
0x180060a78  jz      short loc_180060A88
0x180060a7a  mov     r8, rbx; pSecurityDescriptor
0x180060a7d  mov     edx, esi; SecurityInformation
0x180060a7f  mov     rcx, [r14]; lpFileName
0x180060a82  call    cs:__imp_SetFileSecurityW
0x180060a88  mov     rcx, rbx; Block
0x180060a8b  call    cs:__imp_free
0x180060a91  mov     eax, 1
0x180060a96  jmp     short loc_180060AB1
0x180060a98  mov     rcx, r14; this
0x180060a9b  call    ?Empty@CString@@QEAAXXZ; CString::Empty(void)
0x180060aa0  mov     r9, r12; struct CFileException *
0x180060aa3  mov     r8d, r15d; unsigned int
0x180060aa6  mov     rdx, rdi; unsigned __int16 *
0x180060aa9  mov     rcx, rsi; this
0x180060aac  call    ?Open@CFile@@UEAAHPEBGIPEAVCFileException@@@Z; CFile::Open(ushort const *,uint,CFileException *)
0x180060ab1  mov     rcx, [rbp+1D0h+var_40]
0x180060ab8  xor     rcx, rsp; StackCookie
0x180060abb  call    __security_check_cookie
0x180060ac0  add     rsp, 2A0h
0x180060ac7  pop     r15
0x180060ac9  pop     r14
0x180060acb  pop     r12
0x180060acd  pop     rdi
0x180060ace  pop     rsi
0x180060acf  pop     rbx
0x180060ad0  pop     rbp
0x180060ad1  retn
```
