# GetTempCatalogPath(ushort const *,ushort *,unsigned __int64)

- ea: `0x180014bf8`
- end: `0x180015009`
- name: `?GetTempCatalogPath@@YAJPEBGPEAG_K@Z`
- size: `1041`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180010abc`

## callees

- `0x180003400`
- `0x180004558`
- `0x18000be68`
- `0x18000de1c`
- `0x18000fa4c`
- `0x1800100a0`
- `0x180014bf8`
- `0x180018f58`
- `0x18001958c`
- `0x180019618`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014d13`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014d13`
- `KERNEL32!GetTempPathW` at `0x180014c8d`
- `KERNEL32!GetTempPathW` at `0x180014c8d`
- `KERNEL32!CreateDirectoryW` at `0x180014eeb`
- `KERNEL32!CreateDirectoryW` at `0x180014eeb`
- `KERNEL32!GetFullPathNameW` at `0x180014cd2`
- `KERNEL32!GetFullPathNameW` at `0x180014cd2`
- `KERNEL32!GetLastError` at `0x180014c9d`
- `KERNEL32!GetLastError` at `0x180014ce2`
- `KERNEL32!GetLastError` at `0x180014efb`
- `KERNEL32!GetLastError` at `0x180014f0e`
- `KERNEL32!GetLastError` at `0x180014c9d`
- `KERNEL32!GetLastError` at `0x180014ce2`
- `KERNEL32!GetLastError` at `0x180014efb`
- `KERNEL32!GetLastError` at `0x180014f0e`
- `ole32!CoCreateGuid` at `0x180014e19`
- `ole32!CoCreateGuid` at `0x180014e19`
- `ole32!StringFromGUID2` at `0x180014e3e`
- `ole32!StringFromGUID2` at `0x180014e3e`

## string_xrefs

- `0x180014fc2`: `Failed to update new catalog path for %ws`
- `0x180014fc9`: `GetTempCatalogPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetTempCatalogPath(unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  wchar_t *v7; // rax
  wchar_t *v8; // rdx
  unsigned __int64 v9; // r8
  __int64 v10; // r8
  void **v11; // rax
  char **p_pguid_8; // rcx
  unsigned __int64 v13; // r8
  __int64 v14; // r8
  void **v15; // rax
  const WCHAR *v16; // rcx
  signed int v17; // eax
  LPCWSTR *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r9
  unsigned __int16 *v21; // rdx
  unsigned __int16 v22; // r8
  unsigned __int16 *v23; // rcx
  LPWSTR FilePart[2]; // [rsp+28h] [rbp-E0h] BYREF
  LPCWSTR lpPathName_8[2]; // [rsp+38h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+48h] [rbp-C0h]
  GUID pguid_8; // [rsp+58h] [rbp-B0h] BYREF
  __m128i v29; // [rsp+68h] [rbp-A0h]
  __int128 Src_8; // [rsp+78h] [rbp-90h] BYREF
  __int128 v31; // [rsp+88h] [rbp-80h]
  __int128 v32; // [rsp+98h] [rbp-70h] BYREF
  __int128 v33; // [rsp+A8h] [rbp-60h]
  OLECHAR sz[56]; // [rsp+B8h] [rbp-50h] BYREF
  WCHAR Buffer[264]; // [rsp+128h] [rbp+20h] BYREF
  WCHAR Str[264]; // [rsp+338h] [rbp+230h] BYREF

  FilePart[1] = (LPWSTR)-2LL;
  v4 = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(Str, 0, 0x208u);
  FilePart[0] = 0;
  *(_OWORD *)lpPathName_8 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpPathName_8[0]) = 0;
  if ( GetTempPathW(0x104u, Buffer) )
    goto LABEL_12;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_12:
    if ( !GetFullPathNameW(a2, 0x104u, Str, FilePart) )
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( v4 < 0 )
        goto LABEL_19;
    }
    v7 = wcsstr(Str, L"\\V4Connections\\");
    v8 = v7;
    if ( v7 )
      v8 = v7 + 15;
    else
      v4 = -2147467259;
    if ( v4 >= 0 )
    {
      pguid_8 = 0;
      v29 = 0;
      if ( v8 == FilePart[0] - 1 )
      {
        v29 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(pguid_8.Data1) = 0;
      }
      else
      {
        std::wstring::_Construct<1,unsigned short const *>(&pguid_8, v8, FilePart[0] - 1 - v8);
      }
      Src_8 = 0;
      v31 = 0;
      v9 = -1;
      do
        ++v9;
      while ( Buffer[v9] );
      std::wstring::_Construct<1,unsigned short const *>(&Src_8, Buffer, v9);
      v11 = std::wstring::append((void **)&Src_8, &pguid_8, v10);
      v32 = *(_OWORD *)v11;
      v33 = *((_OWORD *)v11 + 1);
      v11[2] = 0;
      v11[3] = (void *)7;
      *(_WORD *)v11 = 0;
      std::wstring::operator=((char **)lpPathName_8, (__int64)&v32);
      std::wstring::~wstring((char **)&v32);
      std::wstring::~wstring((char **)&Src_8);
      p_pguid_8 = (char **)&pguid_8;
    }
    else
    {
LABEL_19:
      pguid_8 = 0;
      v4 = CoCreateGuid(&pguid_8);
      if ( v4 < 0 )
        goto LABEL_43;
      if ( !StringFromGUID2(&pguid_8, sz, 50) )
      {
        v4 = -2147467259;
        goto LABEL_43;
      }
      Src_8 = 0;
      v31 = 0;
      v13 = -1;
      do
        ++v13;
      while ( Buffer[v13] );
      std::wstring::_Construct<1,unsigned short const *>(&Src_8, Buffer, v13);
      v15 = std::wstring::append((void **)&Src_8, sz, v14);
      v32 = *(_OWORD *)v15;
      v33 = *((_OWORD *)v15 + 1);
      v15[2] = 0;
      v15[3] = (void *)7;
      *(_WORD *)v15 = 0;
      std::wstring::operator=((char **)lpPathName_8, (__int64)&v32);
      std::wstring::~wstring((char **)&v32);
      p_pguid_8 = (char **)&Src_8;
    }
    std::wstring::~wstring(p_pguid_8);
    v16 = (const WCHAR *)lpPathName_8;
    if ( si128.m128i_i64[1] > 7uLL )
      v16 = lpPathName_8[0];
    if ( CreateDirectoryW(v16, 0) || GetLastError() == 183 )
    {
      v18 = lpPathName_8;
      if ( si128.m128i_i64[1] > 7uLL )
        v18 = (LPCWSTR *)lpPathName_8[0];
      v19 = 2147483646;
      v20 = 260;
      v21 = a2;
      do
      {
        if ( !v19 )
          break;
        v22 = *(_WORD *)v18;
        if ( !*(_WORD *)v18 )
          break;
        v18 = (LPCWSTR *)((char *)v18 + 2);
        *v21++ = v22;
        --v19;
        --v20;
      }
      while ( v20 );
      v4 = v20 == 0 ? 0x8007007A : 0;
      v23 = v21 - 1;
      if ( v20 )
        v23 = v21;
      *v23 = 0;
      if ( !v20 || (v4 = StringCchCatW(a2, 260, L"\\"), v4 < 0) || (v4 = StringCchCatW(a2, 260, a1), v4 < 0) )
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "GetTempCatalogPath",
          L"Failed to update new catalog path for %ws",
          a2);
    }
    else
    {
      v17 = GetLastError();
      v4 = v17;
      if ( v17 > 0 )
        v4 = (unsigned __int16)v17 | 0x80070000;
    }
  }
LABEL_43:
  std::wstring::~wstring((char **)lpPathName_8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014bf8  mov     rax, rsp
0x180014bfb  push    rbp
0x180014bfc  push    rsi
0x180014bfd  push    rdi
0x180014bfe  push    r12
0x180014c00  push    r15
0x180014c02  lea     rbp, [rax-478h]
0x180014c09  sub     rsp, 550h
0x180014c10  mov     [rsp+570h+lpPathName], 0FFFFFFFFFFFFFFFEh
0x180014c19  mov     [rax+18h], rbx
0x180014c1d  mov     rax, cs:__security_cookie
0x180014c24  xor     rax, rsp
0x180014c27  mov     [rbp+470h+var_30], rax
0x180014c2e  mov     rdi, rdx
0x180014c31  mov     rsi, rcx
0x180014c34  xor     r15d, r15d
0x180014c37  mov     ebx, r15d
0x180014c3a  xor     edx, edx; Val
0x180014c3c  mov     r8d, 208h; Size
0x180014c42  lea     rcx, [rbp+470h+Buffer]; void *
0x180014c46  call    memset_0
0x180014c4b  xor     edx, edx; Val
0x180014c4d  mov     r8d, 208h; Size
0x180014c53  lea     rcx, [rbp+470h+Str]; void *
0x180014c5a  call    memset_0
0x180014c5f  mov     [rsp+570h+FilePart], r15
0x180014c64  xorps   xmm0, xmm0
0x180014c67  movups  xmmword ptr [rsp+570h+lpPathName+8], xmm0
0x180014c6c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180014c74  movdqu  [rsp+570h+var_538+8], xmm1
0x180014c7a  mov     word ptr [rsp+570h+lpPathName+8], r15w
0x180014c80  lea     rdx, [rbp+470h+Buffer]; lpBuffer
0x180014c84  mov     r12d, 104h
0x180014c8a  mov     ecx, r12d; nBufferLength
0x180014c8d  call    cs:__imp_GetTempPathW
0x180014c94  nop     dword ptr [rax+rax+00h]
0x180014c99  test    eax, eax
0x180014c9b  jnz     short loc_180014CC0
0x180014c9d  call    cs:__imp_GetLastError
0x180014ca4  nop     dword ptr [rax+rax+00h]
0x180014ca9  mov     ebx, eax
0x180014cab  test    eax, eax
0x180014cad  jle     short loc_180014CB8
0x180014caf  movzx   ebx, ax
0x180014cb2  or      ebx, 80070000h
0x180014cb8  test    ebx, ebx
0x180014cba  js      loc_180014FD6
0x180014cc0  lea     r9, [rsp+570h+FilePart]; lpFilePart
0x180014cc5  lea     r8, [rbp+470h+Str]; lpBuffer
0x180014ccc  mov     edx, r12d; nBufferLength
0x180014ccf  mov     rcx, rdi; lpFileName
0x180014cd2  call    cs:__imp_GetFullPathNameW
0x180014cd9  nop     dword ptr [rax+rax+00h]
0x180014cde  test    eax, eax
0x180014ce0  jnz     short loc_180014D05
0x180014ce2  call    cs:__imp_GetLastError
0x180014ce9  nop     dword ptr [rax+rax+00h]
0x180014cee  mov     ebx, eax
0x180014cf0  test    eax, eax
0x180014cf2  jle     short loc_180014CFD
0x180014cf4  movzx   ebx, ax
0x180014cf7  or      ebx, 80070000h
0x180014cfd  test    ebx, ebx
0x180014cff  js      loc_180014E0C
0x180014d05  lea     rdx, aV4connections; "\\V4Connections\\"
0x180014d0c  lea     rcx, [rbp+470h+Str]; Str
0x180014d13  call    cs:__imp_wcsstr
0x180014d1a  nop     dword ptr [rax+rax+00h]
0x180014d1f  mov     rdx, rax
0x180014d22  test    rax, rax
0x180014d25  jz      short loc_180014D2D
0x180014d27  add     rdx, 1Eh
0x180014d2b  jmp     short loc_180014D32
0x180014d2d  mov     ebx, 80004005h
0x180014d32  test    ebx, ebx
0x180014d34  js      loc_180014E0C
0x180014d3a  mov     r8, [rsp+570h+FilePart]
0x180014d3f  add     r8, 0FFFFFFFFFFFFFFFEh
0x180014d43  xorps   xmm0, xmm0
0x180014d46  movups  xmmword ptr [rsp+570h+pguid.Data4], xmm0
0x180014d4b  xorps   xmm1, xmm1
0x180014d4e  movdqu  [rsp+570h+var_518+8], xmm1
0x180014d54  cmp     rdx, r8
0x180014d57  jnz     short loc_180014D6F
0x180014d59  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180014d61  movdqu  [rsp+570h+var_518+8], xmm0
0x180014d67  mov     word ptr [rsp+570h+pguid.Data4], r15w
0x180014d6d  jmp     short loc_180014D80
0x180014d6f  sub     r8, rdx
0x180014d72  sar     r8, 1
0x180014d75  lea     rcx, [rsp+570h+pguid.Data4]
0x180014d7a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180014d7f  nop
0x180014d80  xorps   xmm0, xmm0
0x180014d83  movups  xmmword ptr [rsp+570h+Src+8], xmm0
0x180014d88  xorps   xmm1, xmm1
0x180014d8b  movdqu  [rbp+470h+var_4F0], xmm1
0x180014d90  lea     rax, [rbp+470h+Buffer]
0x180014d94  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014d98  inc     r8
0x180014d9b  cmp     [rax+r8*2], r15w
0x180014da0  jnz     short loc_180014D98
0x180014da2  lea     rdx, [rbp+470h+Buffer]
0x180014da6  lea     rcx, [rsp+570h+Src+8]
0x180014dab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180014db0  nop
0x180014db1  lea     rdx, [rsp+570h+pguid.Data4]
0x180014db6  lea     rcx, [rsp+570h+Src+8]; Src
0x180014dbb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180014dc0  movups  xmm0, xmmword ptr [rax]
0x180014dc3  movups  [rbp+470h+var_4E0], xmm0
0x180014dc7  movups  xmm1, xmmword ptr [rax+10h]
0x180014dcb  movups  [rbp+470h+var_4D0], xmm1
0x180014dcf  mov     [rax+10h], r15
0x180014dd3  mov     qword ptr [rax+18h], 7
0x180014ddb  mov     [rax], r15w
0x180014ddf  lea     rdx, [rbp+470h+var_4E0]
0x180014de3  lea     rcx, [rsp+570h+lpPathName+8]
0x180014de8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180014ded  lea     rcx, [rbp+470h+var_4E0]
0x180014df1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014df6  nop
0x180014df7  lea     rcx, [rsp+570h+Src+8]
0x180014dfc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014e01  nop
0x180014e02  lea     rcx, [rsp+570h+pguid.Data4]
0x180014e07  jmp     loc_180014ED3
0x180014e0c  xorps   xmm0, xmm0
0x180014e0f  movups  xmmword ptr [rsp+570h+pguid.Data4], xmm0
0x180014e14  lea     rcx, [rsp+570h+pguid.Data4]; pguid
0x180014e19  call    cs:__imp_CoCreateGuid
0x180014e20  nop     dword ptr [rax+rax+00h]
0x180014e25  mov     ebx, eax
0x180014e27  test    eax, eax
0x180014e29  js      loc_180014FD6
0x180014e2f  mov     r8d, 32h ; '2'; cchMax
0x180014e35  lea     rdx, [rbp+470h+sz]; lpsz
0x180014e39  lea     rcx, [rsp+570h+pguid.Data4]; rguid
0x180014e3e  call    cs:__imp_StringFromGUID2
0x180014e45  nop     dword ptr [rax+rax+00h]
0x180014e4a  test    eax, eax
0x180014e4c  jnz     short loc_180014E58
0x180014e4e  mov     ebx, 80004005h
0x180014e53  jmp     loc_180014FD6
0x180014e58  xorps   xmm0, xmm0
0x180014e5b  movups  xmmword ptr [rsp+570h+Src+8], xmm0
0x180014e60  xorps   xmm1, xmm1
0x180014e63  movdqu  [rbp+470h+var_4F0], xmm1
0x180014e68  lea     rax, [rbp+470h+Buffer]
0x180014e6c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014e70  inc     r8
0x180014e73  cmp     [rax+r8*2], r15w
0x180014e78  jnz     short loc_180014E70
0x180014e7a  lea     rdx, [rbp+470h+Buffer]
0x180014e7e  lea     rcx, [rsp+570h+Src+8]
0x180014e83  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180014e88  nop
0x180014e89  lea     rdx, [rbp+470h+sz]; void *
0x180014e8d  lea     rcx, [rsp+570h+Src+8]; Src
0x180014e92  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180014e97  movups  xmm0, xmmword ptr [rax]
0x180014e9a  movups  [rbp+470h+var_4E0], xmm0
0x180014e9e  movups  xmm1, xmmword ptr [rax+10h]
0x180014ea2  movups  [rbp+470h+var_4D0], xmm1
0x180014ea6  mov     [rax+10h], r15
0x180014eaa  mov     qword ptr [rax+18h], 7
0x180014eb2  mov     [rax], r15w
0x180014eb6  lea     rdx, [rbp+470h+var_4E0]
0x180014eba  lea     rcx, [rsp+570h+lpPathName+8]
0x180014ebf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180014ec4  lea     rcx, [rbp+470h+var_4E0]
0x180014ec8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014ecd  nop
0x180014ece  lea     rcx, [rsp+570h+Src+8]
0x180014ed3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014ed8  lea     rcx, [rsp+570h+lpPathName+8]
0x180014edd  cmp     qword ptr [rsp+570h+pguid.Data1], 7
0x180014ee3  cmova   rcx, [rsp+570h+lpPathName+8]; lpPathName
0x180014ee9  xor     edx, edx; lpSecurityAttributes
0x180014eeb  call    cs:__imp_CreateDirectoryW
0x180014ef2  nop     dword ptr [rax+rax+00h]
0x180014ef7  test    eax, eax
0x180014ef9  jnz     short loc_180014F32
0x180014efb  call    cs:__imp_GetLastError
0x180014f02  nop     dword ptr [rax+rax+00h]
0x180014f07  cmp     eax, 0B7h
0x180014f0c  jz      short loc_180014F32
0x180014f0e  call    cs:__imp_GetLastError
0x180014f15  nop     dword ptr [rax+rax+00h]
0x180014f1a  mov     ebx, eax
0x180014f1c  test    eax, eax
0x180014f1e  jle     loc_180014FD6
0x180014f24  movzx   ebx, ax
0x180014f27  or      ebx, 80070000h
0x180014f2d  jmp     loc_180014FD6
0x180014f32  lea     rax, [rsp+570h+lpPathName+8]
0x180014f37  cmp     qword ptr [rsp+570h+pguid.Data1], 7
0x180014f3d  cmova   rax, [rsp+570h+lpPathName+8]
0x180014f43  mov     ecx, 7FFFFFFEh
0x180014f48  mov     r9, r12
0x180014f4b  mov     rdx, rdi
0x180014f4e  test    rcx, rcx
0x180014f51  jz      short loc_180014F72
0x180014f53  movzx   r8d, word ptr [rax]
0x180014f57  test    r8w, r8w
0x180014f5b  jz      short loc_180014F72
0x180014f5d  add     rax, 2
0x180014f61  mov     [rdx], r8w
0x180014f65  add     rdx, 2
0x180014f69  dec     rcx
0x180014f6c  sub     r9, 1
0x180014f70  jnz     short loc_180014F4E
0x180014f72  mov     rax, r9
0x180014f75  neg     rax
0x180014f78  sbb     ebx, ebx
0x180014f7a  not     ebx
0x180014f7c  and     ebx, 8007007Ah
0x180014f82  lea     rcx, [rdx-2]
0x180014f86  test    r9, r9
0x180014f89  cmovnz  rcx, rdx
0x180014f8d  mov     [rcx], r15w
0x180014f91  jz      short loc_180014FBF
0x180014f93  lea     r8, SubBlock; "\\"
0x180014f9a  mov     rdx, r12; unsigned __int64
0x180014f9d  mov     rcx, rdi; unsigned __int16 *
0x180014fa0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014fa5  mov     ebx, eax
0x180014fa7  test    eax, eax
0x180014fa9  js      short loc_180014FBF
0x180014fab  mov     r8, rsi; unsigned __int16 *
0x180014fae  mov     rdx, r12; unsigned __int64
0x180014fb1  mov     rcx, rdi; unsigned __int16 *
0x180014fb4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014fb9  mov     ebx, eax
0x180014fbb  test    eax, eax
0x180014fbd  jns     short loc_180014FD6
0x180014fbf  mov     r8, rdi
0x180014fc2  lea     rdx, aFailedToUpdate; "Failed to update new catalog path for %"...
0x180014fc9  lea     rcx, aGettempcatalog; "GetTempCatalogPath"
0x180014fd0  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014fd5  nop
0x180014fd6  lea     rcx, [rsp+570h+lpPathName+8]
0x180014fdb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014fe0  mov     eax, ebx
0x180014fe2  mov     rcx, [rbp+470h+var_30]
0x180014fe9  xor     rcx, rsp; StackCookie
0x180014fec  call    __security_check_cookie
0x180014ff1  mov     rbx, [rsp+570h+arg_10]
0x180014ff9  add     rsp, 550h
0x180015000  pop     r15
0x180015002  pop     r12
0x180015004  pop     rdi
0x180015005  pop     rsi
0x180015006  pop     rbp
0x180015007  retn
```
