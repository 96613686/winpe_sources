# win_musl::consumption::readZip64Extra(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,uint *)

- ea: `0x180090838`
- end: `0x180090c21`
- name: `?readZip64Extra@consumption@win_musl@@YAXPEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAI@Z`
- size: `1001`
- prototype: `__int64 __fastcall(_QWORD *, const struct __MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 *, _DWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180020cc8`
- `0x180024108`

## callees

- `0x180007b44`
- `0x18000a030`
- `0x1800515ec`
- `0x1800517a0`
- `0x180090838`
- `0x180090c28`
- `0x1800cd38c`
- `0x1801108cc`
- `0x180117740`

## string_xrefs

- `0x180090912`: `win_musl::consumption::readZip64Extra`
- `0x180090a04`: `win_musl::consumption::readZip64Extra`
- `0x180090af6`: `win_musl::consumption::readZip64Extra`
- `0x180090b8b`: `win_musl::consumption::readZip64Extra`
- `0x180090926`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180090a1b`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180090b0d`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180090ba2`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x1800909fd`: `compressedSize64`
- `0x18009090b`: `uncompressedSize64`
- `0x1800909aa`: `Local extra field format error: Both original and compressed file sizes must be included.`
- `0x180090a9c`: `Local extra field format error: Both original and compressed file sizes must be included.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall win_musl::consumption::readZip64Extra(
        _QWORD *a1,
        const struct __MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 *a2,
        _DWORD *a3)
{
  _QWORD *v3; // rsi
  const struct __MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 *v7; // rdx
  __int128 v8; // xmm6
  __int64 v9; // rax
  __int64 result; // rax
  _BYTE v11[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v12; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+68h] [rbp-A0h] BYREF

  v3 = a1 + 19;
  if ( win_musl::get_value((win_musl *)(a1 + 19), a2) == 0xFFFFFFFF )
  {
    if ( *(_DWORD *)a2 < 8u )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xEEu,
        0x80511002,
        (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v8 = *(_OWORD *)a2;
    v12 = *(_OWORD *)a2;
    v11[0] = 0;
    v9 = win_musl::detail::vector_read<unsigned __int64>(&v12, a2, v11);
    if ( v11[0] )
    {
      v12 = v8;
      win_musl::detail::ThrowReadError(
        "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
        242,
        "win_musl::consumption::readZip64Extra",
        "uncompressedSize64",
        8,
        &v12);
    }
    *v3 = 3;
    v3[1] = v9;
  }
  else if ( !a3 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xFCu,
      0x80511002,
      (struct win_musl::TStringEllipseBase *)L"Local extra field format error: Both original and compressed file sizes must be included.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  result = win_musl::get_value((win_musl *)(a1 + 21), v7);
  if ( result != 0xFFFFFFFFLL )
  {
    if ( !a3 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x119u,
        0x80511002,
        (struct win_musl::TStringEllipseBase *)L"Local extra field format error: Both original and compressed file sizes m"
                                                "ust be included.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    goto LABEL_13;
  }
  if ( *(_DWORD *)a2 < 8u )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x10Bu,
      0x80511002,
      (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v12 = *(_OWORD *)a2;
  result = win_musl::detail::readThenLog<unsigned __int64>(
             (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
             271,
             (unsigned int)"win_musl::consumption::readZip64Extra",
             (unsigned int)"compressedSize64",
             (__int64)&v12,
             (__int64)a2);
  a1[21] = 3;
  a1[22] = result;
  if ( a3 )
  {
LABEL_13:
    if ( a1[23] == 0xFFFFFFFFLL )
    {
      if ( *(_DWORD *)a2 < 8u )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x126u,
          0x80511002,
          (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v12 = *(_OWORD *)a2;
      result = win_musl::detail::readThenLog<unsigned __int64>(
                 (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
                 297,
                 (unsigned int)"win_musl::consumption::readZip64Extra",
                 (unsigned int)"entry->header.header_offset",
                 (__int64)&v12,
                 (__int64)a2);
      a1[23] = result;
    }
    if ( *a3 == 0xFFFF )
    {
      if ( *(_DWORD *)a2 < 4u )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x134u,
          0x80511002,
          (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v12 = *(_OWORD *)a2;
      result = win_musl::detail::readThenLog<unsigned int>(
                 (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
                 312,
                 (unsigned int)"win_musl::consumption::readZip64Extra",
                 (unsigned int)"diskStart",
                 (__int64)&v12,
                 (__int64)a2);
      *a3 = result;
    }
  }
  if ( *(_DWORD *)a2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x142u,
      0x80511002,
      (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180090838  mov     rax, rsp
0x18009083b  push    rbp
0x18009083c  push    rbx
0x18009083d  push    rsi
0x18009083e  push    rdi
0x18009083f  push    r13
0x180090841  push    r14
0x180090843  push    r15
0x180090845  lea     rbp, [rax-58h]
0x180090849  sub     rsp, 120h
0x180090850  movaps  xmmword ptr [rax-48h], xmm6
0x180090854  mov     rax, cs:__security_cookie
0x18009085b  xor     rax, rsp
0x18009085e  mov     [rbp+50h+var_50], rax
0x180090862  lea     rsi, [rcx+98h]
0x180090869  mov     r14, rcx
0x18009086c  mov     rcx, rsi; this
0x18009086f  mov     rdi, r8
0x180090872  mov     rbx, rdx
0x180090875  call    ?get_value@win_musl@@YA_KAEBU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008@@@Z; win_musl::get_value(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 const &)
0x18009087a  mov     r13d, 0FFFFFFFFh
0x180090880  cmp     rax, r13
0x180090883  jnz     loc_1800909A5
0x180090889  cmp     dword ptr [rbx], 8
0x18009088c  jnb     short loc_1800908D4
0x18009088e  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180090895  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009089a  lea     r9, word_18013A0B6
0x1800908a1  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x1800908a9  lea     r8, aNoFilename; "(no filename)"
0x1800908b0  lea     rcx, [rsp+150h+pExceptionObject]; this
0x1800908b5  mov     [rsp+150h+var_130], 0EEh; unsigned int
0x1800908bd  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800908c2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800908c9  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x1800908ce  call    _CxxThrowException_0
0x1800908d4  movaps  xmm6, xmmword ptr [rbx]
0x1800908d7  lea     r8, [rsp+150h+var_110]
0x1800908dc  mov     rdx, rbx
0x1800908df  movdqa  [rsp+150h+var_108+8], xmm6
0x1800908e5  lea     rcx, [rsp+150h+var_108+8]
0x1800908ea  mov     [rsp+150h+var_110], 0
0x1800908ef  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x1800908f4  cmp     [rsp+150h+var_110], 0
0x1800908f9  jz      short loc_180090933
0x1800908fb  lea     rax, [rsp+150h+var_108+8]
0x180090900  movdqa  [rsp+150h+var_108+8], xmm6
0x180090906  mov     qword ptr [rsp+150h+var_128], rax
0x18009090b  lea     r9, aUncompressedsi; "uncompressedSize64"
0x180090912  lea     r8, aWinMuslConsump_4; "win_musl::consumption::readZip64Extra"
0x180090919  mov     [rsp+150h+var_130], 8
0x180090921  mov     edx, 0F2h
0x180090926  lea     rcx, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18009092d  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x180090933  mov     qword ptr [rsi], 3
0x18009093a  mov     [rsi+8], rax
0x18009093e  lea     rsi, [r14+0A8h]
0x180090945  mov     rcx, rsi; this
0x180090948  call    ?get_value@win_musl@@YA_KAEBU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008@@@Z; win_musl::get_value(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 const &)
0x18009094d  cmp     rax, r13
0x180090950  jnz     loc_180090A97
0x180090956  cmp     dword ptr [rbx], 8
0x180090959  jnb     loc_1800909F0
0x18009095f  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180090966  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009096b  lea     r9, word_18013A0B6
0x180090972  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x18009097a  lea     r8, aNoFilename; "(no filename)"
0x180090981  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180090986  mov     [rsp+150h+var_130], 10Bh; unsigned int
0x18009098e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180090993  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009099a  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x18009099f  call    _CxxThrowException_0
0x1800909a5  test    rdi, rdi
0x1800909a8  jnz     short loc_18009093E
0x1800909aa  lea     rax, aLocalExtraFiel; "Local extra field format error: Both or"...
0x1800909b1  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x1800909b6  lea     r9, word_18013A0B6
0x1800909bd  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x1800909c5  lea     r8, aNoFilename; "(no filename)"
0x1800909cc  lea     rcx, [rsp+150h+pExceptionObject]; this
0x1800909d1  mov     [rsp+150h+var_130], 0FCh; unsigned int
0x1800909d9  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800909de  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800909e5  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x1800909ea  call    _CxxThrowException_0
0x1800909f0  movaps  xmm0, xmmword ptr [rbx]
0x1800909f3  lea     rax, [rsp+150h+var_108+8]
0x1800909f8  mov     qword ptr [rsp+150h+var_128], rbx
0x1800909fd  lea     r9, aCompressedsize; "compressedSize64"
0x180090a04  lea     r8, aWinMuslConsump_4; "win_musl::consumption::readZip64Extra"
0x180090a0b  movdqa  [rsp+150h+var_108+8], xmm0
0x180090a11  mov     edx, 10Fh
0x180090a16  mov     qword ptr [rsp+150h+var_130], rax
0x180090a1b  lea     rcx, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180090a22  call    ??$readThenLog@_K@detail@win_musl@@YA_KPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<unsigned __int64>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180090a27  mov     qword ptr [rsi], 3
0x180090a2e  mov     [rsi+8], rax
0x180090a32  test    rdi, rdi
0x180090a35  jz      loc_180090BB0
0x180090a3b  cmp     [r14+0B8h], r13
0x180090a42  jnz     loc_180090B20
0x180090a48  cmp     dword ptr [rbx], 8
0x180090a4b  jnb     loc_180090AE2
0x180090a51  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180090a58  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180090a5d  lea     r9, word_18013A0B6
0x180090a64  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180090a6c  lea     r8, aNoFilename; "(no filename)"
0x180090a73  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180090a78  mov     [rsp+150h+var_130], 126h; unsigned int
0x180090a80  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180090a85  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180090a8c  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180090a91  call    _CxxThrowException_0
0x180090a97  test    rdi, rdi
0x180090a9a  jnz     short loc_180090A3B
0x180090a9c  lea     rax, aLocalExtraFiel; "Local extra field format error: Both or"...
0x180090aa3  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180090aa8  lea     r9, word_18013A0B6
0x180090aaf  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180090ab7  lea     r8, aNoFilename; "(no filename)"
0x180090abe  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180090ac3  mov     [rsp+150h+var_130], 119h; unsigned int
0x180090acb  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180090ad0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180090ad7  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180090adc  call    _CxxThrowException_0
0x180090ae2  movaps  xmm0, xmmword ptr [rbx]
0x180090ae5  lea     rax, [rsp+150h+var_108+8]
0x180090aea  mov     qword ptr [rsp+150h+var_128], rbx
0x180090aef  lea     r9, aEntryHeaderHea_0; "entry->header.header_offset"
0x180090af6  lea     r8, aWinMuslConsump_4; "win_musl::consumption::readZip64Extra"
0x180090afd  movdqa  [rsp+150h+var_108+8], xmm0
0x180090b03  mov     edx, 129h
0x180090b08  mov     qword ptr [rsp+150h+var_130], rax
0x180090b0d  lea     rcx, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180090b14  call    ??$readThenLog@_K@detail@win_musl@@YA_KPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<unsigned __int64>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180090b19  mov     [r14+0B8h], rax
0x180090b20  cmp     dword ptr [rdi], 0FFFFh
0x180090b26  jnz     loc_180090BB0
0x180090b2c  cmp     dword ptr [rbx], 4
0x180090b2f  jnb     short loc_180090B77
0x180090b31  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180090b38  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180090b3d  lea     r9, word_18013A0B6
0x180090b44  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180090b4c  lea     r8, aNoFilename; "(no filename)"
0x180090b53  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180090b58  mov     [rsp+150h+var_130], 134h; unsigned int
0x180090b60  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180090b65  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180090b6c  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180090b71  call    _CxxThrowException_0
0x180090b77  movaps  xmm0, xmmword ptr [rbx]
0x180090b7a  lea     rax, [rsp+150h+var_108+8]
0x180090b7f  mov     qword ptr [rsp+150h+var_128], rbx
0x180090b84  lea     r9, aDiskstart; "diskStart"
0x180090b8b  lea     r8, aWinMuslConsump_4; "win_musl::consumption::readZip64Extra"
0x180090b92  movdqa  [rsp+150h+var_108+8], xmm0
0x180090b98  mov     edx, 138h
0x180090b9d  mov     qword ptr [rsp+150h+var_130], rax
0x180090ba2  lea     rcx, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180090ba9  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180090bae  mov     [rdi], eax
0x180090bb0  cmp     dword ptr [rbx], 0
0x180090bb3  jz      short loc_180090BFB
0x180090bb5  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180090bbc  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180090bc1  lea     r9, word_18013A0B6
0x180090bc8  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180090bd0  lea     r8, aNoFilename; "(no filename)"
0x180090bd7  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180090bdc  mov     [rsp+150h+var_130], 142h; unsigned int
0x180090be4  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180090be9  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180090bf0  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180090bf5  call    _CxxThrowException_0
0x180090bfb  mov     rcx, [rbp+50h+var_50]
0x180090bff  xor     rcx, rsp; StackCookie
0x180090c02  call    __security_check_cookie
0x180090c07  movaps  xmm6, [rsp+150h+var_48+8]
0x180090c0f  add     rsp, 120h
0x180090c16  pop     r15
0x180090c18  pop     r14
0x180090c1a  pop     r13
0x180090c1c  pop     rdi
0x180090c1d  pop     rsi
0x180090c1e  pop     rbx
0x180090c1f  pop     rbp
0x180090c20  retn
```
