# AppCompatUtility::MsiOperations::GetColumn(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uint,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18004cbac`
- end: `0x18004ce97`
- name: `?GetColumn@MsiOperations@AppCompatUtility@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0IAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004cf98`

## callees

- `0x180001cf0`
- `0x1800085bc`
- `0x18000b720`
- `0x18000bbbc`
- `0x1800118f4`
- `0x180021dd4`
- `0x18002ec04`
- `0x18004cbac`

## import_xrefs

- `MSI!MsiCloseHandle` at `0x18004cc33`
- `MSI!MsiCloseHandle` at `0x18004cc97`
- `MSI!MsiCloseHandle` at `0x18004cd02`
- `MSI!MsiCloseHandle` at `0x18004cd57`
- `MSI!MsiCloseHandle` at `0x18004ce3f`
- `MSI!MsiCloseHandle` at `0x18004ce57`
- `MSI!MsiCloseHandle` at `0x18004ce65`
- `MSI!MsiCloseHandle` at `0x18004cc33`
- `MSI!MsiCloseHandle` at `0x18004cc97`
- `MSI!MsiCloseHandle` at `0x18004cd02`
- `MSI!MsiCloseHandle` at `0x18004cd57`
- `MSI!MsiCloseHandle` at `0x18004ce3f`
- `MSI!MsiCloseHandle` at `0x18004ce57`
- `MSI!MsiCloseHandle` at `0x18004ce65`
- `MSI!MsiOpenDatabaseW` at `0x18004cbf8`
- `MSI!MsiOpenDatabaseW` at `0x18004cbf8`
- `MSI!MsiRecordGetStringW` at `0x18004cd88`
- `MSI!MsiRecordGetStringW` at `0x18004cdca`
- `MSI!MsiRecordGetStringW` at `0x18004cd88`
- `MSI!MsiRecordGetStringW` at `0x18004cdca`
- `MSI!MsiViewFetch` at `0x18004cd6b`
- `MSI!MsiViewFetch` at `0x18004cd6b`
- `MSI!MsiViewExecute` at `0x18004cd3d`
- `MSI!MsiViewExecute` at `0x18004cd3d`
- `MSI!MsiDatabaseOpenViewW` at `0x18004ccb9`
- `MSI!MsiDatabaseOpenViewW` at `0x18004ccb9`

## string_xrefs

- `0x18004cc1a`: `onecore\windows\appcompat\migrationshims\lib\msioperations.cpp`
- `0x18004ccdb`: `onecore\windows\appcompat\migrationshims\lib\msioperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AppCompatUtility::MsiOperations::GetColumn(const WCHAR *a1, __int64 a2, __int64 a3, char **a4)
{
  signed int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  signed int v9; // ebx
  const WCHAR *v11; // rdx
  signed int v12; // eax
  char *v13; // rsi
  char *v14; // rbx
  __m128i si128; // xmm6
  WCHAR *v16; // r8
  char *v17; // rdx
  int v18; // [rsp+28h] [rbp-49h]
  MSIHANDLE hAny; // [rsp+48h] [rbp-29h] BYREF
  MSIHANDLE phRecord; // [rsp+4Ch] [rbp-25h] BYREF
  MSIHANDLE phDatabase; // [rsp+50h] [rbp-21h] BYREF
  DWORD pcchValueBuf; // [rsp+54h] [rbp-1Dh] BYREF
  __int64 v23; // [rsp+58h] [rbp-19h]
  LPWSTR szValueBuf[2]; // [rsp+60h] [rbp-11h] BYREF
  __m128i v25; // [rsp+70h] [rbp-1h]
  LPCWSTR szQuery[4]; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v23 = -2;
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
        (void *)0x5B,
        (unsigned int)"onecore\\windows\\appcompat\\migrationshims\\lib\\msioperations.cpp",
        (const char *)(unsigned int)v9,
        v18);
LABEL_8:
    if ( phDatabase )
      MsiCloseHandle(phDatabase);
    return (unsigned int)v9;
  }
  hAny = 0;
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *(_QWORD *)(a2 + 16)) < 0xE )
    std::_Xlen_string();
  std::wstring::wstring(szQuery, v7, v8, L"SELECT * FROM ");
  hAny = 0;
  v11 = (const WCHAR *)szQuery;
  if ( szQuery[3] > (LPCWSTR)7 )
    v11 = szQuery[0];
  v12 = MsiDatabaseOpenViewW(phDatabase, v11, &hAny);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    if ( v9 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecore\\windows\\appcompat\\migrationshims\\lib\\msioperations.cpp",
        (const char *)(unsigned int)v9,
        14);
    std::wstring::~wstring(szQuery);
    if ( hAny )
      MsiCloseHandle(hAny);
    goto LABEL_8;
  }
  v13 = a4[1];
  v14 = *a4;
  if ( *a4 != v13 )
  {
    do
    {
      std::wstring::~wstring(v14);
      v14 += 32;
    }
    while ( v14 != v13 );
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
    MsiRecordGetStringW(phRecord, 3u, 0, &pcchValueBuf);
    ++pcchValueBuf;
    *(_OWORD *)szValueBuf = 0;
    v25 = si128;
    LOWORD(szValueBuf[0]) = 0;
    std::wstring::resize(szValueBuf);
    v16 = (WCHAR *)szValueBuf;
    if ( v25.m128i_i64[1] > 7uLL )
      v16 = szValueBuf[0];
    MsiRecordGetStringW(phRecord, 3u, v16, &pcchValueBuf);
    std::wstring::resize(szValueBuf);
    v17 = a4[1];
    if ( v17 == a4[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a4, v17, szValueBuf);
    }
    else
    {
      *(_OWORD *)v17 = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 3) = 0;
      *(_OWORD *)v17 = *(_OWORD *)szValueBuf;
      *((__m128i *)v17 + 1) = v25;
      v25 = si128;
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
0x18004cbac  mov     rax, rsp
0x18004cbaf  push    rbp
0x18004cbb0  push    rsi
0x18004cbb1  push    rdi
0x18004cbb2  lea     rbp, [rax-5Fh]
0x18004cbb6  sub     rsp, 0B0h
0x18004cbbd  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x18004cbc5  mov     [rax+18h], rbx
0x18004cbc9  movaps  xmmword ptr [rax-28h], xmm6
0x18004cbcd  mov     rax, cs:__security_cookie
0x18004cbd4  xor     rax, rsp
0x18004cbd7  mov     [rbp+57h+var_28], rax
0x18004cbdb  mov     rdi, r9
0x18004cbde  mov     rsi, rdx
0x18004cbe1  mov     [rbp+57h+phDatabase], 0
0x18004cbe8  cmp     qword ptr [rcx+18h], 7
0x18004cbed  jbe     short loc_18004CBF2
0x18004cbef  mov     rcx, [rcx]; szDatabasePath
0x18004cbf2  lea     r8, [rbp+57h+phDatabase]; phDatabase
0x18004cbf6  xor     edx, edx; szPersist
0x18004cbf8  call    cs:__imp_MsiOpenDatabaseW
0x18004cbfe  mov     ebx, eax
0x18004cc00  test    eax, eax
0x18004cc02  jz      short loc_18004CC40
0x18004cc04  jle     short loc_18004CC0F
0x18004cc06  movzx   ebx, ax
0x18004cc09  or      ebx, 80070000h
0x18004cc0f  test    ebx, ebx
0x18004cc11  jns     short loc_18004CC2C
0x18004cc13  mov     rcx, [rbp+5Fh]; this
0x18004cc17  mov     r9d, ebx; char *
0x18004cc1a  lea     r8, aOnecoreWindows_2; "onecore\\windows\\appcompat\\migrations"...
0x18004cc21  mov     edx, 5Bh ; '['; void *
0x18004cc26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cc2b  nop
0x18004cc2c  mov     ecx, [rbp+57h+phDatabase]; hAny
0x18004cc2f  test    ecx, ecx
0x18004cc31  jz      short loc_18004CC39
0x18004cc33  call    cs:__imp_MsiCloseHandle
0x18004cc39  mov     eax, ebx
0x18004cc3b  jmp     loc_18004CE6D
0x18004cc40  mov     [rbp+57h+hAny], 0
0x18004cc47  mov     rcx, [rsi+10h]
0x18004cc4b  mov     rax, 7FFFFFFFFFFFFFFEh
0x18004cc55  sub     rax, rcx
0x18004cc58  cmp     rax, 0Eh
0x18004cc5c  jb      loc_18004CE91
0x18004cc62  cmp     qword ptr [rsi+18h], 7
0x18004cc67  jbe     short loc_18004CC6C
0x18004cc69  mov     rsi, [rsi]
0x18004cc6c  mov     [rsp+0C0h+var_90], rcx
0x18004cc71  mov     [rsp+0C0h+var_98], rsi
0x18004cc76  mov     qword ptr [rsp+0C0h+var_A0], 0Eh; int
0x18004cc7f  lea     r9, aSelectFrom; "SELECT * FROM "
0x18004cc86  lea     rcx, [rbp+57h+szQuery]
0x18004cc8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004cc8f  nop
0x18004cc90  mov     ecx, [rbp+57h+hAny]; hAny
0x18004cc93  test    ecx, ecx
0x18004cc95  jz      short loc_18004CC9D
0x18004cc97  call    cs:__imp_MsiCloseHandle
0x18004cc9d  mov     [rbp+57h+hAny], 0
0x18004cca4  lea     rdx, [rbp+57h+szQuery]
0x18004cca8  cmp     [rbp+57h+var_30], 7
0x18004ccad  cmova   rdx, [rbp+57h+szQuery]; szQuery
0x18004ccb2  lea     r8, [rbp+57h+hAny]; phView
0x18004ccb6  mov     ecx, [rbp+57h+phDatabase]; hDatabase
0x18004ccb9  call    cs:__imp_MsiDatabaseOpenViewW
0x18004ccbf  mov     ebx, eax
0x18004ccc1  test    eax, eax
0x18004ccc3  jz      short loc_18004CD0D
0x18004ccc5  jle     short loc_18004CCD0
0x18004ccc7  movzx   ebx, ax
0x18004ccca  or      ebx, 80070000h
0x18004ccd0  test    ebx, ebx
0x18004ccd2  jns     short loc_18004CCED
0x18004ccd4  mov     rcx, [rbp+5Fh]; this
0x18004ccd8  mov     r9d, ebx; char *
0x18004ccdb  lea     r8, aOnecoreWindows_2; "onecore\\windows\\appcompat\\migrations"...
0x18004cce2  mov     edx, 60h ; '`'; void *
0x18004cce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ccec  nop
0x18004cced  lea     rcx, [rbp+57h+szQuery]; void *
0x18004ccf1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ccf6  nop
0x18004ccf7  mov     ecx, [rbp+57h+hAny]; hAny
0x18004ccfa  test    ecx, ecx
0x18004ccfc  jz      loc_18004CC2C
0x18004cd02  call    cs:__imp_MsiCloseHandle
0x18004cd08  jmp     loc_18004CC2C
0x18004cd0d  mov     rsi, [rdi+8]
0x18004cd11  mov     rbx, [rdi]
0x18004cd14  cmp     rbx, rsi
0x18004cd17  jz      short loc_18004CD31
0x18004cd19  mov     rcx, rbx; void *
0x18004cd1c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cd21  add     rbx, 20h ; ' '
0x18004cd25  cmp     rbx, rsi
0x18004cd28  jnz     short loc_18004CD19
0x18004cd2a  mov     rax, [rdi]
0x18004cd2d  mov     [rdi+8], rax
0x18004cd31  mov     [rbp+57h+phRecord], 0
0x18004cd38  xor     edx, edx; hRecord
0x18004cd3a  mov     ecx, [rbp+57h+hAny]; hView
0x18004cd3d  call    cs:__imp_MsiViewExecute
0x18004cd43  mov     ebx, 3
0x18004cd48  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18004cd50  mov     ecx, [rbp+57h+phRecord]; hAny
0x18004cd53  test    ecx, ecx
0x18004cd55  jz      short loc_18004CD5D
0x18004cd57  call    cs:__imp_MsiCloseHandle
0x18004cd5d  mov     [rbp+57h+phRecord], 0
0x18004cd64  lea     rdx, [rbp+57h+phRecord]; phRecord
0x18004cd68  mov     ecx, [rbp+57h+hAny]; hView
0x18004cd6b  call    cs:__imp_MsiViewFetch
0x18004cd71  test    eax, eax
0x18004cd73  jnz     loc_18004CE38
0x18004cd79  mov     [rbp+57h+pcchValueBuf], eax
0x18004cd7c  lea     r9, [rbp+57h+pcchValueBuf]; pcchValueBuf
0x18004cd80  xor     r8d, r8d; szValueBuf
0x18004cd83  mov     edx, ebx; iField
0x18004cd85  mov     ecx, [rbp+57h+phRecord]; hRecord
0x18004cd88  call    cs:__imp_MsiRecordGetStringW
0x18004cd8e  mov     eax, [rbp+57h+pcchValueBuf]
0x18004cd91  inc     eax
0x18004cd93  mov     [rbp+57h+pcchValueBuf], eax
0x18004cd96  mov     edx, eax
0x18004cd98  xorps   xmm0, xmm0
0x18004cd9b  movups  xmmword ptr [rbp+57h+szValueBuf], xmm0
0x18004cd9f  movdqu  [rbp+57h+var_58], xmm6
0x18004cda4  xor     eax, eax
0x18004cda6  mov     word ptr [rbp+57h+szValueBuf], ax
0x18004cdaa  lea     rcx, [rbp+57h+szValueBuf]; Src
0x18004cdae  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004cdb3  lea     r8, [rbp+57h+szValueBuf]
0x18004cdb7  cmp     qword ptr [rbp+57h+var_58+8], 7
0x18004cdbc  cmova   r8, [rbp+57h+szValueBuf]; szValueBuf
0x18004cdc1  lea     r9, [rbp+57h+pcchValueBuf]; pcchValueBuf
0x18004cdc5  mov     edx, ebx; iField
0x18004cdc7  mov     ecx, [rbp+57h+phRecord]; hRecord
0x18004cdca  call    cs:__imp_MsiRecordGetStringW
0x18004cdd0  mov     edx, [rbp+57h+pcchValueBuf]
0x18004cdd3  lea     rcx, [rbp+57h+szValueBuf]; Src
0x18004cdd7  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004cddc  mov     rdx, [rdi+8]
0x18004cde0  cmp     rdx, [rdi+10h]
0x18004cde4  jz      short loc_18004CE1D
0x18004cde6  xorps   xmm0, xmm0
0x18004cde9  movups  xmmword ptr [rdx], xmm0
0x18004cdec  mov     qword ptr [rdx+10h], 0
0x18004cdf4  mov     qword ptr [rdx+18h], 0
0x18004cdfc  movups  xmm0, xmmword ptr [rbp+57h+szValueBuf]
0x18004ce00  movups  xmmword ptr [rdx], xmm0
0x18004ce03  movups  xmm1, [rbp+57h+var_58]
0x18004ce07  movups  xmmword ptr [rdx+10h], xmm1
0x18004ce0b  movdqu  [rbp+57h+var_58], xmm6
0x18004ce10  xor     eax, eax
0x18004ce12  mov     word ptr [rbp+57h+szValueBuf], ax
0x18004ce16  add     qword ptr [rdi+8], 20h ; ' '
0x18004ce1b  jmp     short loc_18004CE2A
0x18004ce1d  lea     r8, [rbp+57h+szValueBuf]
0x18004ce21  mov     rcx, rdi
0x18004ce24  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18004ce29  nop
0x18004ce2a  lea     rcx, [rbp+57h+szValueBuf]; void *
0x18004ce2e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ce33  jmp     loc_18004CD50
0x18004ce38  mov     ecx, [rbp+57h+phRecord]; hAny
0x18004ce3b  test    ecx, ecx
0x18004ce3d  jz      short loc_18004CE46
0x18004ce3f  call    cs:__imp_MsiCloseHandle
0x18004ce45  nop
0x18004ce46  lea     rcx, [rbp+57h+szQuery]; void *
0x18004ce4a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ce4f  nop
0x18004ce50  mov     ecx, [rbp+57h+hAny]; hAny
0x18004ce53  test    ecx, ecx
0x18004ce55  jz      short loc_18004CE5E
0x18004ce57  call    cs:__imp_MsiCloseHandle
0x18004ce5d  nop
0x18004ce5e  mov     ecx, [rbp+57h+phDatabase]; hAny
0x18004ce61  test    ecx, ecx
0x18004ce63  jz      short loc_18004CE6B
0x18004ce65  call    cs:__imp_MsiCloseHandle
0x18004ce6b  xor     eax, eax
0x18004ce6d  mov     rcx, [rbp+57h+var_28]
0x18004ce71  xor     rcx, rsp; StackCookie
0x18004ce74  call    __security_check_cookie
0x18004ce79  lea     r11, [rsp+0C0h+var_10]
0x18004ce81  mov     rbx, [r11+30h]
0x18004ce85  movaps  xmm6, xmmword ptr [r11-10h]
0x18004ce8a  mov     rsp, r11
0x18004ce8d  pop     rdi
0x18004ce8e  pop     rsi
0x18004ce8f  pop     rbp
0x18004ce90  retn
0x18004ce91  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
