# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(char const *,_GUID const &,ulong,EMBEDDED_PDB_INFORMATION const &)

- ea: `0x18000bc98`
- end: `0x18000c02a`
- name: `?CreateEmbeddedPdb@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBDAEBU_GUID@@KAEBUEMBEDDED_PDB_INFORMATION@@@Z`
- size: `914`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, const char *, const struct _GUID *, unsigned int, const struct EMBEDDED_PDB_INFORMATION *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a30c`

## callees

- `0x1800021ec`
- `0x180002720`
- `0x1800067f0`
- `0x180006960`
- `0x18000bbb4`
- `0x18000bc98`
- `0x18000da2c`
- `0x18000da64`
- `0x18000f560`
- `0x180010e6c`
- `0x1800268f4`
- `0x180026e30`
- `0x180027910`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000beda`
- `KERNEL32!GetLastError` at `0x18000bf9c`
- `KERNEL32!GetLastError` at `0x18000beda`
- `KERNEL32!GetLastError` at `0x18000bf9c`
- `KERNEL32!CloseHandle` at `0x18000bf96`
- `KERNEL32!CloseHandle` at `0x18000bfb5`
- `KERNEL32!CloseHandle` at `0x18000bf96`
- `KERNEL32!CloseHandle` at `0x18000bfb5`
- `KERNEL32!CreateFileW` at `0x18000becc`
- `KERNEL32!CreateFileW` at `0x18000becc`
- `KERNEL32!CreateDirectoryW` at `0x18000bcf8`
- `KERNEL32!CreateDirectoryW` at `0x18000bd37`
- `KERNEL32!CreateDirectoryW` at `0x18000bd7c`
- `KERNEL32!CreateDirectoryW` at `0x18000bcf8`
- `KERNEL32!CreateDirectoryW` at `0x18000bd37`
- `KERNEL32!CreateDirectoryW` at `0x18000bd7c`
- `KERNEL32!SetFilePointerEx` at `0x18000bf0b`
- `KERNEL32!SetFilePointerEx` at `0x18000bf0b`
- `KERNEL32!SetFilePointer` at `0x18000bf20`
- `KERNEL32!SetFilePointer` at `0x18000bf20`
- `KERNEL32!WriteFile` at `0x18000bf60`
- `KERNEL32!WriteFile` at `0x18000bf60`
- `KERNEL32!GetFileAttributesW` at `0x18000be9a`
- `KERNEL32!GetFileAttributesW` at `0x18000be9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        const char *a2,
        const struct _GUID *a3,
        int a4,
        const struct EMBEDDED_PDB_INFORMATION *a5)
{
  const WCHAR *v9; // rbx
  unsigned int Error; // edi
  int v11; // ecx
  __int64 v12; // r8
  void **v13; // rax
  void **i; // r9
  void **v15; // rax
  __int64 v16; // r9
  __int64 v17; // rax
  void **v18; // r8
  HANDLE FileW; // rsi
  unsigned int v20; // r14d
  LARGE_INTEGER v21; // rdi
  BOOL v22; // eax
  void *v23; // rcx
  LARGE_INTEGER *p_liDistanceToMove; // rax
  DWORD LowPart; // ecx
  char *v26; // r14
  LARGE_INTEGER *v27; // rax
  signed int LastError; // eax
  LPCWSTR lpPathName; // [rsp+50h] [rbp-69h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+58h] [rbp-61h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-59h] BYREF
  int v33; // [rsp+64h] [rbp-55h] BYREF
  int v34; // [rsp+6Ch] [rbp-4Dh] BYREF
  __int64 v35; // [rsp+78h] [rbp-41h]
  _BYTE v36[8]; // [rsp+80h] [rbp-39h] BYREF
  void *v37[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v38; // [rsp+98h] [rbp-21h]
  unsigned __int64 v39; // [rsp+A0h] [rbp-19h]
  _BYTE v40[8]; // [rsp+A8h] [rbp-11h] BYREF
  void *Block; // [rsp+B0h] [rbp-9h]
  __int64 v42; // [rsp+C0h] [rbp+7h]
  unsigned __int64 v43; // [rsp+C8h] [rbp+Fh]

  v35 = -2;
  v9 = (const WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)this + 48) - 24LL) + 24);
  lpPathName = v9;
  if ( !CreateDirectoryW(v9, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u) )
      goto LABEL_52;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpPathName,
    L"\\%hs",
    a2);
  v9 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u) )
      goto LABEL_52;
  }
  Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v11,
    (unsigned int)&lpPathName,
    *((_QWORD *)this + 48),
    (_DWORD)a2,
    (__int64)a3,
    a4);
  v9 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u) )
      goto LABEL_52;
  }
  v39 = 15;
  v38 = 0;
  LOBYTE(v37[0]) = 0;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  std::string::assign(v36, a2);
  if ( v38 )
  {
    v13 = v37;
    if ( v39 >= 0x10 )
      v13 = (void **)v37[0];
    for ( i = (void **)((char *)v13 + v38 - 1); ; i = (void **)((char *)i - 1) )
    {
      v15 = v37;
      if ( *(_BYTE *)i == 46 )
        break;
      if ( v39 >= 0x10 )
        v15 = (void **)v37[0];
      if ( i == v15 )
        goto LABEL_22;
    }
    if ( v39 >= 0x10 )
      v15 = (void **)v37[0];
    v16 = (char *)i - (char *)v15;
  }
  else
  {
LABEL_22:
    v16 = -1;
  }
  if ( v16 != -1 )
  {
    v17 = std::string::substr(v36, v40);
    std::string::assign(v36, v17, 0, -1);
    if ( v43 >= 0x10 )
      operator delete(Block);
    v43 = 15;
    v42 = 0;
    LOBYTE(Block) = 0;
  }
  std::string::operator+=(v36);
  v18 = v37;
  if ( v39 >= 0x10 )
    v18 = (void **)v37[0];
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpPathName,
    L"\\%hs",
    v18);
  v9 = lpPathName;
  if ( GetFileAttributesW(lpPathName) != -1 )
    goto LABEL_48;
  FileW = CreateFileW(v9, 0x40000000u, 0, 0, 1u, 0x80u, 0);
  if ( FileW )
  {
    v20 = *(_DWORD *)a5;
    liDistanceToMove.QuadPart = *(unsigned int *)a5;
    v21 = liDistanceToMove;
    v22 = SetFilePointerEx(FileW, liDistanceToMove, 0, 0);
    v23 = FileW;
    if ( v22 )
    {
      SetFilePointer(FileW, 0, 0, 0);
      v33 = 0x10000;
      p_liDistanceToMove = (LARGE_INTEGER *)&v33;
      if ( v20 <= 0x10000 )
        p_liDistanceToMove = &liDistanceToMove;
      LowPart = p_liDistanceToMove->LowPart;
      v26 = (char *)*((_QWORD *)a5 + 1);
      if ( !p_liDistanceToMove->LowPart )
      {
LABEL_47:
        CloseHandle(FileW);
        goto LABEL_48;
      }
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(FileW, v26, LowPart, &NumberOfBytesWritten, 0) )
          break;
        v21.QuadPart -= NumberOfBytesWritten;
        liDistanceToMove = v21;
        v26 += NumberOfBytesWritten;
        v34 = 0x10000;
        v27 = (LARGE_INTEGER *)&v34;
        if ( v21.LowPart <= 0x10000 )
          v27 = &liDistanceToMove;
        LowPart = v27->LowPart;
        if ( !v27->LowPart )
          goto LABEL_47;
      }
      v23 = FileW;
    }
    CloseHandle(v23);
    goto LABEL_44;
  }
  if ( GetLastError() != 80 )
  {
LABEL_44:
    LastError = GetLastError();
    Error = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      Error = LastError;
    goto LABEL_49;
  }
LABEL_48:
  Error = 0;
LABEL_49:
  if ( v39 >= 0x10 )
    operator delete(v37[0]);
  v39 = 15;
  v38 = 0;
  LOBYTE(v37[0]) = 0;
LABEL_52:
  if ( _InterlockedDecrement((volatile signed __int32 *)v9 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 - 3) + 8LL))(*((_QWORD *)v9 - 3));
  return Error;
}

```

## disassembly

```asm
0x18000bc98  mov     rax, rsp
0x18000bc9b  push    rbp
0x18000bc9c  push    rsi
0x18000bc9d  push    rdi
0x18000bc9e  push    r12
0x18000bca0  push    r13
0x18000bca2  push    r14
0x18000bca4  push    r15
0x18000bca6  lea     rbp, [rax-57h]
0x18000bcaa  sub     rsp, 0D0h
0x18000bcb1  mov     [rbp+4Fh+var_90], 0FFFFFFFFFFFFFFFEh
0x18000bcb9  mov     [rax+20h], rbx
0x18000bcbd  mov     rax, cs:__security_cookie
0x18000bcc4  xor     rax, rsp
0x18000bcc7  mov     [rbp+4Fh+var_38], rax
0x18000bccb  mov     r15d, r9d
0x18000bcce  mov     r12, r8
0x18000bcd1  mov     rsi, rdx
0x18000bcd4  mov     r14, rcx
0x18000bcd7  mov     r13, [rbp+4Fh+arg_20]
0x18000bcdb  mov     rcx, [rcx+180h]
0x18000bce2  sub     rcx, 18h
0x18000bce6  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000bceb  lea     rbx, [rax+18h]
0x18000bcef  mov     [rbp+4Fh+lpPathName], rbx
0x18000bcf3  xor     edx, edx; lpSecurityAttributes
0x18000bcf5  mov     rcx, rbx; lpPathName
0x18000bcf8  call    cs:__imp_CreateDirectoryW
0x18000bcfe  test    eax, eax
0x18000bd00  jnz     short loc_18000BD1B
0x18000bd02  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000bd07  mov     edi, eax
0x18000bd09  mov     ecx, 0B7h; unsigned int
0x18000bd0e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000bd13  cmp     edi, eax
0x18000bd15  jnz     loc_18000BD9E
0x18000bd1b  mov     r8, rsi
0x18000bd1e  lea     rdx, aHs_0; "\\%hs"
0x18000bd25  lea     rcx, [rbp+4Fh+lpPathName]
0x18000bd29  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18000bd2e  xor     edx, edx; lpSecurityAttributes
0x18000bd30  mov     rbx, [rbp+4Fh+lpPathName]
0x18000bd34  mov     rcx, rbx; lpPathName
0x18000bd37  call    cs:__imp_CreateDirectoryW
0x18000bd3d  test    eax, eax
0x18000bd3f  jnz     short loc_18000BD56
0x18000bd41  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000bd46  mov     edi, eax
0x18000bd48  mov     ecx, 0B7h; unsigned int
0x18000bd4d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000bd52  cmp     edi, eax
0x18000bd54  jnz     short loc_18000BD9E
0x18000bd56  mov     [rsp+100h+dwFlagsAndAttributes], r15d
0x18000bd5b  mov     qword ptr [rsp+100h+dwCreationDisposition], r12
0x18000bd60  mov     r9, rsi
0x18000bd63  mov     r8, [r14+180h]
0x18000bd6a  lea     rdx, [rbp+4Fh+lpPathName]
0x18000bd6e  call    ?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)
0x18000bd73  xor     edx, edx; lpSecurityAttributes
0x18000bd75  mov     rbx, [rbp+4Fh+lpPathName]
0x18000bd79  mov     rcx, rbx; lpPathName
0x18000bd7c  call    cs:__imp_CreateDirectoryW
0x18000bd82  xor     r15d, r15d
0x18000bd85  test    eax, eax
0x18000bd87  jnz     short loc_18000BDA7
0x18000bd89  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000bd8e  mov     edi, eax
0x18000bd90  mov     ecx, 0B7h; unsigned int
0x18000bd95  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000bd9a  cmp     edi, eax
0x18000bd9c  jz      short loc_18000BDA7
0x18000bd9e  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000bda2  jmp     loc_18000BFDE
0x18000bda7  mov     ebx, 0Fh
0x18000bdac  mov     [rbp+4Fh+var_68], rbx
0x18000bdb0  mov     [rbp+4Fh+var_70], r15
0x18000bdb4  mov     byte ptr [rbp+4Fh+var_80], r15b
0x18000bdb8  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000bdbc  mov     r8, r12
0x18000bdbf  inc     r8
0x18000bdc2  cmp     [rsi+r8], r15b
0x18000bdc6  jnz     short loc_18000BDBF
0x18000bdc8  mov     rdx, rsi
0x18000bdcb  lea     rcx, [rbp+4Fh+var_88]
0x18000bdcf  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000bdd4  nop
0x18000bdd5  mov     [rbp+4Fh+var_C0], 2Eh ; '.'
0x18000bdd9  mov     r8, [rbp+4Fh+var_70]
0x18000bddd  cmp     r8, 1
0x18000bde1  jb      short loc_18000BE27
0x18000bde3  lea     rax, [rbp+4Fh+var_80]
0x18000bde7  mov     rcx, [rbp+4Fh+var_80]
0x18000bdeb  mov     rdx, [rbp+4Fh+var_68]
0x18000bdef  cmp     rdx, 10h
0x18000bdf3  cmovnb  rax, rcx
0x18000bdf7  lea     r9, [r8-1]
0x18000bdfb  add     r9, rax
0x18000bdfe  lea     rax, [rbp+4Fh+var_80]
0x18000be02  cmp     byte ptr [r9], 2Eh ; '.'
0x18000be06  jz      short loc_18000BE1A
0x18000be08  cmp     rdx, 10h
0x18000be0c  cmovnb  rax, rcx
0x18000be10  cmp     r9, rax
0x18000be13  jz      short loc_18000BE27
0x18000be15  dec     r9
0x18000be18  jmp     short loc_18000BDFE
0x18000be1a  cmp     rdx, 10h
0x18000be1e  cmovnb  rax, rcx
0x18000be22  sub     r9, rax
0x18000be25  jmp     short loc_18000BE2A
0x18000be27  mov     r9, r12
0x18000be2a  cmp     r9, r12
0x18000be2d  jz      short loc_18000BE6C
0x18000be2f  lea     rdx, [rbp+4Fh+var_60]
0x18000be33  lea     rcx, [rbp+4Fh+var_88]
0x18000be37  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x18000be3c  nop
0x18000be3d  mov     r9, r12
0x18000be40  xor     r8d, r8d
0x18000be43  mov     rdx, rax
0x18000be46  lea     rcx, [rbp+4Fh+var_88]
0x18000be4a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000be4f  nop
0x18000be50  cmp     [rbp+4Fh+var_40], 10h
0x18000be55  jb      short loc_18000BE60
0x18000be57  mov     rcx, [rbp+4Fh+Block]; Block
0x18000be5b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be60  mov     [rbp+4Fh+var_40], rbx
0x18000be64  mov     [rbp+4Fh+var_48], r15
0x18000be68  mov     byte ptr [rbp+4Fh+Block], r15b
0x18000be6c  lea     rcx, [rbp+4Fh+var_88]
0x18000be70  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV01@PEBD@Z; std::string::operator+=(char const *)
0x18000be75  lea     r8, [rbp+4Fh+var_80]
0x18000be79  cmp     [rbp+4Fh+var_68], 10h
0x18000be7e  cmovnb  r8, [rbp+4Fh+var_80]
0x18000be83  lea     rdx, aHs_0; "\\%hs"
0x18000be8a  lea     rcx, [rbp+4Fh+lpPathName]
0x18000be8e  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18000be93  mov     rbx, [rbp+4Fh+lpPathName]
0x18000be97  mov     rcx, rbx; lpFileName
0x18000be9a  call    cs:__imp_GetFileAttributesW
0x18000bea0  cmp     eax, 0FFFFFFFFh
0x18000bea3  jnz     loc_18000BFBB
0x18000bea9  mov     [rsp+30h], r15; hTemplateFile
0x18000beae  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000beb6  mov     [rsp+100h+dwCreationDisposition], 1; dwCreationDisposition
0x18000bebe  xor     r9d, r9d; lpSecurityAttributes
0x18000bec1  xor     r8d, r8d; dwShareMode
0x18000bec4  mov     edx, 40000000h; dwDesiredAccess
0x18000bec9  mov     rcx, rbx; lpFileName
0x18000becc  call    cs:__imp_CreateFileW
0x18000bed2  mov     rsi, rax
0x18000bed5  test    rax, rax
0x18000bed8  jnz     short loc_18000BEEE
0x18000beda  call    cs:__imp_GetLastError
0x18000bee0  cmp     eax, 50h ; 'P'
0x18000bee3  jz      loc_18000BFBB
0x18000bee9  jmp     loc_18000BF9C
0x18000beee  mov     r14d, [r13+0]
0x18000bef2  mov     dword ptr [rbp+4Fh+liDistanceToMove], r14d
0x18000bef6  xor     eax, eax
0x18000bef8  mov     dword ptr [rbp+4Fh+liDistanceToMove+4], eax
0x18000befb  xor     r9d, r9d; dwMoveMethod
0x18000befe  xor     r8d, r8d; lpNewFilePointer
0x18000bf01  mov     rdi, qword ptr [rbp+4Fh+liDistanceToMove]
0x18000bf05  mov     rdx, rdi; liDistanceToMove
0x18000bf08  mov     rcx, rsi; hFile
0x18000bf0b  call    cs:__imp_SetFilePointerEx
0x18000bf11  mov     rcx, rsi; hFile
0x18000bf14  test    eax, eax
0x18000bf16  jz      short loc_18000BF96
0x18000bf18  xor     r9d, r9d; dwMoveMethod
0x18000bf1b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000bf1e  xor     edx, edx; lDistanceToMove
0x18000bf20  call    cs:__imp_SetFilePointer
0x18000bf26  mov     edx, 10000h
0x18000bf2b  mov     [rbp+4Fh+var_A4], edx
0x18000bf2e  lea     rax, [rbp+4Fh+var_A4]
0x18000bf32  lea     rcx, [rbp+4Fh+liDistanceToMove]
0x18000bf36  cmp     r14d, edx
0x18000bf39  cmovbe  rax, rcx
0x18000bf3d  mov     ecx, [rax]
0x18000bf3f  mov     r14, [r13+8]
0x18000bf43  test    ecx, ecx
0x18000bf45  jz      short loc_18000BFB2
0x18000bf47  mov     r13d, edx
0x18000bf4a  mov     [rbp+4Fh+NumberOfBytesWritten], r15d
0x18000bf4e  mov     qword ptr [rsp+100h+dwCreationDisposition], r15; lpOverlapped
0x18000bf53  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000bf57  mov     r8d, ecx; nNumberOfBytesToWrite
0x18000bf5a  mov     rdx, r14; lpBuffer
0x18000bf5d  mov     rcx, rsi; hFile
0x18000bf60  call    cs:__imp_WriteFile
0x18000bf66  test    eax, eax
0x18000bf68  jz      short loc_18000BF93
0x18000bf6a  mov     eax, [rbp+4Fh+NumberOfBytesWritten]
0x18000bf6d  sub     rdi, rax
0x18000bf70  mov     qword ptr [rbp+4Fh+liDistanceToMove], rdi
0x18000bf74  add     r14, rax
0x18000bf77  mov     [rbp+4Fh+var_9C], r13d
0x18000bf7b  lea     rax, [rbp+4Fh+var_9C]
0x18000bf7f  lea     rcx, [rbp+4Fh+liDistanceToMove]
0x18000bf83  cmp     dword ptr [rbp+4Fh+liDistanceToMove], r13d
0x18000bf87  cmovbe  rax, rcx
0x18000bf8b  mov     ecx, [rax]
0x18000bf8d  test    ecx, ecx
0x18000bf8f  jnz     short loc_18000BF4A
0x18000bf91  jmp     short loc_18000BFB2
0x18000bf93  mov     rcx, rsi; hObject
0x18000bf96  call    cs:__imp_CloseHandle
0x18000bf9c  call    cs:__imp_GetLastError
0x18000bfa2  movzx   edi, ax
0x18000bfa5  or      edi, 80070000h
0x18000bfab  test    eax, eax
0x18000bfad  cmovle  edi, eax
0x18000bfb0  jmp     short loc_18000BFBE
0x18000bfb2  mov     rcx, rsi; hObject
0x18000bfb5  call    cs:__imp_CloseHandle
0x18000bfbb  mov     edi, r15d
0x18000bfbe  cmp     [rbp+4Fh+var_68], 10h
0x18000bfc3  jb      short loc_18000BFCE
0x18000bfc5  mov     rcx, [rbp+4Fh+var_80]; Block
0x18000bfc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bfce  mov     [rbp+4Fh+var_68], 0Fh
0x18000bfd6  mov     [rbp+4Fh+var_70], r15
0x18000bfda  mov     byte ptr [rbp+4Fh+var_80], r15b
0x18000bfde  lea     rdx, [rbx-18h]
0x18000bfe2  mov     ecx, r12d
0x18000bfe5  lock xadd [rdx+10h], ecx
0x18000bfea  add     ecx, r12d
0x18000bfed  test    ecx, ecx
0x18000bfef  jg      short loc_18000C001
0x18000bff1  mov     rcx, [rdx]
0x18000bff4  mov     r8, [rcx]
0x18000bff7  mov     rax, [r8+8]
0x18000bffb  call    cs:__guard_dispatch_icall_fptr
0x18000c001  mov     eax, edi
0x18000c003  mov     rcx, [rbp+4Fh+var_38]
0x18000c007  xor     rcx, rsp; StackCookie
0x18000c00a  call    __security_check_cookie
0x18000c00f  mov     rbx, [rsp+100h+arg_18]
0x18000c017  add     rsp, 0D0h
0x18000c01e  pop     r15
0x18000c020  pop     r14
0x18000c022  pop     r13
0x18000c024  pop     r12
0x18000c026  pop     rdi
0x18000c027  pop     rsi
0x18000c028  pop     rbp
0x18000c029  retn
```
