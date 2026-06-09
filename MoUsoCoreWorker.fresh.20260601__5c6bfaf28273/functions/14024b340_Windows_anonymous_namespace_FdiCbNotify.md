# Windows::_anonymous_namespace_::FdiCbNotify

- ea: `0x14024b340`
- end: `0x14024b982`
- name: `Windows::_anonymous_namespace_::FdiCbNotify`
- size: `1602`
- prototype: `INT_PTR __fastcall(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops`

## callees

- `0x14002b6ec`
- `0x140034318`
- `0x1400447ac`
- `0x140044b18`
- `0x140044b90`
- `0x140044f20`
- `0x140045184`
- `0x140045404`
- `0x140249f30`
- `0x14024a094`
- `0x14024a704`
- `0x14024a920`
- `0x14024b0d0`
- `0x14024b340`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14024b656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14024b656`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x14024b821`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x14024b821`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14024b624`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14024b8f6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14024b624`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14024b8f6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x14024b7fd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x14024b7fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
INT_PTR __fastcall Windows::_anonymous_namespace_::FdiCbNotify(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  int v3; // ecx
  int v4; // ecx
  __int64 v5; // rdi
  char *psz1; // rdx
  __int64 v7; // r8
  __int64 v8; // r14
  _QWORD *pv; // r14
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int128 v15; // xmm7
  __m128i v16; // xmm6
  wil *v17; // rcx
  __int64 v18; // rax
  const WCHAR *v19; // rcx
  LPCWSTR *v20; // rcx
  INT_PTR v21; // rax
  signed int LastError; // eax
  unsigned int v23; // ecx
  char *v24; // rdx
  __int64 v25; // rdi
  USHORT attribs; // r8
  int v27; // edx
  int v28; // ecx
  DWORD v29; // edi
  __int64 v30; // rcx
  __int64 v31; // rax
  const WCHAR *v32; // rcx
  __int64 v33; // rbx
  _BYTE v34[40]; // [rsp+40h] [rbp-138h] BYREF
  _OWORD v35[2]; // [rsp+68h] [rbp-110h] BYREF
  _BYTE v36[32]; // [rsp+88h] [rbp-F0h] BYREF
  struct _FILETIME FileTime; // [rsp+A8h] [rbp-D0h] BYREF
  LPCWSTR v38[2]; // [rsp+B0h] [rbp-C8h] BYREF
  __m128i v39; // [rsp+C0h] [rbp-B8h]
  __int128 v40; // [rsp+D0h] [rbp-A8h] BYREF
  __int128 v41; // [rsp+E0h] [rbp-98h]
  LPCWSTR lpFileName[2]; // [rsp+F0h] [rbp-88h] BYREF
  __m128i si128; // [rsp+100h] [rbp-78h]
  __int128 v44; // [rsp+110h] [rbp-68h] BYREF
  __int128 v45; // [rsp+120h] [rbp-58h]

  v3 = fdint - 2;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 1 )
        return -1;
      return 0;
    }
    v5 = -1;
    goto LABEL_30;
  }
  v40 = 0;
  *(_QWORD *)&v41 = 0;
  *((_QWORD *)&v41 + 1) = 7;
  LOWORD(v40) = 0;
  psz1 = pfdin->psz1;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  v5 = -1;
  v7 = -1;
  do
    ++v7;
  while ( psz1[v7] );
  try
  {
    std::string::_Construct<1,char const *>(v38, psz1);
    v8 = MultiByteToUnicode(v34, v38);
    if ( &v40 != (__int128 *)v8 )
    {
      std::wstring::~wstring(&v40);
      v40 = *(_OWORD *)v8;
      v41 = *(_OWORD *)(v8 + 16);
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 7;
      *(_WORD *)v8 = 0;
    }
    std::wstring::~wstring(v34);
    std::string::_Tidy_deallocate(v38);
  }
  catch ( ... )
  {
    std::wstring::~wstring(&v40);
    return 0;
  }
  pv = pfdin->pv;
  FileTime = (struct _FILETIME)pv;
  if ( *(_DWORD *)pv )
  {
    std::wstring::~wstring(&v40);
LABEL_30:
    v44 = 0;
    *(_QWORD *)&v45 = 0;
    *((_QWORD *)&v45 + 1) = 7;
    LOWORD(v44) = 0;
    v24 = pfdin->psz1;
    *(_OWORD *)v38 = 0;
    v39 = 0;
    do
      ++v5;
    while ( v24[v5] );
    try
    {
      std::string::_Construct<1,char const *>(v38, v24);
      v25 = MultiByteToUnicode(v34, v38);
      if ( &v44 != (__int128 *)v25 )
      {
        std::wstring::~wstring(&v44);
        v44 = *(_OWORD *)v25;
        v45 = *(_OWORD *)(v25 + 16);
        *(_QWORD *)(v25 + 16) = 0;
        *(_QWORD *)(v25 + 24) = 7;
        *(_WORD *)v25 = 0;
      }
      std::wstring::~wstring(v34);
      std::string::_Tidy_deallocate(v38);
      attribs = pfdin->attribs;
      v27 = attribs & 1 | 0x20;
      if ( (attribs & 0x20) == 0 )
        v27 = pfdin->attribs & 1;
      v28 = v27 | 2;
      if ( (attribs & 2) == 0 )
        v28 = v27;
      v29 = v28 | 4;
      if ( (attribs & 4) == 0 )
        v29 = v28;
      if ( !v29 )
        v29 = 128;
      FileTime = 0;
      if ( DosDateTimeToFileTime(pfdin->date, pfdin->time, &FileTime) )
        SetFileTime(*(HANDLE *)pfdin->hf, &FileTime, 0, &FileTime);
      Windows::_anonymous_namespace_::FdiCbFileClose(pfdin->hf);
    }
    catch ( ... )
    {
      v33 = 0;
      goto LABEL_50;
    }
    v30 = *((_QWORD *)pfdin->pv + 3);
    if ( v30 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    std::wstring::wstring(v34, v30, L"\\", 1);
    v31 = std::wstring::append(v34);
    *(_OWORD *)v38 = 0;
    v39 = 0;
    *(_OWORD *)v38 = *(_OWORD *)v31;
    v39 = *(__m128i *)(v31 + 16);
    *(_WORD *)v31 = 0;
    *(_QWORD *)(v31 + 16) = 0;
    *(_QWORD *)(v31 + 24) = 7;
    v32 = (const WCHAR *)v38;
    if ( v39.m128i_i64[1] > 7uLL )
      v32 = v38[0];
    SetFileAttributesW(v32, v29);
    std::wstring::~wstring(v38);
    std::wstring::~wstring(v34);
    v33 = 1;
LABEL_50:
    std::wstring::~wstring(&v44);
    return v33;
  }
  v10 = std::wstring::wstring(v34, &v40);
  LOBYTE(v11) = 1;
  if ( (unsigned __int8)Windows::_anonymous_namespace_::ValidateFilePath(v10, v11) )
  {
    try
    {
      *(_OWORD *)lpFileName = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(lpFileName[0]) = 0;
      v13 = pv[3];
      if ( v13 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      std::wstring::wstring(v36, v13, L"\\", 1);
      v14 = std::wstring::append(v36);
      v35[0] = *(_OWORD *)v14;
      v15 = v35[0];
      v16 = *(__m128i *)(v14 + 16);
      *(_WORD *)v14 = 0;
      *(_QWORD *)(v14 + 16) = 0;
      *(_QWORD *)(v14 + 24) = 7;
      std::wstring::~wstring(lpFileName);
      *(_OWORD *)lpFileName = v15;
      si128 = v16;
      v35[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v35[0]) = 0;
      std::wstring::~wstring(v35);
      std::wstring::~wstring(v36);
    }
    catch ( ... )
    {
      *(_DWORD *)(*(_QWORD *)&FileTime + 104LL) = wil::ResultFromCaughtException(v17);
      goto LABEL_27;
    }
    try
    {
      *(_OWORD *)v38 = 0;
      v39 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v38[0]) = 0;
      v18 = UnicodeToMultiByte(v34, lpFileName);
      std::string::operator=(v38, v18);
      std::string::_Tidy_deallocate(v34);
      v19 = (const WCHAR *)lpFileName;
      if ( si128.m128i_i64[1] > 7uLL )
        v19 = lpFileName[0];
      SetFileAttributesW(v19, 0x80u);
      v20 = v38;
      if ( v39.m128i_i64[1] > 0xFuLL )
        v20 = (LPCWSTR *)v38[0];
    }
    catch ( ... )
    {
      *(_DWORD *)(*(_QWORD *)&FileTime + 104LL) = wil::ResultFromCaughtException((wil *)v20);
      std::string::_Tidy_deallocate(v38);
LABEL_27:
      std::wstring::~wstring(lpFileName);
      std::wstring::~wstring(&v40);
      return -1;
    }
    v21 = Windows::_anonymous_namespace_::FdiCbFileOpen((LPSTR)v20, 0x8121u, 0);
    if ( v21 == -1 )
    {
      LastError = GetLastError();
      v23 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v23 = LastError;
      *((_DWORD *)pv + 26) = v23;
    }
    else
    {
      v5 = v21;
    }
    std::string::_Tidy_deallocate(v38);
    std::wstring::~wstring(lpFileName);
  }
  std::wstring::~wstring(&v40);
  return v5;
}

```

## disassembly

```asm
0x14024b340  mov     rax, rsp
0x14024b343  mov     [rax+8], rbx
0x14024b347  mov     [rax+18h], rsi
0x14024b34b  mov     [rax+20h], rdi
0x14024b34f  push    r12
0x14024b351  push    r14
0x14024b353  push    r15
0x14024b355  sub     rsp, 160h
0x14024b35c  movaps  xmmword ptr [rax-28h], xmm6
0x14024b360  movaps  xmmword ptr [rax-38h], xmm7
0x14024b364  mov     rax, cs:__security_cookie
0x14024b36b  xor     rax, rsp
0x14024b36e  mov     [rsp+178h+var_48], rax
0x14024b376  mov     r15, rdx
0x14024b379  xor     ebx, ebx
0x14024b37b  sub     ecx, 2
0x14024b37e  jz      short loc_14024B39F
0x14024b380  sub     ecx, 1
0x14024b383  jz      short loc_14024B393
0x14024b385  cmp     ecx, 1
0x14024b388  jnz     loc_14024B93C
0x14024b38e  jmp     loc_14024B6BD
0x14024b393  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14024b397  lea     esi, [rdi+8]
0x14024b39a  jmp     loc_14024B6D3
0x14024b39f  xorps   xmm0, xmm0
0x14024b3a2  movups  [rsp+178h+var_A8], xmm0
0x14024b3aa  mov     qword ptr [rsp+178h+var_98], rbx
0x14024b3b2  mov     esi, 7
0x14024b3b7  mov     qword ptr [rsp+178h+var_98+8], rsi
0x14024b3bf  mov     word ptr [rsp+178h+var_A8], bx
0x14024b3c7  mov     rdx, [rdx+8]
0x14024b3cb  movups  xmmword ptr [rsp+178h+var_C8], xmm0
0x14024b3d3  xorps   xmm1, xmm1
0x14024b3d6  movdqu  [rsp+178h+var_B8], xmm1
0x14024b3df  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14024b3e3  mov     r8, rdi
0x14024b3e6  inc     r8
0x14024b3e9  cmp     [rdx+r8], bl
0x14024b3ed  jnz     short loc_14024B3E6
0x14024b3ef  lea     rcx, [rsp+178h+var_C8]
0x14024b3f7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14024b3fc  nop
0x14024b3fd  lea     rdx, [rsp+178h+var_C8]
0x14024b405  lea     rcx, [rsp+178h+var_138]
0x14024b40a  call    MultiByteToUnicode
0x14024b40f  mov     r14, rax
0x14024b412  lea     rax, [rsp+178h+var_A8]
0x14024b41a  cmp     rax, r14
0x14024b41d  jz      short loc_14024B451
0x14024b41f  lea     rcx, [rsp+178h+var_A8]
0x14024b427  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b42c  movups  xmm0, xmmword ptr [r14]
0x14024b430  movups  [rsp+178h+var_A8], xmm0
0x14024b438  movups  xmm1, xmmword ptr [r14+10h]
0x14024b43d  movups  [rsp+178h+var_98], xmm1
0x14024b445  mov     [r14+10h], rbx
0x14024b449  mov     [r14+18h], rsi
0x14024b44d  mov     [r14], bx
0x14024b451  lea     rcx, [rsp+178h+var_138]
0x14024b456  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b45b  nop
0x14024b45c  lea     rcx, [rsp+178h+var_C8]
0x14024b464  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14024b469  nop
0x14024b46a  mov     r14, [r15+20h]
0x14024b46e  mov     qword ptr [rsp+178h+FileTime.dwLowDateTime], r14
0x14024b476  cmp     [r14], ebx
0x14024b479  jnz     loc_14024B6C6
0x14024b47f  lea     rdx, [rsp+178h+var_A8]
0x14024b487  lea     rcx, [rsp+178h+var_138]
0x14024b48c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14024b491  mov     dl, 1
0x14024b493  mov     rcx, rax
0x14024b496  call    Windows___anonymous_namespace___ValidateFilePath
0x14024b49b  test    al, al
0x14024b49d  jnz     short loc_14024B4B4
0x14024b49f  lea     rcx, [rsp+178h+var_A8]
0x14024b4a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b4ac  mov     rax, rdi
0x14024b4af  jmp     loc_14024B93E
0x14024b4b4  xorps   xmm0, xmm0
0x14024b4b7  movups  xmmword ptr [rsp+178h+lpFileName], xmm0
0x14024b4bf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14024b4c7  movdqu  [rsp+178h+var_78], xmm1
0x14024b4d0  mov     word ptr [rsp+178h+lpFileName], bx
0x14024b4d8  lea     r9, [r14+8]
0x14024b4dc  mov     rcx, [r9+10h]
0x14024b4e0  mov     rax, 7FFFFFFFFFFFFFFEh
0x14024b4ea  sub     rax, rcx
0x14024b4ed  cmp     rax, 1
0x14024b4f1  jb      loc_14024B976
0x14024b4f7  cmp     [r9+18h], rsi
0x14024b4fb  jbe     short loc_14024B500
0x14024b4fd  mov     r9, [r9]
0x14024b500  mov     [rsp+178h+var_148], 1; __int64
0x14024b509  lea     rax, asc_14041A8E0; "\\"
0x14024b510  mov     [rsp+178h+Src], rax; Src
0x14024b515  mov     [rsp+178h+var_158], rcx; __int64
0x14024b51a  lea     rcx, [rsp+178h+var_F0]; void *
0x14024b522  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14024b527  nop
0x14024b528  lea     rdx, [rsp+178h+var_A8]
0x14024b530  cmp     qword ptr [rsp+178h+var_98+8], rsi
0x14024b538  cmova   rdx, qword ptr [rsp+178h+var_A8]
0x14024b541  mov     r8, qword ptr [rsp+178h+var_98]
0x14024b549  lea     rcx, [rsp+178h+var_F0]; Src
0x14024b551  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x14024b556  movups  xmm7, xmmword ptr [rax]
0x14024b559  movups  [rsp+178h+var_110], xmm7
0x14024b55e  movups  xmm6, xmmword ptr [rax+10h]
0x14024b562  mov     [rax], bx
0x14024b565  mov     [rax+10h], rbx
0x14024b569  mov     [rax+18h], rsi
0x14024b56d  lea     rcx, [rsp+178h+lpFileName]
0x14024b575  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b57a  movups  xmmword ptr [rsp+178h+lpFileName], xmm7
0x14024b582  movups  [rsp+178h+var_78], xmm6
0x14024b58a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14024b592  movdqu  [rsp+178h+var_100], xmm0
0x14024b598  mov     word ptr [rsp+178h+var_110], bx
0x14024b59d  lea     rcx, [rsp+178h+var_110]
0x14024b5a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b5a7  nop
0x14024b5a8  lea     rcx, [rsp+178h+var_F0]
0x14024b5b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b5b5  nop
0x14024b5b6  xorps   xmm0, xmm0
0x14024b5b9  movups  xmmword ptr [rsp+178h+var_C8], xmm0
0x14024b5c1  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x14024b5c9  movdqu  [rsp+178h+var_B8], xmm1
0x14024b5d2  mov     byte ptr [rsp+178h+var_C8], bl
0x14024b5d9  lea     rdx, [rsp+178h+lpFileName]
0x14024b5e1  lea     rcx, [rsp+178h+var_138]
0x14024b5e6  call    UnicodeToMultiByte
0x14024b5eb  mov     rdx, rax
0x14024b5ee  lea     rcx, [rsp+178h+var_C8]
0x14024b5f6  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14024b5fb  lea     rcx, [rsp+178h+var_138]
0x14024b600  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14024b605  nop
0x14024b606  lea     rcx, [rsp+178h+lpFileName]
0x14024b60e  cmp     qword ptr [rsp+178h+var_78+8], rsi
0x14024b616  cmova   rcx, [rsp+178h+lpFileName]; lpFileName
0x14024b61f  mov     edx, 80h; dwFileAttributes
0x14024b624  call    cs:__imp_SetFileAttributesW
0x14024b62a  lea     rcx, [rsp+178h+var_C8]
0x14024b632  cmp     qword ptr [rsp+178h+var_B8+8], 0Fh
0x14024b63b  cmova   rcx, [rsp+178h+var_C8]; pszFile
0x14024b644  xor     r8d, r8d; pmode
0x14024b647  mov     edx, 8121h; oflag
0x14024b64c  call    Windows___anonymous_namespace___FdiCbFileOpen
0x14024b651  cmp     rax, rdi
0x14024b654  jnz     short loc_14024B670
0x14024b656  call    cs:__imp_GetLastError
0x14024b65c  movzx   ecx, ax
0x14024b65f  or      ecx, 80070000h
0x14024b665  test    eax, eax
0x14024b667  cmovle  ecx, eax
0x14024b66a  mov     [r14+68h], ecx
0x14024b66e  jmp     short loc_14024B673
0x14024b670  mov     rdi, rax
0x14024b673  lea     rcx, [rsp+178h+var_C8]
0x14024b67b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14024b680  nop
0x14024b681  lea     rcx, [rsp+178h+lpFileName]
0x14024b689  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b68e  jmp     loc_14024B49F
0x14024b693  lea     rcx, [rsp+178h+var_C8]
0x14024b69b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14024b6a0  jmp     short $+2
0x14024b6a2  lea     rcx, [rsp+178h+lpFileName]
0x14024b6aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b6af  nop
0x14024b6b0  lea     rcx, [rsp+178h+var_A8]
0x14024b6b8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b6bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x14024b6c1  jmp     loc_14024B93E
0x14024b6c6  lea     rcx, [rsp+178h+var_A8]
0x14024b6ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b6d3  xorps   xmm0, xmm0
0x14024b6d6  movups  [rsp+178h+var_68], xmm0
0x14024b6de  mov     r14, rbx
0x14024b6e1  mov     qword ptr [rsp+178h+var_58], rbx
0x14024b6e9  mov     r12, rsi
0x14024b6ec  mov     qword ptr [rsp+178h+var_58+8], rsi
0x14024b6f4  mov     word ptr [rsp+178h+var_68], bx
0x14024b6fc  mov     rdx, [r15+8]
0x14024b700  movups  xmmword ptr [rsp+178h+var_C8], xmm0
0x14024b708  xorps   xmm1, xmm1
0x14024b70b  movdqu  [rsp+178h+var_B8], xmm1
0x14024b714  inc     rdi
0x14024b717  cmp     [rdx+rdi], bl
0x14024b71a  jnz     short loc_14024B714
0x14024b71c  mov     r8, rdi
0x14024b71f  lea     rcx, [rsp+178h+var_C8]
0x14024b727  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14024b72c  nop
0x14024b72d  lea     rdx, [rsp+178h+var_C8]
0x14024b735  lea     rcx, [rsp+178h+var_138]
0x14024b73a  call    MultiByteToUnicode
0x14024b73f  mov     rdi, rax
0x14024b742  lea     rax, [rsp+178h+var_68]
0x14024b74a  cmp     rax, rdi
0x14024b74d  jz      short loc_14024B791
0x14024b74f  lea     rcx, [rsp+178h+var_68]
0x14024b757  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b75c  movups  xmm0, xmmword ptr [rdi]
0x14024b75f  movups  [rsp+178h+var_68], xmm0
0x14024b767  movups  xmm1, xmmword ptr [rdi+10h]
0x14024b76b  movups  [rsp+178h+var_58], xmm1
0x14024b773  mov     [rdi+10h], rbx
0x14024b777  mov     [rdi+18h], rsi
0x14024b77b  mov     [rdi], bx
0x14024b77e  movdqa  xmm0, xmm1
0x14024b782  psrldq  xmm0, 8
0x14024b787  movq    r12, xmm0
0x14024b78c  movq    r14, xmm1
0x14024b791  lea     rcx, [rsp+178h+var_138]
0x14024b796  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b79b  nop
0x14024b79c  lea     rcx, [rsp+178h+var_C8]
0x14024b7a4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14024b7a9  nop
0x14024b7aa  movzx   r8d, word ptr [r15+34h]
0x14024b7af  mov     ecx, r8d
0x14024b7b2  and     ecx, 1
0x14024b7b5  mov     edx, ecx
0x14024b7b7  or      edx, 20h
0x14024b7ba  test    r8b, 20h
0x14024b7be  cmovz   edx, ecx
0x14024b7c1  mov     ecx, edx
0x14024b7c3  or      ecx, 2
0x14024b7c6  test    r8b, 2
0x14024b7ca  cmovz   ecx, edx
0x14024b7cd  mov     edi, ecx
0x14024b7cf  or      edi, 4
0x14024b7d2  test    r8b, 4
0x14024b7d6  cmovz   edi, ecx
0x14024b7d9  mov     eax, 80h
0x14024b7de  test    edi, edi
0x14024b7e0  cmovz   edi, eax
0x14024b7e3  mov     qword ptr [rsp+178h+FileTime.dwLowDateTime], rbx
0x14024b7eb  lea     r8, [rsp+178h+FileTime]; lpFileTime
0x14024b7f3  movzx   edx, word ptr [r15+32h]; wFatTime
0x14024b7f8  movzx   ecx, word ptr [r15+30h]; wFatDate
0x14024b7fd  call    cs:__imp_DosDateTimeToFileTime
0x14024b803  test    eax, eax
0x14024b805  jz      short loc_14024B827
0x14024b807  mov     rcx, [r15+28h]
0x14024b80b  lea     r9, [rsp+178h+FileTime]; lpLastWriteTime
0x14024b813  xor     r8d, r8d; lpLastAccessTime
0x14024b816  lea     rdx, [rsp+178h+FileTime]; lpCreationTime
0x14024b81e  mov     rcx, [rcx]; hFile
0x14024b821  call    cs:__imp_SetFileTime
0x14024b827  mov     rcx, [r15+28h]; hf
0x14024b82b  call    Windows___anonymous_namespace___FdiCbFileClose
0x14024b830  mov     r9, [r15+20h]
0x14024b834  add     r9, 8
0x14024b838  mov     rcx, [r9+10h]
0x14024b83c  mov     rax, 7FFFFFFFFFFFFFFEh
0x14024b846  sub     rax, rcx
0x14024b849  cmp     rax, 1
0x14024b84d  jb      loc_14024B97C
0x14024b853  cmp     [r9+18h], rsi
0x14024b857  jbe     short loc_14024B85C
0x14024b859  mov     r9, [r9]
0x14024b85c  mov     [rsp+178h+var_148], 1; __int64
0x14024b865  lea     rax, asc_14041A8E0; "\\"
0x14024b86c  mov     [rsp+178h+Src], rax; Src
0x14024b871  mov     [rsp+178h+var_158], rcx; __int64
0x14024b876  lea     rcx, [rsp+178h+var_138]; void *
0x14024b87b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14024b880  nop
0x14024b881  lea     rdx, [rsp+178h+var_68]
0x14024b889  cmp     r12, rsi
0x14024b88c  cmova   rdx, qword ptr [rsp+178h+var_68]
0x14024b895  mov     r8, r14
0x14024b898  lea     rcx, [rsp+178h+var_138]; Src
0x14024b89d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x14024b8a2  xorps   xmm0, xmm0
0x14024b8a5  movups  xmmword ptr [rsp+178h+var_C8], xmm0
0x14024b8ad  xorps   xmm1, xmm1
0x14024b8b0  movdqu  [rsp+178h+var_B8], xmm1
0x14024b8b9  movups  xmm0, xmmword ptr [rax]
0x14024b8bc  movups  xmmword ptr [rsp+178h+var_C8], xmm0
0x14024b8c4  movups  xmm1, xmmword ptr [rax+10h]
0x14024b8c8  movups  [rsp+178h+var_B8], xmm1
0x14024b8d0  mov     [rax], bx
0x14024b8d3  mov     [rax+10h], rbx
0x14024b8d7  mov     [rax+18h], rsi
0x14024b8db  lea     rcx, [rsp+178h+var_C8]
0x14024b8e3  cmp     qword ptr [rsp+178h+var_B8+8], rsi
0x14024b8eb  cmova   rcx, [rsp+178h+var_C8]; lpFileName
0x14024b8f4  mov     edx, edi; dwFileAttributes
0x14024b8f6  call    cs:__imp_SetFileAttributesW
0x14024b8fc  lea     rcx, [rsp+178h+var_C8]
0x14024b904  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024b909  nop
0x14024b90a  lea     rcx, [rsp+178h+var_138]
  ... truncated ...
```
