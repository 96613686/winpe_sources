# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18009129c`
- end: `0x18009181c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180093290`

## callees

- `0x180061320`
- `0x180062314`
- `0x18006afd4`
- `0x18006b880`
- `0x18008f830`
- `0x180090c90`
- `0x18009129c`
- `0x180091824`
- `0x180091914`
- `0x180092970`
- `0x180093b44`
- `0x1800b7bf0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180091459`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180091475`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180091459`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180091475`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800914de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180091571`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009176f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800917c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800914de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180091571`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009176f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800917c6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180091337`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180091337`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18009152a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18009152a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegParser *v6; // r15
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rax
  int v12; // eax
  unsigned __int64 v13; // rax
  BYTE *v14; // rdi
  HKEY *v15; // r13
  WCHAR *j; // r14
  const WCHAR *v17; // rax
  DWORD cbData; // r10d
  BYTE *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  LSTATUS v22; // edi
  HRESULT v23; // edi
  __int64 v24; // rsi
  DWORD v25; // r14d
  size_t v26; // rdi
  unsigned __int64 v27; // rax
  BYTE *v28; // rcx
  HKEY *v29; // r15
  unsigned int v30; // r10d
  unsigned int v31; // edx
  char v32; // r9
  __int64 v33; // rsi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21B8h] BYREF
  ATL::CRegParser *v36; // [rsp+38h] [rbp-21B0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-21A8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-21A0h]
  HKEY *v39; // [rsp+50h] [rbp-2198h]
  ATL::CRegParser *v40; // [rsp+58h] [rbp-2190h]
  const WCHAR *v41; // [rsp+60h] [rbp-2188h]
  size_t v42; // [rsp+70h] [rbp-2178h]
  HKEY *v43; // [rsp+78h] [rbp-2170h]
  unsigned __int16 *v44; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v46[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v39 = a2;
  v6 = this;
  v36 = this;
  *(_QWORD *)Data = a2;
  v40 = this;
  v43 = a2;
  v41 = a3;
  v44 = a4;
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
      v33 = -1;
      do
        ++v33;
      while ( String1[v33] );
      v22 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
      goto LABEL_80;
    case 17:
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      *(_DWORD *)Data = v24;
      if ( (v24 & 1) != 0 )
        return 2147500037LL;
      v25 = (int)v24 / 2;
      lpData = 0;
      v26 = (int)v24 / 2;
      v42 = v26;
      try
      {
        v27 = ((__int64 (*)(void))ATL::AtlMultiplyThrow<unsigned __int64>)();
        if ( v27 <= 0x100 )
        {
          v28 = v46;
          lpData = v46;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v27);
          v28 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v24) = *(_DWORD *)Data;
        v28 = lpData;
        v26 = v42;
        v36 = v40;
        v29 = v43;
        lpValueName = v41;
        v25 = v42;
        goto LABEL_47;
      }
      v29 = v39;
LABEL_47:
      if ( !v28 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v28, 0, v26);
      v30 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_76:
        v22 = RegSetValueExW(*v29, lpValueName, 0, 3u, lpData, v25);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_34;
      }
      while ( 1 )
      {
        v31 = String1[v30];
        if ( v31 > 0x61 )
        {
          if ( v31 == 98 || v31 == 99 || v31 == 100 || v31 - 101 < 2 )
          {
LABEL_74:
            v32 = v31 - 87;
            goto LABEL_75;
          }
LABEL_73:
          v32 = 0;
          goto LABEL_75;
        }
        if ( v31 == 97 )
          goto LABEL_74;
        if ( v31 <= 0x38 )
          break;
        if ( v31 == 57 )
          goto LABEL_61;
        if ( v31 != 65 && v31 != 66 && v31 != 67 && v31 != 68 && v31 - 69 > 1 )
          goto LABEL_73;
        v32 = v31 - 55;
LABEL_75:
        lpData[(unsigned __int64)v30 >> 1] |= v32 << (4 - 4 * (v30 & 1));
        if ( (int)++v30 >= (int)v24 )
          goto LABEL_76;
      }
      if ( v31 != 56 && v31 != 48 && v31 != 49 && v31 != 50 && v31 != 51 && v31 != 52 && v31 != 53 && v31 - 54 > 1 )
        goto LABEL_73;
LABEL_61:
      v32 = v31 - 48;
      goto LABEL_75;
    case 19:
      pulOut = 0;
      v36 = 0;
      v23 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v23 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v22 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v36);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v36);
      return (unsigned int)v23;
    case 16392:
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      v12 = v11 + 2;
      lpData = 0;
      try
      {
        v13 = ATL::AtlMultiplyThrow<unsigned __int64>(v12, 2);
        if ( v13 <= 0x100 )
        {
          v14 = v46;
          lpData = v46;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v13);
          v14 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        v14 = lpData;
        v15 = *(HKEY **)Data;
        v36 = v40;
        lpValueName = v41;
        goto LABEL_18;
      }
      v15 = v39;
LABEL_18:
      if ( v14 )
      {
        for ( j = String1; *j; v14 += 2 )
        {
          v17 = CharNextW(j);
          if ( *j == 92 && *v17 == 48 )
          {
            *(_WORD *)v14 = 0;
            j = CharNextW(v17);
          }
          else
          {
            *(_WORD *)v14 = *j++;
          }
        }
        *(_DWORD *)v14 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v19 = lpData;
        do
        {
          v20 = -1;
          do
            ++v20;
          while ( *(_WORD *)&v19[2 * v20] );
          v21 = (unsigned int)(v20 + 1);
          v19 += 2 * v21;
          cbData += 2 * v21;
        }
        while ( (_DWORD)v21 != 1 );
        v22 = RegSetValueExW(*v15, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v22 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_34:
      v6 = v36;
LABEL_80:
      if ( v22 )
      {
        return ATL::AtlHresultFromWin32(v22);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v44);
        if ( Token < 0 )
          return (unsigned int)Token;
        return v8;
      }
    default:
      goto LABEL_82;
  }
}

```

## disassembly

```asm
0x18009129c  push    rbx
0x18009129e  push    rsi
0x18009129f  push    rdi
0x1800912a0  push    r12
0x1800912a2  push    r13
0x1800912a4  push    r14
0x1800912a6  push    r15
0x1800912a8  mov     eax, 21B0h
0x1800912ad  call    _alloca_probe
0x1800912b2  sub     rsp, rax
0x1800912b5  mov     rax, cs:__security_cookie
0x1800912bc  xor     rax, rsp
0x1800912bf  mov     [rsp+21E8h+var_48], rax
0x1800912c7  mov     r14, r8
0x1800912ca  mov     [rsp+21E8h+lpValueName], r8
0x1800912cf  mov     r12, rdx
0x1800912d2  mov     [rsp+21E8h+var_2198], rdx
0x1800912d7  mov     r15, rcx
0x1800912da  mov     [rsp+21E8h+var_21B0], rcx
0x1800912df  mov     qword ptr [rsp+21E8h+Data], rdx
0x1800912e4  mov     [rsp+21E8h+var_2190], rcx
0x1800912e9  mov     [rsp+21E8h+var_2170], rdx
0x1800912ee  mov     [rsp+21E8h+var_2188], r8
0x1800912f3  mov     [rsp+21E8h+var_2168], r9
0x1800912fb  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180091303  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180091308  xor     ebx, ebx
0x18009130a  test    eax, eax
0x18009130c  js      loc_1800917F9
0x180091312  mov     edi, ebx
0x180091314  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18009131b  cmp     edi, 4
0x18009131e  jnb     loc_1800917F4
0x180091324  movsxd  rsi, edi
0x180091327  add     rsi, rsi
0x18009132a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18009132f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180091337  call    cs:__imp_lstrcmpiW
0x18009133d  test    eax, eax
0x18009133f  jz      short loc_180091345
0x180091341  inc     edi
0x180091343  jmp     short loc_18009131B
0x180091345  movzx   edi, word ptr [r13+rsi*8+8]
0x18009134b  mov     rcx, r15; this
0x18009134e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180091353  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18009135b  mov     rcx, r15; this
0x18009135e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180091363  test    eax, eax
0x180091365  js      loc_1800917F9
0x18009136b  mov     r13d, 8
0x180091371  cmp     di, r13w
0x180091375  jz      loc_180091789
0x18009137b  cmp     di, 11h
0x18009137f  jz      loc_180091588
0x180091385  cmp     di, 13h
0x180091389  jz      loc_18009150F
0x18009138f  mov     eax, 4008h
0x180091394  cmp     di, ax
0x180091397  jnz     loc_1800917DB
0x18009139d  lea     rcx, [rsp+21E8h+String1]
0x1800913a5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800913a9  mov     rax, rsi
0x1800913ac  inc     rax
0x1800913af  cmp     [rcx+rax*2], bx
0x1800913b3  jnz     short loc_1800913AC
0x1800913b5  add     eax, 2
0x1800913b8  mov     [rsp+21E8h+var_2158], rbx
0x1800913c0  movsxd  rcx, eax
0x1800913c3  mov     r15d, 2
0x1800913c9  mov     edx, r15d
0x1800913cc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800913d1  cmp     rax, 100h
0x1800913d7  jbe     short loc_1800913F3
0x1800913d9  mov     rdx, rax
0x1800913dc  lea     rcx, [rsp+21E8h+var_2158]
0x1800913e4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800913e9  mov     rdi, [rsp+21E8h+var_2158]
0x1800913f1  jmp     short loc_180091403
0x1800913f3  lea     rdi, [rsp+21E8h+var_2150]
0x1800913fb  mov     [rsp+21E8h+var_2158], rdi
0x180091403  mov     r13, [rsp+21E8h+var_2198]
0x180091408  jmp     short loc_180091435
0x18009140a  xor     ebx, ebx
0x18009140c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180091410  lea     r15d, [rbx+2]
0x180091414  mov     rdi, [rsp+21E8h+var_2158]
0x18009141c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180091421  mov     rax, [rsp+21E8h+var_2190]
0x180091426  mov     [rsp+21E8h+var_21B0], rax
0x18009142b  mov     rax, [rsp+21E8h+var_2188]
0x180091430  mov     [rsp+21E8h+lpValueName], rax
0x180091435  test    rdi, rdi
0x180091438  jz      loc_1800914F3
0x18009143e  lea     r14, [rsp+21E8h+String1]
0x180091446  cmp     [rsp+21E8h+String1], bx
0x18009144e  jz      short loc_18009148F
0x180091450  mov     r12d, 30h ; '0'
0x180091456  mov     rcx, r14; lpsz
0x180091459  call    cs:__imp_CharNextW
0x18009145f  movzx   ecx, word ptr [r14]
0x180091463  cmp     cx, 5Ch ; '\'
0x180091467  jnz     short loc_180091480
0x180091469  cmp     [rax], r12w
0x18009146d  jnz     short loc_180091480
0x18009146f  mov     [rdi], bx
0x180091472  mov     rcx, rax; lpsz
0x180091475  call    cs:__imp_CharNextW
0x18009147b  mov     r14, rax
0x18009147e  jmp     short loc_180091486
0x180091480  mov     [rdi], cx
0x180091483  add     r14, r15
0x180091486  add     rdi, r15
0x180091489  cmp     [r14], bx
0x18009148d  jnz     short loc_180091456
0x18009148f  mov     dword ptr [rdi], 0
0x180091495  mov     r8, [rsp+21E8h+var_2158]
0x18009149d  test    r8, r8
0x1800914a0  jz      short loc_1800914E8
0x1800914a2  mov     r10d, ebx
0x1800914a5  mov     r9, r8
0x1800914a8  mov     rcx, rsi
0x1800914ab  inc     rcx
0x1800914ae  cmp     [r9+rcx*2], bx
0x1800914b3  jnz     short loc_1800914AB
0x1800914b5  inc     ecx
0x1800914b7  lea     r9, [r9+rcx*2]
0x1800914bb  lea     r10d, [r10+rcx*2]
0x1800914bf  cmp     ecx, 1
0x1800914c2  jnz     short loc_1800914A8
0x1800914c4  mov     [rsp+21E8h+cbData], r10d; cbData
0x1800914c9  mov     [rsp+21E8h+lpData], r8; lpData
0x1800914ce  lea     r9d, [rcx+6]; dwType
0x1800914d2  xor     r8d, r8d; Reserved
0x1800914d5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x1800914da  mov     rcx, [r13+0]; hKey
0x1800914de  call    cs:__imp_RegSetValueExW
0x1800914e4  mov     edi, eax
0x1800914e6  jmp     short loc_1800914F8
0x1800914e8  mov     ecx, 80004005h; int
0x1800914ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800914f3  mov     edi, 0Eh
0x1800914f8  lea     rcx, [rsp+21E8h+var_2158]
0x180091500  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180091505  mov     r15, [rsp+21E8h+var_21B0]
0x18009150a  jmp     loc_1800917CE
0x18009150f  mov     [rsp+21E8h+pulOut], ebx
0x180091513  mov     [rsp+21E8h+var_21B0], rbx
0x180091518  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18009151d  xor     r8d, r8d; dwFlags
0x180091520  xor     edx, edx; lcid
0x180091522  lea     rcx, [rsp+21E8h+String1]; strIn
0x18009152a  call    cs:__imp_VarUI4FromStr
0x180091530  mov     edi, eax
0x180091532  test    eax, eax
0x180091534  jns     short loc_180091547
0x180091536  lea     rcx, [rsp+21E8h+var_21B0]
0x18009153b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180091540  mov     eax, edi
0x180091542  jmp     loc_1800917F9
0x180091547  mov     eax, [rsp+21E8h+pulOut]
0x18009154b  mov     dword ptr [rsp+21E8h+Data], eax
0x18009154f  mov     [rsp+21E8h+cbData], 4; cbData
0x180091557  lea     rax, [rsp+21E8h+Data]
0x18009155c  mov     [rsp+21E8h+lpData], rax; lpData
0x180091561  mov     r9d, 4; dwType
0x180091567  xor     r8d, r8d; Reserved
0x18009156a  mov     rdx, r14; lpValueName
0x18009156d  mov     rcx, [r12]; hKey
0x180091571  call    cs:__imp_RegSetValueExW
0x180091577  mov     edi, eax
0x180091579  lea     rcx, [rsp+21E8h+var_21B0]
0x18009157e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180091583  jmp     loc_1800917CE
0x180091588  lea     rax, [rsp+21E8h+String1]
0x180091590  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180091594  inc     rsi
0x180091597  cmp     [rax+rsi*2], bx
0x18009159b  jnz     short loc_180091594
0x18009159d  mov     dword ptr [rsp+21E8h+Data], esi
0x1800915a1  test    sil, 1
0x1800915a5  jz      short loc_1800915B1
0x1800915a7  mov     eax, 80004005h
0x1800915ac  jmp     loc_1800917F9
0x1800915b1  mov     eax, esi
0x1800915b3  cdq
0x1800915b4  mov     r15d, 2
0x1800915ba  idiv    r15d
0x1800915bd  movsxd  r14, eax
0x1800915c0  mov     [rsp+21E8h+var_2158], rbx
0x1800915c8  mov     rdi, r14
0x1800915cb  mov     [rsp+21E8h+var_2178], r14
0x1800915d0  lea     edx, [r15-1]
0x1800915d4  mov     rcx, r14
0x1800915d7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800915dc  cmp     rax, 100h
0x1800915e2  jbe     short loc_1800915FE
0x1800915e4  mov     rdx, rax
0x1800915e7  lea     rcx, [rsp+21E8h+var_2158]
0x1800915ef  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800915f4  mov     rcx, [rsp+21E8h+var_2158]
0x1800915fc  jmp     short loc_18009160E
0x1800915fe  lea     rcx, [rsp+21E8h+var_2150]
0x180091606  mov     [rsp+21E8h+var_2158], rcx
0x18009160e  mov     r15, [rsp+21E8h+var_2198]
0x180091613  jmp     short loc_180091648
0x180091615  xor     ebx, ebx
0x180091617  lea     r13d, [rbx+8]
0x18009161b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18009161f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180091627  mov     rdi, [rsp+21E8h+var_2178]
0x18009162c  mov     rax, [rsp+21E8h+var_2190]
0x180091631  mov     [rsp+21E8h+var_21B0], rax
0x180091636  mov     r15, [rsp+21E8h+var_2170]
0x18009163b  mov     rax, [rsp+21E8h+var_2188]
0x180091640  mov     [rsp+21E8h+lpValueName], rax
0x180091645  mov     r14d, edi
0x180091648  test    rcx, rcx
0x18009164b  jnz     short loc_18009165F
0x18009164d  lea     rcx, [rsp+21E8h+var_2158]
0x180091655  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18009165a  jmp     loc_1800915A7
0x18009165f  mov     r8, rdi; Size
0x180091662  xor     edx, edx; Val
0x180091664  call    memset_0
0x180091669  mov     r10d, ebx
0x18009166c  test    esi, esi
0x18009166e  jle     loc_18009174C
0x180091674  mov     r12d, 30h ; '0'
0x18009167a  mov     eax, r10d
0x18009167d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180091685  cmp     edx, 61h ; 'a'
0x180091688  ja      short loc_1800916F7
0x18009168a  jz      loc_180091717
0x180091690  cmp     edx, 38h ; '8'
0x180091693  ja      short loc_1800916C9
0x180091695  jz      short loc_1800916C1
0x180091697  mov     ecx, edx
0x180091699  sub     ecx, r12d
0x18009169c  jz      short loc_1800916C1
0x18009169e  sub     ecx, 1
0x1800916a1  jz      short loc_1800916C1
0x1800916a3  sub     ecx, 1
0x1800916a6  jz      short loc_1800916C1
0x1800916a8  sub     ecx, 1
0x1800916ab  jz      short loc_1800916C1
0x1800916ad  sub     ecx, 1
0x1800916b0  jz      short loc_1800916C1
0x1800916b2  sub     ecx, 1
0x1800916b5  jz      short loc_1800916C1
0x1800916b7  sub     ecx, 1
0x1800916ba  jz      short loc_1800916C1
0x1800916bc  cmp     ecx, 1
0x1800916bf  jnz     short loc_180091712
0x1800916c1  mov     r9d, edx
0x1800916c4  sub     r9d, r12d
0x1800916c7  jmp     short loc_18009171B
0x1800916c9  mov     r9d, edx
0x1800916cc  mov     ecx, edx
0x1800916ce  sub     ecx, 39h ; '9'
0x1800916d1  jz      short loc_1800916C1
0x1800916d3  sub     ecx, r13d
0x1800916d6  jz      short loc_1800916F1
0x1800916d8  sub     ecx, 1
0x1800916db  jz      short loc_1800916F1
0x1800916dd  sub     ecx, 1
0x1800916e0  jz      short loc_1800916F1
0x1800916e2  sub     ecx, 1
0x1800916e5  jz      short loc_1800916F1
0x1800916e7  sub     ecx, 1
0x1800916ea  jz      short loc_1800916F1
0x1800916ec  cmp     ecx, 1
0x1800916ef  jnz     short loc_180091712
0x1800916f1  add     r9d, 0FFFFFFC9h
0x1800916f5  jmp     short loc_18009171B
0x1800916f7  mov     ecx, edx
0x1800916f9  sub     ecx, 62h ; 'b'
0x1800916fc  jz      short loc_180091717
0x1800916fe  sub     ecx, 1
0x180091701  jz      short loc_180091717
0x180091703  sub     ecx, 1
0x180091706  jz      short loc_180091717
0x180091708  sub     ecx, 1
0x18009170b  jz      short loc_180091717
0x18009170d  cmp     ecx, 1
0x180091710  jz      short loc_180091717
0x180091712  mov     r9d, ebx
0x180091715  jmp     short loc_18009171B
0x180091717  lea     r9d, [rdx-57h]
0x18009171b  mov     r8d, r10d
0x18009171e  shr     r8, 1
0x180091721  mov     rdx, [rsp+21E8h+var_2158]
0x180091729  mov     eax, r10d
0x18009172c  and     eax, 1
0x18009172f  shl     eax, 2
0x180091732  mov     ecx, 4
0x180091737  sub     ecx, eax
0x180091739  shl     r9b, cl
0x18009173c  or      [r8+rdx], r9b
0x180091740  inc     r10d
  ... truncated ...
```
