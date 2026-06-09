# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180007f20`
- end: `0x1800084a0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180004fb8`

## callees

- `0x1800059a4`
- `0x1800059dc`
- `0x180005a10`
- `0x180006330`
- `0x180006490`
- `0x1800065fc`
- `0x180006720`
- `0x180007f20`
- `0x1800085bc`
- `0x18000b5fe`
- `0x18000b630`
- `0x18000b6f0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180007fbb`
- `KERNEL32!lstrcmpiW` at `0x180007fbb`
- `USER32!CharNextW` at `0x1800080dd`
- `USER32!CharNextW` at `0x1800080f9`
- `USER32!CharNextW` at `0x1800080dd`
- `USER32!CharNextW` at `0x1800080f9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800081ae`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800081ae`
- `ADVAPI32!RegSetValueExW` at `0x180008162`
- `ADVAPI32!RegSetValueExW` at `0x1800081f5`
- `ADVAPI32!RegSetValueExW` at `0x1800083f3`
- `ADVAPI32!RegSetValueExW` at `0x18000844a`
- `ADVAPI32!RegSetValueExW` at `0x180008162`
- `ADVAPI32!RegSetValueExW` at `0x1800081f5`
- `ADVAPI32!RegSetValueExW` at `0x1800083f3`
- `ADVAPI32!RegSetValueExW` at `0x18000844a`

## pseudocode

```c
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
  unsigned __int64 v12; // rax
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
  unsigned __int64 v26; // rax
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
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
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
0x180007f20  push    rbx
0x180007f22  push    rsi
0x180007f23  push    rdi
0x180007f24  push    r12
0x180007f26  push    r13
0x180007f28  push    r14
0x180007f2a  push    r15
0x180007f2c  mov     eax, 21B0h
0x180007f31  call    _alloca_probe
0x180007f36  sub     rsp, rax
0x180007f39  mov     rax, cs:__security_cookie
0x180007f40  xor     rax, rsp
0x180007f43  mov     [rsp+21E8h+var_48], rax
0x180007f4b  mov     r14, r8
0x180007f4e  mov     [rsp+21E8h+lpValueName], r8
0x180007f53  mov     r12, rdx
0x180007f56  mov     [rsp+21E8h+var_2198], rdx
0x180007f5b  mov     r15, rcx
0x180007f5e  mov     [rsp+21E8h+var_21B0], rcx
0x180007f63  mov     qword ptr [rsp+21E8h+Data], rdx
0x180007f68  mov     [rsp+21E8h+var_2190], rcx
0x180007f6d  mov     [rsp+21E8h+var_2170], rdx
0x180007f72  mov     [rsp+21E8h+var_2188], r8
0x180007f77  mov     [rsp+21E8h+var_2168], r9
0x180007f7f  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180007f87  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007f8c  xor     ebx, ebx
0x180007f8e  test    eax, eax
0x180007f90  js      loc_18000847D
0x180007f96  mov     edi, ebx
0x180007f98  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180007f9f  cmp     edi, 4
0x180007fa2  jnb     loc_180008478
0x180007fa8  movsxd  rsi, edi
0x180007fab  add     rsi, rsi
0x180007fae  mov     rdx, [r13+rsi*8+0]; lpString2
0x180007fb3  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180007fbb  call    cs:__imp_lstrcmpiW
0x180007fc1  test    eax, eax
0x180007fc3  jz      short loc_180007FC9
0x180007fc5  inc     edi
0x180007fc7  jmp     short loc_180007F9F
0x180007fc9  movzx   edi, word ptr [r13+rsi*8+8]
0x180007fcf  mov     rcx, r15; this
0x180007fd2  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180007fd7  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180007fdf  mov     rcx, r15; this
0x180007fe2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007fe7  test    eax, eax
0x180007fe9  js      loc_18000847D
0x180007fef  mov     r13d, 8
0x180007ff5  cmp     di, r13w
0x180007ff9  jz      loc_18000840D
0x180007fff  cmp     di, 11h
0x180008003  jz      loc_18000820C
0x180008009  cmp     di, 13h
0x18000800d  jz      loc_180008193
0x180008013  mov     eax, 4008h
0x180008018  cmp     di, ax
0x18000801b  jnz     loc_18000845F
0x180008021  lea     rcx, [rsp+21E8h+String1]
0x180008029  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000802d  mov     rax, rsi
0x180008030  inc     rax
0x180008033  cmp     [rcx+rax*2], bx
0x180008037  jnz     short loc_180008030
0x180008039  add     eax, 2
0x18000803c  mov     [rsp+21E8h+var_2158], rbx
0x180008044  movsxd  rcx, eax
0x180008047  mov     r15d, 2
0x18000804d  mov     edx, r15d
0x180008050  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180008055  cmp     rax, 100h
0x18000805b  jbe     short loc_180008077
0x18000805d  mov     rdx, rax
0x180008060  lea     rcx, [rsp+21E8h+var_2158]
0x180008068  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000806d  mov     rdi, [rsp+21E8h+var_2158]
0x180008075  jmp     short loc_180008087
0x180008077  lea     rdi, [rsp+21E8h+var_2150]
0x18000807f  mov     [rsp+21E8h+var_2158], rdi
0x180008087  mov     r13, [rsp+21E8h+var_2198]
0x18000808c  jmp     short loc_1800080B9
0x18000808e  xor     ebx, ebx
0x180008090  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008094  lea     r15d, [rbx+2]
0x180008098  mov     rdi, [rsp+21E8h+var_2158]
0x1800080a0  mov     r13, qword ptr [rsp+21E8h+Data]
0x1800080a5  mov     rax, [rsp+21E8h+var_2190]
0x1800080aa  mov     [rsp+21E8h+var_21B0], rax
0x1800080af  mov     rax, [rsp+21E8h+var_2188]
0x1800080b4  mov     [rsp+21E8h+lpValueName], rax
0x1800080b9  test    rdi, rdi
0x1800080bc  jz      loc_180008177
0x1800080c2  lea     r14, [rsp+21E8h+String1]
0x1800080ca  cmp     [rsp+21E8h+String1], bx
0x1800080d2  jz      short loc_180008113
0x1800080d4  mov     r12d, 30h ; '0'
0x1800080da  mov     rcx, r14; lpsz
0x1800080dd  call    cs:__imp_CharNextW
0x1800080e3  movzx   ecx, word ptr [r14]
0x1800080e7  cmp     cx, 5Ch ; '\'
0x1800080eb  jnz     short loc_180008104
0x1800080ed  cmp     [rax], r12w
0x1800080f1  jnz     short loc_180008104
0x1800080f3  mov     [rdi], bx
0x1800080f6  mov     rcx, rax; lpsz
0x1800080f9  call    cs:__imp_CharNextW
0x1800080ff  mov     r14, rax
0x180008102  jmp     short loc_18000810A
0x180008104  mov     [rdi], cx
0x180008107  add     r14, r15
0x18000810a  add     rdi, r15
0x18000810d  cmp     [r14], bx
0x180008111  jnz     short loc_1800080DA
0x180008113  mov     dword ptr [rdi], 0
0x180008119  mov     r8, [rsp+21E8h+var_2158]
0x180008121  test    r8, r8
0x180008124  jz      short loc_18000816C
0x180008126  mov     r10d, ebx
0x180008129  mov     r9, r8
0x18000812c  mov     rcx, rsi
0x18000812f  inc     rcx
0x180008132  cmp     [r9+rcx*2], bx
0x180008137  jnz     short loc_18000812F
0x180008139  inc     ecx
0x18000813b  lea     r9, [r9+rcx*2]
0x18000813f  lea     r10d, [r10+rcx*2]
0x180008143  cmp     ecx, 1
0x180008146  jnz     short loc_18000812C
0x180008148  mov     [rsp+21E8h+cbData], r10d; cbData
0x18000814d  mov     [rsp+21E8h+lpData], r8; lpData
0x180008152  lea     r9d, [rcx+6]; dwType
0x180008156  xor     r8d, r8d; Reserved
0x180008159  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18000815e  mov     rcx, [r13+0]; hKey
0x180008162  call    cs:__imp_RegSetValueExW
0x180008168  mov     edi, eax
0x18000816a  jmp     short loc_18000817C
0x18000816c  mov     ecx, 80004005h; int
0x180008171  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008177  mov     edi, 0Eh
0x18000817c  lea     rcx, [rsp+21E8h+var_2158]
0x180008184  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180008189  mov     r15, [rsp+21E8h+var_21B0]
0x18000818e  jmp     loc_180008452
0x180008193  mov     [rsp+21E8h+pulOut], ebx
0x180008197  mov     [rsp+21E8h+var_21B0], rbx
0x18000819c  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x1800081a1  xor     r8d, r8d; dwFlags
0x1800081a4  xor     edx, edx; lcid
0x1800081a6  lea     rcx, [rsp+21E8h+String1]; strIn
0x1800081ae  call    cs:__imp_VarUI4FromStr
0x1800081b4  mov     edi, eax
0x1800081b6  test    eax, eax
0x1800081b8  jns     short loc_1800081CB
0x1800081ba  lea     rcx, [rsp+21E8h+var_21B0]
0x1800081bf  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800081c4  mov     eax, edi
0x1800081c6  jmp     loc_18000847D
0x1800081cb  mov     eax, [rsp+21E8h+pulOut]
0x1800081cf  mov     dword ptr [rsp+21E8h+Data], eax
0x1800081d3  mov     [rsp+21E8h+cbData], 4; cbData
0x1800081db  lea     rax, [rsp+21E8h+Data]
0x1800081e0  mov     [rsp+21E8h+lpData], rax; lpData
0x1800081e5  mov     r9d, 4; dwType
0x1800081eb  xor     r8d, r8d; Reserved
0x1800081ee  mov     rdx, r14; lpValueName
0x1800081f1  mov     rcx, [r12]; hKey
0x1800081f5  call    cs:__imp_RegSetValueExW
0x1800081fb  mov     edi, eax
0x1800081fd  lea     rcx, [rsp+21E8h+var_21B0]
0x180008202  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008207  jmp     loc_180008452
0x18000820c  lea     rax, [rsp+21E8h+String1]
0x180008214  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008218  inc     rsi
0x18000821b  cmp     [rax+rsi*2], bx
0x18000821f  jnz     short loc_180008218
0x180008221  mov     dword ptr [rsp+21E8h+Data], esi
0x180008225  test    sil, 1
0x180008229  jz      short loc_180008235
0x18000822b  mov     eax, 80004005h
0x180008230  jmp     loc_18000847D
0x180008235  mov     eax, esi
0x180008237  cdq
0x180008238  mov     r15d, 2
0x18000823e  idiv    r15d
0x180008241  movsxd  r14, eax
0x180008244  mov     [rsp+21E8h+var_2158], rbx
0x18000824c  mov     rdi, r14
0x18000824f  mov     [rsp+21E8h+var_2178], r14
0x180008254  lea     edx, [r15-1]
0x180008258  mov     rcx, r14
0x18000825b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180008260  cmp     rax, 100h
0x180008266  jbe     short loc_180008282
0x180008268  mov     rdx, rax
0x18000826b  lea     rcx, [rsp+21E8h+var_2158]
0x180008273  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180008278  mov     rcx, [rsp+21E8h+var_2158]
0x180008280  jmp     short loc_180008292
0x180008282  lea     rcx, [rsp+21E8h+var_2150]
0x18000828a  mov     [rsp+21E8h+var_2158], rcx
0x180008292  mov     r15, [rsp+21E8h+var_2198]
0x180008297  jmp     short loc_1800082CC
0x180008299  xor     ebx, ebx
0x18000829b  lea     r13d, [rbx+8]
0x18000829f  mov     esi, dword ptr [rsp+21E8h+Data]
0x1800082a3  mov     rcx, [rsp+21E8h+var_2158]; void *
0x1800082ab  mov     rdi, [rsp+21E8h+var_2178]
0x1800082b0  mov     rax, [rsp+21E8h+var_2190]
0x1800082b5  mov     [rsp+21E8h+var_21B0], rax
0x1800082ba  mov     r15, [rsp+21E8h+var_2170]
0x1800082bf  mov     rax, [rsp+21E8h+var_2188]
0x1800082c4  mov     [rsp+21E8h+lpValueName], rax
0x1800082c9  mov     r14d, edi
0x1800082cc  test    rcx, rcx
0x1800082cf  jnz     short loc_1800082E3
0x1800082d1  lea     rcx, [rsp+21E8h+var_2158]
0x1800082d9  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800082de  jmp     loc_18000822B
0x1800082e3  mov     r8, rdi; Size
0x1800082e6  xor     edx, edx; Val
0x1800082e8  call    memset_0
0x1800082ed  mov     r10d, ebx
0x1800082f0  test    esi, esi
0x1800082f2  jle     loc_1800083D0
0x1800082f8  mov     r12d, 30h ; '0'
0x1800082fe  mov     eax, r10d
0x180008301  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180008309  cmp     edx, 61h ; 'a'
0x18000830c  ja      short loc_18000837B
0x18000830e  jz      loc_18000839B
0x180008314  cmp     edx, 38h ; '8'
0x180008317  ja      short loc_18000834D
0x180008319  jz      short loc_180008345
0x18000831b  mov     ecx, edx
0x18000831d  sub     ecx, r12d
0x180008320  jz      short loc_180008345
0x180008322  sub     ecx, 1
0x180008325  jz      short loc_180008345
0x180008327  sub     ecx, 1
0x18000832a  jz      short loc_180008345
0x18000832c  sub     ecx, 1
0x18000832f  jz      short loc_180008345
0x180008331  sub     ecx, 1
0x180008334  jz      short loc_180008345
0x180008336  sub     ecx, 1
0x180008339  jz      short loc_180008345
0x18000833b  sub     ecx, 1
0x18000833e  jz      short loc_180008345
0x180008340  cmp     ecx, 1
0x180008343  jnz     short loc_180008396
0x180008345  mov     r9d, edx
0x180008348  sub     r9d, r12d
0x18000834b  jmp     short loc_18000839F
0x18000834d  mov     r9d, edx
0x180008350  mov     ecx, edx
0x180008352  sub     ecx, 39h ; '9'
0x180008355  jz      short loc_180008345
0x180008357  sub     ecx, r13d
0x18000835a  jz      short loc_180008375
0x18000835c  sub     ecx, 1
0x18000835f  jz      short loc_180008375
0x180008361  sub     ecx, 1
0x180008364  jz      short loc_180008375
0x180008366  sub     ecx, 1
0x180008369  jz      short loc_180008375
0x18000836b  sub     ecx, 1
0x18000836e  jz      short loc_180008375
0x180008370  cmp     ecx, 1
0x180008373  jnz     short loc_180008396
0x180008375  add     r9d, 0FFFFFFC9h
0x180008379  jmp     short loc_18000839F
0x18000837b  mov     ecx, edx
0x18000837d  sub     ecx, 62h ; 'b'
0x180008380  jz      short loc_18000839B
0x180008382  sub     ecx, 1
0x180008385  jz      short loc_18000839B
0x180008387  sub     ecx, 1
0x18000838a  jz      short loc_18000839B
0x18000838c  sub     ecx, 1
0x18000838f  jz      short loc_18000839B
0x180008391  cmp     ecx, 1
0x180008394  jz      short loc_18000839B
0x180008396  mov     r9d, ebx
0x180008399  jmp     short loc_18000839F
0x18000839b  lea     r9d, [rdx-57h]
0x18000839f  mov     r8d, r10d
0x1800083a2  shr     r8, 1
0x1800083a5  mov     rdx, [rsp+21E8h+var_2158]
0x1800083ad  mov     eax, r10d
0x1800083b0  and     eax, 1
0x1800083b3  shl     eax, 2
0x1800083b6  mov     ecx, 4
0x1800083bb  sub     ecx, eax
0x1800083bd  shl     r9b, cl
0x1800083c0  or      [r8+rdx], r9b
0x1800083c4  inc     r10d
  ... truncated ...
```
