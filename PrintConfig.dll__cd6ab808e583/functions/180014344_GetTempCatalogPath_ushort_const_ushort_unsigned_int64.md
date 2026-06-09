# GetTempCatalogPath(ushort const *,ushort *,unsigned __int64)

- ea: `0x180014344`
- end: `0x180014718`
- name: `?GetTempCatalogPath@@YAJPEBGPEAG_K@Z`
- size: `980`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18001053c`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x18000be0c`
- `0x18000da28`
- `0x18000f590`
- `0x18000fb88`
- `0x180014344`
- `0x1800183f8`
- `0x18001899c`
- `0x180018a28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014447`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014447`
- `KERNEL32!GetTempPathW` at `0x1800143d9`
- `KERNEL32!GetTempPathW` at `0x1800143d9`
- `KERNEL32!CreateDirectoryW` at `0x18001460d`
- `KERNEL32!CreateDirectoryW` at `0x18001460d`
- `KERNEL32!GetFullPathNameW` at `0x180014412`
- `KERNEL32!GetFullPathNameW` at `0x180014412`
- `KERNEL32!GetLastError` at `0x1800143e3`
- `KERNEL32!GetLastError` at `0x18001441c`
- `KERNEL32!GetLastError` at `0x180014617`
- `KERNEL32!GetLastError` at `0x180014624`
- `KERNEL32!GetLastError` at `0x1800143e3`
- `KERNEL32!GetLastError` at `0x18001441c`
- `KERNEL32!GetLastError` at `0x180014617`
- `KERNEL32!GetLastError` at `0x180014624`
- `ole32!CoCreateGuid` at `0x180014547`
- `ole32!CoCreateGuid` at `0x180014547`
- `ole32!StringFromGUID2` at `0x180014566`
- `ole32!StringFromGUID2` at `0x180014566`

## string_xrefs

- `0x1800146d2`: `Failed to update new catalog path for %ws`
- `0x1800146d9`: `GetTempCatalogPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetTempCatalogPath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  wchar_t *v7; // rax
  wchar_t *v8; // rdx
  unsigned __int64 v9; // r8
  __int64 v10; // rax
  GUID *p_pguid_8; // rcx
  unsigned __int64 v12; // r8
  __int64 v13; // rax
  const WCHAR *v14; // rcx
  signed int v15; // eax
  LPCWSTR *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r9
  unsigned __int16 *v19; // rdx
  unsigned __int16 v20; // r8
  unsigned __int16 *v21; // rcx
  LPWSTR FilePart[2]; // [rsp+28h] [rbp-E0h] BYREF
  LPCWSTR lpPathName_8[2]; // [rsp+38h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+48h] [rbp-C0h]
  GUID pguid_8; // [rsp+58h] [rbp-B0h] BYREF
  __m128i v27; // [rsp+68h] [rbp-A0h]
  __int128 Src_8; // [rsp+78h] [rbp-90h] BYREF
  __int128 v29; // [rsp+88h] [rbp-80h]
  __int128 v30; // [rsp+98h] [rbp-70h] BYREF
  __int128 v31; // [rsp+A8h] [rbp-60h]
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
      v27 = 0;
      if ( v8 == FilePart[0] - 1 )
      {
        v27 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(pguid_8.Data1) = 0;
      }
      else
      {
        std::wstring::_Construct<1,unsigned short const *>((char **)&pguid_8, v8, FilePart[0] - 1 - v8);
      }
      Src_8 = 0;
      v29 = 0;
      v9 = -1;
      do
        ++v9;
      while ( Buffer[v9] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&Src_8, Buffer, v9);
      v10 = std::wstring::append(&Src_8);
      v30 = *(_OWORD *)v10;
      v31 = *(_OWORD *)(v10 + 16);
      *(_QWORD *)(v10 + 16) = 0;
      *(_QWORD *)(v10 + 24) = 7;
      *(_WORD *)v10 = 0;
      std::wstring::operator=(lpPathName_8, &v30);
      std::wstring::~wstring(&v30);
      std::wstring::~wstring(&Src_8);
      p_pguid_8 = &pguid_8;
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
      v29 = 0;
      v12 = -1;
      do
        ++v12;
      while ( Buffer[v12] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&Src_8, Buffer, v12);
      v13 = std::wstring::append(&Src_8, sz);
      v30 = *(_OWORD *)v13;
      v31 = *(_OWORD *)(v13 + 16);
      *(_QWORD *)(v13 + 16) = 0;
      *(_QWORD *)(v13 + 24) = 7;
      *(_WORD *)v13 = 0;
      std::wstring::operator=(lpPathName_8, &v30);
      std::wstring::~wstring(&v30);
      p_pguid_8 = (GUID *)&Src_8;
    }
    std::wstring::~wstring(p_pguid_8);
    v14 = (const WCHAR *)lpPathName_8;
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = lpPathName_8[0];
    if ( CreateDirectoryW(v14, 0) || GetLastError() == 183 )
    {
      v16 = lpPathName_8;
      if ( si128.m128i_i64[1] > 7uLL )
        v16 = (LPCWSTR *)lpPathName_8[0];
      v17 = 2147483646;
      v18 = 260;
      v19 = a2;
      do
      {
        if ( !v17 )
          break;
        v20 = *(_WORD *)v16;
        if ( !*(_WORD *)v16 )
          break;
        v16 = (LPCWSTR *)((char *)v16 + 2);
        *v19++ = v20;
        --v17;
        --v18;
      }
      while ( v18 );
      v4 = v18 == 0 ? 0x8007007A : 0;
      v21 = v19 - 1;
      if ( v18 )
        v21 = v19;
      *v21 = 0;
      if ( !v18 || (v4 = StringCchCatW(a2, 0x104u, L"\\"), v4 < 0) || (v4 = StringCchCatW(a2, 0x104u, a1), v4 < 0) )
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "GetTempCatalogPath",
          L"Failed to update new catalog path for %ws",
          a2);
    }
    else
    {
      v15 = GetLastError();
      v4 = v15;
      if ( v15 > 0 )
        v4 = (unsigned __int16)v15 | 0x80070000;
    }
  }
LABEL_43:
  std::wstring::~wstring(lpPathName_8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014344  mov     rax, rsp
0x180014347  push    rbp
0x180014348  push    rsi
0x180014349  push    rdi
0x18001434a  push    r12
0x18001434c  push    r15
0x18001434e  lea     rbp, [rax-478h]
0x180014355  sub     rsp, 550h
0x18001435c  mov     [rsp+570h+lpPathName], 0FFFFFFFFFFFFFFFEh
0x180014365  mov     [rax+18h], rbx
0x180014369  mov     rax, cs:__security_cookie
0x180014370  xor     rax, rsp
0x180014373  mov     [rbp+470h+var_30], rax
0x18001437a  mov     rdi, rdx
0x18001437d  mov     rsi, rcx
0x180014380  xor     r15d, r15d
0x180014383  mov     ebx, r15d
0x180014386  xor     edx, edx; Val
0x180014388  mov     r8d, 208h; Size
0x18001438e  lea     rcx, [rbp+470h+Buffer]; void *
0x180014392  call    memset_0
0x180014397  xor     edx, edx; Val
0x180014399  mov     r8d, 208h; Size
0x18001439f  lea     rcx, [rbp+470h+Str]; void *
0x1800143a6  call    memset_0
0x1800143ab  mov     [rsp+570h+FilePart], r15
0x1800143b0  xorps   xmm0, xmm0
0x1800143b3  movups  xmmword ptr [rsp+570h+lpPathName+8], xmm0
0x1800143b8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800143c0  movdqu  [rsp+570h+var_538+8], xmm1
0x1800143c6  mov     word ptr [rsp+570h+lpPathName+8], r15w
0x1800143cc  lea     rdx, [rbp+470h+Buffer]; lpBuffer
0x1800143d0  mov     r12d, 104h
0x1800143d6  mov     ecx, r12d; nBufferLength
0x1800143d9  call    cs:__imp_GetTempPathW
0x1800143df  test    eax, eax
0x1800143e1  jnz     short loc_180014400
0x1800143e3  call    cs:__imp_GetLastError
0x1800143e9  mov     ebx, eax
0x1800143eb  test    eax, eax
0x1800143ed  jle     short loc_1800143F8
0x1800143ef  movzx   ebx, ax
0x1800143f2  or      ebx, 80070000h
0x1800143f8  test    ebx, ebx
0x1800143fa  js      loc_1800146E6
0x180014400  lea     r9, [rsp+570h+FilePart]; lpFilePart
0x180014405  lea     r8, [rbp+470h+Str]; lpBuffer
0x18001440c  mov     edx, r12d; nBufferLength
0x18001440f  mov     rcx, rdi; lpFileName
0x180014412  call    cs:__imp_GetFullPathNameW
0x180014418  test    eax, eax
0x18001441a  jnz     short loc_180014439
0x18001441c  call    cs:__imp_GetLastError
0x180014422  mov     ebx, eax
0x180014424  test    eax, eax
0x180014426  jle     short loc_180014431
0x180014428  movzx   ebx, ax
0x18001442b  or      ebx, 80070000h
0x180014431  test    ebx, ebx
0x180014433  js      loc_18001453A
0x180014439  lea     rdx, aV4connections; "\\V4Connections\\"
0x180014440  lea     rcx, [rbp+470h+Str]; Str
0x180014447  call    cs:__imp_wcsstr
0x18001444d  mov     rdx, rax
0x180014450  test    rax, rax
0x180014453  jz      short loc_18001445B
0x180014455  add     rdx, 1Eh
0x180014459  jmp     short loc_180014460
0x18001445b  mov     ebx, 80004005h
0x180014460  test    ebx, ebx
0x180014462  js      loc_18001453A
0x180014468  mov     r8, [rsp+570h+FilePart]
0x18001446d  add     r8, 0FFFFFFFFFFFFFFFEh
0x180014471  xorps   xmm0, xmm0
0x180014474  movups  xmmword ptr [rsp+570h+pguid.Data4], xmm0
0x180014479  xorps   xmm1, xmm1
0x18001447c  movdqu  [rsp+570h+var_518+8], xmm1
0x180014482  cmp     rdx, r8
0x180014485  jnz     short loc_18001449D
0x180014487  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001448f  movdqu  [rsp+570h+var_518+8], xmm0
0x180014495  mov     word ptr [rsp+570h+pguid.Data4], r15w
0x18001449b  jmp     short loc_1800144AE
0x18001449d  sub     r8, rdx
0x1800144a0  sar     r8, 1
0x1800144a3  lea     rcx, [rsp+570h+pguid.Data4]
0x1800144a8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800144ad  nop
0x1800144ae  xorps   xmm0, xmm0
0x1800144b1  movups  xmmword ptr [rsp+570h+Src+8], xmm0
0x1800144b6  xorps   xmm1, xmm1
0x1800144b9  movdqu  [rbp+470h+var_4F0], xmm1
0x1800144be  lea     rax, [rbp+470h+Buffer]
0x1800144c2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800144c6  inc     r8
0x1800144c9  cmp     [rax+r8*2], r15w
0x1800144ce  jnz     short loc_1800144C6
0x1800144d0  lea     rdx, [rbp+470h+Buffer]
0x1800144d4  lea     rcx, [rsp+570h+Src+8]
0x1800144d9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800144de  nop
0x1800144df  lea     rdx, [rsp+570h+pguid.Data4]
0x1800144e4  lea     rcx, [rsp+570h+Src+8]; Src
0x1800144e9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800144ee  movups  xmm0, xmmword ptr [rax]
0x1800144f1  movups  [rbp+470h+var_4E0], xmm0
0x1800144f5  movups  xmm1, xmmword ptr [rax+10h]
0x1800144f9  movups  [rbp+470h+var_4D0], xmm1
0x1800144fd  mov     [rax+10h], r15
0x180014501  mov     qword ptr [rax+18h], 7
0x180014509  mov     [rax], r15w
0x18001450d  lea     rdx, [rbp+470h+var_4E0]
0x180014511  lea     rcx, [rsp+570h+lpPathName+8]
0x180014516  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001451b  lea     rcx, [rbp+470h+var_4E0]
0x18001451f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014524  nop
0x180014525  lea     rcx, [rsp+570h+Src+8]
0x18001452a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001452f  nop
0x180014530  lea     rcx, [rsp+570h+pguid.Data4]
0x180014535  jmp     loc_1800145F5
0x18001453a  xorps   xmm0, xmm0
0x18001453d  movups  xmmword ptr [rsp+570h+pguid.Data4], xmm0
0x180014542  lea     rcx, [rsp+570h+pguid.Data4]; pguid
0x180014547  call    cs:__imp_CoCreateGuid
0x18001454d  mov     ebx, eax
0x18001454f  test    eax, eax
0x180014551  js      loc_1800146E6
0x180014557  mov     r8d, 32h ; '2'; cchMax
0x18001455d  lea     rdx, [rbp+470h+sz]; lpsz
0x180014561  lea     rcx, [rsp+570h+pguid.Data4]; rguid
0x180014566  call    cs:__imp_StringFromGUID2
0x18001456c  test    eax, eax
0x18001456e  jnz     short loc_18001457A
0x180014570  mov     ebx, 80004005h
0x180014575  jmp     loc_1800146E6
0x18001457a  xorps   xmm0, xmm0
0x18001457d  movups  xmmword ptr [rsp+570h+Src+8], xmm0
0x180014582  xorps   xmm1, xmm1
0x180014585  movdqu  [rbp+470h+var_4F0], xmm1
0x18001458a  lea     rax, [rbp+470h+Buffer]
0x18001458e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014592  inc     r8
0x180014595  cmp     [rax+r8*2], r15w
0x18001459a  jnz     short loc_180014592
0x18001459c  lea     rdx, [rbp+470h+Buffer]
0x1800145a0  lea     rcx, [rsp+570h+Src+8]
0x1800145a5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800145aa  nop
0x1800145ab  lea     rdx, [rbp+470h+sz]; void *
0x1800145af  lea     rcx, [rsp+570h+Src+8]; Src
0x1800145b4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800145b9  movups  xmm0, xmmword ptr [rax]
0x1800145bc  movups  [rbp+470h+var_4E0], xmm0
0x1800145c0  movups  xmm1, xmmword ptr [rax+10h]
0x1800145c4  movups  [rbp+470h+var_4D0], xmm1
0x1800145c8  mov     [rax+10h], r15
0x1800145cc  mov     qword ptr [rax+18h], 7
0x1800145d4  mov     [rax], r15w
0x1800145d8  lea     rdx, [rbp+470h+var_4E0]
0x1800145dc  lea     rcx, [rsp+570h+lpPathName+8]
0x1800145e1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800145e6  lea     rcx, [rbp+470h+var_4E0]
0x1800145ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800145ef  nop
0x1800145f0  lea     rcx, [rsp+570h+Src+8]
0x1800145f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800145fa  lea     rcx, [rsp+570h+lpPathName+8]
0x1800145ff  cmp     qword ptr [rsp+570h+pguid.Data1], 7
0x180014605  cmova   rcx, [rsp+570h+lpPathName+8]; lpPathName
0x18001460b  xor     edx, edx; lpSecurityAttributes
0x18001460d  call    cs:__imp_CreateDirectoryW
0x180014613  test    eax, eax
0x180014615  jnz     short loc_180014642
0x180014617  call    cs:__imp_GetLastError
0x18001461d  cmp     eax, 0B7h
0x180014622  jz      short loc_180014642
0x180014624  call    cs:__imp_GetLastError
0x18001462a  mov     ebx, eax
0x18001462c  test    eax, eax
0x18001462e  jle     loc_1800146E6
0x180014634  movzx   ebx, ax
0x180014637  or      ebx, 80070000h
0x18001463d  jmp     loc_1800146E6
0x180014642  lea     rax, [rsp+570h+lpPathName+8]
0x180014647  cmp     qword ptr [rsp+570h+pguid.Data1], 7
0x18001464d  cmova   rax, [rsp+570h+lpPathName+8]
0x180014653  mov     ecx, 7FFFFFFEh
0x180014658  mov     r9, r12
0x18001465b  mov     rdx, rdi
0x18001465e  test    rcx, rcx
0x180014661  jz      short loc_180014682
0x180014663  movzx   r8d, word ptr [rax]
0x180014667  test    r8w, r8w
0x18001466b  jz      short loc_180014682
0x18001466d  add     rax, 2
0x180014671  mov     [rdx], r8w
0x180014675  add     rdx, 2
0x180014679  dec     rcx
0x18001467c  sub     r9, 1
0x180014680  jnz     short loc_18001465E
0x180014682  mov     rax, r9
0x180014685  neg     rax
0x180014688  sbb     ebx, ebx
0x18001468a  not     ebx
0x18001468c  and     ebx, 8007007Ah
0x180014692  lea     rcx, [rdx-2]
0x180014696  test    r9, r9
0x180014699  cmovnz  rcx, rdx
0x18001469d  mov     [rcx], r15w
0x1800146a1  jz      short loc_1800146CF
0x1800146a3  lea     r8, SubBlock; "\\"
0x1800146aa  mov     rdx, r12; unsigned __int64
0x1800146ad  mov     rcx, rdi; unsigned __int16 *
0x1800146b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800146b5  mov     ebx, eax
0x1800146b7  test    eax, eax
0x1800146b9  js      short loc_1800146CF
0x1800146bb  mov     r8, rsi; unsigned __int16 *
0x1800146be  mov     rdx, r12; unsigned __int64
0x1800146c1  mov     rcx, rdi; unsigned __int16 *
0x1800146c4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800146c9  mov     ebx, eax
0x1800146cb  test    eax, eax
0x1800146cd  jns     short loc_1800146E6
0x1800146cf  mov     r8, rdi
0x1800146d2  lea     rdx, aFailedToUpdate; "Failed to update new catalog path for %"...
0x1800146d9  lea     rcx, aGettempcatalog; "GetTempCatalogPath"
0x1800146e0  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800146e5  nop
0x1800146e6  lea     rcx, [rsp+570h+lpPathName+8]
0x1800146eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800146f0  mov     eax, ebx
0x1800146f2  mov     rcx, [rbp+470h+var_30]
0x1800146f9  xor     rcx, rsp; StackCookie
0x1800146fc  call    __security_check_cookie
0x180014701  mov     rbx, [rsp+570h+arg_10]
0x180014709  add     rsp, 550h
0x180014710  pop     r15
0x180014712  pop     r12
0x180014714  pop     rdi
0x180014715  pop     rsi
0x180014716  pop     rbp
0x180014717  retn
```
