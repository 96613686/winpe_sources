# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800185b8`
- end: `0x180018a91`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1241`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18001a0d8`

## callees

- `0x1800147f8`
- `0x180016a40`
- `0x180017408`
- `0x18001803c`
- `0x180018078`
- `0x180018118`
- `0x1800185b8`
- `0x180018a98`
- `0x180018d60`
- `0x1800191d4`
- `0x180019700`
- `0x18001a8a4`
- `0x1800276d0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018757`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018779`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018757`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018779`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800187e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018885`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800189da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018a37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800187e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018885`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800189da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018a37`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180018645`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180018645`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180018838`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180018838`

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
  ULONG pulOut; // [rsp+30h] [rbp-21A8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-21A0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-2198h] BYREF
  ATL::CRegParser *v37; // [rsp+48h] [rbp-2190h]
  const unsigned __int16 *v38; // [rsp+50h] [rbp-2188h]
  size_t v39; // [rsp+60h] [rbp-2178h]
  struct ATL::CRegKey *v40; // [rsp+68h] [rbp-2170h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-2168h]
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v43[264]; // [rsp+88h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v35 = this;
  *(_QWORD *)Data = a2;
  v37 = this;
  v40 = (struct ATL::CRegKey *)a2;
  v38 = a3;
  v41 = a4;
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
        lpData = 0;
        v24 = (int)v22 / 2;
        v39 = v24;
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
          v24 = v39;
          v35 = v37;
          v5 = (HKEY *)v40;
          v4 = v38;
          v23 = v39;
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
          v6 = v35;
          break;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    case 19:
      pulOut = 0;
      v35 = 0;
      v21 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v21 < 0 )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        return (unsigned int)v21;
      }
      *(_DWORD *)Data = pulOut;
      v20 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
      break;
    case 16392:
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
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
        v35 = v37;
        v4 = v38;
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
      Token = ATL::CRegParser::NextToken(v6, v41);
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
0x1800185b8  push    rbx
0x1800185ba  push    rsi
0x1800185bb  push    rdi
0x1800185bc  push    r12
0x1800185be  push    r13
0x1800185c0  push    r14
0x1800185c2  push    r15
0x1800185c4  mov     eax, 21A0h
0x1800185c9  call    _alloca_probe
0x1800185ce  sub     rsp, rax
0x1800185d1  mov     rax, cs:__security_cookie
0x1800185d8  xor     rax, rsp
0x1800185db  mov     [rsp+21D8h+var_48], rax
0x1800185e3  mov     r13, r8
0x1800185e6  mov     r12, rdx
0x1800185e9  mov     r14, rcx
0x1800185ec  mov     [rsp+21D8h+var_21A0], rcx
0x1800185f1  mov     qword ptr [rsp+21D8h+Data], rdx
0x1800185f6  mov     [rsp+21D8h+var_2190], rcx
0x1800185fb  mov     [rsp+21D8h+var_2170], rdx
0x180018600  mov     [rsp+21D8h+var_2188], r8
0x180018605  mov     [rsp+21D8h+var_2168], r9
0x18001860a  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180018612  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180018617  xor     ebx, ebx
0x180018619  test    eax, eax
0x18001861b  js      loc_180018A6D
0x180018621  mov     edi, ebx
0x180018623  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001862a  cmp     edi, 4
0x18001862d  jnb     loc_180018A68
0x180018633  movsxd  rsi, edi
0x180018636  add     rsi, rsi
0x180018639  mov     rdx, [r15+rsi*8]; lpString2
0x18001863d  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180018645  call    cs:__imp_lstrcmpiW
0x18001864c  nop     dword ptr [rax+rax+00h]
0x180018651  test    eax, eax
0x180018653  jz      short loc_180018659
0x180018655  inc     edi
0x180018657  jmp     short loc_18001862A
0x180018659  movzx   edi, word ptr [r15+rsi*8+8]
0x18001865f  mov     rcx, r14; this
0x180018662  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180018667  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x18001866f  mov     rcx, r14; this
0x180018672  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180018677  test    eax, eax
0x180018679  js      loc_180018A6D
0x18001867f  cmp     di, 8
0x180018683  jz      loc_1800189FA
0x180018689  cmp     di, 11h
0x18001868d  jz      loc_1800188A2
0x180018693  cmp     di, 13h
0x180018697  jz      loc_18001881D
0x18001869d  mov     eax, 4008h
0x1800186a2  cmp     di, ax
0x1800186a5  jnz     loc_180018A52
0x1800186ab  lea     rcx, [rsp+21D8h+String1]
0x1800186b3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800186b7  mov     rax, rdi
0x1800186ba  inc     rax
0x1800186bd  cmp     [rcx+rax*2], bx
0x1800186c1  jnz     short loc_1800186BA
0x1800186c3  add     eax, 2
0x1800186c6  mov     [rsp+21D8h+var_2158], rbx
0x1800186ce  movsxd  rcx, eax
0x1800186d1  mov     r15d, 2
0x1800186d7  mov     edx, r15d
0x1800186da  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800186df  cmp     rax, 100h
0x1800186e5  jbe     short loc_180018701
0x1800186e7  mov     rdx, rax
0x1800186ea  lea     rcx, [rsp+21D8h+var_2158]
0x1800186f2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800186f7  mov     rsi, [rsp+21D8h+var_2158]
0x1800186ff  jmp     short loc_180018711
0x180018701  lea     rsi, [rsp+21D8h+var_2150]
0x180018709  mov     [rsp+21D8h+var_2158], rsi
0x180018711  jmp     short loc_180018739
0x180018713  xor     ebx, ebx
0x180018715  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018719  lea     r15d, [rbx+2]
0x18001871d  mov     rsi, [rsp+21D8h+var_2158]
0x180018725  mov     r12, qword ptr [rsp+21D8h+Data]
0x18001872a  mov     rax, [rsp+21D8h+var_2190]
0x18001872f  mov     [rsp+21D8h+var_21A0], rax
0x180018734  mov     r13, [rsp+21D8h+var_2188]
0x180018739  test    rsi, rsi
0x18001873c  jz      loc_180018801
0x180018742  lea     r14, [rsp+21D8h+String1]
0x18001874a  cmp     [rsp+21D8h+String1], bx
0x180018752  jz      short loc_180018799
0x180018754  mov     rcx, r14; lpsz
0x180018757  call    cs:__imp_CharNextW
0x18001875e  nop     dword ptr [rax+rax+00h]
0x180018763  movzx   ecx, word ptr [r14]
0x180018767  cmp     cx, 5Ch ; '\'
0x18001876b  jnz     short loc_18001878A
0x18001876d  cmp     word ptr [rax], 30h ; '0'
0x180018771  jnz     short loc_18001878A
0x180018773  mov     [rsi], bx
0x180018776  mov     rcx, rax; lpsz
0x180018779  call    cs:__imp_CharNextW
0x180018780  nop     dword ptr [rax+rax+00h]
0x180018785  mov     r14, rax
0x180018788  jmp     short loc_180018790
0x18001878a  mov     [rsi], cx
0x18001878d  add     r14, r15
0x180018790  add     rsi, r15
0x180018793  cmp     [r14], bx
0x180018797  jnz     short loc_180018754
0x180018799  mov     dword ptr [rsi], 0
0x18001879f  mov     r8, [rsp+21D8h+var_2158]
0x1800187a7  test    r8, r8
0x1800187aa  jz      short loc_1800187F6
0x1800187ac  mov     r10d, ebx
0x1800187af  mov     r9, r8
0x1800187b2  mov     rcx, rdi
0x1800187b5  inc     rcx
0x1800187b8  cmp     [r9+rcx*2], bx
0x1800187bd  jnz     short loc_1800187B5
0x1800187bf  inc     ecx
0x1800187c1  lea     r9, [r9+rcx*2]
0x1800187c5  lea     r10d, [r10+rcx*2]
0x1800187c9  cmp     ecx, 1
0x1800187cc  jnz     short loc_1800187B2
0x1800187ce  mov     [rsp+21D8h+cbData], r10d; cbData
0x1800187d3  mov     [rsp+21D8h+lpData], r8; lpData
0x1800187d8  lea     r9d, [rcx+6]; dwType
0x1800187dc  xor     r8d, r8d; Reserved
0x1800187df  mov     rdx, r13; lpValueName
0x1800187e2  mov     rcx, [r12]; hKey
0x1800187e6  call    cs:__imp_RegSetValueExW
0x1800187ed  nop     dword ptr [rax+rax+00h]
0x1800187f2  mov     edi, eax
0x1800187f4  jmp     short loc_180018806
0x1800187f6  mov     ecx, 80004005h; int
0x1800187fb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018801  mov     edi, 0Eh
0x180018806  lea     rcx, [rsp+21D8h+var_2158]
0x18001880e  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180018813  mov     r14, [rsp+21D8h+var_21A0]
0x180018818  jmp     loc_180018A45
0x18001881d  mov     [rsp+21D8h+pulOut], ebx
0x180018821  mov     [rsp+21D8h+var_21A0], rbx
0x180018826  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x18001882b  xor     r8d, r8d; dwFlags
0x18001882e  xor     edx, edx; lcid
0x180018830  lea     rcx, [rsp+21D8h+String1]; strIn
0x180018838  call    cs:__imp_VarUI4FromStr
0x18001883f  nop     dword ptr [rax+rax+00h]
0x180018844  mov     edi, eax
0x180018846  test    eax, eax
0x180018848  jns     short loc_18001885B
0x18001884a  lea     rcx, [rsp+21D8h+var_21A0]
0x18001884f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180018854  mov     eax, edi
0x180018856  jmp     loc_180018A6D
0x18001885b  mov     eax, [rsp+21D8h+pulOut]
0x18001885f  mov     dword ptr [rsp+21D8h+Data], eax
0x180018863  mov     [rsp+21D8h+cbData], 4; cbData
0x18001886b  lea     rax, [rsp+21D8h+Data]
0x180018870  mov     [rsp+21D8h+lpData], rax; lpData
0x180018875  mov     r9d, 4; dwType
0x18001887b  xor     r8d, r8d; Reserved
0x18001887e  mov     rdx, r13; lpValueName
0x180018881  mov     rcx, [r12]; hKey
0x180018885  call    cs:__imp_RegSetValueExW
0x18001888c  nop     dword ptr [rax+rax+00h]
0x180018891  mov     edi, eax
0x180018893  lea     rcx, [rsp+21D8h+var_21A0]
0x180018898  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001889d  jmp     loc_180018A45
0x1800188a2  lea     rax, [rsp+21D8h+String1]
0x1800188aa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800188ae  inc     rdi
0x1800188b1  cmp     [rax+rdi*2], bx
0x1800188b5  jnz     short loc_1800188AE
0x1800188b7  mov     dword ptr [rsp+21D8h+Data], edi
0x1800188bb  test    dil, 1
0x1800188bf  jz      short loc_1800188CB
0x1800188c1  mov     eax, 80004005h
0x1800188c6  jmp     loc_180018A6D
0x1800188cb  mov     eax, edi
0x1800188cd  cdq
0x1800188ce  mov     r15d, 2
0x1800188d4  idiv    r15d
0x1800188d7  movsxd  r14, eax
0x1800188da  mov     [rsp+21D8h+var_2158], rbx
0x1800188e2  mov     rsi, r14
0x1800188e5  mov     [rsp+21D8h+var_2178], r14
0x1800188ea  lea     edx, [r15-1]
0x1800188ee  mov     rcx, r14
0x1800188f1  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800188f6  cmp     rax, 100h
0x1800188fc  jbe     short loc_180018918
0x1800188fe  mov     rdx, rax
0x180018901  lea     rcx, [rsp+21D8h+var_2158]
0x180018909  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001890e  mov     rcx, [rsp+21D8h+var_2158]
0x180018916  jmp     short loc_180018928
0x180018918  lea     rcx, [rsp+21D8h+var_2150]
0x180018920  mov     [rsp+21D8h+var_2158], rcx
0x180018928  jmp     short loc_180018954
0x18001892a  xor     ebx, ebx
0x18001892c  mov     edi, dword ptr [rsp+21D8h+Data]
0x180018930  mov     rcx, [rsp+21D8h+var_2158]; void *
0x180018938  mov     rsi, [rsp+21D8h+var_2178]
0x18001893d  mov     rax, [rsp+21D8h+var_2190]
0x180018942  mov     [rsp+21D8h+var_21A0], rax
0x180018947  mov     r12, [rsp+21D8h+var_2170]
0x18001894c  mov     r13, [rsp+21D8h+var_2188]
0x180018951  mov     r14d, esi
0x180018954  test    rcx, rcx
0x180018957  jnz     short loc_18001896B
0x180018959  lea     rcx, [rsp+21D8h+var_2158]
0x180018961  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180018966  jmp     loc_1800188C1
0x18001896b  mov     r8, rsi; Size
0x18001896e  xor     edx, edx; Val
0x180018970  call    memset_0
0x180018975  mov     r10d, ebx
0x180018978  test    edi, edi
0x18001897a  jle     short loc_1800189B8
0x18001897c  mov     r9d, r10d
0x18001897f  shr     r9, 1
0x180018982  mov     r8, [rsp+21D8h+var_2158]
0x18001898a  mov     ecx, r10d
0x18001898d  movzx   ecx, [rsp+rcx*2+21D8h+String1]; unsigned __int16
0x180018995  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18001899a  mov     edx, r10d
0x18001899d  and     edx, 1
0x1800189a0  shl     edx, 2
0x1800189a3  mov     ecx, 4
0x1800189a8  sub     ecx, edx
0x1800189aa  shl     al, cl
0x1800189ac  or      [r9+r8], al
0x1800189b0  inc     r10d
0x1800189b3  cmp     r10d, edi
0x1800189b6  jl      short loc_18001897C
0x1800189b8  mov     rax, [rsp+21D8h+var_2158]
0x1800189c0  mov     [rsp+21D8h+cbData], r14d; cbData
0x1800189c5  mov     [rsp+21D8h+lpData], rax; lpData
0x1800189ca  mov     r9d, 3; dwType
0x1800189d0  xor     r8d, r8d; Reserved
0x1800189d3  mov     rdx, r13; lpValueName
0x1800189d6  mov     rcx, [r12]; hKey
0x1800189da  call    cs:__imp_RegSetValueExW
0x1800189e1  nop     dword ptr [rax+rax+00h]
0x1800189e6  mov     edi, eax
0x1800189e8  lea     rcx, [rsp+21D8h+var_2158]
0x1800189f0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800189f5  jmp     loc_180018813
0x1800189fa  lea     rax, [rsp+21D8h+String1]
0x180018a02  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018a06  inc     rdi
0x180018a09  cmp     [rax+rdi*2], bx
0x180018a0d  jnz     short loc_180018A06
0x180018a0f  lea     eax, ds:2[rdi*2]
0x180018a16  mov     [rsp+21D8h+cbData], eax; cbData
0x180018a1a  lea     rax, [rsp+21D8h+String1]
0x180018a22  mov     [rsp+21D8h+lpData], rax; lpData
0x180018a27  mov     r9d, 1; dwType
0x180018a2d  xor     r8d, r8d; Reserved
0x180018a30  mov     rdx, r13; lpValueName
0x180018a33  mov     rcx, [r12]; hKey
0x180018a37  call    cs:__imp_RegSetValueExW
0x180018a3e  nop     dword ptr [rax+rax+00h]
0x180018a43  mov     edi, eax
0x180018a45  test    edi, edi
0x180018a47  jz      short loc_180018A52
0x180018a49  mov     ecx, edi; unsigned int
0x180018a4b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180018a50  jmp     short loc_180018A6D
0x180018a52  mov     rdx, [rsp+21D8h+var_2168]; unsigned __int16 *
0x180018a57  mov     rcx, r14; this
0x180018a5a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180018a5f  test    eax, eax
0x180018a61  cmovs   ebx, eax
0x180018a64  mov     eax, ebx
0x180018a66  jmp     short loc_180018A6D
0x180018a68  mov     eax, 80020009h
0x180018a6d  mov     rcx, [rsp+21D8h+var_48]
0x180018a75  xor     rcx, rsp; StackCookie
0x180018a78  call    __security_check_cookie
0x180018a7d  add     rsp, 21A0h
0x180018a84  pop     r15
0x180018a86  pop     r14
0x180018a88  pop     r13
0x180018a8a  pop     r12
0x180018a8c  pop     rdi
0x180018a8d  pop     rsi
0x180018a8e  pop     rbx
0x180018a8f  retn
```
