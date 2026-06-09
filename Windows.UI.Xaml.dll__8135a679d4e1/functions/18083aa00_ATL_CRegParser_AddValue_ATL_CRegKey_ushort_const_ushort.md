# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18083aa00`
- end: `0x18083aeac`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1196`
- prototype: `HRESULT __fastcall(ATL::CRegParser *this, ATL::CRegKey *rkParent, const wchar_t *szValueName, wchar_t *szToken)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18083d2c8`

## callees

- `0x18076e110`
- `0x18076f0a4`
- `0x180839ef8`
- `0x180839f68`
- `0x180839f98`
- `0x18083aa00`
- `0x18083aeb4`
- `0x18083b9b8`
- `0x18083b9d0`
- `0x18083c928`
- `0x18083e0d0`
- `0x180c010f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18083abe1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18083ac6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18083ae09`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18083ae59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18083abe1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18083ac6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18083ae09`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18083ae59`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083ab59`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083ab75`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083ab59`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18083ab75`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083aa81`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18083aa81`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18083ac26`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18083ac26`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        ATL::CRegKey *rkParent,
        const wchar_t *szValueName,
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::CAtlSafeAllocBufferNode *szToken)
{
  ATL::CRegKey *v4; // r12
  wchar_t *m_pHead; // r15
  ATL::CRegParser *v7; // r14
  HRESULT result; // eax
  unsigned int i; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  unsigned __int8 *m_p; // rbx
  wchar_t *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  unsigned __int8 *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // ebx
  HRESULT v21; // ebx
  HKEY m_hKey; // rcx
  __int64 v23; // rdi
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // rax
  unsigned __int8 *m_abFixedBuffer; // rcx
  int v27; // r10d
  unsigned int v28; // r9d
  char v29; // r9
  unsigned __int64 v30; // r8
  char v31; // r9
  __int64 v32; // rdi
  int Token; // eax
  int v34; // ecx
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator> _AtlSafeAllocaManager; // [rsp+30h] [rbp-D0h] BYREF
  ATL::CRegKey *ulVal; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator> rgBinary; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t szValue[4096]; // [rsp+160h] [rbp+60h] BYREF

  v4 = rkParent;
  ulVal = rkParent;
  _AtlSafeAllocaManager.m_pHead = szToken;
  m_pHead = (wchar_t *)szToken;
  *(_QWORD *)Data = this;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, szValue);
  if ( result < 0 )
    return result;
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
      return -2147352567;
    if ( !lstrcmpiW(szValue, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * (int)i]) )
      break;
  }
  v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * (int)i + 4);
  ATL::CRegParser::SkipWhiteSpace(v7);
  result = ATL::CRegParser::NextToken(v7, szValue);
  if ( result < 0 )
    return result;
  if ( v10 == 8 )
  {
    v32 = -1;
    do
      ++v32;
    while ( szValue[v32] );
    v20 = RegSetValueExW(v4->m_hKey, szValueName, 0, 1u, (const BYTE *)szValue, 2 * v32 + 2);
    goto LABEL_77;
  }
  if ( v10 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( szValue[v23] );
    if ( (v23 & 1) != 0 )
      return -2147467259;
    v24 = (int)v23 / 2;
    rgBinary.m_p = 0;
    v25 = ATL::AtlMultiplyThrow<unsigned __int64>(v24, 1u);
    if ( v25 <= 0x100 )
    {
      m_abFixedBuffer = rgBinary.m_abFixedBuffer;
      rgBinary.m_p = rgBinary.m_abFixedBuffer;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(
        (ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator> *)&rgBinary,
        v25);
      m_abFixedBuffer = rgBinary.m_p;
    }
    if ( !m_abFixedBuffer )
    {
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>((ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator> *)&rgBinary);
      return -2147467259;
    }
    memset_0(m_abFixedBuffer, 0, v24);
    v27 = 0;
    if ( (int)v23 <= 0 )
      goto LABEL_73;
    while ( 1 )
    {
      v28 = szValue[v27];
      if ( v28 > 0x61 )
      {
        if ( v28 == 98 || v28 == 99 || v28 == 100 || v28 - 101 < 2 )
        {
LABEL_70:
          v29 = v28 - 87;
          goto LABEL_71;
        }
LABEL_69:
        v29 = 0;
        goto LABEL_71;
      }
      if ( v28 == 97 )
        goto LABEL_70;
      if ( v28 <= 0x38 )
        break;
      if ( v28 == 57 )
        goto LABEL_57;
      if ( v28 != 65 && v28 != 66 && v28 != 67 && v28 != 68 && v28 - 69 > 1 )
        goto LABEL_69;
      v29 = v28 - 55;
LABEL_71:
      v30 = (unsigned __int64)(unsigned int)v27 >> 1;
      v31 = v29 << (4 - 4 * (v27++ & 1));
      rgBinary.m_p[v30] |= v31;
      if ( v27 >= (int)v23 )
      {
        m_pHead = (wchar_t *)_AtlSafeAllocaManager.m_pHead;
LABEL_73:
        v20 = RegSetValueExW(v4->m_hKey, szValueName, 0, 3u, rgBinary.m_p, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>((ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator> *)&rgBinary);
        v7 = *(ATL::CRegParser **)Data;
LABEL_77:
        if ( v20 )
          return ATL::AtlHresultFromWin32(v20);
LABEL_79:
        Token = ATL::CRegParser::NextToken(v7, m_pHead);
        v34 = 0;
        if ( Token < 0 )
          return Token;
        return v34;
      }
    }
    if ( v28 != 56 && v28 != 48 && v28 != 49 && v28 != 50 && v28 != 51 && v28 != 52 && v28 != 53 && v28 - 54 > 1 )
      goto LABEL_69;
LABEL_57:
    v29 = v28 - 48;
    goto LABEL_71;
  }
  if ( v10 != 19 )
  {
    if ( v10 == 16392 )
    {
      v11 = -1;
      do
        ++v11;
      while ( szValue[v11] );
      rgBinary.m_p = 0;
      v12 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v11 + 2, 2u);
      if ( v12 <= 0x100 )
      {
        m_p = rgBinary.m_abFixedBuffer;
        rgBinary.m_p = rgBinary.m_abFixedBuffer;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(
          (ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator> *)&rgBinary,
          v12);
        m_p = rgBinary.m_p;
      }
      if ( m_p )
      {
        v14 = szValue;
        if ( szValue[0] )
        {
          do
          {
            v15 = CharNextW(v14);
            if ( *v14 == 92 && *v15 == 48 )
            {
              *(_WORD *)m_p = 0;
              v14 = CharNextW(v15);
            }
            else
            {
              *(_WORD *)m_p = *v14++;
            }
            m_p += 2;
          }
          while ( *v14 );
          v4 = ulVal;
          m_pHead = (wchar_t *)_AtlSafeAllocaManager.m_pHead;
        }
        *(_DWORD *)m_p = 0;
        if ( !rgBinary.m_p )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v17 = rgBinary.m_p;
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
        v20 = RegSetValueExW(v4->m_hKey, szValueName, 0, 7u, rgBinary.m_p, cbData);
      }
      else
      {
        v20 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>((ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator> *)&rgBinary);
      v7 = *(ATL::CRegParser **)Data;
      goto LABEL_77;
    }
    goto LABEL_79;
  }
  LODWORD(ulVal) = 0;
  _AtlSafeAllocaManager.m_pHead = 0;
  v21 = VarUI4FromStr(szValue, 0, 0, (ULONG *)&ulVal);
  if ( v21 >= 0 )
  {
    m_hKey = v4->m_hKey;
    *(_DWORD *)Data = (_DWORD)ulVal;
    v20 = RegSetValueExW(m_hKey, szValueName, 0, 4u, Data, 4u);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&_AtlSafeAllocaManager);
    goto LABEL_77;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&_AtlSafeAllocaManager);
  return v21;
}

```

## disassembly

```asm
0x18083aa00  push    rbp
0x18083aa02  push    rbx
0x18083aa03  push    rsi
0x18083aa04  push    rdi
0x18083aa05  push    r12
0x18083aa07  push    r13
0x18083aa09  push    r14
0x18083aa0b  push    r15
0x18083aa0d  lea     rbp, [rsp-2078h]
0x18083aa15  mov     eax, 2178h
0x18083aa1a  call    _alloca_probe
0x18083aa1f  sub     rsp, rax
0x18083aa22  mov     rax, cs:__security_cookie
0x18083aa29  xor     rax, rsp
0x18083aa2c  mov     [rbp+20B0h+var_50], rax
0x18083aa33  mov     r12, rkParent
0x18083aa36  mov     [rsp+21B0h+ulVal], rkParent
0x18083aa3b  lea     rkParent, [rbp+20B0h+szValue]; szToken
0x18083aa3f  mov     [rsp+21B0h+_AtlSafeAllocaManager.m_pHead], szToken
0x18083aa44  mov     r15, szToken
0x18083aa47  mov     qword ptr [rsp+21B0h+Data], this
0x18083aa4c  mov     r13, szValueName
0x18083aa4f  mov     r14, this
0x18083aa52  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083aa57  xor     esi, esi
0x18083aa59  test    eax, eax
0x18083aa5b  js      loc_18083AE89
0x18083aa61  mov     ebx, esi
0x18083aa63  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18083aa6a  cmp     ebx, 4
0x18083aa6d  jnb     loc_18083AE84
0x18083aa73  movsxd  rdi, ebx
0x18083aa76  lea     this, [rbp+20B0h+szValue]; lpString1
0x18083aa7a  add     rdi, rdi
0x18083aa7d  mov     rkParent, [rax+rdi*8]; lpString2
0x18083aa81  call    cs:__imp_lstrcmpiW
0x18083aa87  test    eax, eax
0x18083aa89  jz      short loc_18083AA8F
0x18083aa8b  inc     ebx
0x18083aa8d  jmp     short loc_18083AA63
0x18083aa8f  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18083aa96  mov     this, r14; this
0x18083aa99  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18083aa9e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18083aaa3  lea     rkParent, [rbp+20B0h+szValue]; szToken
0x18083aaa7  mov     this, r14; this
0x18083aaaa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18083aaaf  test    eax, eax
0x18083aab1  js      loc_18083AE89
0x18083aab7  mov     eax, 8
0x18083aabc  cmp     bx, ax
0x18083aabf  jz      loc_18083AE24
0x18083aac5  cmp     bx, 11h
0x18083aac9  jz      loc_18083AC84
0x18083aacf  cmp     bx, 13h
0x18083aad3  jz      loc_18083AC0F
0x18083aad9  mov     eax, 4008h
0x18083aade  cmp     bx, ax
0x18083aae1  jnz     loc_18083AE6E
0x18083aae7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18083aaeb  lea     this, [rbp+20B0h+szValue]
0x18083aaef  mov     rax, rdi
0x18083aaf2  inc     rax
0x18083aaf5  cmp     [this+rax*2], si
0x18083aaf9  jnz     short loc_18083AAF2
0x18083aafb  add     eax, 2
0x18083aafe  mov     [rsp+21B0h+rgBinary.m_p], rsi
0x18083ab03  mov     r14d, 2
0x18083ab09  movsxd  this, eax; tLeft
0x18083ab0c  mov     edx, r14d; tRight
0x18083ab0f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18083ab14  cmp     rax, 100h
0x18083ab1a  jbe     short loc_18083AB30
0x18083ab1c  mov     rkParent, rax; nBytes
0x18083ab1f  lea     this, [rsp+21B0h+rgBinary]; this
0x18083ab24  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18083ab29  mov     rbx, [rsp+21B0h+rgBinary.m_p]
0x18083ab2e  jmp     short loc_18083AB3A
0x18083ab30  lea     rbx, [rsp+21B0h+rgBinary.m_abFixedBuffer]
0x18083ab35  mov     [rsp+21B0h+rgBinary.m_p], rbx
0x18083ab3a  test    rbx, rbx
0x18083ab3d  jz      loc_18083ABF6
0x18083ab43  xor     eax, eax
0x18083ab45  lea     rsi, [rbp+20B0h+szValue]
0x18083ab49  cmp     [rbp+20B0h+szValue], ax
0x18083ab4d  jz      short loc_18083AB99
0x18083ab4f  lea     r15d, [rax+30h]
0x18083ab53  xor     r12d, r12d
0x18083ab56  mov     this, rsi; lpsz
0x18083ab59  call    cs:__imp_CharNextW
0x18083ab5f  movzx   ecx, word ptr [rsi]
0x18083ab62  cmp     cx, 5Ch ; '\'
0x18083ab66  jnz     short loc_18083AB80
0x18083ab68  cmp     [rax], r15w
0x18083ab6c  jnz     short loc_18083AB80
0x18083ab6e  mov     this, rax; lpsz
0x18083ab71  mov     [rbx], r12w
0x18083ab75  call    cs:__imp_CharNextW
0x18083ab7b  mov     rsi, rax
0x18083ab7e  jmp     short loc_18083AB86
0x18083ab80  mov     [rbx], cx
0x18083ab83  add     rsi, r14
0x18083ab86  add     rbx, r14
0x18083ab89  cmp     [rsi], r12w
0x18083ab8d  jnz     short loc_18083AB56
0x18083ab8f  mov     r12, [rsp+21B0h+ulVal]
0x18083ab94  mov     r15, [rsp+21B0h+_AtlSafeAllocaManager.m_pHead]
0x18083ab99  xor     esi, esi
0x18083ab9b  mov     [rbx], esi
0x18083ab9d  mov     szValueName, [rsp+21B0h+rgBinary.m_p]
0x18083aba2  test    szValueName, szValueName
0x18083aba5  jz      short loc_18083ABEB
0x18083aba7  mov     r10d, esi
0x18083abaa  mov     szToken, szValueName
0x18083abad  mov     this, rdi
0x18083abb0  inc     this
0x18083abb3  cmp     [szToken+this*2], si
0x18083abb8  jnz     short loc_18083ABB0
0x18083abba  inc     ecx
0x18083abbc  lea     szToken, [szToken+this*2]
0x18083abc0  lea     r10d, [r10+this*2]
0x18083abc4  cmp     ecx, 1
0x18083abc7  jnz     short loc_18083ABAD
0x18083abc9  mov     [rsp+21B0h+cbData], r10d; cbData
0x18083abce  lea     r9d, [this+6]; dwType
0x18083abd2  mov     this, [r12]; hKey
0x18083abd6  mov     rkParent, r13; lpValueName
0x18083abd9  mov     [rsp+21B0h+lpData], szValueName; lpData
0x18083abde  xor     r8d, r8d; Reserved
0x18083abe1  call    cs:__imp_RegSetValueExW
0x18083abe7  mov     ebx, eax
0x18083abe9  jmp     short loc_18083ABFB
0x18083abeb  mov     ecx, 80004005h; hr
0x18083abf0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18083abf6  mov     ebx, 0Eh
0x18083abfb  lea     this, [rsp+21B0h+rgBinary]; this
0x18083ac00  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18083ac05  mov     r14, qword ptr [rsp+21B0h+Data]
0x18083ac0a  jmp     loc_18083AE61
0x18083ac0f  lea     szToken, [rsp+21B0h+ulVal]; pulOut
0x18083ac14  mov     dword ptr [rsp+21B0h+ulVal], esi
0x18083ac18  xor     r8d, r8d; dwFlags
0x18083ac1b  mov     [rsp+21B0h+_AtlSafeAllocaManager.m_pHead], rsi
0x18083ac20  xor     edx, edx; lcid
0x18083ac22  lea     this, [rbp+20B0h+szValue]; strIn
0x18083ac26  call    cs:__imp_VarUI4FromStr
0x18083ac2c  mov     ebx, eax
0x18083ac2e  test    eax, eax
0x18083ac30  jns     short loc_18083AC43
0x18083ac32  lea     this, [rsp+21B0h+_AtlSafeAllocaManager]; this
0x18083ac37  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18083ac3c  mov     eax, ebx
0x18083ac3e  jmp     loc_18083AE89
0x18083ac43  mov     eax, dword ptr [rsp+21B0h+ulVal]
0x18083ac47  mov     r9d, 4; dwType
0x18083ac4d  mov     this, [r12]; hKey
0x18083ac51  xor     r8d, r8d; Reserved
0x18083ac54  mov     dword ptr [rsp+21B0h+Data], eax
0x18083ac58  mov     rkParent, r13; lpValueName
0x18083ac5b  lea     rax, [rsp+21B0h+Data]
0x18083ac60  mov     [rsp+21B0h+cbData], 4; cbData
0x18083ac68  mov     [rsp+21B0h+lpData], rax; lpData
0x18083ac6d  call    cs:__imp_RegSetValueExW
0x18083ac73  lea     this, [rsp+21B0h+_AtlSafeAllocaManager]; this
0x18083ac78  mov     ebx, eax
0x18083ac7a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18083ac7f  jmp     loc_18083AE61
0x18083ac84  lea     rax, [rbp+20B0h+szValue]
0x18083ac88  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18083ac8c  inc     rdi
0x18083ac8f  cmp     [rax+rdi*2], si
0x18083ac93  jnz     short loc_18083AC8C
0x18083ac95  test    dil, 1
0x18083ac99  jz      short loc_18083ACA5
0x18083ac9b  mov     eax, 80004005h
0x18083aca0  jmp     loc_18083AE89
0x18083aca5  mov     eax, edi
0x18083aca7  mov     r14d, 2
0x18083acad  cdq
0x18083acae  idiv    r14d
0x18083acb1  xor     r14d, r14d
0x18083acb4  movsxd  rsi, eax
0x18083acb7  mov     this, rsi; tLeft
0x18083acba  mov     [rsp+21B0h+rgBinary.m_p], r14
0x18083acbf  lea     edx, [r14+1]; tRight
0x18083acc3  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18083acc8  cmp     rax, 100h
0x18083acce  jbe     short loc_18083ACE4
0x18083acd0  mov     rkParent, rax; nBytes
0x18083acd3  lea     this, [rsp+21B0h+rgBinary]; this
0x18083acd8  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18083acdd  mov     this, [rsp+21B0h+rgBinary.m_p]
0x18083ace2  jmp     short loc_18083ACEE
0x18083ace4  lea     this, [rsp+21B0h+rgBinary.m_abFixedBuffer]; void *
0x18083ace9  mov     [rsp+21B0h+rgBinary.m_p], this
0x18083acee  test    this, this
0x18083acf1  jnz     short loc_18083ACFF
0x18083acf3  lea     this, [rsp+21B0h+rgBinary]; this
0x18083acf8  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18083acfd  jmp     short loc_18083AC9B
0x18083acff  mov     szValueName, rsi; Size
0x18083ad02  xor     edx, edx; Val
0x18083ad04  call    memset_0
0x18083ad09  mov     r10d, r14d
0x18083ad0c  test    edi, edi
0x18083ad0e  jle     loc_18083ADEB
0x18083ad14  mov     r15d, 30h ; '0'
0x18083ad1a  mov     eax, r10d
0x18083ad1d  movzx   r9d, [rbp+rax*2+20B0h+szValue]
0x18083ad23  cmp     r9d, 61h ; 'a'
0x18083ad27  ja      short loc_18083AD93
0x18083ad29  jz      loc_18083ADB4
0x18083ad2f  cmp     r9d, 38h ; '8'
0x18083ad33  ja      short loc_18083AD67
0x18083ad35  jz      short loc_18083AD62
0x18083ad37  mov     ecx, r9d
0x18083ad3a  sub     ecx, r15d
0x18083ad3d  jz      short loc_18083AD62
0x18083ad3f  sub     ecx, 1
0x18083ad42  jz      short loc_18083AD62
0x18083ad44  sub     ecx, 1
0x18083ad47  jz      short loc_18083AD62
0x18083ad49  sub     ecx, 1
0x18083ad4c  jz      short loc_18083AD62
0x18083ad4e  sub     ecx, 1
0x18083ad51  jz      short loc_18083AD62
0x18083ad53  sub     ecx, 1
0x18083ad56  jz      short loc_18083AD62
0x18083ad58  sub     ecx, 1
0x18083ad5b  jz      short loc_18083AD62
0x18083ad5d  cmp     ecx, 1
0x18083ad60  jnz     short loc_18083ADAF
0x18083ad62  sub     r9b, r15b
0x18083ad65  jmp     short loc_18083ADB8
0x18083ad67  mov     ecx, r9d
0x18083ad6a  sub     ecx, 39h ; '9'
0x18083ad6d  jz      short loc_18083AD62
0x18083ad6f  sub     ecx, 8
0x18083ad72  jz      short loc_18083AD8D
0x18083ad74  sub     ecx, 1
0x18083ad77  jz      short loc_18083AD8D
0x18083ad79  sub     ecx, 1
0x18083ad7c  jz      short loc_18083AD8D
0x18083ad7e  sub     ecx, 1
0x18083ad81  jz      short loc_18083AD8D
0x18083ad83  sub     ecx, 1
0x18083ad86  jz      short loc_18083AD8D
0x18083ad88  cmp     ecx, 1
0x18083ad8b  jnz     short loc_18083ADAF
0x18083ad8d  sub     r9b, 37h ; '7'
0x18083ad91  jmp     short loc_18083ADB8
0x18083ad93  mov     ecx, r9d
0x18083ad96  sub     ecx, 62h ; 'b'
0x18083ad99  jz      short loc_18083ADB4
0x18083ad9b  sub     ecx, 1
0x18083ad9e  jz      short loc_18083ADB4
0x18083ada0  sub     ecx, 1
0x18083ada3  jz      short loc_18083ADB4
0x18083ada5  sub     ecx, 1
0x18083ada8  jz      short loc_18083ADB4
0x18083adaa  cmp     ecx, 1
0x18083adad  jz      short loc_18083ADB4
0x18083adaf  mov     r9b, r14b
0x18083adb2  jmp     short loc_18083ADB8
0x18083adb4  sub     r9b, 57h ; 'W'
0x18083adb8  mov     rkParent, [rsp+21B0h+rgBinary.m_p]
0x18083adbd  mov     eax, r10d
0x18083adc0  and     eax, 1
0x18083adc3  mov     r8d, r10d
0x18083adc6  shl     eax, 2
0x18083adc9  mov     ecx, 4
0x18083adce  shr     szValueName, 1
0x18083add1  sub     ecx, eax
0x18083add3  shl     r9b, cl
0x18083add6  inc     r10d
0x18083add9  or      [szValueName+rkParent], r9b
0x18083addd  cmp     r10d, edi
0x18083ade0  jl      loc_18083AD1A
0x18083ade6  mov     r15, [rsp+21B0h+_AtlSafeAllocaManager.m_pHead]
0x18083adeb  mov     rax, [rsp+21B0h+rgBinary.m_p]
0x18083adf0  mov     r9d, 3; dwType
0x18083adf6  mov     this, [r12]; hKey
0x18083adfa  xor     r8d, r8d; Reserved
0x18083adfd  mov     [rsp+21B0h+cbData], esi; cbData
0x18083ae01  mov     rkParent, r13; lpValueName
0x18083ae04  mov     [rsp+21B0h+lpData], rax; lpData
0x18083ae09  call    cs:__imp_RegSetValueExW
0x18083ae0f  lea     this, [rsp+21B0h+rgBinary]; this
0x18083ae14  mov     ebx, eax
0x18083ae16  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18083ae1b  mov     r14, qword ptr [rsp+21B0h+Data]
0x18083ae20  xor     esi, esi
0x18083ae22  jmp     short loc_18083AE61
0x18083ae24  lea     rax, [rbp+20B0h+szValue]
0x18083ae28  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18083ae2c  inc     rdi
0x18083ae2f  cmp     [rax+rdi*2], si
0x18083ae33  jnz     short loc_18083AE2C
0x18083ae35  mov     this, [r12]; hKey
0x18083ae39  lea     eax, ds:2[rdi*2]
  ... truncated ...
```
