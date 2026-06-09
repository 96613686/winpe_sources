# CFtpFileFind::FindFile(ushort const *,ulong)

- ea: `0x18006e260`
- end: `0x18006e42f`
- name: `?FindFile@CFtpFileFind@@UEAAHPEBGK@Z`
- size: `463`
- prototype: `__int64 __fastcall(CFtpFileFind *__hidden this, wchar_t *Str, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000b3a0`
- `0x18000ce50`
- `0x18000cfe0`
- `0x18000d960`
- `0x180019290`
- `0x180025ae0`
- `0x18006e260`
- `0x18006e9a0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18006e3a5`
- `msvcrt!wcsrchr` at `0x18006e3b6`
- `msvcrt!wcsrchr` at `0x18006e3a5`
- `msvcrt!wcsrchr` at `0x18006e3b6`
- `msvcrt!wcspbrk` at `0x18006e32b`
- `msvcrt!wcspbrk` at `0x18006e32b`
- `msvcrt!wcscpy_s` at `0x18006e2d4`
- `msvcrt!wcscpy_s` at `0x18006e2d4`
- `WININET!FtpSetCurrentDirectoryW` at `0x18006e35e`
- `WININET!FtpSetCurrentDirectoryW` at `0x18006e382`
- `WININET!FtpSetCurrentDirectoryW` at `0x18006e35e`
- `WININET!FtpSetCurrentDirectoryW` at `0x18006e382`
- `WININET!FtpFindFirstFileW` at `0x18006e2f5`
- `WININET!FtpFindFirstFileW` at `0x18006e2f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFtpFileFind::FindFile(CFtpFileFind *this, wchar_t *Str, DWORD dwFlags)
{
  unsigned __int64 v6; // rax
  wchar_t *v7; // rax
  const wchar_t *v8; // rbp
  HINTERNET FirstFileW; // rax
  wchar_t *v11; // rbx
  wchar_t *v12; // rbx
  wchar_t *v13; // rdi
  __int64 v14; // rdi
  __int64 v15; // r8
  __int64 v16; // rax
  LPCWSTR lpszDirectory; // [rsp+50h] [rbp+8h] BYREF
  char v18; // [rsp+68h] [rbp+20h] BYREF

  if ( !*((_QWORD *)this + 7) )
    return 0;
  if ( Str )
  {
    v6 = -1;
    do
      ++v6;
    while ( Str[v6] );
    if ( v6 >= 0x104 )
      return 0;
  }
  CFileFind::Close(this);
  v7 = (wchar_t *)operator new(0x250u);
  *((_QWORD *)this + 2) = v7;
  *((_DWORD *)this + 8) = 0;
  v8 = L"*";
  if ( Str )
    v8 = Str;
  wcscpy_s(v7 + 22, 0x104u, v8);
  FirstFileW = FtpFindFirstFileW(
                 *(HINTERNET *)(*((_QWORD *)this + 7) + 8LL),
                 v8,
                 *((LPWIN32_FIND_DATAW *)this + 2),
                 dwFlags,
                 *((_QWORD *)this + 8));
  *((_QWORD *)this + 3) = FirstFileW;
  if ( !FirstFileW )
  {
    CFileFind::Close(this);
    return 0;
  }
  v11 = wcspbrk(v8, L"\\/");
  lpszDirectory = _afxPchNil;
  CFtpConnection::GetCurrentDirectoryW(*((CFtpConnection **)this + 7), (struct CString *)&lpszDirectory);
  if ( v11 )
  {
    v12 = wcsrchr(v8, 0x5Cu);
    v13 = wcsrchr(v8, 0x2Fu);
    if ( !v13 )
      v13 = (wchar_t *)v8;
    if ( !v12 )
      v12 = (wchar_t *)v8;
    if ( v13 < v12 )
      v13 = v12;
    v14 = v13 - v8;
    CString::operator=((char *)this + 40, v8);
    v15 = 1;
    if ( (_DWORD)v14 )
      v15 = (unsigned int)v14;
    v16 = CString::Left((char *)this + 40, &v18, v15);
    CString::operator=((char *)this + 40, v16);
    CString::~CString((CString *)&v18);
  }
  else if ( FtpSetCurrentDirectoryW(*(HINTERNET *)(*((_QWORD *)this + 7) + 8LL), v8) )
  {
    CFtpConnection::GetCurrentDirectoryW(*((CFtpConnection **)this + 7), (CFtpFileFind *)((char *)this + 40));
    FtpSetCurrentDirectoryW(*(HINTERNET *)(*((_QWORD *)this + 7) + 8LL), lpszDirectory);
  }
  else
  {
    CString::operator=((char *)this + 40, &lpszDirectory);
  }
  CString::~CString((CString *)&lpszDirectory);
  return 1;
}

```

## disassembly

```asm
0x18006e260  mov     [rsp+arg_8], rbx
0x18006e265  mov     [rsp+arg_10], rbp
0x18006e26a  push    rsi
0x18006e26b  push    rdi
0x18006e26c  push    r14
0x18006e26e  sub     rsp, 30h
0x18006e272  mov     edi, r8d
0x18006e275  mov     rbx, rdx
0x18006e278  mov     rsi, rcx
0x18006e27b  xor     r14d, r14d
0x18006e27e  cmp     [rcx+38h], r14
0x18006e282  jz      loc_18006E30C
0x18006e288  test    rdx, rdx
0x18006e28b  jz      short loc_18006E2A3
0x18006e28d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e291  inc     rax
0x18006e294  cmp     [rdx+rax*2], r14w
0x18006e299  jnz     short loc_18006E291
0x18006e29b  cmp     rax, 104h
0x18006e2a1  jnb     short loc_18006E30C
0x18006e2a3  call    ?Close@CFileFind@@QEAAXXZ; CFileFind::Close(void)
0x18006e2a8  mov     ecx, 250h; Size
0x18006e2ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e2b2  mov     [rsi+10h], rax
0x18006e2b6  mov     [rsi+20h], r14d
0x18006e2ba  lea     rbp, asc_1800FC914; "*"
0x18006e2c1  test    rbx, rbx
0x18006e2c4  cmovnz  rbp, rbx
0x18006e2c8  lea     rcx, [rax+2Ch]; Destination
0x18006e2cc  mov     r8, rbp; Source
0x18006e2cf  mov     edx, 104h; SizeInWords
0x18006e2d4  call    cs:__imp_wcscpy_s
0x18006e2da  mov     rcx, [rsi+38h]
0x18006e2de  mov     rax, [rsi+40h]
0x18006e2e2  mov     [rsp+48h+dwContext], rax; dwContext
0x18006e2e7  mov     r9d, edi; dwFlags
0x18006e2ea  mov     r8, [rsi+10h]; lpFindFileData
0x18006e2ee  mov     rdx, rbp; lpszSearchFile
0x18006e2f1  mov     rcx, [rcx+8]; hConnect
0x18006e2f5  call    cs:__imp_FtpFindFirstFileW
0x18006e2fb  mov     [rsi+18h], rax
0x18006e2ff  test    rax, rax
0x18006e302  jnz     short loc_18006E321
0x18006e304  mov     rcx, rsi; this
0x18006e307  call    ?Close@CFileFind@@QEAAXXZ; CFileFind::Close(void)
0x18006e30c  xor     eax, eax
0x18006e30e  mov     rbx, [rsp+48h+arg_8]
0x18006e313  mov     rbp, [rsp+48h+arg_10]
0x18006e318  add     rsp, 30h
0x18006e31c  pop     r14
0x18006e31e  pop     rdi
0x18006e31f  pop     rsi
0x18006e320  retn
0x18006e321  lea     rdx, Control; "\\/"
0x18006e328  mov     rcx, rbp; String
0x18006e32b  call    cs:__imp_wcspbrk
0x18006e331  mov     rbx, rax
0x18006e334  mov     rcx, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x18006e33b  mov     [rsp+48h+lpszDirectory], rcx
0x18006e340  lea     rdx, [rsp+48h+lpszDirectory]; struct CString *
0x18006e345  mov     rcx, [rsi+38h]; this
0x18006e349  call    ?GetCurrentDirectoryW@CFtpConnection@@QEBAHAEAVCString@@@Z; CFtpConnection::GetCurrentDirectoryW(CString &)
0x18006e34e  test    rbx, rbx
0x18006e351  jnz     short loc_18006E39D
0x18006e353  mov     rcx, [rsi+38h]
0x18006e357  mov     rdx, rbp; lpszDirectory
0x18006e35a  mov     rcx, [rcx+8]; hConnect
0x18006e35e  call    cs:__imp_FtpSetCurrentDirectoryW
0x18006e364  test    eax, eax
0x18006e366  jz      short loc_18006E38D
0x18006e368  lea     rdx, [rsi+28h]; struct CString *
0x18006e36c  mov     rcx, [rsi+38h]; this
0x18006e370  call    ?GetCurrentDirectoryW@CFtpConnection@@QEBAHAEAVCString@@@Z; CFtpConnection::GetCurrentDirectoryW(CString &)
0x18006e375  mov     rcx, [rsi+38h]
0x18006e379  mov     rdx, [rsp+48h+lpszDirectory]; lpszDirectory
0x18006e37e  mov     rcx, [rcx+8]; hConnect
0x18006e382  call    cs:__imp_FtpSetCurrentDirectoryW
0x18006e388  jmp     loc_18006E41B
0x18006e38d  lea     rdx, [rsp+48h+lpszDirectory]
0x18006e392  lea     rcx, [rsi+28h]
0x18006e396  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18006e39b  jmp     short loc_18006E41B
0x18006e39d  mov     edx, 5Ch ; '\'; Ch
0x18006e3a2  mov     rcx, rbp; Str
0x18006e3a5  call    cs:__imp_wcsrchr
0x18006e3ab  mov     rbx, rax
0x18006e3ae  mov     edx, 2Fh ; '/'; Ch
0x18006e3b3  mov     rcx, rbp; Str
0x18006e3b6  call    cs:__imp_wcsrchr
0x18006e3bc  mov     rdi, rax
0x18006e3bf  test    rax, rax
0x18006e3c2  cmovz   rdi, rbp
0x18006e3c6  test    rbx, rbx
0x18006e3c9  cmovz   rbx, rbp
0x18006e3cd  cmp     rdi, rbx
0x18006e3d0  jnb     short loc_18006E3D5
0x18006e3d2  mov     rdi, rbx
0x18006e3d5  sub     rdi, rbp
0x18006e3d8  sar     rdi, 1
0x18006e3db  lea     rbx, [rsi+28h]
0x18006e3df  mov     rdx, rbp
0x18006e3e2  mov     rcx, rbx
0x18006e3e5  call    ??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18006e3ea  mov     r8d, 1
0x18006e3f0  test    edi, edi
0x18006e3f2  cmovnz  r8d, edi
0x18006e3f6  lea     rdx, [rsp+48h+arg_18]
0x18006e3fb  mov     rcx, rbx
0x18006e3fe  call    ?Left@CString@@QEBA?AV1@H@Z; CString::Left(int)
0x18006e403  nop
0x18006e404  mov     rdx, rax
0x18006e407  mov     rcx, rbx
0x18006e40a  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18006e40f  nop
0x18006e410  lea     rcx, [rsp+48h+arg_18]; this
0x18006e415  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18006e41a  nop
0x18006e41b  lea     rcx, [rsp+48h+lpszDirectory]; this
0x18006e420  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18006e425  mov     eax, 1
0x18006e42a  jmp     loc_18006E30E
```
