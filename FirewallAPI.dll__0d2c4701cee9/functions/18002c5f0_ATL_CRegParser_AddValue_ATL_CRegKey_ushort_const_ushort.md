# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18002c5f0`
- end: `0x18002caf3`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1283`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18002f318`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x18002bde4`
- `0x18002be80`
- `0x18002c054`
- `0x18002c5f0`
- `0x18002cafc`
- `0x18002cea4`
- `0x18002d68c`
- `0x18002d7d4`
- `0x18002e8d0`
- `0x18002fb28`
- `0x18005f820`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002c7a4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002c7c6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002c7a4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002c7c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c833`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c8d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca3c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c833`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c8d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca3c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca99`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002c67d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002c67d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002c885`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002c885`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r13
  HKEY *v5; // r12
  ATL::CRegParser *v6; // r14
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rsi
  WCHAR *k; // r14
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // edi
  HRESULT v21; // edi
  __int64 v22; // rdi
  DWORD v23; // r14d
  size_t v24; // rsi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int j; // r10d
  unsigned __int8 v28; // al
  int v29; // r10d
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdi
  int Token; // eax
  ATL::CRegParser *v34; // [rsp+30h] [rbp-21A8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-21A0h]
  const unsigned __int16 *v36; // [rsp+40h] [rbp-2198h]
  size_t v37; // [rsp+50h] [rbp-2188h]
  struct ATL::CRegKey *v38; // [rsp+58h] [rbp-2180h]
  unsigned __int16 *v39; // [rsp+60h] [rbp-2178h]
  ULONG pulOut; // [rsp+68h] [rbp-2170h] BYREF
  BYTE Data[16]; // [rsp+70h] [rbp-2168h] BYREF
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v43[264]; // [rsp+88h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v34 = this;
  *(_QWORD *)Data = a2;
  v35 = this;
  v38 = (struct ATL::CRegKey *)a2;
  v36 = a3;
  v39 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
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
  ATL::CRegParser::SkipWhiteSpace(v6);
  result = ATL::CRegParser::NextToken(v6, String1);
  if ( (int)result < 0 )
    return result;
  switch ( v10 )
  {
    case 8:
      v32 = -1;
      do
        ++v32;
      while ( String1[v32] );
      v20 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
      break;
    case 17:
      v22 = -1;
      do
        ++v22;
      while ( String1[v22] );
      *(_DWORD *)Data = v22;
      if ( (v22 & 1) == 0 )
      {
        v23 = (int)v22 / 2;
        memset_0(&lpData, 0, 0x108u);
        lpData = 0;
        v24 = (int)v22 / 2;
        v37 = v24;
        try
        {
          v25 = ATL::AtlMultiplyThrow<unsigned __int64>();
          if ( v25 <= 0x100 )
          {
            v26 = v43;
            lpData = v43;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
            v26 = lpData;
          }
        }
        catch ( ... )
        {
          v8 = 0;
          LODWORD(v22) = *(_DWORD *)Data;
          v26 = lpData;
          v24 = v37;
          v34 = v35;
          v5 = (HKEY *)v38;
          v4 = v36;
          v23 = v37;
        }
        if ( v26 )
        {
          memset_0(v26, 0, v24);
          for ( j = 0; j < (int)v22; j = v29 + 1 )
          {
            v28 = ATL::CRegParser::ChToByte(String1[j]);
            *(_BYTE *)(v31 + v30) |= v28 << (4 - 4 * (v29 & 1));
          }
          v20 = RegSetValueExW(*v5, v4, 0, 3u, lpData, v23);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_33:
          v6 = v34;
          break;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    case 19:
      pulOut = 0;
      v34 = 0;
      v21 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v21 < 0 )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v34);
        return (unsigned int)v21;
      }
      *(_DWORD *)Data = pulOut;
      v20 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v34);
      break;
    case 16392:
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      memset_0(&lpData, 0, 0x108u);
      lpData = 0;
      try
      {
        v12 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v12 <= 0x100 )
        {
          v13 = v43;
          lpData = v43;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
          v13 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        v13 = lpData;
        v5 = *(HKEY **)Data;
        v34 = v35;
        v4 = v36;
      }
      if ( v13 )
      {
        for ( k = String1; *k; v13 += 2 )
        {
          v15 = CharNextW(k);
          if ( *k == 92 && *v15 == 48 )
          {
            *(_WORD *)v13 = 0;
            k = CharNextW(v15);
          }
          else
          {
            *(_WORD *)v13 = *k++;
          }
        }
        *(_DWORD *)v13 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v17 = lpData;
        do
        {
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)&v17[2 * v18] );
          v19 = (unsigned int)(v18 + 1);
          v17 += 2 * v19;
          cbData += 2 * v19;
        }
        while ( (_DWORD)v19 != 1 );
        v20 = RegSetValueExW(*v5, v4, 0, 7u, lpData, cbData);
      }
      else
      {
        v20 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      goto LABEL_33;
    default:
LABEL_55:
      Token = ATL::CRegParser::NextToken(v6, v39);
      if ( Token < 0 )
        return (unsigned int)Token;
      return v8;
  }
  if ( !v20 )
    goto LABEL_55;
  return ATL::AtlHresultFromWin32(v20);
}

```

## disassembly

```asm
0x18002c5f0  push    rbx
0x18002c5f2  push    rsi
0x18002c5f3  push    rdi
0x18002c5f4  push    r12
0x18002c5f6  push    r13
0x18002c5f8  push    r14
0x18002c5fa  push    r15
0x18002c5fc  mov     eax, 21A0h
0x18002c601  call    _alloca_probe
0x18002c606  sub     rsp, rax
0x18002c609  mov     rax, cs:__security_cookie
0x18002c610  xor     rax, rsp
0x18002c613  mov     [rsp+21D8h+var_48], rax
0x18002c61b  mov     r13, r8
0x18002c61e  mov     r12, rdx
0x18002c621  mov     r14, rcx
0x18002c624  mov     [rsp+21D8h+var_21A8], rcx
0x18002c629  mov     qword ptr [rsp+21D8h+Data], rdx
0x18002c62e  mov     [rsp+21D8h+var_21A0], rcx
0x18002c633  mov     [rsp+21D8h+var_2180], rdx
0x18002c638  mov     [rsp+21D8h+var_2198], r8
0x18002c63d  mov     [rsp+21D8h+var_2178], r9
0x18002c642  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x18002c64a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002c64f  xor     ebx, ebx
0x18002c651  test    eax, eax
0x18002c653  js      loc_18002CACF
0x18002c659  mov     edi, ebx
0x18002c65b  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18002c662  cmp     edi, 4
0x18002c665  jnb     loc_18002CACA
0x18002c66b  movsxd  rsi, edi
0x18002c66e  add     rsi, rsi
0x18002c671  mov     rdx, [r15+rsi*8]; lpString2
0x18002c675  lea     rcx, [rsp+21D8h+String1]; lpString1
0x18002c67d  call    cs:__imp_lstrcmpiW
0x18002c684  nop     dword ptr [rax+rax+00h]
0x18002c689  test    eax, eax
0x18002c68b  jz      short loc_18002C691
0x18002c68d  inc     edi
0x18002c68f  jmp     short loc_18002C662
0x18002c691  movzx   edi, word ptr [r15+rsi*8+8]
0x18002c697  mov     rcx, r14; this
0x18002c69a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18002c69f  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x18002c6a7  mov     rcx, r14; this
0x18002c6aa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002c6af  test    eax, eax
0x18002c6b1  js      loc_18002CACF
0x18002c6b7  cmp     di, 8
0x18002c6bb  jz      loc_18002CA5C
0x18002c6c1  cmp     di, 11h
0x18002c6c5  jz      loc_18002C8EF
0x18002c6cb  cmp     di, 13h
0x18002c6cf  jz      loc_18002C86A
0x18002c6d5  mov     eax, 4008h
0x18002c6da  cmp     di, ax
0x18002c6dd  jnz     loc_18002CAB4
0x18002c6e3  lea     rcx, [rsp+21D8h+String1]
0x18002c6eb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c6ef  mov     rax, rdi
0x18002c6f2  inc     rax
0x18002c6f5  cmp     [rcx+rax*2], bx
0x18002c6f9  jnz     short loc_18002C6F2
0x18002c6fb  lea     esi, [rax+2]
0x18002c6fe  xor     edx, edx; Val
0x18002c700  mov     r8d, 108h; Size
0x18002c706  lea     rcx, [rsp+21D8h+var_2158]; void *
0x18002c70e  call    memset_0
0x18002c713  mov     [rsp+21D8h+var_2158], rbx
0x18002c71b  movsxd  rcx, esi
0x18002c71e  mov     r15d, 2
0x18002c724  mov     edx, r15d
0x18002c727  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002c72c  cmp     rax, 100h
0x18002c732  jbe     short loc_18002C74E
0x18002c734  mov     rdx, rax
0x18002c737  lea     rcx, [rsp+21D8h+var_2158]
0x18002c73f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002c744  mov     rsi, [rsp+21D8h+var_2158]
0x18002c74c  jmp     short loc_18002C75E
0x18002c74e  lea     rsi, [rsp+21D8h+var_2150]
0x18002c756  mov     [rsp+21D8h+var_2158], rsi
0x18002c75e  jmp     short loc_18002C786
0x18002c760  xor     ebx, ebx
0x18002c762  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c766  lea     r15d, [rbx+2]
0x18002c76a  mov     rsi, [rsp+21D8h+var_2158]
0x18002c772  mov     r12, qword ptr [rsp+21D8h+Data]
0x18002c777  mov     rax, [rsp+21D8h+var_21A0]
0x18002c77c  mov     [rsp+21D8h+var_21A8], rax
0x18002c781  mov     r13, [rsp+21D8h+var_2198]
0x18002c786  test    rsi, rsi
0x18002c789  jz      loc_18002C84E
0x18002c78f  lea     r14, [rsp+21D8h+String1]
0x18002c797  cmp     [rsp+21D8h+String1], bx
0x18002c79f  jz      short loc_18002C7E6
0x18002c7a1  mov     rcx, r14; lpsz
0x18002c7a4  call    cs:__imp_CharNextW
0x18002c7ab  nop     dword ptr [rax+rax+00h]
0x18002c7b0  movzx   ecx, word ptr [r14]
0x18002c7b4  cmp     cx, 5Ch ; '\'
0x18002c7b8  jnz     short loc_18002C7D7
0x18002c7ba  cmp     word ptr [rax], 30h ; '0'
0x18002c7be  jnz     short loc_18002C7D7
0x18002c7c0  mov     [rsi], bx
0x18002c7c3  mov     rcx, rax; lpsz
0x18002c7c6  call    cs:__imp_CharNextW
0x18002c7cd  nop     dword ptr [rax+rax+00h]
0x18002c7d2  mov     r14, rax
0x18002c7d5  jmp     short loc_18002C7DD
0x18002c7d7  mov     [rsi], cx
0x18002c7da  add     r14, r15
0x18002c7dd  add     rsi, r15
0x18002c7e0  cmp     [r14], bx
0x18002c7e4  jnz     short loc_18002C7A1
0x18002c7e6  mov     dword ptr [rsi], 0
0x18002c7ec  mov     r8, [rsp+21D8h+var_2158]
0x18002c7f4  test    r8, r8
0x18002c7f7  jz      short loc_18002C843
0x18002c7f9  mov     r10d, ebx
0x18002c7fc  mov     r9, r8
0x18002c7ff  mov     rcx, rdi
0x18002c802  inc     rcx
0x18002c805  cmp     [r9+rcx*2], bx
0x18002c80a  jnz     short loc_18002C802
0x18002c80c  inc     ecx
0x18002c80e  lea     r9, [r9+rcx*2]
0x18002c812  lea     r10d, [r10+rcx*2]
0x18002c816  cmp     ecx, 1
0x18002c819  jnz     short loc_18002C7FF
0x18002c81b  mov     [rsp+21D8h+cbData], r10d; cbData
0x18002c820  mov     [rsp+21D8h+lpData], r8; lpData
0x18002c825  lea     r9d, [rcx+6]; dwType
0x18002c829  xor     r8d, r8d; Reserved
0x18002c82c  mov     rdx, r13; lpValueName
0x18002c82f  mov     rcx, [r12]; hKey
0x18002c833  call    cs:__imp_RegSetValueExW
0x18002c83a  nop     dword ptr [rax+rax+00h]
0x18002c83f  mov     edi, eax
0x18002c841  jmp     short loc_18002C853
0x18002c843  mov     ecx, 80004005h; int
0x18002c848  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c84e  mov     edi, 0Eh
0x18002c853  lea     rcx, [rsp+21D8h+var_2158]
0x18002c85b  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002c860  mov     r14, [rsp+21D8h+var_21A8]
0x18002c865  jmp     loc_18002CAA7
0x18002c86a  mov     [rsp+21D8h+pulOut], ebx
0x18002c86e  mov     [rsp+21D8h+var_21A8], rbx
0x18002c873  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x18002c878  xor     r8d, r8d; dwFlags
0x18002c87b  xor     edx, edx; lcid
0x18002c87d  lea     rcx, [rsp+21D8h+String1]; strIn
0x18002c885  call    cs:__imp_VarUI4FromStr
0x18002c88c  nop     dword ptr [rax+rax+00h]
0x18002c891  mov     edi, eax
0x18002c893  test    eax, eax
0x18002c895  jns     short loc_18002C8A8
0x18002c897  lea     rcx, [rsp+21D8h+var_21A8]
0x18002c89c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c8a1  mov     eax, edi
0x18002c8a3  jmp     loc_18002CACF
0x18002c8a8  mov     eax, [rsp+21D8h+pulOut]
0x18002c8ac  mov     dword ptr [rsp+21D8h+Data], eax
0x18002c8b0  mov     [rsp+21D8h+cbData], 4; cbData
0x18002c8b8  lea     rax, [rsp+21D8h+Data]
0x18002c8bd  mov     [rsp+21D8h+lpData], rax; lpData
0x18002c8c2  mov     r9d, 4; dwType
0x18002c8c8  xor     r8d, r8d; Reserved
0x18002c8cb  mov     rdx, r13; lpValueName
0x18002c8ce  mov     rcx, [r12]; hKey
0x18002c8d2  call    cs:__imp_RegSetValueExW
0x18002c8d9  nop     dword ptr [rax+rax+00h]
0x18002c8de  mov     edi, eax
0x18002c8e0  lea     rcx, [rsp+21D8h+var_21A8]
0x18002c8e5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c8ea  jmp     loc_18002CAA7
0x18002c8ef  lea     rax, [rsp+21D8h+String1]
0x18002c8f7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c8fb  inc     rdi
0x18002c8fe  cmp     [rax+rdi*2], bx
0x18002c902  jnz     short loc_18002C8FB
0x18002c904  mov     dword ptr [rsp+21D8h+Data], edi
0x18002c908  test    dil, 1
0x18002c90c  jz      short loc_18002C918
0x18002c90e  mov     eax, 80004005h
0x18002c913  jmp     loc_18002CACF
0x18002c918  mov     eax, edi
0x18002c91a  cdq
0x18002c91b  mov     r15d, 2
0x18002c921  idiv    r15d
0x18002c924  movsxd  r14, eax
0x18002c927  xor     edx, edx; Val
0x18002c929  mov     r8d, 108h; Size
0x18002c92f  lea     rcx, [rsp+21D8h+var_2158]; void *
0x18002c937  call    memset_0
0x18002c93c  mov     [rsp+21D8h+var_2158], rbx
0x18002c944  mov     rsi, r14
0x18002c947  mov     [rsp+21D8h+var_2188], r14
0x18002c94c  lea     edx, [r15-1]
0x18002c950  mov     rcx, r14
0x18002c953  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002c958  cmp     rax, 100h
0x18002c95e  jbe     short loc_18002C97A
0x18002c960  mov     rdx, rax
0x18002c963  lea     rcx, [rsp+21D8h+var_2158]
0x18002c96b  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002c970  mov     rcx, [rsp+21D8h+var_2158]
0x18002c978  jmp     short loc_18002C98A
0x18002c97a  lea     rcx, [rsp+21D8h+var_2150]
0x18002c982  mov     [rsp+21D8h+var_2158], rcx
0x18002c98a  jmp     short loc_18002C9B6
0x18002c98c  xor     ebx, ebx
0x18002c98e  mov     edi, dword ptr [rsp+21D8h+Data]
0x18002c992  mov     rcx, [rsp+21D8h+var_2158]; void *
0x18002c99a  mov     rsi, [rsp+21D8h+var_2188]
0x18002c99f  mov     rax, [rsp+21D8h+var_21A0]
0x18002c9a4  mov     [rsp+21D8h+var_21A8], rax
0x18002c9a9  mov     r12, [rsp+21D8h+var_2180]
0x18002c9ae  mov     r13, [rsp+21D8h+var_2198]
0x18002c9b3  mov     r14d, esi
0x18002c9b6  test    rcx, rcx
0x18002c9b9  jnz     short loc_18002C9CD
0x18002c9bb  lea     rcx, [rsp+21D8h+var_2158]
0x18002c9c3  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002c9c8  jmp     loc_18002C90E
0x18002c9cd  mov     r8, rsi; Size
0x18002c9d0  xor     edx, edx; Val
0x18002c9d2  call    memset_0
0x18002c9d7  mov     r10d, ebx
0x18002c9da  test    edi, edi
0x18002c9dc  jle     short loc_18002CA1A
0x18002c9de  mov     r9d, r10d
0x18002c9e1  shr     r9, 1
0x18002c9e4  mov     r8, [rsp+21D8h+var_2158]
0x18002c9ec  mov     ecx, r10d
0x18002c9ef  movzx   ecx, [rsp+rcx*2+21D8h+String1]; unsigned __int16
0x18002c9f7  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18002c9fc  mov     edx, r10d
0x18002c9ff  and     edx, 1
0x18002ca02  shl     edx, 2
0x18002ca05  mov     ecx, 4
0x18002ca0a  sub     ecx, edx
0x18002ca0c  shl     al, cl
0x18002ca0e  or      [r9+r8], al
0x18002ca12  inc     r10d
0x18002ca15  cmp     r10d, edi
0x18002ca18  jl      short loc_18002C9DE
0x18002ca1a  mov     rax, [rsp+21D8h+var_2158]
0x18002ca22  mov     [rsp+21D8h+cbData], r14d; cbData
0x18002ca27  mov     [rsp+21D8h+lpData], rax; lpData
0x18002ca2c  mov     r9d, 3; dwType
0x18002ca32  xor     r8d, r8d; Reserved
0x18002ca35  mov     rdx, r13; lpValueName
0x18002ca38  mov     rcx, [r12]; hKey
0x18002ca3c  call    cs:__imp_RegSetValueExW
0x18002ca43  nop     dword ptr [rax+rax+00h]
0x18002ca48  mov     edi, eax
0x18002ca4a  lea     rcx, [rsp+21D8h+var_2158]
0x18002ca52  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002ca57  jmp     loc_18002C860
0x18002ca5c  lea     rax, [rsp+21D8h+String1]
0x18002ca64  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002ca68  inc     rdi
0x18002ca6b  cmp     [rax+rdi*2], bx
0x18002ca6f  jnz     short loc_18002CA68
0x18002ca71  lea     eax, ds:2[rdi*2]
0x18002ca78  mov     [rsp+21D8h+cbData], eax; cbData
0x18002ca7c  lea     rax, [rsp+21D8h+String1]
0x18002ca84  mov     [rsp+21D8h+lpData], rax; lpData
0x18002ca89  mov     r9d, 1; dwType
0x18002ca8f  xor     r8d, r8d; Reserved
0x18002ca92  mov     rdx, r13; lpValueName
0x18002ca95  mov     rcx, [r12]; hKey
0x18002ca99  call    cs:__imp_RegSetValueExW
0x18002caa0  nop     dword ptr [rax+rax+00h]
0x18002caa5  mov     edi, eax
0x18002caa7  test    edi, edi
0x18002caa9  jz      short loc_18002CAB4
0x18002caab  mov     ecx, edi; unsigned int
0x18002caad  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002cab2  jmp     short loc_18002CACF
0x18002cab4  mov     rdx, [rsp+21D8h+var_2178]; unsigned __int16 *
0x18002cab9  mov     rcx, r14; this
0x18002cabc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002cac1  test    eax, eax
0x18002cac3  cmovs   ebx, eax
0x18002cac6  mov     eax, ebx
0x18002cac8  jmp     short loc_18002CACF
0x18002caca  mov     eax, 80020009h
0x18002cacf  mov     rcx, [rsp+21D8h+var_48]
0x18002cad7  xor     rcx, rsp; StackCookie
0x18002cada  call    __security_check_cookie
0x18002cadf  add     rsp, 21A0h
0x18002cae6  pop     r15
0x18002cae8  pop     r14
0x18002caea  pop     r13
0x18002caec  pop     r12
0x18002caee  pop     rdi
  ... truncated ...
```
