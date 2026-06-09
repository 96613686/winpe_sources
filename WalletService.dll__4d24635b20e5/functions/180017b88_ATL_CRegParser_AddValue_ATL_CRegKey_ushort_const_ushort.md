# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180017b88`
- end: `0x180017fe8`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1120`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180019820`

## callees

- `0x18000ddb4`
- `0x18001248c`
- `0x180012608`
- `0x180016f68`
- `0x180017530`
- `0x180017588`
- `0x180017b88`
- `0x180017ff0`
- `0x180018110`
- `0x180018f74`
- `0x18001a19c`
- `0x180043052`
- `0x180043090`
- `0x180043150`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180017db6`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180017db6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017d6b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017f74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017d6b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017f74`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017ce3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017cff`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017ce3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017cff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017c0b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017c0b`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        struct ATL::CRegKey *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegKey *v4; // r12
  unsigned __int16 *v5; // r14
  ATL::CRegParser *v7; // rsi
  __int64 result; // rax
  unsigned int i; // ebx
  __int16 v10; // bx
  unsigned int v11; // r9d
  __int64 v12; // rax
  unsigned __int64 v13; // rax
  BYTE *v14; // rbx
  WCHAR *v15; // rdi
  const WCHAR *v16; // rax
  DWORD cbData; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // ebx
  HRESULT v22; // ebx
  __int64 v23; // r14
  size_t v24; // rdi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int v27; // r10d
  unsigned int v28; // r9d
  char v29; // r9
  unsigned __int64 v30; // r8
  char v31; // r9
  int Token; // eax
  unsigned int v33; // ecx
  ULONG pulOut[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct ATL::CRegKey *v35; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v36; // [rsp+40h] [rbp-C0h]
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v38[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v4 = a2;
  v35 = a2;
  v36 = a4;
  v5 = a4;
  *(_QWORD *)pulOut = this;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( (int)result < 0 )
    return result;
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
      return 2147614729LL;
    if ( !lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * (int)i]) )
      break;
  }
  v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * (int)i + 4);
  ATL::CRegParser::SkipWhiteSpace(v7);
  result = ATL::CRegParser::NextToken(v7, String1);
  if ( (int)result < 0 )
    return result;
  switch ( v10 )
  {
    case 8:
      v21 = ATL::CRegKey::SetStringValue(v4, a3, String1, v11);
      goto LABEL_75;
    case 17:
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      if ( (v23 & 1) != 0 )
        return 2147500037LL;
      lpData = 0;
      v24 = (int)v23 / 2;
      v25 = ATL::AtlMultiplyThrow<unsigned __int64>(v24, 1);
      if ( v25 <= 0x100 )
      {
        v26 = v38;
        lpData = v38;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
        v26 = lpData;
      }
      if ( !v26 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v26, 0, v24);
      v27 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_73:
        v21 = RegSetValueExW(*(HKEY *)v4, a3, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_33;
      }
      while ( 1 )
      {
        v28 = String1[v27];
        if ( v28 > 0x61 )
        {
          if ( v28 == 98 || v28 == 99 || v28 == 100 || v28 - 101 < 2 )
          {
LABEL_71:
            v29 = v28 - 87;
            goto LABEL_72;
          }
LABEL_70:
          v29 = 0;
          goto LABEL_72;
        }
        if ( v28 == 97 )
          goto LABEL_71;
        if ( v28 <= 0x38 )
          break;
        if ( v28 == 57 )
          goto LABEL_58;
        if ( v28 != 65 && v28 != 66 && v28 != 67 && v28 != 68 && v28 - 69 > 1 )
          goto LABEL_70;
        v29 = v28 - 55;
LABEL_72:
        v30 = (unsigned __int64)(unsigned int)v27 >> 1;
        v31 = v29 << (4 - 4 * (v27++ & 1));
        lpData[v30] |= v31;
        if ( v27 >= (int)v23 )
          goto LABEL_73;
      }
      if ( v28 != 56 && v28 != 48 && v28 != 49 && v28 != 50 && v28 != 51 && v28 != 52 && v28 != 53 && v28 - 54 > 1 )
        goto LABEL_70;
LABEL_58:
      v29 = v28 - 48;
      goto LABEL_72;
    case 19:
      pulOut[0] = 0;
      v35 = 0;
      v22 = VarUI4FromStr(String1, 0, 0, pulOut);
      if ( v22 >= 0 )
      {
        v21 = ATL::CRegKey::SetDWORDValue(v4, a3, pulOut[0]);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        goto LABEL_75;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
      return (unsigned int)v22;
    case 16392:
      v12 = -1;
      do
        ++v12;
      while ( String1[v12] );
      lpData = 0;
      v13 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v12 + 2, 2);
      if ( v13 <= 0x100 )
      {
        v14 = v38;
        lpData = v38;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v13);
        v14 = lpData;
      }
      if ( v14 )
      {
        v15 = String1;
        if ( String1[0] )
        {
          do
          {
            v16 = CharNextW(v15);
            if ( *v15 == 92 && *v16 == 48 )
            {
              *(_WORD *)v14 = 0;
              v15 = CharNextW(v16);
            }
            else
            {
              *(_WORD *)v14 = *v15++;
            }
            v14 += 2;
          }
          while ( *v15 );
          v4 = v35;
        }
        *(_DWORD *)v14 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v18 = lpData;
        do
        {
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)&v18[2 * v19] );
          v20 = (unsigned int)(v19 + 1);
          v18 += 2 * v20;
          cbData += 2 * v20;
        }
        while ( (_DWORD)v20 != 1 );
        v21 = RegSetValueExW(*(HKEY *)v4, a3, 0, 7u, lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_33:
      v7 = *(ATL::CRegParser **)pulOut;
      v5 = v36;
LABEL_75:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_77:
        Token = ATL::CRegParser::NextToken(v7, v5);
        v33 = 0;
        if ( Token < 0 )
          return (unsigned int)Token;
        return v33;
      }
    default:
      goto LABEL_77;
  }
}

```

## disassembly

```asm
0x180017b88  push    rbp
0x180017b8a  push    rbx
0x180017b8b  push    rsi
0x180017b8c  push    rdi
0x180017b8d  push    r12
0x180017b8f  push    r13
0x180017b91  push    r14
0x180017b93  push    r15
0x180017b95  lea     rbp, [rsp-2078h]
0x180017b9d  mov     eax, 2178h
0x180017ba2  call    _alloca_probe
0x180017ba7  sub     rsp, rax
0x180017baa  mov     rax, cs:__security_cookie
0x180017bb1  xor     rax, rsp
0x180017bb4  mov     [rbp+20B0h+var_50], rax
0x180017bbb  mov     r12, rdx
0x180017bbe  mov     [rsp+21B0h+var_2178], rdx
0x180017bc3  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180017bc7  mov     [rsp+21B0h+var_2170], r9
0x180017bcc  mov     r14, r9
0x180017bcf  mov     qword ptr [rsp+21B0h+pulOut], rcx
0x180017bd4  mov     r13, r8
0x180017bd7  mov     rsi, rcx
0x180017bda  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180017bdf  xor     r15d, r15d
0x180017be2  test    eax, eax
0x180017be4  js      loc_180017FC5
0x180017bea  mov     ebx, r15d
0x180017bed  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180017bf4  cmp     ebx, 4
0x180017bf7  jnb     loc_180017FC0
0x180017bfd  movsxd  rdi, ebx
0x180017c00  lea     rcx, [rbp+20B0h+String1]; lpString1
0x180017c04  add     rdi, rdi
0x180017c07  mov     rdx, [rax+rdi*8]; lpString2
0x180017c0b  call    cs:__imp_lstrcmpiW
0x180017c11  test    eax, eax
0x180017c13  jz      short loc_180017C19
0x180017c15  inc     ebx
0x180017c17  jmp     short loc_180017BED
0x180017c19  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180017c20  mov     rcx, rsi; this
0x180017c23  movzx   ebx, word ptr [rbx+rdi*8+8]
0x180017c28  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180017c2d  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180017c31  mov     rcx, rsi; this
0x180017c34  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180017c39  test    eax, eax
0x180017c3b  js      loc_180017FC5
0x180017c41  mov     eax, 8
0x180017c46  cmp     bx, ax
0x180017c49  jz      loc_180017F8B
0x180017c4f  cmp     bx, 11h
0x180017c53  jz      loc_180017DF4
0x180017c59  cmp     bx, 13h
0x180017c5d  jz      loc_180017D9E
0x180017c63  mov     eax, 4008h
0x180017c68  cmp     bx, ax
0x180017c6b  jnz     loc_180017FA9
0x180017c71  or      r14, 0FFFFFFFFFFFFFFFFh
0x180017c75  lea     rcx, [rbp+20B0h+String1]
0x180017c79  mov     rax, r14
0x180017c7c  inc     rax
0x180017c7f  cmp     [rcx+rax*2], r15w
0x180017c84  jnz     short loc_180017C7C
0x180017c86  add     eax, 2
0x180017c89  mov     [rsp+21B0h+var_2160], r15
0x180017c8e  mov     esi, 2
0x180017c93  movsxd  rcx, eax
0x180017c96  mov     edx, esi
0x180017c98  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180017c9d  cmp     rax, 100h
0x180017ca3  jbe     short loc_180017CB9
0x180017ca5  mov     rdx, rax
0x180017ca8  lea     rcx, [rsp+21B0h+var_2160]
0x180017cad  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180017cb2  mov     rbx, [rsp+21B0h+var_2160]
0x180017cb7  jmp     short loc_180017CC3
0x180017cb9  lea     rbx, [rsp+21B0h+var_2158]
0x180017cbe  mov     [rsp+21B0h+var_2160], rbx
0x180017cc3  test    rbx, rbx
0x180017cc6  jz      loc_180017D80
0x180017ccc  lea     rdi, [rbp+20B0h+String1]
0x180017cd0  cmp     [rbp+20B0h+String1], r15w
0x180017cd5  jz      short loc_180017D21
0x180017cd7  mov     r15d, 30h ; '0'
0x180017cdd  xor     r12d, r12d
0x180017ce0  mov     rcx, rdi; lpsz
0x180017ce3  call    cs:__imp_CharNextW
0x180017ce9  movzx   ecx, word ptr [rdi]
0x180017cec  cmp     cx, 5Ch ; '\'
0x180017cf0  jnz     short loc_180017D0A
0x180017cf2  cmp     [rax], r15w
0x180017cf6  jnz     short loc_180017D0A
0x180017cf8  mov     rcx, rax; lpsz
0x180017cfb  mov     [rbx], r12w
0x180017cff  call    cs:__imp_CharNextW
0x180017d05  mov     rdi, rax
0x180017d08  jmp     short loc_180017D10
0x180017d0a  mov     [rbx], cx
0x180017d0d  add     rdi, rsi
0x180017d10  add     rbx, rsi
0x180017d13  cmp     [rdi], r12w
0x180017d17  jnz     short loc_180017CE0
0x180017d19  mov     r12, [rsp+21B0h+var_2178]
0x180017d1e  xor     r15d, r15d
0x180017d21  mov     dword ptr [rbx], 0
0x180017d27  mov     r8, [rsp+21B0h+var_2160]
0x180017d2c  test    r8, r8
0x180017d2f  jz      short loc_180017D75
0x180017d31  mov     r10d, r15d
0x180017d34  mov     r9, r8
0x180017d37  mov     rcx, r14
0x180017d3a  inc     rcx
0x180017d3d  cmp     [r9+rcx*2], r15w
0x180017d42  jnz     short loc_180017D3A
0x180017d44  inc     ecx
0x180017d46  lea     r9, [r9+rcx*2]
0x180017d4a  lea     r10d, [r10+rcx*2]
0x180017d4e  cmp     ecx, 1
0x180017d51  jnz     short loc_180017D37
0x180017d53  mov     [rsp+21B0h+cbData], r10d; cbData
0x180017d58  lea     r9d, [rcx+6]; dwType
0x180017d5c  mov     rcx, [r12]; hKey
0x180017d60  mov     rdx, r13; lpValueName
0x180017d63  mov     [rsp+21B0h+lpData], r8; lpData
0x180017d68  xor     r8d, r8d; Reserved
0x180017d6b  call    cs:__imp_RegSetValueExW
0x180017d71  mov     ebx, eax
0x180017d73  jmp     short loc_180017D85
0x180017d75  mov     ecx, 80004005h; int
0x180017d7a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017d80  mov     ebx, 0Eh
0x180017d85  lea     rcx, [rsp+21B0h+var_2160]
0x180017d8a  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180017d8f  mov     rsi, qword ptr [rsp+21B0h+pulOut]
0x180017d94  mov     r14, [rsp+21B0h+var_2170]
0x180017d99  jmp     loc_180017F9C
0x180017d9e  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x180017da3  mov     [rsp+21B0h+pulOut], r15d
0x180017da8  xor     r8d, r8d; dwFlags
0x180017dab  mov     [rsp+21B0h+var_2178], r15
0x180017db0  xor     edx, edx; lcid
0x180017db2  lea     rcx, [rbp+20B0h+String1]; strIn
0x180017db6  call    cs:__imp_VarUI4FromStr
0x180017dbc  mov     ebx, eax
0x180017dbe  test    eax, eax
0x180017dc0  jns     short loc_180017DD3
0x180017dc2  lea     rcx, [rsp+21B0h+var_2178]
0x180017dc7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017dcc  mov     eax, ebx
0x180017dce  jmp     loc_180017FC5
0x180017dd3  mov     r8d, [rsp+21B0h+pulOut]; unsigned int
0x180017dd8  mov     rdx, r13; unsigned __int16 *
0x180017ddb  mov     rcx, r12; this
0x180017dde  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180017de3  lea     rcx, [rsp+21B0h+var_2178]
0x180017de8  mov     ebx, eax
0x180017dea  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017def  jmp     loc_180017F9C
0x180017df4  lea     rax, [rbp+20B0h+String1]
0x180017df8  or      r14, 0FFFFFFFFFFFFFFFFh
0x180017dfc  inc     r14
0x180017dff  cmp     [rax+r14*2], r15w
0x180017e04  jnz     short loc_180017DFC
0x180017e06  test    r14b, 1
0x180017e0a  jz      short loc_180017E16
0x180017e0c  mov     eax, 80004005h
0x180017e11  jmp     loc_180017FC5
0x180017e16  mov     eax, r14d
0x180017e19  mov     [rsp+21B0h+var_2160], r15
0x180017e1e  cdq
0x180017e1f  mov     esi, 2
0x180017e24  idiv    esi
0x180017e26  lea     edx, [rsi-1]
0x180017e29  movsxd  rdi, eax
0x180017e2c  mov     rcx, rdi
0x180017e2f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180017e34  cmp     rax, 100h
0x180017e3a  jbe     short loc_180017E50
0x180017e3c  mov     rdx, rax
0x180017e3f  lea     rcx, [rsp+21B0h+var_2160]
0x180017e44  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180017e49  mov     rcx, [rsp+21B0h+var_2160]
0x180017e4e  jmp     short loc_180017E5A
0x180017e50  lea     rcx, [rsp+21B0h+var_2158]; void *
0x180017e55  mov     [rsp+21B0h+var_2160], rcx
0x180017e5a  test    rcx, rcx
0x180017e5d  jnz     short loc_180017E6B
0x180017e5f  lea     rcx, [rsp+21B0h+var_2160]
0x180017e64  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180017e69  jmp     short loc_180017E0C
0x180017e6b  mov     r8, rdi; Size
0x180017e6e  xor     edx, edx; Val
0x180017e70  call    memset_0
0x180017e75  mov     r10d, r15d
0x180017e78  test    r14d, r14d
0x180017e7b  jle     loc_180017F56
0x180017e81  mov     r15d, 30h ; '0'
0x180017e87  mov     eax, r10d
0x180017e8a  movzx   r9d, [rbp+rax*2+20B0h+String1]
0x180017e90  cmp     r9d, 61h ; 'a'
0x180017e94  ja      short loc_180017F00
0x180017e96  jz      loc_180017F21
0x180017e9c  cmp     r9d, 38h ; '8'
0x180017ea0  ja      short loc_180017ED4
0x180017ea2  jz      short loc_180017ECF
0x180017ea4  mov     ecx, r9d
0x180017ea7  sub     ecx, r15d
0x180017eaa  jz      short loc_180017ECF
0x180017eac  sub     ecx, 1
0x180017eaf  jz      short loc_180017ECF
0x180017eb1  sub     ecx, 1
0x180017eb4  jz      short loc_180017ECF
0x180017eb6  sub     ecx, 1
0x180017eb9  jz      short loc_180017ECF
0x180017ebb  sub     ecx, 1
0x180017ebe  jz      short loc_180017ECF
0x180017ec0  sub     ecx, 1
0x180017ec3  jz      short loc_180017ECF
0x180017ec5  sub     ecx, 1
0x180017ec8  jz      short loc_180017ECF
0x180017eca  cmp     ecx, 1
0x180017ecd  jnz     short loc_180017F1C
0x180017ecf  sub     r9b, r15b
0x180017ed2  jmp     short loc_180017F25
0x180017ed4  mov     ecx, r9d
0x180017ed7  sub     ecx, 39h ; '9'
0x180017eda  jz      short loc_180017ECF
0x180017edc  sub     ecx, 8
0x180017edf  jz      short loc_180017EFA
0x180017ee1  sub     ecx, 1
0x180017ee4  jz      short loc_180017EFA
0x180017ee6  sub     ecx, 1
0x180017ee9  jz      short loc_180017EFA
0x180017eeb  sub     ecx, 1
0x180017eee  jz      short loc_180017EFA
0x180017ef0  sub     ecx, 1
0x180017ef3  jz      short loc_180017EFA
0x180017ef5  cmp     ecx, 1
0x180017ef8  jnz     short loc_180017F1C
0x180017efa  sub     r9b, 37h ; '7'
0x180017efe  jmp     short loc_180017F25
0x180017f00  mov     ecx, r9d
0x180017f03  sub     ecx, 62h ; 'b'
0x180017f06  jz      short loc_180017F21
0x180017f08  sub     ecx, 1
0x180017f0b  jz      short loc_180017F21
0x180017f0d  sub     ecx, 1
0x180017f10  jz      short loc_180017F21
0x180017f12  sub     ecx, 1
0x180017f15  jz      short loc_180017F21
0x180017f17  cmp     ecx, 1
0x180017f1a  jz      short loc_180017F21
0x180017f1c  xor     r9b, r9b
0x180017f1f  jmp     short loc_180017F25
0x180017f21  sub     r9b, 57h ; 'W'
0x180017f25  mov     rdx, [rsp+21B0h+var_2160]
0x180017f2a  mov     eax, r10d
0x180017f2d  and     eax, 1
0x180017f30  mov     r8d, r10d
0x180017f33  shl     eax, 2
0x180017f36  mov     ecx, 4
0x180017f3b  shr     r8, 1
0x180017f3e  sub     ecx, eax
0x180017f40  shl     r9b, cl
0x180017f43  inc     r10d
0x180017f46  or      [r8+rdx], r9b
0x180017f4a  cmp     r10d, r14d
0x180017f4d  jl      loc_180017E87
0x180017f53  xor     r15d, r15d
0x180017f56  mov     rax, [rsp+21B0h+var_2160]
0x180017f5b  mov     r9d, 3; dwType
0x180017f61  mov     rcx, [r12]; hKey
0x180017f65  xor     r8d, r8d; Reserved
0x180017f68  mov     [rsp+21B0h+cbData], edi; cbData
0x180017f6c  mov     rdx, r13; lpValueName
0x180017f6f  mov     [rsp+21B0h+lpData], rax; lpData
0x180017f74  call    cs:__imp_RegSetValueExW
0x180017f7a  lea     rcx, [rsp+21B0h+var_2160]
0x180017f7f  mov     ebx, eax
0x180017f81  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180017f86  jmp     loc_180017D8F
0x180017f8b  lea     r8, [rbp+20B0h+String1]; unsigned __int16 *
0x180017f8f  mov     rdx, r13; unsigned __int16 *
0x180017f92  mov     rcx, r12; this
0x180017f95  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180017f9a  mov     ebx, eax
0x180017f9c  test    ebx, ebx
0x180017f9e  jz      short loc_180017FA9
0x180017fa0  mov     ecx, ebx; unsigned int
0x180017fa2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180017fa7  jmp     short loc_180017FC5
0x180017fa9  mov     rdx, r14; unsigned __int16 *
0x180017fac  mov     rcx, rsi; this
0x180017faf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180017fb4  test    eax, eax
0x180017fb6  mov     ecx, r15d
0x180017fb9  cmovs   ecx, eax
0x180017fbc  mov     eax, ecx
  ... truncated ...
```
