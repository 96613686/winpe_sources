# ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageFullNameFromId(PACKAGE_ID const *,uint *,ushort *)

- ea: `0x180027bf0`
- end: `0x18002850f`
- name: `?PackageFullNameFromId@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBUPACKAGE_ID@@PEAIPEAG@Z`
- size: `2335`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026b54`
- `0x180027720`
- `0x1800279b0`

## callees

- `0x1800133fc`
- `0x180027bf0`
- `0x180028518`
- `0x1800285a4`
- `0x180028770`
- `0x180028910`
- `0x180028afc`
- `0x180028b28`
- `0x180071f50`
- `0x1800771bc`
- `0x18007b358`
- `0x1800992a0`
- `0x1800992c4`
- `0x180099e38`
- `0x18009d729`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027d11`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027d60`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028002`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028113`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028163`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800281c2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027d11`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027d60`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028002`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028113`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028163`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800281c2`

## string_xrefs

- `0x180027e6b`: `onecore\base\appmodel\common\cryptoprovider.cpp`
- `0x1800284ec`: `onecore\base\appmodel\common\cryptoprovider.cpp`

## pseudocode

```c
__int64 __fastcall ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageFullNameFromId(
        __int64 a1,
        _DWORD *a2,
        void *a3)
{
  const WCHAR *v4; // rsi
  unsigned __int16 *v5; // rdx
  unsigned __int16 *v6; // r8
  __int64 v7; // r15
  unsigned __int16 v8; // cx
  int v9; // r14d
  unsigned __int64 v10; // rdi
  unsigned __int64 i; // rbx
  __int64 v12; // r9
  unsigned __int64 j; // rbx
  unsigned __int64 v14; // rdx
  __int64 result; // rax
  _DWORD *v16; // r12
  __int64 v17; // rsi
  __int64 v18; // rdi
  __int64 v19; // r14
  int v20; // eax
  int v21; // ebx
  Common::CryptoProvider *v22; // rdi
  int started; // eax
  __int64 v24; // rcx
  int v25; // eax
  unsigned int v26; // edx
  bool v27; // zf
  __m128i v28; // xmm6
  __int64 v29; // rcx
  int v30; // ebx
  __int64 v31; // r8
  char *v32; // r14
  _WORD *v33; // rsi
  unsigned __int64 v34; // rbx
  unsigned __int64 v35; // rdi
  __int64 v36; // rdx
  unsigned __int64 v37; // r9
  Common::CryptoProvider *v38; // rcx
  unsigned __int64 k; // rbx
  __int64 v40; // r9
  unsigned __int64 m; // rbx
  unsigned __int64 v42; // rdx
  unsigned __int64 n; // rbx
  unsigned __int16 *v44; // r9
  unsigned int v45; // r15d
  int v46; // r8d
  const char *ii; // rdx
  unsigned __int16 *v48; // r10
  __int64 v49; // rsi
  _WORD *v50; // rax
  __int64 v51; // rdi
  int v52; // r10d
  __int64 v53; // r9
  __int64 v54; // rax
  unsigned int v55; // edx
  __int64 v56; // r11
  const wchar_t *v57; // rcx
  __int64 v58; // r11
  unsigned int v59; // r10d
  unsigned __int16 *v60; // r8
  unsigned int v61; // eax
  __int64 v62; // rcx
  Common::CryptoProvider *v63; // r11
  __int64 v64; // r12
  __int64 v65; // rsi
  WCHAR v66; // cx
  unsigned int v67; // eax
  WCHAR *v68; // r8
  unsigned int v69; // r9d
  WCHAR *v70; // rdx
  __int64 v71; // r15
  int v72; // eax
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-E0h]
  Common::CryptoProvider **bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int v75; // [rsp+28h] [rbp-D8h]
  int v76; // [rsp+30h] [rbp-D0h]
  unsigned int v77[2]; // [rsp+40h] [rbp-C0h] BYREF
  Common::CryptoProvider *v78[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *v79; // [rsp+58h] [rbp-A8h]
  unsigned __int16 Src[128]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v79 = a3;
  *(_QWORD *)v77 = a2;
  v78[0] = (Common::CryptoProvider *)a1;
  if ( !a1 || !a2 || *a2 && !a3 )
    return 87;
  memset_0(Src, 0, 0xFEu);
  v4 = *(const WCHAR **)(a1 + 16);
  if ( !v4 )
    return 87;
  v5 = *(unsigned __int16 **)(a1 + 16);
  v6 = Src;
  v7 = 0;
  while ( 1 )
  {
    v8 = *v5;
    if ( !*v5 )
      break;
    if ( (unsigned int)v7 >= 0x32 )
      return 87;
    if ( v8 >= 0x61u )
    {
      if ( v8 > 0x7Au )
        return 87;
      *v6 = v8;
      ++v5;
      ++v6;
      v7 = (unsigned int)(v7 + 1);
    }
    else
    {
      if ( v8 >= 0x41u )
      {
        if ( v8 > 0x5Au )
          return 87;
      }
      else if ( (unsigned __int16)(v8 - 45) > 1u && (unsigned __int16)(v8 - 48) > 9u )
      {
        return 87;
      }
      *v6 = v8;
      ++v5;
      ++v6;
      v7 = (unsigned int)(v7 + 1);
    }
  }
  if ( (unsigned int)v7 < 3 )
    return 87;
  v9 = 1;
  v10 = (unsigned int)(v5 - v4);
  for ( i = 0; i < 0x18; ++i )
  {
    v12 = (unsigned int)dword_180109CD0[4 * i];
    if ( v10 == v12 && CompareStringOrdinal(v4, v10, (&off_180109CD8)[2 * i], v12, 1) == 2 )
      return 87;
  }
  for ( j = 0; j < 0x17; ++j )
  {
    v14 = (unsigned int)dword_180109B60[4 * j];
    if ( v10 >= v14 && CompareStringOrdinal(v4, v14, (&off_180109B68)[2 * j], v14, 1) == 2 )
      return 87;
  }
  if ( v10 && v4[v10 - 1] == 46 )
    return 87;
  if ( v10 >= 5 )
  {
    v34 = 0;
    v35 = v10 - 5;
    while ( v34 <= v35 )
    {
      if ( CompareStringOrdinal(&v4[v34], 5, L".xn--", 5, 1) == 2 )
        return 87;
      ++v34;
    }
  }
  v51 = (unsigned int)(v7 + 1);
  v52 = *(unsigned __int16 *)(a1 + 12);
  v53 = *(unsigned __int16 *)(a1 + 14);
  v76 = *(unsigned __int16 *)(a1 + 8);
  v75 = *(unsigned __int16 *)(a1 + 10);
  Src[v7] = 95;
  bIgnoreCase[0] = v52;
  if ( (int)RtlStringCchPrintfW(
              &Src[v51],
              (unsigned int)(127 - v51),
              L"%hu.%hu.%hu.%hu",
              v53,
              *(_QWORD *)bIgnoreCase,
              v75,
              v76) < 0 )
    return 87;
  v54 = -1;
  do
    v27 = Src[v51 + 1 + v54++] == 0;
  while ( !v27 );
  v55 = *(_DWORD *)(a1 + 4);
  v56 = (unsigned int)(v51 + v54);
  Src[v56] = 95;
  if ( v55 > 0xFFFF )
    return 87;
  if ( v55 == 11 )
  {
    v57 = L"neutral";
  }
  else if ( v55 > 0xC )
  {
    if ( v55 == 14 )
    {
      v57 = L"x86a64";
    }
    else
    {
      if ( v55 != 0xFFFF )
        return 87;
      v57 = L"unknown";
    }
  }
  else if ( v55 == 12 )
  {
    v57 = L"arm64";
  }
  else if ( v55 )
  {
    if ( v55 == 5 )
    {
      v57 = L"arm";
    }
    else
    {
      if ( v55 != 9 )
        return 87;
      v57 = L"x64";
    }
  }
  else
  {
    v57 = L"x86";
  }
  v58 = (unsigned int)(v56 + 1);
  v59 = 7;
  v60 = &Src[v58];
  if ( (unsigned int)(127 - v58) < 7 )
    v59 = 127 - v58;
  v61 = 0;
  while ( *v57 )
  {
    if ( v61 >= v59 )
      return 87;
    *v60++ = *v57++;
    ++v61;
  }
  v62 = v61 + (unsigned int)v58;
  v63 = v78[0];
  Src[v62] = 95;
  v64 = (unsigned int)(v62 + 1);
  v65 = *((_QWORD *)v63 + 4);
  if ( v65 && (v66 = *(_WORD *)v65) != 0 )
  {
    v67 = 127 - v64;
    v68 = &Src[v64];
    if ( v66 != 126 || *(_WORD *)(v65 + 2) )
    {
      v69 = 30;
      v70 = (WCHAR *)*((_QWORD *)v63 + 4);
      if ( v67 < 0x1E )
        v69 = 127 - v64;
      v71 = 0;
      while ( v66 )
      {
        if ( (unsigned int)v71 >= v69 )
          return 87;
        if ( (unsigned __int16)(v66 - 97) > 0x19u )
        {
          if ( v66 >= 0x41u )
          {
            if ( v66 > 0x5Au )
              return 87;
          }
          else if ( (unsigned __int16)(v66 - 45) > 1u && (unsigned __int16)(v66 - 48) > 9u )
          {
            return 87;
          }
        }
        ++v70;
        *v68++ = v66;
        v71 = (unsigned int)(v71 + 1);
        v66 = *v70;
      }
      for ( k = 0; k < 0x18; ++k )
      {
        v40 = (unsigned int)dword_180109CD0[4 * k];
        if ( (unsigned int)v71 == v40 && CompareStringOrdinal((LPCWCH)v65, v71, (&off_180109CD8)[2 * k], v40, 1) == 2 )
          return 87;
      }
      for ( m = 0; m < 0x17; ++m )
      {
        v42 = (unsigned int)dword_180109B60[4 * m];
        if ( (unsigned int)v71 >= v42 && CompareStringOrdinal((LPCWCH)v65, v42, (&off_180109B68)[2 * m], v42, 1) == 2 )
          return 87;
      }
      if ( (_DWORD)v71 && *(_WORD *)(v65 + 2 * v71 - 2) == 46 )
        return 87;
      if ( (unsigned int)v71 >= 5uLL )
      {
        for ( n = 0; n <= (unsigned __int64)(unsigned int)v71 - 5; ++n )
        {
          if ( CompareStringOrdinal((LPCWCH)(v65 + 2 * n), 5, L".xn--", 5, 1) == 2 )
            return 87;
        }
      }
      v63 = v78[0];
      v9 = v71;
    }
    else
    {
      if ( !v67 )
        return 87;
      *v68 = 126;
      if ( v55 != 11 )
        return 87;
    }
  }
  else
  {
    v9 = 0;
  }
  v48 = (unsigned __int16 *)*((_QWORD *)v63 + 5);
  v49 = (unsigned int)(v64 + v9);
  Src[v49] = 95;
  if ( v48 )
  {
    v44 = v48;
    v45 = 0;
LABEL_86:
    v46 = *v44;
    if ( (_WORD)v46 )
    {
      if ( v45 < 0xD )
      {
        for ( ii = "1234567890abcdefghjkmnpqrstvwxyzABCDEFGHJKMNPQRSTVWXYZ"; *ii; ++ii )
        {
          if ( v46 == *ii )
          {
            ++v45;
            ++v44;
            goto LABEL_86;
          }
        }
      }
      return 87;
    }
    if ( v45 == 13 )
      goto LABEL_31;
    return 87;
  }
  v50 = (_WORD *)*((_QWORD *)v63 + 3);
  if ( !v50 )
    return 87;
  v45 = 0;
  while ( *v50 )
  {
    if ( v45 >= 0x2000 )
      return 87;
    ++v45;
    ++v50;
  }
  if ( v45 < 3 )
    return 87;
LABEL_31:
  v16 = *(_DWORD **)v77;
  v17 = (unsigned int)(v49 + 1);
  v18 = (unsigned int)(v17 + 13);
  if ( **(_DWORD **)v77 < (unsigned int)(v17 + 14) )
  {
    **(_DWORD **)v77 = v17 + 14;
    return 122;
  }
  if ( v48 )
  {
    memcpy_0(&Src[v17], v48, 2LL * v45);
    goto LABEL_46;
  }
  v19 = *((_QWORD *)v63 + 3);
  v78[0] = 0;
  v20 = Common::CryptoProvider::Create(v78);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v22 = v78[0];
    started = Common::CryptoProvider::StartDigest(v78[0]);
    v21 = started;
    if ( started < 0 )
    {
      v36 = 979;
    }
    else
    {
      v24 = *((_QWORD *)v22 + 1);
      HIDWORD(v78[0]) = 0;
      v25 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))xmmword_18016A3E8)(v24, v19, 2 * v45, 0);
      if ( v25 >= 0
        || (started = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x91,
                        (unsigned int)"onecore\\base\\appmodel\\common\\cryptoprovider.cpp",
                        (const char *)(unsigned int)v25,
                        (int)bIgnoreCasea),
            v21 = started,
            started >= 0) )
      {
        v27 = *((_DWORD *)v22 + 208) == 0;
        v28 = 0;
        v77[0] = 0;
        if ( !v27 )
        {
LABEL_43:
          v28 = *((__m128i *)v22 + 52);
LABEL_44:
          v77[0] = 0;
          started = Common::Base32Encoding::GetChars(
                      (const unsigned __int8 *)_mm_srli_si128(v28, 8).m128i_i64[0],
                      v26,
                      127 - (int)v17,
                      &Src[v17],
                      v77);
          v21 = started;
          if ( started >= 0 )
          {
            Common::CryptoProvider::~CryptoProvider(v22);
            operator delete(v22, 0x350u);
            v18 = (unsigned int)(v17 + v77[0]);
LABEL_46:
            v33 = v79;
            memcpy_0(v79, Src, 2 * v18);
            v33[v18] = 0;
            *v16 = v18 + 1;
            return 0;
          }
          v36 = 993;
          goto LABEL_59;
        }
        v29 = *(_QWORD *)v22;
        bIgnoreCasea = v78;
        LODWORD(v78[0]) = 0;
        v30 = ((__int64 (__fastcall *)(__int64, const WCHAR *, unsigned int *, __int64))xmmword_18016A3D8)(
                v29,
                L"HashDigestLength",
                v77,
                4);
        if ( !v30 )
        {
          v31 = v77[0];
          if ( v77[0] > 0x40 )
          {
            v72 = Common::ByteBuffer::SetLength((Common::CryptoProvider *)((char *)v22 + 40), v77[0]);
            v21 = v72;
            if ( v72 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xB8,
                (unsigned int)"onecore\\base\\appmodel\\common\\cryptoprovider.cpp",
                (const char *)(unsigned int)v72,
                (int)v78);
              goto LABEL_67;
            }
            v32 = (char *)*((_QWORD *)v22 + 6);
            v31 = v77[0];
          }
          else
          {
            v32 = (char *)v22 + 764;
          }
          v30 = (*((__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))&xmmword_18016A3E8 + 1))(
                  *((_QWORD *)v22 + 1),
                  v32,
                  v31,
                  0);
          if ( !v30 )
          {
            *((_DWORD *)v22 + 208) = v77[0];
            *((_QWORD *)v22 + 105) = v32;
            goto LABEL_43;
          }
        }
        v21 = v30 | 0x10000000;
        if ( v21 >= 0 )
          goto LABEL_44;
LABEL_67:
        v37 = (unsigned int)v21;
        v36 = 984;
        goto LABEL_60;
      }
      v36 = 982;
    }
LABEL_59:
    v37 = (unsigned int)started;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\monikerinternal.cpp",
      (const char *)v37,
      (int)bIgnoreCasea);
    v38 = v22;
    goto LABEL_61;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3D2,
    (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\monikerinternal.cpp",
    (const char *)(unsigned int)v20,
    (int)bIgnoreCasea);
  v38 = v78[0];
LABEL_61:
  Common::AutoPtrDeallocate<Common::CryptoProvider>(v38);
  result = (unsigned __int16)v21;
  if ( (v21 & 0x1FFF0000) != 0x70000 )
    return (unsigned int)v21;
  return result;
}

```

## disassembly

```asm
0x180027bf0  mov     [rsp-8+arg_18], rbx
0x180027bf5  push    rbp
0x180027bf6  push    rsi
0x180027bf7  push    rdi
0x180027bf8  push    r12
0x180027bfa  push    r13
0x180027bfc  push    r14
0x180027bfe  push    r15
0x180027c00  lea     rbp, [rsp-80h]
0x180027c05  sub     rsp, 180h
0x180027c0c  mov     rax, cs:__security_cookie
0x180027c13  xor     rax, rsp
0x180027c16  mov     [rbp+0B0h+var_50], rax
0x180027c1a  mov     [rsp+1B0h+var_158], r8
0x180027c1f  mov     r12, rcx
0x180027c22  mov     qword ptr [rsp+1B0h+var_170], rdx
0x180027c27  mov     [rsp+1B0h+var_168], rcx
0x180027c2c  test    rcx, rcx
0x180027c2f  jz      loc_180027D83
0x180027c35  test    rdx, rdx
0x180027c38  jz      loc_180027D83
0x180027c3e  cmp     dword ptr [rdx], 0
0x180027c41  ja      loc_18002801C
0x180027c47  xor     edx, edx; Val
0x180027c49  lea     rcx, [rsp+1B0h+Src]; void *
0x180027c4e  mov     r8d, 0FEh; Size
0x180027c54  call    memset_0
0x180027c59  mov     rsi, [r12+10h]
0x180027c5e  test    rsi, rsi
0x180027c61  jz      loc_180027D83
0x180027c67  mov     rdx, rsi
0x180027c6a  lea     r8, [rsp+1B0h+Src]
0x180027c6f  xor     r15d, r15d
0x180027c72  mov     eax, 41h ; 'A'
0x180027c77  mov     r9d, 61h ; 'a'
0x180027c7d  movzx   ecx, word ptr [rdx]
0x180027c80  test    cx, cx
0x180027c83  jz      short loc_180027CC5
0x180027c85  cmp     r15d, 32h ; '2'
0x180027c89  jnb     loc_180027D83
0x180027c8f  cmp     r9w, cx
0x180027c93  jbe     loc_180027DB0
0x180027c99  cmp     ax, cx
0x180027c9c  jbe     loc_180027DD9
0x180027ca2  lea     eax, [rcx-2Dh]
0x180027ca5  cmp     ax, 1
0x180027ca9  ja      loc_180027DCA
0x180027caf  mov     eax, 41h ; 'A'
0x180027cb4  mov     [r8], cx
0x180027cb8  add     rdx, 2
0x180027cbc  add     r8, 2
0x180027cc0  inc     r15d
0x180027cc3  jmp     short loc_180027C7D
0x180027cc5  cmp     r15d, 3
0x180027cc9  jb      loc_180027D83
0x180027ccf  sub     rdx, rsi
0x180027cd2  lea     rax, __ImageBase
0x180027cd9  sar     rdx, 1
0x180027cdc  mov     r14d, 1
0x180027ce2  mov     edi, edx
0x180027ce4  xor     ebx, ebx
0x180027ce6  cmp     rbx, 18h
0x180027cea  jnb     short loc_180027D2E
0x180027cec  mov     r8, rbx
0x180027cef  add     r8, r8
0x180027cf2  mov     r9d, ds:rva dword_180109CD0[rax+r8*8]; cchCount2
0x180027cfa  cmp     rdi, r9
0x180027cfd  jnz     short loc_180027D29
0x180027cff  mov     r8, ds:rva off_180109CD8[rax+r8*8]; lpString2
0x180027d07  mov     edx, edi; cchCount1
0x180027d09  mov     rcx, rsi; lpString1
0x180027d0c  mov     [rsp+1B0h+bIgnoreCase], r14d; bIgnoreCase
0x180027d11  call    cs:__imp_CompareStringOrdinal
0x180027d18  nop     dword ptr [rax+rax+00h]
0x180027d1d  cmp     eax, 2
0x180027d20  jz      short loc_180027D83
0x180027d22  lea     rax, __ImageBase
0x180027d29  inc     rbx
0x180027d2c  jmp     short loc_180027CE6
0x180027d2e  xor     ebx, ebx
0x180027d30  cmp     rbx, 17h
0x180027d34  jnb     loc_180027FBE
0x180027d3a  mov     r8, rbx
0x180027d3d  add     r8, r8
0x180027d40  mov     edx, ds:rva dword_180109B60[rax+r8*8]; cchCount1
0x180027d48  cmp     rdi, rdx
0x180027d4b  jb      short loc_180027D78
0x180027d4d  mov     r8, ds:rva off_180109B68[rax+r8*8]; lpString2
0x180027d55  mov     r9d, edx; cchCount2
0x180027d58  mov     rcx, rsi; lpString1
0x180027d5b  mov     [rsp+1B0h+bIgnoreCase], r14d; bIgnoreCase
0x180027d60  call    cs:__imp_CompareStringOrdinal
0x180027d67  nop     dword ptr [rax+rax+00h]
0x180027d6c  cmp     eax, 2
0x180027d6f  jz      short loc_180027D83
0x180027d71  lea     rax, __ImageBase
0x180027d78  inc     rbx
0x180027d7b  jmp     short loc_180027D30
0x180027d7d  cmp     r15d, 3
0x180027d81  jnb     short loc_180027DE4
0x180027d83  mov     eax, 57h ; 'W'
0x180027d88  mov     rcx, [rbp+0B0h+var_50]
0x180027d8c  xor     rcx, rsp; StackCookie
0x180027d8f  call    __security_check_cookie
0x180027d94  mov     rbx, [rsp+1B0h+arg_18]
0x180027d9c  add     rsp, 180h
0x180027da3  pop     r15
0x180027da5  pop     r14
0x180027da7  pop     r13
0x180027da9  pop     r12
0x180027dab  pop     rdi
0x180027dac  pop     rsi
0x180027dad  pop     rbp
0x180027dae  retn
0x180027db0  cmp     cx, 7Ah ; 'z'
0x180027db4  ja      short loc_180027D83
0x180027db6  mov     [r8], cx
0x180027dba  add     rdx, 2
0x180027dbe  add     r8, 2
0x180027dc2  inc     r15d
0x180027dc5  jmp     loc_180027C7D
0x180027dca  lea     eax, [rcx-30h]
0x180027dcd  cmp     ax, 9
0x180027dd1  jbe     loc_180027CAF
0x180027dd7  jmp     short loc_180027D83
0x180027dd9  cmp     cx, 5Ah ; 'Z'
0x180027ddd  ja      short loc_180027D83
0x180027ddf  jmp     loc_180027CB4
0x180027de4  mov     r12, qword ptr [rsp+1B0h+var_170]
0x180027de9  inc     esi
0x180027deb  lea     edi, [rsi+0Dh]
0x180027dee  lea     eax, [rdi+1]
0x180027df1  cmp     [r12], eax
0x180027df5  jb      loc_180028046
0x180027dfb  movaps  [rsp+1B0h+var_40], xmm6
0x180027e03  test    r10, r10
0x180027e06  jnz     loc_18002802A
0x180027e0c  mov     r14, [r11+18h]
0x180027e10  lea     rcx, [rsp+1B0h+var_168]; struct Common::CryptoProvider **
0x180027e15  mov     [rsp+1B0h+var_168], r10
0x180027e1a  call    ?Create@CryptoProvider@Common@@SAJPEAPEAV12@@Z; Common::CryptoProvider::Create(Common::CryptoProvider * *)
0x180027e1f  mov     ebx, eax
0x180027e21  test    eax, eax
0x180027e23  js      loc_180028098
0x180027e29  mov     rdi, [rsp+1B0h+var_168]
0x180027e2e  mov     rcx, rdi; this
0x180027e31  call    ?StartDigest@CryptoProvider@Common@@QEAAJXZ; Common::CryptoProvider::StartDigest(void)
0x180027e36  mov     ebx, eax
0x180027e38  test    eax, eax
0x180027e3a  js      loc_180028054
0x180027e40  mov     rcx, [rdi+8]
0x180027e44  lea     r8d, [r15+r15]
0x180027e48  xor     eax, eax
0x180027e4a  xor     r9d, r9d
0x180027e4d  mov     dword ptr [rsp+1B0h+var_168+4], eax
0x180027e51  mov     rdx, r14
0x180027e54  mov     rax, qword ptr cs:xmmword_18016A3E8
0x180027e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e60  test    eax, eax
0x180027e62  jns     short loc_180027E89
0x180027e64  mov     rcx, [rbp+0B8h]; this
0x180027e6b  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\common\\crypto"...
0x180027e72  mov     r9d, eax; char *
0x180027e75  mov     edx, 91h; void *
0x180027e7a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180027e7f  mov     ebx, eax
0x180027e81  test    eax, eax
0x180027e83  js      loc_1800280BA
0x180027e89  cmp     dword ptr [rdi+340h], 0
0x180027e90  xorps   xmm6, xmm6
0x180027e93  mov     [rsp+1B0h+var_170], 0
0x180027e9b  jnz     loc_180027F2D
0x180027ea1  mov     rcx, [rdi]
0x180027ea4  lea     rax, [rsp+1B0h+var_168]
0x180027ea9  mov     [rsp+1B0h+var_188], 0
0x180027eb1  lea     r8, [rsp+1B0h+var_170]
0x180027eb6  mov     qword ptr [rsp+1B0h+bIgnoreCase], rax; int
0x180027ebb  lea     rdx, pszProperty; "HashDigestLength"
0x180027ec2  mov     rax, qword ptr cs:xmmword_18016A3D8
0x180027ec9  mov     r9d, 4
0x180027ecf  mov     dword ptr [rsp+1B0h+var_168], 0
0x180027ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027edc  mov     ebx, eax
0x180027ede  test    eax, eax
0x180027ee0  jnz     loc_1800280C1
0x180027ee6  mov     r8d, [rsp+1B0h+var_170]
0x180027eeb  cmp     r8d, 40h ; '@'
0x180027eef  ja      loc_1800284B8
0x180027ef5  lea     r14, [rdi+2FCh]
0x180027efc  mov     rcx, [rdi+8]
0x180027f00  xor     r9d, r9d
0x180027f03  mov     rax, qword ptr cs:xmmword_18016A3E8+8
0x180027f0a  mov     rdx, r14
0x180027f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f12  mov     ebx, eax
0x180027f14  test    eax, eax
0x180027f16  jnz     loc_1800280C1
0x180027f1c  mov     eax, [rsp+1B0h+var_170]
0x180027f20  mov     [rdi+340h], eax
0x180027f26  mov     [rdi+348h], r14
0x180027f2d  movups  xmm6, xmmword ptr [rdi+340h]
0x180027f34  lea     rax, [rsp+1B0h+var_170]
0x180027f39  psrldq  xmm6, 8
0x180027f3e  lea     r9, [rsp+1B0h+Src]
0x180027f43  mov     [rsp+1B0h+var_170], 0
0x180027f4b  sub     r13d, esi
0x180027f4e  mov     qword ptr [rsp+1B0h+bIgnoreCase], rax; unsigned int *
0x180027f53  lea     r9, [r9+rsi*2]; unsigned __int16 *
0x180027f57  mov     r8d, r13d; unsigned int
0x180027f5a  movq    rcx, xmm6; unsigned __int8 *
0x180027f5f  call    ?GetChars@Base32Encoding@Common@@SAJPEBEKKPEAGPEAK@Z; Common::Base32Encoding::GetChars(uchar const *,ulong,ulong,ushort *,ulong *)
0x180027f64  mov     ebx, eax
0x180027f66  test    eax, eax
0x180027f68  js      loc_180028505
0x180027f6e  mov     rcx, rdi; this
0x180027f71  call    ??1CryptoProvider@Common@@QEAA@XZ; Common::CryptoProvider::~CryptoProvider(void)
0x180027f76  mov     edx, 350h; unsigned __int64
0x180027f7b  mov     rcx, rdi; void *
0x180027f7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027f83  mov     edi, [rsp+1B0h+var_170]
0x180027f87  add     edi, esi
0x180027f89  mov     rsi, [rsp+1B0h+var_158]
0x180027f8e  lea     rbx, [rdi+rdi]
0x180027f92  mov     r8, rbx; Size
0x180027f95  lea     rdx, [rsp+1B0h+Src]; Src
0x180027f9a  mov     rcx, rsi; void *
0x180027f9d  call    memcpy_0
0x180027fa2  movaps  xmm6, [rsp+1B0h+var_40]
0x180027faa  xor     eax, eax
0x180027fac  mov     [rsi+rbx], ax
0x180027fb0  lea     eax, [rdi+1]
0x180027fb3  mov     [r12], eax
0x180027fb7  xor     eax, eax
0x180027fb9  jmp     loc_180027D88
0x180027fbe  test    rdi, rdi
0x180027fc1  jz      short loc_180027FCF
0x180027fc3  cmp     word ptr [rsi+rdi*2-2], 2Eh ; '.'
0x180027fc9  jz      loc_180027D83
0x180027fcf  cmp     rdi, 5
0x180027fd3  jb      loc_180028280
0x180027fd9  xor     ebx, ebx
0x180027fdb  add     rdi, 0FFFFFFFFFFFFFFFBh
0x180027fdf  nop
0x180027fe0  cmp     rbx, rdi
0x180027fe3  ja      loc_180028280
0x180027fe9  mov     r9d, 5; cchCount2
0x180027fef  mov     [rsp+1B0h+bIgnoreCase], r14d; bIgnoreCase
0x180027ff4  mov     edx, r9d; cchCount1
0x180027ff7  lea     rcx, [rsi+rbx*2]; lpString1
0x180027ffb  lea     r8, aXn_0; ".xn--"
0x180028002  call    cs:__imp_CompareStringOrdinal
0x180028009  nop     dword ptr [rax+rax+00h]
0x18002800e  cmp     eax, 2
0x180028011  jz      loc_180027D83
0x180028017  inc     rbx
0x18002801a  jmp     short loc_180027FE0
0x18002801c  test    r8, r8
0x18002801f  jnz     loc_180027C47
0x180028025  jmp     loc_180027D83
0x18002802a  mov     r8d, r15d
0x18002802d  lea     rcx, [rsp+1B0h+Src]
0x180028032  add     r8, r8; Size
0x180028035  lea     rcx, [rcx+rsi*2]; void *
0x180028039  mov     rdx, r10; Src
0x18002803c  call    memcpy_0
0x180028041  jmp     loc_180027F89
0x180028046  mov     [r12], eax
0x18002804a  mov     eax, 7Ah ; 'z'
0x18002804f  jmp     loc_180027D88
0x180028054  mov     edx, 3D3h; void *
0x180028059  mov     r9d, eax; char *
0x18002805c  mov     rcx, [rbp+0B8h]; this
0x180028063  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18002806a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002806f  mov     rcx, rdi; void *
0x180028072  call    ??$AutoPtrDeallocate@VCryptoProvider@Common@@@Common@@YAXPEAVCryptoProvider@0@@Z; Common::AutoPtrDeallocate<Common::CryptoProvider>(Common::CryptoProvider *)
0x180028077  movaps  xmm6, [rsp+1B0h+var_40]
0x18002807f  mov     ecx, ebx
0x180028081  and     ecx, 1FFF0000h
0x180028087  movzx   eax, bx
0x18002808a  cmp     ecx, 70000h
0x180028090  cmovnz  eax, ebx
0x180028093  jmp     loc_180027D88
0x180028098  mov     rcx, [rbp+0B8h]; this
0x18002809f  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\runtime\\src\\"...
0x1800280a6  mov     r9d, eax; char *
0x1800280a9  mov     edx, 3D2h; void *
0x1800280ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800280b3  mov     rcx, [rsp+1B0h+var_168]
0x1800280b8  jmp     short loc_180028072
0x1800280ba  mov     edx, 3D6h
0x1800280bf  jmp     short loc_180028059
0x1800280c1  or      ebx, 10000000h
0x1800280c7  jge     loc_180027F34
0x1800280cd  mov     r9d, ebx
0x1800280d0  mov     edx, 3D8h
0x1800280d5  jmp     short loc_18002805C
0x1800280d7  mov     edi, r15d
0x1800280da  xor     ebx, ebx
0x1800280dc  nop     dword ptr [rax+00h]
  ... truncated ...
```
