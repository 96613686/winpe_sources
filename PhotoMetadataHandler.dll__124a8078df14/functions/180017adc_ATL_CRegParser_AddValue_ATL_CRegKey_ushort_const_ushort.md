# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180017adc`
- end: `0x18001805c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180019528`

## callees

- `0x180013e34`
- `0x180016020`
- `0x1800169b8`
- `0x180017584`
- `0x1800175c0`
- `0x180017654`
- `0x180017adc`
- `0x180018064`
- `0x180018324`
- `0x180018bfc`
- `0x180019cb8`
- `0x180026420`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017c99`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017cb5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017c99`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017cb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017d1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017db1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017faf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018006`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017d1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017db1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017faf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018006`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017b77`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017b77`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180017d6a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180017d6a`

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
  size_t v12; // rax
  BYTE *v13; // rdi
  HKEY *v14; // r13
  WCHAR *j; // r14
  const WCHAR *v16; // rax
  DWORD cbData; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // edi
  HRESULT v22; // edi
  __int64 v23; // rsi
  DWORD v24; // r14d
  size_t v25; // rdi
  size_t v26; // rax
  BYTE *v27; // rcx
  HKEY *v28; // r15
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  __int64 v32; // rsi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21B8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-21B0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-21A8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-21A0h]
  HKEY *v38; // [rsp+50h] [rbp-2198h]
  ATL::CRegParser *v39; // [rsp+58h] [rbp-2190h]
  const WCHAR *v40; // [rsp+60h] [rbp-2188h]
  size_t v41; // [rsp+70h] [rbp-2178h]
  HKEY *v42; // [rsp+78h] [rbp-2170h]
  unsigned __int16 *v43; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v38 = a2;
  v6 = this;
  v35 = this;
  *(_QWORD *)Data = a2;
  v39 = this;
  v42 = a2;
  v40 = a3;
  v43 = a4;
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
      v21 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
      goto LABEL_80;
    case 17:
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      *(_DWORD *)Data = v23;
      if ( (v23 & 1) != 0 )
        return 2147500037LL;
      v24 = (int)v23 / 2;
      lpData = 0;
      v25 = (int)v23 / 2;
      v41 = v25;
      try
      {
        v26 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v26 <= 0x100 )
        {
          v27 = v45;
          lpData = v45;
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
        LODWORD(v23) = *(_DWORD *)Data;
        v27 = lpData;
        v25 = v41;
        v35 = v39;
        v28 = v42;
        lpValueName = v40;
        v24 = v41;
        goto LABEL_47;
      }
      v28 = v38;
LABEL_47:
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v27, 0, v25);
      v29 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_76:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_34;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_74:
            v31 = v30 - 87;
            goto LABEL_75;
          }
LABEL_73:
          v31 = 0;
          goto LABEL_75;
        }
        if ( v30 == 97 )
          goto LABEL_74;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_61;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_73;
        v31 = v30 - 55;
LABEL_75:
        lpData[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v23 )
          goto LABEL_76;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_73;
LABEL_61:
      v31 = v30 - 48;
      goto LABEL_75;
    case 19:
      pulOut = 0;
      v35 = 0;
      v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v22 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v21 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
      return (unsigned int)v22;
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
          v13 = v45;
          lpData = v45;
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
        v14 = *(HKEY **)Data;
        v35 = v39;
        lpValueName = v40;
        goto LABEL_18;
      }
      v14 = v38;
LABEL_18:
      if ( v13 )
      {
        for ( j = String1; *j; v13 += 2 )
        {
          v16 = CharNextW(j);
          if ( *j == 92 && *v16 == 48 )
          {
            *(_WORD *)v13 = 0;
            j = CharNextW(v16);
          }
          else
          {
            *(_WORD *)v13 = *j++;
          }
        }
        *(_DWORD *)v13 = 0;
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
        v21 = RegSetValueExW(*v14, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_34:
      v6 = v35;
LABEL_80:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v43);
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
0x180017adc  push    rbx
0x180017ade  push    rsi
0x180017adf  push    rdi
0x180017ae0  push    r12
0x180017ae2  push    r13
0x180017ae4  push    r14
0x180017ae6  push    r15
0x180017ae8  mov     eax, 21B0h
0x180017aed  call    _alloca_probe
0x180017af2  sub     rsp, rax
0x180017af5  mov     rax, cs:__security_cookie
0x180017afc  xor     rax, rsp
0x180017aff  mov     [rsp+21E8h+var_48], rax
0x180017b07  mov     r14, r8
0x180017b0a  mov     [rsp+21E8h+lpValueName], r8
0x180017b0f  mov     r12, rdx
0x180017b12  mov     [rsp+21E8h+var_2198], rdx
0x180017b17  mov     r15, rcx
0x180017b1a  mov     [rsp+21E8h+var_21B0], rcx
0x180017b1f  mov     qword ptr [rsp+21E8h+Data], rdx
0x180017b24  mov     [rsp+21E8h+var_2190], rcx
0x180017b29  mov     [rsp+21E8h+var_2170], rdx
0x180017b2e  mov     [rsp+21E8h+var_2188], r8
0x180017b33  mov     [rsp+21E8h+var_2168], r9
0x180017b3b  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180017b43  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180017b48  xor     ebx, ebx
0x180017b4a  test    eax, eax
0x180017b4c  js      loc_180018039
0x180017b52  mov     edi, ebx
0x180017b54  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180017b5b  cmp     edi, 4
0x180017b5e  jnb     loc_180018034
0x180017b64  movsxd  rsi, edi
0x180017b67  add     rsi, rsi
0x180017b6a  mov     rdx, [r13+rsi*8+0]; lpString2
0x180017b6f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180017b77  call    cs:__imp_lstrcmpiW
0x180017b7d  test    eax, eax
0x180017b7f  jz      short loc_180017B85
0x180017b81  inc     edi
0x180017b83  jmp     short loc_180017B5B
0x180017b85  movzx   edi, word ptr [r13+rsi*8+8]
0x180017b8b  mov     rcx, r15; this
0x180017b8e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180017b93  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180017b9b  mov     rcx, r15; this
0x180017b9e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180017ba3  test    eax, eax
0x180017ba5  js      loc_180018039
0x180017bab  mov     r13d, 8
0x180017bb1  cmp     di, r13w
0x180017bb5  jz      loc_180017FC9
0x180017bbb  cmp     di, 11h
0x180017bbf  jz      loc_180017DC8
0x180017bc5  cmp     di, 13h
0x180017bc9  jz      loc_180017D4F
0x180017bcf  mov     eax, 4008h
0x180017bd4  cmp     di, ax
0x180017bd7  jnz     loc_18001801B
0x180017bdd  lea     rcx, [rsp+21E8h+String1]
0x180017be5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017be9  mov     rax, rsi
0x180017bec  inc     rax
0x180017bef  cmp     [rcx+rax*2], bx
0x180017bf3  jnz     short loc_180017BEC
0x180017bf5  add     eax, 2
0x180017bf8  mov     [rsp+21E8h+var_2158], rbx
0x180017c00  movsxd  rcx, eax
0x180017c03  mov     r15d, 2
0x180017c09  mov     edx, r15d
0x180017c0c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180017c11  cmp     rax, 100h
0x180017c17  jbe     short loc_180017C33
0x180017c19  mov     rdx, rax
0x180017c1c  lea     rcx, [rsp+21E8h+var_2158]
0x180017c24  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180017c29  mov     rdi, [rsp+21E8h+var_2158]
0x180017c31  jmp     short loc_180017C43
0x180017c33  lea     rdi, [rsp+21E8h+var_2150]
0x180017c3b  mov     [rsp+21E8h+var_2158], rdi
0x180017c43  mov     r13, [rsp+21E8h+var_2198]
0x180017c48  jmp     short loc_180017C75
0x180017c4a  xor     ebx, ebx
0x180017c4c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017c50  lea     r15d, [rbx+2]
0x180017c54  mov     rdi, [rsp+21E8h+var_2158]
0x180017c5c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180017c61  mov     rax, [rsp+21E8h+var_2190]
0x180017c66  mov     [rsp+21E8h+var_21B0], rax
0x180017c6b  mov     rax, [rsp+21E8h+var_2188]
0x180017c70  mov     [rsp+21E8h+lpValueName], rax
0x180017c75  test    rdi, rdi
0x180017c78  jz      loc_180017D33
0x180017c7e  lea     r14, [rsp+21E8h+String1]
0x180017c86  cmp     [rsp+21E8h+String1], bx
0x180017c8e  jz      short loc_180017CCF
0x180017c90  mov     r12d, 30h ; '0'
0x180017c96  mov     rcx, r14; lpsz
0x180017c99  call    cs:__imp_CharNextW
0x180017c9f  movzx   ecx, word ptr [r14]
0x180017ca3  cmp     cx, 5Ch ; '\'
0x180017ca7  jnz     short loc_180017CC0
0x180017ca9  cmp     [rax], r12w
0x180017cad  jnz     short loc_180017CC0
0x180017caf  mov     [rdi], bx
0x180017cb2  mov     rcx, rax; lpsz
0x180017cb5  call    cs:__imp_CharNextW
0x180017cbb  mov     r14, rax
0x180017cbe  jmp     short loc_180017CC6
0x180017cc0  mov     [rdi], cx
0x180017cc3  add     r14, r15
0x180017cc6  add     rdi, r15
0x180017cc9  cmp     [r14], bx
0x180017ccd  jnz     short loc_180017C96
0x180017ccf  mov     dword ptr [rdi], 0
0x180017cd5  mov     r8, [rsp+21E8h+var_2158]
0x180017cdd  test    r8, r8
0x180017ce0  jz      short loc_180017D28
0x180017ce2  mov     r10d, ebx
0x180017ce5  mov     r9, r8
0x180017ce8  mov     rcx, rsi
0x180017ceb  inc     rcx
0x180017cee  cmp     [r9+rcx*2], bx
0x180017cf3  jnz     short loc_180017CEB
0x180017cf5  inc     ecx
0x180017cf7  lea     r9, [r9+rcx*2]
0x180017cfb  lea     r10d, [r10+rcx*2]
0x180017cff  cmp     ecx, 1
0x180017d02  jnz     short loc_180017CE8
0x180017d04  mov     [rsp+21E8h+cbData], r10d; cbData
0x180017d09  mov     [rsp+21E8h+lpData], r8; lpData
0x180017d0e  lea     r9d, [rcx+6]; dwType
0x180017d12  xor     r8d, r8d; Reserved
0x180017d15  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x180017d1a  mov     rcx, [r13+0]; hKey
0x180017d1e  call    cs:__imp_RegSetValueExW
0x180017d24  mov     edi, eax
0x180017d26  jmp     short loc_180017D38
0x180017d28  mov     ecx, 80004005h; int
0x180017d2d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017d33  mov     edi, 0Eh
0x180017d38  lea     rcx, [rsp+21E8h+var_2158]
0x180017d40  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180017d45  mov     r15, [rsp+21E8h+var_21B0]
0x180017d4a  jmp     loc_18001800E
0x180017d4f  mov     [rsp+21E8h+pulOut], ebx
0x180017d53  mov     [rsp+21E8h+var_21B0], rbx
0x180017d58  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x180017d5d  xor     r8d, r8d; dwFlags
0x180017d60  xor     edx, edx; lcid
0x180017d62  lea     rcx, [rsp+21E8h+String1]; strIn
0x180017d6a  call    cs:__imp_VarUI4FromStr
0x180017d70  mov     edi, eax
0x180017d72  test    eax, eax
0x180017d74  jns     short loc_180017D87
0x180017d76  lea     rcx, [rsp+21E8h+var_21B0]
0x180017d7b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017d80  mov     eax, edi
0x180017d82  jmp     loc_180018039
0x180017d87  mov     eax, [rsp+21E8h+pulOut]
0x180017d8b  mov     dword ptr [rsp+21E8h+Data], eax
0x180017d8f  mov     [rsp+21E8h+cbData], 4; cbData
0x180017d97  lea     rax, [rsp+21E8h+Data]
0x180017d9c  mov     [rsp+21E8h+lpData], rax; lpData
0x180017da1  mov     r9d, 4; dwType
0x180017da7  xor     r8d, r8d; Reserved
0x180017daa  mov     rdx, r14; lpValueName
0x180017dad  mov     rcx, [r12]; hKey
0x180017db1  call    cs:__imp_RegSetValueExW
0x180017db7  mov     edi, eax
0x180017db9  lea     rcx, [rsp+21E8h+var_21B0]
0x180017dbe  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017dc3  jmp     loc_18001800E
0x180017dc8  lea     rax, [rsp+21E8h+String1]
0x180017dd0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017dd4  inc     rsi
0x180017dd7  cmp     [rax+rsi*2], bx
0x180017ddb  jnz     short loc_180017DD4
0x180017ddd  mov     dword ptr [rsp+21E8h+Data], esi
0x180017de1  test    sil, 1
0x180017de5  jz      short loc_180017DF1
0x180017de7  mov     eax, 80004005h
0x180017dec  jmp     loc_180018039
0x180017df1  mov     eax, esi
0x180017df3  cdq
0x180017df4  mov     r15d, 2
0x180017dfa  idiv    r15d
0x180017dfd  movsxd  r14, eax
0x180017e00  mov     [rsp+21E8h+var_2158], rbx
0x180017e08  mov     rdi, r14
0x180017e0b  mov     [rsp+21E8h+var_2178], r14
0x180017e10  lea     edx, [r15-1]
0x180017e14  mov     rcx, r14
0x180017e17  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180017e1c  cmp     rax, 100h
0x180017e22  jbe     short loc_180017E3E
0x180017e24  mov     rdx, rax
0x180017e27  lea     rcx, [rsp+21E8h+var_2158]
0x180017e2f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180017e34  mov     rcx, [rsp+21E8h+var_2158]
0x180017e3c  jmp     short loc_180017E4E
0x180017e3e  lea     rcx, [rsp+21E8h+var_2150]
0x180017e46  mov     [rsp+21E8h+var_2158], rcx
0x180017e4e  mov     r15, [rsp+21E8h+var_2198]
0x180017e53  jmp     short loc_180017E88
0x180017e55  xor     ebx, ebx
0x180017e57  lea     r13d, [rbx+8]
0x180017e5b  mov     esi, dword ptr [rsp+21E8h+Data]
0x180017e5f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180017e67  mov     rdi, [rsp+21E8h+var_2178]
0x180017e6c  mov     rax, [rsp+21E8h+var_2190]
0x180017e71  mov     [rsp+21E8h+var_21B0], rax
0x180017e76  mov     r15, [rsp+21E8h+var_2170]
0x180017e7b  mov     rax, [rsp+21E8h+var_2188]
0x180017e80  mov     [rsp+21E8h+lpValueName], rax
0x180017e85  mov     r14d, edi
0x180017e88  test    rcx, rcx
0x180017e8b  jnz     short loc_180017E9F
0x180017e8d  lea     rcx, [rsp+21E8h+var_2158]
0x180017e95  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180017e9a  jmp     loc_180017DE7
0x180017e9f  mov     r8, rdi; Size
0x180017ea2  xor     edx, edx; Val
0x180017ea4  call    memset_0
0x180017ea9  mov     r10d, ebx
0x180017eac  test    esi, esi
0x180017eae  jle     loc_180017F8C
0x180017eb4  mov     r12d, 30h ; '0'
0x180017eba  mov     eax, r10d
0x180017ebd  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180017ec5  cmp     edx, 61h ; 'a'
0x180017ec8  ja      short loc_180017F37
0x180017eca  jz      loc_180017F57
0x180017ed0  cmp     edx, 38h ; '8'
0x180017ed3  ja      short loc_180017F09
0x180017ed5  jz      short loc_180017F01
0x180017ed7  mov     ecx, edx
0x180017ed9  sub     ecx, r12d
0x180017edc  jz      short loc_180017F01
0x180017ede  sub     ecx, 1
0x180017ee1  jz      short loc_180017F01
0x180017ee3  sub     ecx, 1
0x180017ee6  jz      short loc_180017F01
0x180017ee8  sub     ecx, 1
0x180017eeb  jz      short loc_180017F01
0x180017eed  sub     ecx, 1
0x180017ef0  jz      short loc_180017F01
0x180017ef2  sub     ecx, 1
0x180017ef5  jz      short loc_180017F01
0x180017ef7  sub     ecx, 1
0x180017efa  jz      short loc_180017F01
0x180017efc  cmp     ecx, 1
0x180017eff  jnz     short loc_180017F52
0x180017f01  mov     r9d, edx
0x180017f04  sub     r9d, r12d
0x180017f07  jmp     short loc_180017F5B
0x180017f09  mov     r9d, edx
0x180017f0c  mov     ecx, edx
0x180017f0e  sub     ecx, 39h ; '9'
0x180017f11  jz      short loc_180017F01
0x180017f13  sub     ecx, r13d
0x180017f16  jz      short loc_180017F31
0x180017f18  sub     ecx, 1
0x180017f1b  jz      short loc_180017F31
0x180017f1d  sub     ecx, 1
0x180017f20  jz      short loc_180017F31
0x180017f22  sub     ecx, 1
0x180017f25  jz      short loc_180017F31
0x180017f27  sub     ecx, 1
0x180017f2a  jz      short loc_180017F31
0x180017f2c  cmp     ecx, 1
0x180017f2f  jnz     short loc_180017F52
0x180017f31  add     r9d, 0FFFFFFC9h
0x180017f35  jmp     short loc_180017F5B
0x180017f37  mov     ecx, edx
0x180017f39  sub     ecx, 62h ; 'b'
0x180017f3c  jz      short loc_180017F57
0x180017f3e  sub     ecx, 1
0x180017f41  jz      short loc_180017F57
0x180017f43  sub     ecx, 1
0x180017f46  jz      short loc_180017F57
0x180017f48  sub     ecx, 1
0x180017f4b  jz      short loc_180017F57
0x180017f4d  cmp     ecx, 1
0x180017f50  jz      short loc_180017F57
0x180017f52  mov     r9d, ebx
0x180017f55  jmp     short loc_180017F5B
0x180017f57  lea     r9d, [rdx-57h]
0x180017f5b  mov     r8d, r10d
0x180017f5e  shr     r8, 1
0x180017f61  mov     rdx, [rsp+21E8h+var_2158]
0x180017f69  mov     eax, r10d
0x180017f6c  and     eax, 1
0x180017f6f  shl     eax, 2
0x180017f72  mov     ecx, 4
0x180017f77  sub     ecx, eax
0x180017f79  shl     r9b, cl
0x180017f7c  or      [r8+rdx], r9b
0x180017f80  inc     r10d
  ... truncated ...
```
