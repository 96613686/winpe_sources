# win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close(win_musl::ByteReceiverUnique<win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer,0,IUnknown> &)

- ea: `0x180008e48`
- end: `0x1800094af`
- name: `?Close@ZipEndOfCentralDirectoryZip64Consumer@consumption@win_musl@@QEAAXAEAV?$ByteReceiverUnique@VZipEndOfCentralDirectoryZip64Consumer@consumption@win_musl@@$0A@UIUnknown@@@3@@Z`
- size: `1639`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180085574`

## callees

- `0x1800079d8`
- `0x180007b44`
- `0x180008e48`
- `0x18000a030`
- `0x180015af4`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1801108cc`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800091f1`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800091f1`

## string_xrefs

- `0x1800093d8`: `sizeCentralDirectory`
- `0x180008fc7`: `diskNumberDirectoryStart`
- `0x180009334`: `directoryEntriesCountThisDisk`
- `0x180009408`: `offsetCentralDirectory`
- `0x180008f16`: `win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close`
- `0x18000927b`: `win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close`
- `0x180008f25`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryzip64consumer.cpp`
- `0x180009287`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryzip64consumer.cpp`
- `0x180009420`: `invalid end_of_central_directory source value!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close(_QWORD *a1)
{
  __int64 v2; // rcx
  __int128 v3; // xmm6
  __int64 v4; // rax
  __int128 v5; // xmm6
  __int64 v6; // r15
  __int128 v7; // xmm6
  __int64 v8; // rax
  __int64 v9; // r14
  __int128 v10; // xmm6
  __int64 v11; // r15
  __int128 v12; // xmm6
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  int v16; // ecx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 result; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  _BYTE v23[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+78h] [rbp-90h]
  _QWORD pExceptionObject[3]; // [rsp+88h] [rbp-80h] BYREF
  _DWORD v28[2]; // [rsp+A0h] [rbp-68h] BYREF
  const char *v29; // [rsp+A8h] [rbp-60h]
  _BYTE v30[56]; // [rsp+B0h] [rbp-58h] BYREF
  GUID v31; // [rsp+E8h] [rbp-20h]
  int v32; // [rsp+110h] [rbp+8h]

  v26 = -2;
  v2 = a1[7];
  if ( !v2 || a1[8] - v2 != 52 )
  {
    win_musl::DebugLogHelper("(no filename)", &word_18013A0B6, 143, 1024, -2142171135, L"Wrong number of bytes sent");
    *(_QWORD *)&v25 = "Unexpected HRESULT returned by API";
    exception::exception((exception *)pExceptionObject, (const char *const *)&v25);
    memset_0(v30, 0, 0x68u);
    v29 = "(no filename)";
    v28[1] = 143;
    v32 = -1;
    pExceptionObject[0] = &SplException::THResultException::`vftable';
    v28[0] = -2142171135;
    v31 = GUID_NULL;
    if ( SplException::Functions )
      v32 = SplException::Functions(v28);
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_QWORD *)&v25 = 52;
  *((_QWORD *)&v25 + 1) = v2;
  v3 = v25;
  v23[0] = 0;
  v24 = v25;
  v4 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  if ( v23[0] )
  {
    v24 = v3;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      154,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "sizeOfThis",
      8,
      &v24);
  }
  a1[10] = v4 - 44;
  v24 = v25;
  win_musl::detail::readThenLog<unsigned short>(
    (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirector"
                  "yzip64consumer.cpp",
    160,
    (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
    (unsigned int)"versionMadeBy",
    (__int64)&v24,
    (__int64)&v25);
  v24 = v25;
  win_musl::detail::readThenLog<unsigned short>(
    (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirector"
                  "yzip64consumer.cpp",
    164,
    (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
    (unsigned int)"versionMinimumExtract",
    (__int64)&v24,
    (__int64)&v25);
  v24 = v25;
  if ( (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                       (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipe"
                                     "ndofcentraldirectoryzip64consumer.cpp",
                       168,
                       (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
                       (unsigned int)"diskNumberThis",
                       (__int64)&v24,
                       (__int64)&v25) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xACu,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v24 = v25;
  if ( (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                       (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipe"
                                     "ndofcentraldirectoryzip64consumer.cpp",
                       178,
                       (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
                       (unsigned int)"diskNumberDirectoryStart",
                       (__int64)&v24,
                       (__int64)&v25) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xB6u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v5 = v25;
  v23[0] = 0;
  v24 = v25;
  v6 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  if ( v23[0] )
  {
    v24 = v5;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      188,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "directoryEntriesCountThisDisk",
      8,
      &v24);
  }
  v7 = v25;
  v23[0] = 0;
  v24 = v25;
  v8 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  v9 = v8;
  if ( v23[0] )
  {
    v24 = v7;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      199,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "countEntries",
      8,
      &v24);
  }
  if ( v6 != v8 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xD0u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v10 = v25;
  v23[0] = 0;
  v24 = v25;
  v11 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  if ( v23[0] )
  {
    v24 = v10;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      219,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "sizeCentralDirectory",
      8,
      &v24);
  }
  v12 = v25;
  v23[0] = 0;
  v24 = v25;
  v13 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  v14 = v13;
  if ( v23[0] )
  {
    v24 = v12;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      231,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "offsetCentralDirectory",
      8,
      &v24);
  }
  v15 = a1[3];
  v16 = *(_DWORD *)(v15 + 128);
  if ( !v16 )
  {
    *(_DWORD *)(v15 + 128) = 2;
    *(_QWORD *)(a1[3] + 152LL) = v13;
    *(_QWORD *)(a1[3] + 144LL) = v11;
    *(_QWORD *)(a1[3] + 136LL) = v9;
    *(_DWORD *)(a1[3] + 168LL) = 0;
    result = a1[3];
LABEL_22:
    *(_DWORD *)(result + 172) = 0;
    goto LABEL_23;
  }
  if ( v16 != 1 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x120u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"invalid end_of_central_directory source value!");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *(_QWORD *)(v15 + 152) == 0xFFFFFFFFLL )
    *(_QWORD *)(v15 + 152) = v13;
  v17 = a1[3];
  if ( *(_QWORD *)(v17 + 144) == 0xFFFFFFFFLL )
    *(_QWORD *)(v17 + 144) = v11;
  v18 = a1[3];
  if ( *(_QWORD *)(v18 + 136) == 0xFFFF )
    *(_QWORD *)(v18 + 136) = v9;
  v19 = a1[3];
  if ( *(_DWORD *)(v19 + 168) == 0xFFFF )
    *(_DWORD *)(v19 + 168) = 0;
  result = a1[3];
  if ( *(_DWORD *)(result + 172) == 0xFFFF )
    goto LABEL_22;
LABEL_23:
  v21 = a1[4];
  if ( v21 && dword_1801C4FE0 != -1 )
  {
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v21 + 40LL))(v21, a1[10] + a1[5], v14);
    v22 = a1[4];
    a1[4] = 0;
    if ( v22 )
      return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return result;
}

```

## disassembly

```asm
0x180008e48  mov     rax, rsp
0x180008e4b  push    rbp
0x180008e4c  push    rdi
0x180008e4d  push    r12
0x180008e4f  push    r14
0x180008e51  push    r15
0x180008e53  lea     rbp, [rax-68h]
0x180008e57  sub     rsp, 140h
0x180008e5e  mov     [rsp+160h+var_F0], 0FFFFFFFFFFFFFFFEh
0x180008e67  mov     [rax+10h], rbx
0x180008e6b  mov     [rax+18h], rsi
0x180008e6f  movaps  xmmword ptr [rax-38h], xmm6
0x180008e73  mov     rax, cs:__security_cookie
0x180008e7a  xor     rax, rsp
0x180008e7d  mov     [rbp+60h+var_40], rax
0x180008e81  mov     rbx, rcx
0x180008e84  xor     r12d, r12d
0x180008e87  mov     rcx, [rcx+38h]
0x180008e8b  test    rcx, rcx
0x180008e8e  jz      loc_1800091A4
0x180008e94  mov     rax, [rbx+40h]
0x180008e98  sub     rax, rcx
0x180008e9b  cmp     rax, 34h ; '4'
0x180008e9f  jnz     loc_1800091A4
0x180008ea5  mov     dword ptr [rsp+160h+var_108+8], eax
0x180008ea9  xor     eax, eax
0x180008eab  mov     dword ptr [rsp+160h+var_108+0Ch], eax
0x180008eaf  mov     [rsp+160h+var_F8], rcx
0x180008eb4  movaps  xmm6, [rsp+160h+var_108+8]
0x180008eb9  movaps  [rsp+160h+var_108+8], xmm6
0x180008ebe  mov     [rsp+160h+var_120], r12b
0x180008ec3  movdqa  [rsp+160h+var_118+8], xmm6
0x180008ec9  lea     r8, [rsp+160h+var_120]
0x180008ece  lea     rdx, [rsp+160h+var_108+8]
0x180008ed3  lea     rcx, [rsp+160h+var_118+8]
0x180008ed8  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x180008edd  cmp     [rsp+160h+var_120], r12b
0x180008ee2  jnz     loc_18000925C
0x180008ee8  add     rax, 0FFFFFFFFFFFFFFD4h
0x180008eec  mov     [rbx+50h], rax
0x180008ef0  movaps  xmm0, [rsp+160h+var_108+8]
0x180008ef5  movdqa  [rsp+160h+var_118+8], xmm0
0x180008efb  lea     rax, [rsp+160h+var_108+8]
0x180008f00  mov     qword ptr [rsp+160h+var_138], rax
0x180008f05  lea     rax, [rsp+160h+var_118+8]
0x180008f0a  mov     qword ptr [rsp+160h+var_140], rax
0x180008f0f  lea     r9, aVersionmadeby; "versionMadeBy"
0x180008f16  lea     rdi, aWinMuslConsump; "win_musl::consumption::ZipEndOfCentralD"...
0x180008f1d  mov     r8, rdi
0x180008f20  mov     edx, 0A0h
0x180008f25  lea     rsi, aOnecorePrintsc_8; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180008f2c  mov     rcx, rsi
0x180008f2f  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180008f34  movaps  xmm0, [rsp+160h+var_108+8]
0x180008f39  movdqa  [rsp+160h+var_118+8], xmm0
0x180008f3f  lea     rax, [rsp+160h+var_108+8]
0x180008f44  mov     qword ptr [rsp+160h+var_138], rax
0x180008f49  lea     rax, [rsp+160h+var_118+8]
0x180008f4e  mov     qword ptr [rsp+160h+var_140], rax
0x180008f53  lea     r9, aVersionminimum; "versionMinimumExtract"
0x180008f5a  mov     r8, rdi
0x180008f5d  mov     edx, 0A4h
0x180008f62  mov     rcx, rsi
0x180008f65  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180008f6a  movaps  xmm0, [rsp+160h+var_108+8]
0x180008f6f  movdqa  [rsp+160h+var_118+8], xmm0
0x180008f75  lea     rax, [rsp+160h+var_108+8]
0x180008f7a  mov     qword ptr [rsp+160h+var_138], rax
0x180008f7f  lea     rax, [rsp+160h+var_118+8]
0x180008f84  mov     qword ptr [rsp+160h+var_140], rax
0x180008f89  lea     r9, aDisknumberthis; "diskNumberThis"
0x180008f90  mov     r8, rdi
0x180008f93  mov     edx, 0A8h
0x180008f98  mov     rcx, rsi
0x180008f9b  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180008fa0  test    eax, eax
0x180008fa2  jnz     loc_180009294
0x180008fa8  movaps  xmm0, [rsp+160h+var_108+8]
0x180008fad  movdqa  [rsp+160h+var_118+8], xmm0
0x180008fb3  lea     rax, [rsp+160h+var_108+8]
0x180008fb8  mov     qword ptr [rsp+160h+var_138], rax
0x180008fbd  lea     rax, [rsp+160h+var_118+8]
0x180008fc2  mov     qword ptr [rsp+160h+var_140], rax
0x180008fc7  lea     r9, aDisknumberdire; "diskNumberDirectoryStart"
0x180008fce  mov     r8, rdi
0x180008fd1  mov     edx, 0B2h
0x180008fd6  mov     rcx, rsi
0x180008fd9  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180008fde  test    eax, eax
0x180008fe0  jnz     loc_1800092D8
0x180008fe6  movaps  xmm6, [rsp+160h+var_108+8]
0x180008feb  mov     [rsp+160h+var_120], r12b
0x180008ff0  movdqa  [rsp+160h+var_118+8], xmm6
0x180008ff6  lea     r8, [rsp+160h+var_120]
0x180008ffb  lea     rdx, [rsp+160h+var_108+8]
0x180009000  lea     rcx, [rsp+160h+var_118+8]
0x180009005  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18000900a  mov     r15, rax
0x18000900d  cmp     [rsp+160h+var_120], r12b
0x180009012  jnz     loc_18000931C
0x180009018  movaps  xmm6, [rsp+160h+var_108+8]
0x18000901d  mov     [rsp+160h+var_120], r12b
0x180009022  movdqa  [rsp+160h+var_118+8], xmm6
0x180009028  lea     r8, [rsp+160h+var_120]
0x18000902d  lea     rdx, [rsp+160h+var_108+8]
0x180009032  lea     rcx, [rsp+160h+var_118+8]
0x180009037  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18000903c  mov     r14, rax
0x18000903f  cmp     [rsp+160h+var_120], r12b
0x180009044  jnz     loc_18000934C
0x18000904a  cmp     r15, rax
0x18000904d  jnz     loc_18000937C
0x180009053  movaps  xmm6, [rsp+160h+var_108+8]
0x180009058  mov     [rsp+160h+var_120], r12b
0x18000905d  movdqa  [rsp+160h+var_118+8], xmm6
0x180009063  lea     r8, [rsp+160h+var_120]
0x180009068  lea     rdx, [rsp+160h+var_108+8]
0x18000906d  lea     rcx, [rsp+160h+var_118+8]
0x180009072  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x180009077  mov     r15, rax
0x18000907a  cmp     [rsp+160h+var_120], r12b
0x18000907f  jnz     loc_1800093C0
0x180009085  movaps  xmm6, [rsp+160h+var_108+8]
0x18000908a  mov     [rsp+160h+var_120], r12b
0x18000908f  movdqa  [rsp+160h+var_118+8], xmm6
0x180009095  lea     r8, [rsp+160h+var_120]
0x18000909a  lea     rdx, [rsp+160h+var_108+8]
0x18000909f  lea     rcx, [rsp+160h+var_118+8]
0x1800090a4  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x1800090a9  mov     r8, rax
0x1800090ac  cmp     [rsp+160h+var_120], r12b
0x1800090b1  jnz     loc_1800093F0
0x1800090b7  mov     rdx, [rbx+18h]
0x1800090bb  mov     ecx, [rdx+80h]
0x1800090c1  test    ecx, ecx
0x1800090c3  jz      loc_180009470
0x1800090c9  cmp     ecx, 1
0x1800090cc  jnz     loc_180009420
0x1800090d2  mov     eax, 0FFFFFFFFh
0x1800090d7  cmp     [rdx+98h], rax
0x1800090de  jnz     short loc_1800090E7
0x1800090e0  mov     [rdx+98h], r8
0x1800090e7  mov     rcx, [rbx+18h]
0x1800090eb  cmp     [rcx+90h], rax
0x1800090f2  jnz     short loc_1800090FB
0x1800090f4  mov     [rcx+90h], r15
0x1800090fb  mov     rax, [rbx+18h]
0x1800090ff  mov     ecx, 0FFFFh
0x180009104  cmp     [rax+88h], rcx
0x18000910b  jnz     short loc_180009114
0x18000910d  mov     [rax+88h], r14
0x180009114  mov     rax, [rbx+18h]
0x180009118  cmp     [rax+0A8h], ecx
0x18000911e  jz      loc_180009464
0x180009124  mov     rax, [rbx+18h]
0x180009128  cmp     [rax+0ACh], ecx
0x18000912e  jnz     short loc_180009137
0x180009130  mov     [rax+0ACh], r12d
0x180009137  mov     rcx, [rbx+20h]
0x18000913b  test    rcx, rcx
0x18000913e  jz      short loc_180009177
0x180009140  cmp     cs:dword_1801C4FE0, 0FFFFFFFFh
0x180009147  jz      short loc_180009177
0x180009149  mov     rax, [rcx]
0x18000914c  mov     rdx, [rbx+28h]
0x180009150  add     rdx, [rbx+50h]
0x180009154  mov     rax, [rax+28h]
0x180009158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000915d  mov     rcx, [rbx+20h]
0x180009161  mov     [rbx+20h], r12
0x180009165  test    rcx, rcx
0x180009168  jz      short loc_180009177
0x18000916a  mov     rax, [rcx]
0x18000916d  mov     rax, [rax+10h]
0x180009171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009176  nop
0x180009177  mov     rcx, [rbp+60h+var_40]
0x18000917b  xor     rcx, rsp; StackCookie
0x18000917e  call    __security_check_cookie
0x180009183  lea     r11, [rsp+160h+var_20]
0x18000918b  mov     rbx, [r11+38h]
0x18000918f  mov     rsi, [r11+40h]
0x180009193  movaps  xmm6, xmmword ptr [r11-10h]
0x180009198  mov     rsp, r11
0x18000919b  pop     r15
0x18000919d  pop     r14
0x18000919f  pop     r12
0x1800091a1  pop     rdi
0x1800091a2  pop     rbp
0x1800091a3  retn
0x1800091a4  lea     rax, aWrongNumberOfB; "Wrong number of bytes sent"
0x1800091ab  mov     qword ptr [rsp+160h+var_138], rax
0x1800091b0  mov     [rsp+160h+var_140], 80511001h
0x1800091b8  mov     edi, 8Fh
0x1800091bd  mov     r9d, 400h
0x1800091c3  mov     r8d, edi
0x1800091c6  lea     rdx, word_18013A0B6
0x1800091cd  lea     rbx, aNoFilename; "(no filename)"
0x1800091d4  mov     rcx, rbx
0x1800091d7  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x1800091dc  lea     rax, aUnexpectedHres; "Unexpected HRESULT returned by API"
0x1800091e3  mov     qword ptr [rsp+160h+var_108+8], rax
0x1800091e8  lea     rdx, [rsp+160h+var_108+8]
0x1800091ed  lea     rcx, [rbp+60h+pExceptionObject]
0x1800091f1  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x1800091f7  xor     edx, edx; Val
0x1800091f9  lea     r8d, [rdi-27h]; Size
0x1800091fd  lea     rcx, [rbp+60h+var_B8]; void *
0x180009201  call    memset_0
0x180009206  mov     [rbp+60h+var_C0], rbx
0x18000920a  mov     [rbp+60h+var_C4], edi
0x18000920d  mov     eax, 0FFFFFFFFh
0x180009212  mov     [rbp+60h+var_58], eax
0x180009215  lea     rax, ??_7THResultException@SplException@@6B@; const SplException::THResultException::`vftable'
0x18000921c  mov     [rbp+60h+pExceptionObject], rax
0x180009220  mov     [rbp+60h+var_C8], 80511001h
0x180009227  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000922e  movdqu  [rbp+60h+var_80], xmm0
0x180009233  mov     rax, cs:?Functions@SplException@@3UExceptionTableFunctions@1@A; SplException::ExceptionTableFunctions SplException::Functions
0x18000923a  test    rax, rax
0x18000923d  jz      short loc_18000924B
0x18000923f  lea     rcx, [rbp+60h+var_C8]
0x180009243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009248  mov     [rbp+60h+var_58], eax
0x18000924b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180009252  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180009256  call    _CxxThrowException_0
0x18000925c  movdqa  [rsp+160h+var_118+8], xmm6
0x180009262  lea     rax, [rsp+160h+var_118+8]
0x180009267  mov     qword ptr [rsp+160h+var_138], rax
0x18000926c  mov     [rsp+160h+var_140], 8
0x180009274  lea     r9, aSizeofthis; "sizeOfThis"
0x18000927b  lea     r8, aWinMuslConsump; "win_musl::consumption::ZipEndOfCentralD"...
0x180009282  mov     edx, 9Ah
0x180009287  lea     rcx, aOnecorePrintsc_8; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18000928e  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x180009294  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x18000929b  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x1800092a0  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x1800092a8  mov     [rsp+160h+var_140], 0ACh; unsigned int
0x1800092b0  lea     r9, word_18013A0B6
0x1800092b7  lea     r8, aNoFilename; "(no filename)"
0x1800092be  lea     rcx, [rbp+60h+pExceptionObject]; this
0x1800092c2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800092c7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800092ce  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x1800092d2  call    _CxxThrowException_0
0x1800092d8  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x1800092df  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x1800092e4  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x1800092ec  mov     [rsp+160h+var_140], 0B6h; unsigned int
0x1800092f4  lea     r9, word_18013A0B6
0x1800092fb  lea     r8, aNoFilename; "(no filename)"
0x180009302  lea     rcx, [rbp+60h+pExceptionObject]; this
0x180009306  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000930b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180009312  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180009316  call    _CxxThrowException_0
0x18000931c  movdqa  [rsp+160h+var_118+8], xmm6
0x180009322  lea     rax, [rsp+160h+var_118+8]
0x180009327  mov     qword ptr [rsp+160h+var_138], rax
0x18000932c  mov     [rsp+160h+var_140], 8
0x180009334  lea     r9, aDirectoryentri; "directoryEntriesCountThisDisk"
0x18000933b  mov     r8, rdi
0x18000933e  mov     edx, 0BCh
0x180009343  mov     rcx, rsi
0x180009346  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18000934c  movdqa  [rsp+160h+var_118+8], xmm6
0x180009352  lea     rax, [rsp+160h+var_118+8]
0x180009357  mov     qword ptr [rsp+160h+var_138], rax
0x18000935c  mov     [rsp+160h+var_140], 8
0x180009364  lea     r9, aCountentries; "countEntries"
0x18000936b  mov     r8, rdi
0x18000936e  mov     edx, 0C7h
0x180009373  mov     rcx, rsi
0x180009376  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18000937c  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x180009383  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x180009388  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x180009390  mov     [rsp+160h+var_140], 0D0h; unsigned int
0x180009398  lea     r9, word_18013A0B6
0x18000939f  lea     r8, aNoFilename; "(no filename)"
0x1800093a6  lea     rcx, [rbp+60h+pExceptionObject]; this
0x1800093aa  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800093af  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800093b6  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x1800093ba  call    _CxxThrowException_0
0x1800093c0  movdqa  [rsp+160h+var_118+8], xmm6
0x1800093c6  lea     rax, [rsp+160h+var_118+8]
0x1800093cb  mov     qword ptr [rsp+160h+var_138], rax
0x1800093d0  mov     [rsp+160h+var_140], 8
0x1800093d8  lea     r9, aSizecentraldir; "sizeCentralDirectory"
0x1800093df  mov     r8, rdi
0x1800093e2  mov     edx, 0DBh
0x1800093e7  mov     rcx, rsi
0x1800093ea  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x1800093f0  movdqa  [rsp+160h+var_118+8], xmm6
0x1800093f6  lea     rax, [rsp+160h+var_118+8]
0x1800093fb  mov     qword ptr [rsp+160h+var_138], rax
0x180009400  mov     [rsp+160h+var_140], 8
  ... truncated ...
```
