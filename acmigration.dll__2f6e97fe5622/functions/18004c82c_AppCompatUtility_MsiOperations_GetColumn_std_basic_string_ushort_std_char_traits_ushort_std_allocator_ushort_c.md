# AppCompatUtility::MsiOperations::GetColumn(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18004c82c`
- end: `0x18004cba5`
- name: `?GetColumn@MsiOperations@AppCompatUtility@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z`
- size: `889`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004cea0`

## callees

- `0x180001cf0`
- `0x1800085bc`
- `0x18000b720`
- `0x18000bbbc`
- `0x18000dfd8`
- `0x18000e064`
- `0x1800118f4`
- `0x180021dd4`
- `0x18002ec04`
- `0x18004c82c`

## import_xrefs

- `MSI!MsiCloseHandle` at `0x18004c8bc`
- `MSI!MsiCloseHandle` at `0x18004c9a7`
- `MSI!MsiCloseHandle` at `0x18004ca11`
- `MSI!MsiCloseHandle` at `0x18004ca66`
- `MSI!MsiCloseHandle` at `0x18004cb4d`
- `MSI!MsiCloseHandle` at `0x18004cb65`
- `MSI!MsiCloseHandle` at `0x18004cb73`
- `MSI!MsiCloseHandle` at `0x18004c8bc`
- `MSI!MsiCloseHandle` at `0x18004c9a7`
- `MSI!MsiCloseHandle` at `0x18004ca11`
- `MSI!MsiCloseHandle` at `0x18004ca66`
- `MSI!MsiCloseHandle` at `0x18004cb4d`
- `MSI!MsiCloseHandle` at `0x18004cb65`
- `MSI!MsiCloseHandle` at `0x18004cb73`
- `MSI!MsiOpenDatabaseW` at `0x18004c881`
- `MSI!MsiOpenDatabaseW` at `0x18004c881`
- `MSI!MsiRecordGetStringW` at `0x18004ca97`
- `MSI!MsiRecordGetStringW` at `0x18004cad8`
- `MSI!MsiRecordGetStringW` at `0x18004ca97`
- `MSI!MsiRecordGetStringW` at `0x18004cad8`
- `MSI!MsiViewFetch` at `0x18004ca7a`
- `MSI!MsiViewFetch` at `0x18004ca7a`
- `MSI!MsiViewExecute` at `0x18004ca4c`
- `MSI!MsiViewExecute` at `0x18004ca4c`
- `MSI!MsiDatabaseOpenViewW` at `0x18004c9c8`
- `MSI!MsiDatabaseOpenViewW` at `0x18004c9c8`

## string_xrefs

- `0x18004c8a3`: `onecore\windows\appcompat\migrationshims\lib\msioperations.cpp`
- `0x18004c9ea`: `onecore\windows\appcompat\migrationshims\lib\msioperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppCompatUtility::MsiOperations::GetColumn(const WCHAR *a1, __int64 a2, __int64 a3, char **a4)
{
  signed int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  signed int v9; // ebx
  __int64 v11; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rdx
  signed int v14; // eax
  char *v15; // rsi
  char *v16; // rbx
  __m128i si128; // xmm6
  WCHAR *v18; // r8
  char *v19; // rdx
  int v20; // [rsp+28h] [rbp-89h]
  MSIHANDLE hAny; // [rsp+48h] [rbp-69h] BYREF
  MSIHANDLE phRecord; // [rsp+4Ch] [rbp-65h] BYREF
  MSIHANDLE phDatabase; // [rsp+50h] [rbp-61h] BYREF
  DWORD pcchValueBuf; // [rsp+54h] [rbp-5Dh] BYREF
  __int64 v25; // [rsp+58h] [rbp-59h]
  LPWSTR szValueBuf[2]; // [rsp+60h] [rbp-51h] BYREF
  __m128i v27; // [rsp+70h] [rbp-41h]
  LPCWSTR szQuery[2]; // [rsp+80h] [rbp-31h] BYREF
  __int128 v29; // [rsp+90h] [rbp-21h]
  _BYTE Src[32]; // [rsp+A0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]

  v25 = -2;
  phDatabase = 0;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  v6 = MsiOpenDatabaseW(a1, 0, &phDatabase);
  v9 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v9 = (unsigned __int16)v6 | 0x80070000;
    if ( v9 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecore\\windows\\appcompat\\migrationshims\\lib\\msioperations.cpp",
        (const char *)(unsigned int)v9,
        v20);
LABEL_8:
    if ( phDatabase )
      MsiCloseHandle(phDatabase);
    return (unsigned int)v9;
  }
  hAny = 0;
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *(_QWORD *)(a3 + 16)) < 7 )
    std::_Xlen_string();
  std::wstring::wstring(Src, v7, v8, L"SELECT ");
  v11 = std::wstring::append(Src, L" FROM ");
  *(_OWORD *)szValueBuf = 0;
  v27 = 0;
  *(_OWORD *)szValueBuf = *(_OWORD *)v11;
  v27 = *(__m128i *)(v11 + 16);
  *(_QWORD *)(v11 + 16) = 0;
  *(_QWORD *)(v11 + 24) = 7;
  *(_WORD *)v11 = 0;
  v12 = std::wstring::append(szValueBuf);
  *(_OWORD *)szQuery = 0;
  v29 = 0;
  *(_OWORD *)szQuery = *(_OWORD *)v12;
  v29 = *(_OWORD *)(v12 + 16);
  *(_QWORD *)(v12 + 16) = 0;
  *(_QWORD *)(v12 + 24) = 7;
  *(_WORD *)v12 = 0;
  std::wstring::~wstring(szValueBuf);
  std::wstring::~wstring(Src);
  if ( hAny )
    MsiCloseHandle(hAny);
  hAny = 0;
  v13 = (const WCHAR *)szQuery;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    v13 = szQuery[0];
  v14 = MsiDatabaseOpenViewW(phDatabase, v13, &hAny);
  v9 = v14;
  if ( v14 )
  {
    if ( v14 > 0 )
      v9 = (unsigned __int16)v14 | 0x80070000;
    if ( v9 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\windows\\appcompat\\migrationshims\\lib\\msioperations.cpp",
        (const char *)(unsigned int)v9,
        7);
    std::wstring::~wstring(szQuery);
    if ( hAny )
      MsiCloseHandle(hAny);
    goto LABEL_8;
  }
  v15 = a4[1];
  v16 = *a4;
  if ( *a4 != v15 )
  {
    do
    {
      std::wstring::~wstring(v16);
      v16 += 32;
    }
    while ( v16 != v15 );
    a4[1] = *a4;
  }
  phRecord = 0;
  MsiViewExecute(hAny, 0);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    if ( phRecord )
      MsiCloseHandle(phRecord);
    phRecord = 0;
    if ( MsiViewFetch(hAny, &phRecord) )
      break;
    pcchValueBuf = 0;
    MsiRecordGetStringW(phRecord, 1u, 0, &pcchValueBuf);
    ++pcchValueBuf;
    *(_OWORD *)szValueBuf = 0;
    v27 = si128;
    LOWORD(szValueBuf[0]) = 0;
    std::wstring::resize(szValueBuf);
    v18 = (WCHAR *)szValueBuf;
    if ( v27.m128i_i64[1] > 7uLL )
      v18 = szValueBuf[0];
    MsiRecordGetStringW(phRecord, 1u, v18, &pcchValueBuf);
    std::wstring::resize(szValueBuf);
    v19 = a4[1];
    if ( v19 == a4[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a4, v19, szValueBuf);
    }
    else
    {
      *(_OWORD *)v19 = 0;
      *((_QWORD *)v19 + 2) = 0;
      *((_QWORD *)v19 + 3) = 0;
      *(_OWORD *)v19 = *(_OWORD *)szValueBuf;
      *((__m128i *)v19 + 1) = v27;
      v27 = si128;
      LOWORD(szValueBuf[0]) = 0;
      a4[1] += 32;
    }
    std::wstring::~wstring(szValueBuf);
  }
  if ( phRecord )
    MsiCloseHandle(phRecord);
  std::wstring::~wstring(szQuery);
  if ( hAny )
    MsiCloseHandle(hAny);
  if ( phDatabase )
    MsiCloseHandle(phDatabase);
  return 0;
}

```

## disassembly

```asm
0x18004c82c  mov     rax, rsp
0x18004c82f  push    rbp
0x18004c830  push    rbx
0x18004c831  push    rsi
0x18004c832  push    rdi
0x18004c833  push    r12
0x18004c835  push    r14
0x18004c837  lea     rbp, [rax-5Fh]
0x18004c83b  sub     rsp, 0D8h
0x18004c842  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFEh
0x18004c84a  movaps  xmmword ptr [rax-48h], xmm6
0x18004c84e  mov     rax, cs:__security_cookie
0x18004c855  xor     rax, rsp
0x18004c858  mov     qword ptr [rbp+57h+var_48], rax
0x18004c85c  mov     rdi, r9
0x18004c85f  mov     rsi, r8
0x18004c862  mov     r14, rdx
0x18004c865  mov     [rbp+57h+phDatabase], 0
0x18004c86c  mov     r12d, 7
0x18004c872  cmp     [rcx+18h], r12
0x18004c876  jbe     short loc_18004C87B
0x18004c878  mov     rcx, [rcx]; szDatabasePath
0x18004c87b  lea     r8, [rbp+57h+phDatabase]; phDatabase
0x18004c87f  xor     edx, edx; szPersist
0x18004c881  call    cs:__imp_MsiOpenDatabaseW
0x18004c887  mov     ebx, eax
0x18004c889  test    eax, eax
0x18004c88b  jz      short loc_18004C8C9
0x18004c88d  jle     short loc_18004C898
0x18004c88f  movzx   ebx, ax
0x18004c892  or      ebx, 80070000h
0x18004c898  test    ebx, ebx
0x18004c89a  jns     short loc_18004C8B5
0x18004c89c  mov     rcx, [rbp+5Fh]; this
0x18004c8a0  mov     r9d, ebx; char *
0x18004c8a3  lea     r8, aOnecoreWindows_2; "onecore\\windows\\appcompat\\migrations"...
0x18004c8aa  mov     edx, 25h ; '%'; void *
0x18004c8af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c8b4  nop
0x18004c8b5  mov     ecx, [rbp+57h+phDatabase]; hAny
0x18004c8b8  test    ecx, ecx
0x18004c8ba  jz      short loc_18004C8C2
0x18004c8bc  call    cs:__imp_MsiCloseHandle
0x18004c8c2  mov     eax, ebx
0x18004c8c4  jmp     loc_18004CB7B
0x18004c8c9  mov     [rbp+57h+hAny], 0
0x18004c8d0  mov     rcx, [rsi+10h]
0x18004c8d4  mov     rax, 7FFFFFFFFFFFFFFEh
0x18004c8de  sub     rax, rcx
0x18004c8e1  cmp     rax, r12
0x18004c8e4  jb      loc_18004CB9F
0x18004c8ea  cmp     [rsi+18h], r12
0x18004c8ee  jbe     short loc_18004C8F3
0x18004c8f0  mov     rsi, [rsi]
0x18004c8f3  mov     [rsp+30h], rcx
0x18004c8f8  mov     [rsp+100h+var_D8], rsi
0x18004c8fd  mov     qword ptr [rsp+100h+var_E0], r12; int
0x18004c902  lea     r9, aSelect; "SELECT "
0x18004c909  lea     rcx, [rbp+57h+Src]
0x18004c90d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004c912  nop
0x18004c913  lea     rdx, aFrom_0; " FROM "
0x18004c91a  lea     rcx, [rbp+57h+Src]; Src
0x18004c91e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004c923  xorps   xmm0, xmm0
0x18004c926  movups  xmmword ptr [rbp+57h+szValueBuf], xmm0
0x18004c92a  xorps   xmm1, xmm1
0x18004c92d  movdqu  [rbp+57h+var_98], xmm1
0x18004c932  movups  xmm0, xmmword ptr [rax]
0x18004c935  movups  xmmword ptr [rbp+57h+szValueBuf], xmm0
0x18004c939  movups  xmm1, xmmword ptr [rax+10h]
0x18004c93d  movups  [rbp+57h+var_98], xmm1
0x18004c941  mov     qword ptr [rax+10h], 0
0x18004c949  mov     [rax+18h], r12
0x18004c94d  xor     ecx, ecx
0x18004c94f  mov     [rax], cx
0x18004c952  mov     rdx, r14
0x18004c955  lea     rcx, [rbp+57h+szValueBuf]; Src
0x18004c959  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18004c95e  xorps   xmm0, xmm0
0x18004c961  movups  xmmword ptr [rbp+57h+szQuery], xmm0
0x18004c965  xorps   xmm1, xmm1
0x18004c968  movdqu  [rbp+57h+var_78], xmm1
0x18004c96d  movups  xmm0, xmmword ptr [rax]
0x18004c970  movups  xmmword ptr [rbp+57h+szQuery], xmm0
0x18004c974  movups  xmm1, xmmword ptr [rax+10h]
0x18004c978  movups  [rbp+57h+var_78], xmm1
0x18004c97c  mov     qword ptr [rax+10h], 0
0x18004c984  mov     [rax+18h], r12
0x18004c988  xor     ecx, ecx
0x18004c98a  mov     [rax], cx
0x18004c98d  lea     rcx, [rbp+57h+szValueBuf]; void *
0x18004c991  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c996  nop
0x18004c997  lea     rcx, [rbp+57h+Src]; void *
0x18004c99b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c9a0  mov     ecx, [rbp+57h+hAny]; hAny
0x18004c9a3  test    ecx, ecx
0x18004c9a5  jz      short loc_18004C9AD
0x18004c9a7  call    cs:__imp_MsiCloseHandle
0x18004c9ad  mov     [rbp+57h+hAny], 0
0x18004c9b4  lea     rdx, [rbp+57h+szQuery]
0x18004c9b8  cmp     qword ptr [rbp+57h+var_78+8], r12
0x18004c9bc  cmova   rdx, [rbp+57h+szQuery]; szQuery
0x18004c9c1  lea     r8, [rbp+57h+hAny]; phView
0x18004c9c5  mov     ecx, [rbp+57h+phDatabase]; hDatabase
0x18004c9c8  call    cs:__imp_MsiDatabaseOpenViewW
0x18004c9ce  mov     ebx, eax
0x18004c9d0  test    eax, eax
0x18004c9d2  jz      short loc_18004CA1C
0x18004c9d4  jle     short loc_18004C9DF
0x18004c9d6  movzx   ebx, ax
0x18004c9d9  or      ebx, 80070000h
0x18004c9df  test    ebx, ebx
0x18004c9e1  jns     short loc_18004C9FC
0x18004c9e3  mov     rcx, [rbp+5Fh]; this
0x18004c9e7  mov     r9d, ebx; char *
0x18004c9ea  lea     r8, aOnecoreWindows_2; "onecore\\windows\\appcompat\\migrations"...
0x18004c9f1  mov     edx, 2Ah ; '*'; void *
0x18004c9f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c9fb  nop
0x18004c9fc  lea     rcx, [rbp+57h+szQuery]; void *
0x18004ca00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ca05  nop
0x18004ca06  mov     ecx, [rbp+57h+hAny]; hAny
0x18004ca09  test    ecx, ecx
0x18004ca0b  jz      loc_18004C8B5
0x18004ca11  call    cs:__imp_MsiCloseHandle
0x18004ca17  jmp     loc_18004C8B5
0x18004ca1c  mov     rsi, [rdi+8]
0x18004ca20  mov     rbx, [rdi]
0x18004ca23  cmp     rbx, rsi
0x18004ca26  jz      short loc_18004CA40
0x18004ca28  mov     rcx, rbx; void *
0x18004ca2b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ca30  add     rbx, 20h ; ' '
0x18004ca34  cmp     rbx, rsi
0x18004ca37  jnz     short loc_18004CA28
0x18004ca39  mov     rax, [rdi]
0x18004ca3c  mov     [rdi+8], rax
0x18004ca40  mov     [rbp+57h+phRecord], 0
0x18004ca47  xor     edx, edx; hRecord
0x18004ca49  mov     ecx, [rbp+57h+hAny]; hView
0x18004ca4c  call    cs:__imp_MsiViewExecute
0x18004ca52  mov     ebx, 1
0x18004ca57  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18004ca5f  mov     ecx, [rbp+57h+phRecord]; hAny
0x18004ca62  test    ecx, ecx
0x18004ca64  jz      short loc_18004CA6C
0x18004ca66  call    cs:__imp_MsiCloseHandle
0x18004ca6c  mov     [rbp+57h+phRecord], 0
0x18004ca73  lea     rdx, [rbp+57h+phRecord]; phRecord
0x18004ca77  mov     ecx, [rbp+57h+hAny]; hView
0x18004ca7a  call    cs:__imp_MsiViewFetch
0x18004ca80  test    eax, eax
0x18004ca82  jnz     loc_18004CB46
0x18004ca88  mov     [rbp+57h+pcchValueBuf], eax
0x18004ca8b  lea     r9, [rbp+57h+pcchValueBuf]; pcchValueBuf
0x18004ca8f  xor     r8d, r8d; szValueBuf
0x18004ca92  mov     edx, ebx; iField
0x18004ca94  mov     ecx, [rbp+57h+phRecord]; hRecord
0x18004ca97  call    cs:__imp_MsiRecordGetStringW
0x18004ca9d  mov     eax, [rbp+57h+pcchValueBuf]
0x18004caa0  add     eax, ebx
0x18004caa2  mov     [rbp+57h+pcchValueBuf], eax
0x18004caa5  mov     edx, eax
0x18004caa7  xorps   xmm0, xmm0
0x18004caaa  movups  xmmword ptr [rbp+57h+szValueBuf], xmm0
0x18004caae  movdqu  [rbp+57h+var_98], xmm6
0x18004cab3  xor     eax, eax
0x18004cab5  mov     word ptr [rbp+57h+szValueBuf], ax
0x18004cab9  lea     rcx, [rbp+57h+szValueBuf]; Src
0x18004cabd  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004cac2  lea     r8, [rbp+57h+szValueBuf]
0x18004cac6  cmp     qword ptr [rbp+57h+var_98+8], r12
0x18004caca  cmova   r8, [rbp+57h+szValueBuf]; szValueBuf
0x18004cacf  lea     r9, [rbp+57h+pcchValueBuf]; pcchValueBuf
0x18004cad3  mov     edx, ebx; iField
0x18004cad5  mov     ecx, [rbp+57h+phRecord]; hRecord
0x18004cad8  call    cs:__imp_MsiRecordGetStringW
0x18004cade  mov     edx, [rbp+57h+pcchValueBuf]
0x18004cae1  lea     rcx, [rbp+57h+szValueBuf]; Src
0x18004cae5  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004caea  mov     rdx, [rdi+8]
0x18004caee  cmp     rdx, [rdi+10h]
0x18004caf2  jz      short loc_18004CB2B
0x18004caf4  xorps   xmm0, xmm0
0x18004caf7  movups  xmmword ptr [rdx], xmm0
0x18004cafa  mov     qword ptr [rdx+10h], 0
0x18004cb02  mov     qword ptr [rdx+18h], 0
0x18004cb0a  movups  xmm0, xmmword ptr [rbp+57h+szValueBuf]
0x18004cb0e  movups  xmmword ptr [rdx], xmm0
0x18004cb11  movups  xmm1, [rbp+57h+var_98]
0x18004cb15  movups  xmmword ptr [rdx+10h], xmm1
0x18004cb19  movdqu  [rbp+57h+var_98], xmm6
0x18004cb1e  xor     eax, eax
0x18004cb20  mov     word ptr [rbp+57h+szValueBuf], ax
0x18004cb24  add     qword ptr [rdi+8], 20h ; ' '
0x18004cb29  jmp     short loc_18004CB38
0x18004cb2b  lea     r8, [rbp+57h+szValueBuf]
0x18004cb2f  mov     rcx, rdi
0x18004cb32  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18004cb37  nop
0x18004cb38  lea     rcx, [rbp+57h+szValueBuf]; void *
0x18004cb3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cb41  jmp     loc_18004CA5F
0x18004cb46  mov     ecx, [rbp+57h+phRecord]; hAny
0x18004cb49  test    ecx, ecx
0x18004cb4b  jz      short loc_18004CB54
0x18004cb4d  call    cs:__imp_MsiCloseHandle
0x18004cb53  nop
0x18004cb54  lea     rcx, [rbp+57h+szQuery]; void *
0x18004cb58  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cb5d  nop
0x18004cb5e  mov     ecx, [rbp+57h+hAny]; hAny
0x18004cb61  test    ecx, ecx
0x18004cb63  jz      short loc_18004CB6C
0x18004cb65  call    cs:__imp_MsiCloseHandle
0x18004cb6b  nop
0x18004cb6c  mov     ecx, [rbp+57h+phDatabase]; hAny
0x18004cb6f  test    ecx, ecx
0x18004cb71  jz      short loc_18004CB79
0x18004cb73  call    cs:__imp_MsiCloseHandle
0x18004cb79  xor     eax, eax
0x18004cb7b  mov     rcx, qword ptr [rbp+57h+var_48]
0x18004cb7f  xor     rcx, rsp; StackCookie
0x18004cb82  call    __security_check_cookie
0x18004cb87  movaps  xmm6, [rsp+100h+var_48+8]
0x18004cb8f  add     rsp, 0D8h
0x18004cb96  pop     r14
0x18004cb98  pop     r12
0x18004cb9a  pop     rdi
0x18004cb9b  pop     rsi
0x18004cb9c  pop     rbx
0x18004cb9d  pop     rbp
0x18004cb9e  retn
0x18004cb9f  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
