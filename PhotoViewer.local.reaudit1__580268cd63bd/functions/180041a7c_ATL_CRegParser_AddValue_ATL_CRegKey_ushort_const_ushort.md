# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180041a7c`
- end: `0x180041f99`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1309`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180043de4`

## callees

- `0x180038944`
- `0x18003f800`
- `0x180040264`
- `0x1800409bc`
- `0x180041118`
- `0x180041a7c`
- `0x180041fa0`
- `0x18004224c`
- `0x180043260`
- `0x180044764`
- `0x180044798`
- `0x180044880`
- `0x18007afa0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180041b11`
- `KERNEL32!lstrcmpiW` at `0x180041b11`
- `ADVAPI32!RegSetValueExW` at `0x180041cb1`
- `ADVAPI32!RegSetValueExW` at `0x180041f1c`
- `ADVAPI32!RegSetValueExW` at `0x180041cb1`
- `ADVAPI32!RegSetValueExW` at `0x180041f1c`
- `USER32!CharNextW` at `0x180041c2e`
- `USER32!CharNextW` at `0x180041c49`
- `USER32!CharNextW` at `0x180041c2e`
- `USER32!CharNextW` at `0x180041c49`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180041cfe`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180041cfe`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180041cc0`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180041cc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        struct ATL::CRegKey *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegKey *v5; // r13
  ATL::CRegParser *v6; // r15
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  unsigned int v11; // r9d
  __int64 v12; // rax
  unsigned __int64 v13; // rax
  BYTE *v14; // rdi
  WCHAR *j; // rsi
  const WCHAR *v16; // rax
  DWORD cbData; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // edi
  HRESULT v22; // edi
  __int64 v23; // r14
  DWORD v24; // esi
  size_t v25; // rdi
  unsigned __int64 v26; // rax
  BYTE *v27; // rcx
  const WCHAR *v28; // r15
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21B8h] BYREF
  LPCWSTR lpValueName; // [rsp+38h] [rbp-21B0h] BYREF
  ATL::CRegParser *v35; // [rsp+40h] [rbp-21A8h]
  struct ATL::CRegKey *v36; // [rsp+48h] [rbp-21A0h]
  ATL::CRegParser *v37; // [rsp+50h] [rbp-2198h]
  const WCHAR *v38; // [rsp+60h] [rbp-2188h]
  size_t v39; // [rsp+70h] [rbp-2178h]
  struct ATL::CRegKey *v40; // [rsp+78h] [rbp-2170h]
  unsigned __int16 *v41; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v43[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v6 = this;
  v35 = this;
  v36 = a2;
  v37 = this;
  v40 = a2;
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
      v21 = ATL::CRegKey::SetStringValue(v5, a3, String1, v11);
      goto LABEL_77;
    case 17:
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      pulOut = v23;
      if ( (v23 & 1) != 0 )
        return 2147500037LL;
      v24 = (int)v23 / 2;
      lpData = 0;
      v25 = (int)v23 / 2;
      v39 = v25;
      try
      {
        v26 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v26 <= 0x100 )
        {
          v27 = v43;
          lpData = v43;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v26);
          v27 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v23) = pulOut;
        v27 = lpData;
        v25 = v39;
        v35 = v37;
        v5 = v40;
        v28 = v38;
        v24 = v39;
        goto LABEL_46;
      }
      v28 = lpValueName;
LABEL_46:
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v27, 0, v25);
      v29 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_75:
        v21 = RegSetValueExW(*(HKEY *)v5, v28, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_33;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_73:
            v31 = v30 - 87;
            goto LABEL_74;
          }
LABEL_72:
          v31 = 0;
          goto LABEL_74;
        }
        if ( v30 == 97 )
          goto LABEL_73;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_60;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_72;
        v31 = v30 - 55;
LABEL_74:
        lpData[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v23 )
          goto LABEL_75;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_72;
LABEL_60:
      v31 = v30 - 48;
      goto LABEL_74;
    case 19:
      pulOut = 0;
      lpValueName = 0;
      v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v22 >= 0 )
      {
        v21 = ATL::CRegKey::SetDWORDValue(v5, a3, pulOut);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&lpValueName);
        goto LABEL_77;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&lpValueName);
      return (unsigned int)v22;
    case 16392:
      v12 = -1;
      do
        ++v12;
      while ( String1[v12] );
      lpData = 0;
      try
      {
        v13 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v13 <= 0x100 )
        {
          v14 = v43;
          lpData = v43;
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
        v5 = v36;
        v35 = v37;
        lpValueName = v38;
      }
      if ( v14 )
      {
        for ( j = String1; *j; v14 += 2 )
        {
          v16 = CharNextW(j);
          if ( *j == 92 && *v16 == 48 )
          {
            *(_WORD *)v14 = 0;
            j = CharNextW(v16);
          }
          else
          {
            *(_WORD *)v14 = *j++;
          }
        }
        *(_DWORD *)v14 = 0;
        if ( !lpData )
        {
          ATL::BaseAtlThrow(-2147467259);
          __debugbreak();
        }
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
        v21 = RegSetValueExW(*(HKEY *)v5, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_33:
      v6 = v35;
LABEL_77:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_79:
        Token = ATL::CRegParser::NextToken(v6, v41);
        if ( Token < 0 )
          return (unsigned int)Token;
        return v8;
      }
    default:
      goto LABEL_79;
  }
}

```

## disassembly

```asm
0x180041a7c  push    rbx
0x180041a7e  push    rsi
0x180041a7f  push    rdi
0x180041a80  push    r12
0x180041a82  push    r13
0x180041a84  push    r14
0x180041a86  push    r15
0x180041a88  mov     eax, 21B0h
0x180041a8d  call    _alloca_probe
0x180041a92  sub     rsp, rax
0x180041a95  mov     rax, cs:__security_cookie
0x180041a9c  xor     rax, rsp
0x180041a9f  mov     [rsp+21E8h+var_48], rax
0x180041aa7  mov     r14, r8
0x180041aaa  mov     [rsp+21E8h+lpValueName], r8
0x180041aaf  mov     r13, rdx
0x180041ab2  mov     r15, rcx
0x180041ab5  mov     [rsp+21E8h+var_21A8], rcx
0x180041aba  mov     [rsp+21E8h+var_21A0], rdx
0x180041abf  mov     [rsp+21E8h+var_2198], rcx
0x180041ac4  mov     [rsp+21E8h+var_2170], rdx
0x180041ac9  mov     [rsp+21E8h+var_2188], r8
0x180041ace  mov     [rsp+21E8h+var_2168], r9
0x180041ad6  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180041ade  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041ae3  xor     ebx, ebx
0x180041ae5  test    eax, eax
0x180041ae7  js      loc_180041F76
0x180041aed  mov     edi, ebx
0x180041aef  lea     r12, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180041af6  cmp     edi, 4
0x180041af9  jnb     loc_180041F71
0x180041aff  movsxd  rsi, edi
0x180041b02  add     rsi, rsi
0x180041b05  mov     rdx, [r12+rsi*8]; lpString2
0x180041b09  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180041b11  call    cs:__imp_lstrcmpiW
0x180041b17  test    eax, eax
0x180041b19  jz      short loc_180041B1F
0x180041b1b  inc     edi
0x180041b1d  jmp     short loc_180041AF6
0x180041b1f  movzx   edi, word ptr [r12+rsi*8+8]
0x180041b25  mov     rcx, r15; this
0x180041b28  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180041b2d  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180041b35  mov     rcx, r15; this
0x180041b38  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041b3d  test    eax, eax
0x180041b3f  js      loc_180041F76
0x180041b45  mov     r12d, 8
0x180041b4b  cmp     di, r12w
0x180041b4f  jz      loc_180041F36
0x180041b55  cmp     di, 11h
0x180041b59  jz      loc_180041D3C
0x180041b5f  cmp     di, 13h
0x180041b63  jz      loc_180041CE3
0x180041b69  mov     eax, 4008h
0x180041b6e  cmp     di, ax
0x180041b71  jnz     loc_180041F58
0x180041b77  lea     rcx, [rsp+21E8h+String1]
0x180041b7f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180041b83  mov     rax, r14
0x180041b86  inc     rax
0x180041b89  cmp     [rcx+rax*2], bx
0x180041b8d  jnz     short loc_180041B86
0x180041b8f  add     eax, 2
0x180041b92  mov     [rsp+21E8h+var_2158], rbx
0x180041b9a  movsxd  rcx, eax
0x180041b9d  mov     r15d, 2
0x180041ba3  mov     edx, r15d
0x180041ba6  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180041bab  cmp     rax, 100h
0x180041bb1  jbe     short loc_180041BCD
0x180041bb3  mov     rdx, rax
0x180041bb6  lea     rcx, [rsp+21E8h+var_2158]
0x180041bbe  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180041bc3  mov     rdi, [rsp+21E8h+var_2158]
0x180041bcb  jmp     short loc_180041BDD
0x180041bcd  lea     rdi, [rsp+21E8h+var_2150]
0x180041bd5  mov     [rsp+21E8h+var_2158], rdi
0x180041bdd  jmp     short loc_180041C0A
0x180041bdf  xor     ebx, ebx
0x180041be1  or      r14, 0FFFFFFFFFFFFFFFFh
0x180041be5  lea     r15d, [rbx+2]
0x180041be9  mov     rdi, [rsp+21E8h+var_2158]
0x180041bf1  mov     r13, [rsp+21E8h+var_21A0]
0x180041bf6  mov     rax, [rsp+21E8h+var_2198]
0x180041bfb  mov     [rsp+21E8h+var_21A8], rax
0x180041c00  mov     rax, [rsp+21E8h+var_2188]
0x180041c05  mov     [rsp+21E8h+lpValueName], rax
0x180041c0a  test    rdi, rdi
0x180041c0d  jz      loc_180041CC7
0x180041c13  lea     rsi, [rsp+21E8h+String1]
0x180041c1b  cmp     [rsp+21E8h+String1], bx
0x180041c23  jz      short loc_180041C62
0x180041c25  mov     r12d, 30h ; '0'
0x180041c2b  mov     rcx, rsi; lpsz
0x180041c2e  call    cs:__imp_CharNextW
0x180041c34  movzx   ecx, word ptr [rsi]
0x180041c37  cmp     cx, 5Ch ; '\'
0x180041c3b  jnz     short loc_180041C54
0x180041c3d  cmp     [rax], r12w
0x180041c41  jnz     short loc_180041C54
0x180041c43  mov     [rdi], bx
0x180041c46  mov     rcx, rax; lpsz
0x180041c49  call    cs:__imp_CharNextW
0x180041c4f  mov     rsi, rax
0x180041c52  jmp     short loc_180041C5A
0x180041c54  mov     [rdi], cx
0x180041c57  add     rsi, r15
0x180041c5a  add     rdi, r15
0x180041c5d  cmp     [rsi], bx
0x180041c60  jnz     short loc_180041C2B
0x180041c62  mov     dword ptr [rdi], 0
0x180041c68  mov     r8, [rsp+21E8h+var_2158]
0x180041c70  test    r8, r8
0x180041c73  jz      short loc_180041CBB
0x180041c75  mov     r10d, ebx
0x180041c78  mov     r9, r8
0x180041c7b  mov     rcx, r14
0x180041c7e  inc     rcx
0x180041c81  cmp     [r9+rcx*2], bx
0x180041c86  jnz     short loc_180041C7E
0x180041c88  inc     ecx
0x180041c8a  lea     r9, [r9+rcx*2]
0x180041c8e  lea     r10d, [r10+rcx*2]
0x180041c92  cmp     ecx, 1
0x180041c95  jnz     short loc_180041C7B
0x180041c97  mov     [rsp+21E8h+cbData], r10d; cbData
0x180041c9c  mov     [rsp+21E8h+lpData], r8; lpData
0x180041ca1  lea     r9d, [rcx+6]; dwType
0x180041ca5  xor     r8d, r8d; Reserved
0x180041ca8  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x180041cad  mov     rcx, [r13+0]; hKey
0x180041cb1  call    cs:__imp_RegSetValueExW
0x180041cb7  mov     edi, eax
0x180041cb9  jmp     short loc_180041CCC
0x180041cbb  mov     ecx, 80004005h
0x180041cc0  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180041cc6  int     3; Trap to Debugger
0x180041cc7  mov     edi, 0Eh
0x180041ccc  lea     rcx, [rsp+21E8h+var_2158]
0x180041cd4  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180041cd9  mov     r15, [rsp+21E8h+var_21A8]
0x180041cde  jmp     loc_180041F4B
0x180041ce3  mov     [rsp+21E8h+pulOut], ebx
0x180041ce7  mov     [rsp+21E8h+lpValueName], rbx
0x180041cec  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x180041cf1  xor     r8d, r8d; dwFlags
0x180041cf4  xor     edx, edx; lcid
0x180041cf6  lea     rcx, [rsp+21E8h+String1]; strIn
0x180041cfe  call    cs:__imp_VarUI4FromStr
0x180041d04  mov     edi, eax
0x180041d06  test    eax, eax
0x180041d08  jns     short loc_180041D1B
0x180041d0a  lea     rcx, [rsp+21E8h+lpValueName]
0x180041d0f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180041d14  mov     eax, edi
0x180041d16  jmp     loc_180041F76
0x180041d1b  mov     r8d, [rsp+21E8h+pulOut]; unsigned int
0x180041d20  mov     rdx, r14; unsigned __int16 *
0x180041d23  mov     rcx, r13; this
0x180041d26  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180041d2b  mov     edi, eax
0x180041d2d  lea     rcx, [rsp+21E8h+lpValueName]
0x180041d32  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180041d37  jmp     loc_180041F4B
0x180041d3c  lea     rax, [rsp+21E8h+String1]
0x180041d44  or      r14, 0FFFFFFFFFFFFFFFFh
0x180041d48  inc     r14
0x180041d4b  cmp     [rax+r14*2], bx
0x180041d50  jnz     short loc_180041D48
0x180041d52  mov     [rsp+21E8h+pulOut], r14d
0x180041d57  test    r14b, 1
0x180041d5b  jz      short loc_180041D67
0x180041d5d  mov     eax, 80004005h
0x180041d62  jmp     loc_180041F76
0x180041d67  mov     eax, r14d
0x180041d6a  cdq
0x180041d6b  mov     r15d, 2
0x180041d71  idiv    r15d
0x180041d74  movsxd  rsi, eax
0x180041d77  mov     [rsp+21E8h+var_2158], rbx
0x180041d7f  mov     rdi, rsi
0x180041d82  mov     [rsp+21E8h+var_2178], rsi
0x180041d87  lea     edx, [r15-1]
0x180041d8b  mov     rcx, rsi
0x180041d8e  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180041d93  cmp     rax, 100h
0x180041d99  jbe     short loc_180041DB5
0x180041d9b  mov     rdx, rax
0x180041d9e  lea     rcx, [rsp+21E8h+var_2158]
0x180041da6  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180041dab  mov     rcx, [rsp+21E8h+var_2158]
0x180041db3  jmp     short loc_180041DC5
0x180041db5  lea     rcx, [rsp+21E8h+var_2150]
0x180041dbd  mov     [rsp+21E8h+var_2158], rcx
0x180041dc5  mov     r15, [rsp+21E8h+lpValueName]
0x180041dca  jmp     short loc_180041DF6
0x180041dcc  xor     ebx, ebx
0x180041dce  mov     r14d, [rsp+21E8h+pulOut]
0x180041dd3  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180041ddb  mov     rdi, [rsp+21E8h+var_2178]
0x180041de0  mov     rax, [rsp+21E8h+var_2198]
0x180041de5  mov     [rsp+21E8h+var_21A8], rax
0x180041dea  mov     r13, [rsp+21E8h+var_2170]
0x180041def  mov     r15, [rsp+21E8h+var_2188]
0x180041df4  mov     esi, edi
0x180041df6  test    rcx, rcx
0x180041df9  jnz     short loc_180041E0D
0x180041dfb  lea     rcx, [rsp+21E8h+var_2158]
0x180041e03  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180041e08  jmp     loc_180041D5D
0x180041e0d  mov     r8, rdi; Size
0x180041e10  xor     edx, edx; Val
0x180041e12  call    memset_0
0x180041e17  mov     r10d, ebx
0x180041e1a  test    r14d, r14d
0x180041e1d  jle     loc_180041EFB
0x180041e23  mov     r12d, 30h ; '0'
0x180041e29  mov     eax, r10d
0x180041e2c  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180041e34  cmp     edx, 61h ; 'a'
0x180041e37  ja      short loc_180041EA6
0x180041e39  jz      loc_180041EC6
0x180041e3f  cmp     edx, 38h ; '8'
0x180041e42  ja      short loc_180041E78
0x180041e44  jz      short loc_180041E70
0x180041e46  mov     ecx, edx
0x180041e48  sub     ecx, r12d
0x180041e4b  jz      short loc_180041E70
0x180041e4d  sub     ecx, 1
0x180041e50  jz      short loc_180041E70
0x180041e52  sub     ecx, 1
0x180041e55  jz      short loc_180041E70
0x180041e57  sub     ecx, 1
0x180041e5a  jz      short loc_180041E70
0x180041e5c  sub     ecx, 1
0x180041e5f  jz      short loc_180041E70
0x180041e61  sub     ecx, 1
0x180041e64  jz      short loc_180041E70
0x180041e66  sub     ecx, 1
0x180041e69  jz      short loc_180041E70
0x180041e6b  cmp     ecx, 1
0x180041e6e  jnz     short loc_180041EC1
0x180041e70  mov     r9d, edx
0x180041e73  sub     r9d, r12d
0x180041e76  jmp     short loc_180041ECA
0x180041e78  mov     r9d, edx
0x180041e7b  mov     ecx, edx
0x180041e7d  sub     ecx, 39h ; '9'
0x180041e80  jz      short loc_180041E70
0x180041e82  sub     ecx, 8
0x180041e85  jz      short loc_180041EA0
0x180041e87  sub     ecx, 1
0x180041e8a  jz      short loc_180041EA0
0x180041e8c  sub     ecx, 1
0x180041e8f  jz      short loc_180041EA0
0x180041e91  sub     ecx, 1
0x180041e94  jz      short loc_180041EA0
0x180041e96  sub     ecx, 1
0x180041e99  jz      short loc_180041EA0
0x180041e9b  cmp     ecx, 1
0x180041e9e  jnz     short loc_180041EC1
0x180041ea0  add     r9d, 0FFFFFFC9h
0x180041ea4  jmp     short loc_180041ECA
0x180041ea6  mov     ecx, edx
0x180041ea8  sub     ecx, 62h ; 'b'
0x180041eab  jz      short loc_180041EC6
0x180041ead  sub     ecx, 1
0x180041eb0  jz      short loc_180041EC6
0x180041eb2  sub     ecx, 1
0x180041eb5  jz      short loc_180041EC6
0x180041eb7  sub     ecx, 1
0x180041eba  jz      short loc_180041EC6
0x180041ebc  cmp     ecx, 1
0x180041ebf  jz      short loc_180041EC6
0x180041ec1  mov     r9d, ebx
0x180041ec4  jmp     short loc_180041ECA
0x180041ec6  lea     r9d, [rdx-57h]
0x180041eca  mov     r8d, r10d
0x180041ecd  shr     r8, 1
0x180041ed0  mov     rdx, [rsp+21E8h+var_2158]
0x180041ed8  mov     eax, r10d
0x180041edb  and     eax, 1
0x180041ede  shl     eax, 2
0x180041ee1  mov     ecx, 4
0x180041ee6  sub     ecx, eax
0x180041ee8  shl     r9b, cl
0x180041eeb  or      [r8+rdx], r9b
0x180041eef  inc     r10d
0x180041ef2  cmp     r10d, r14d
0x180041ef5  jl      loc_180041E29
0x180041efb  mov     rax, [rsp+21E8h+var_2158]
0x180041f03  mov     [rsp+21E8h+cbData], esi; cbData
0x180041f07  mov     [rsp+21E8h+lpData], rax; lpData
0x180041f0c  mov     r9d, 3; dwType
0x180041f12  xor     r8d, r8d; Reserved
0x180041f15  mov     rdx, r15; lpValueName
0x180041f18  mov     rcx, [r13+0]; hKey
  ... truncated ...
```
