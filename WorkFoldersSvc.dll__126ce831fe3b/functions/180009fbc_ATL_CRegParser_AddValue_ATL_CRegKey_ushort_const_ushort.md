# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180009fbc`
- end: `0x18000a542`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1414`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000ec40`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180008520`
- `0x180008e98`
- `0x180009214`
- `0x180009fbc`
- `0x18000a598`
- `0x18000a7c4`
- `0x18000a988`
- `0x18000dd70`
- `0x18000ff9c`
- `0x180124400`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000a24b`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000a24b`
- `KERNEL32!lstrcmpiW` at `0x18000a05d`
- `KERNEL32!lstrcmpiW` at `0x18000a05d`
- `ADVAPI32!RegSetValueExW` at `0x18000a1ff`
- `ADVAPI32!RegSetValueExW` at `0x18000a292`
- `ADVAPI32!RegSetValueExW` at `0x18000a495`
- `ADVAPI32!RegSetValueExW` at `0x18000a4ec`
- `ADVAPI32!RegSetValueExW` at `0x18000a1ff`
- `ADVAPI32!RegSetValueExW` at `0x18000a292`
- `ADVAPI32!RegSetValueExW` at `0x18000a495`
- `ADVAPI32!RegSetValueExW` at `0x18000a4ec`
- `USER32!CharNextW` at `0x18000a17a`
- `USER32!CharNextW` at `0x18000a196`
- `USER32!CharNextW` at `0x18000a17a`
- `USER32!CharNextW` at `0x18000a196`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  HKEY *v14; // r13
  BYTE *v15; // rsi
  WCHAR *j; // r14
  const WCHAR *v17; // rax
  DWORD cbData; // r10d
  BYTE *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  LSTATUS v22; // edi
  HRESULT v23; // edi
  __int64 v24; // rdi
  int v25; // eax
  DWORD v26; // r14d
  size_t v27; // rsi
  unsigned __int64 v28; // rax
  HKEY *v29; // r15
  unsigned int v30; // r10d
  unsigned int v31; // edx
  char v32; // r9
  __int64 v33; // rdi
  int Token; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-22D8h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp-22D0h] BYREF
  LPCWSTR lpValueName; // [rsp+40h] [rbp-22C8h]
  ATL::CRegParser *v38; // [rsp+48h] [rbp-22C0h]
  int v39; // [rsp+50h] [rbp-22B8h]
  HKEY *v40; // [rsp+58h] [rbp-22B0h]
  __int64 v41; // [rsp+60h] [rbp-22A8h] BYREF
  HKEY *v42; // [rsp+68h] [rbp-22A0h]
  ATL::CRegParser *v43; // [rsp+70h] [rbp-2298h]
  const WCHAR *v44; // [rsp+80h] [rbp-2288h]
  HKEY *v45; // [rsp+90h] [rbp-2278h]
  unsigned __int16 *v46; // [rsp+98h] [rbp-2270h]
  BYTE *v47; // [rsp+A0h] [rbp-2268h] BYREF
  char v48; // [rsp+A8h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1B0h] [rbp-2158h] BYREF
  char v50; // [rsp+1B8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2C0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v42 = a2;
  v6 = this;
  v38 = this;
  v40 = a2;
  v43 = this;
  v45 = a2;
  v44 = a3;
  v46 = a4;
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
      v39 = v24;
      if ( (v24 & 1) != 0 )
        return 2147500037LL;
      v25 = (int)v24 / 2;
      v26 = (int)v24 / 2;
      *(_DWORD *)Data = (int)v24 / 2;
      LODWORD(v40) = (int)v24 / 2;
      v47 = 0;
      try
      {
        v27 = v25;
        v28 = ATL::AtlMultiplyThrow<unsigned __int64>(v25, 1);
        if ( v28 <= 0x100 )
          v47 = (BYTE *)&v48;
        else
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v47, v28);
      }
      catch ( ... )
      {
        v27 = *(int *)Data;
        v8 = 0;
        LODWORD(v24) = v39;
        v26 = (unsigned int)v40;
        v38 = v43;
        v29 = v45;
        lpValueName = v44;
        goto LABEL_47;
      }
      v29 = v42;
LABEL_47:
      if ( !v47 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v47);
        return 2147500037LL;
      }
      memset_0(v47, 0, v27);
      v30 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_76:
        v22 = RegSetValueExW(*v29, lpValueName, 0, 3u, v47, v26);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v47);
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
        v47[(unsigned __int64)v30 >> 1] |= v32 << (4 - 4 * (v30 & 1));
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
      v41 = 0;
      v23 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v23 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v22 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v41);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v41);
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
          lpData = (BYTE *)&v50;
        else
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v13);
      }
      catch ( ... )
      {
        v8 = 0;
        v14 = v40;
        v38 = v43;
        lpValueName = v44;
        goto LABEL_18;
      }
      v14 = v42;
LABEL_18:
      v15 = lpData;
      if ( lpData )
      {
        for ( j = String1; *j; v15 += 2 )
        {
          v17 = CharNextW(j);
          if ( *j == 92 && *v17 == 48 )
          {
            *(_WORD *)v15 = 0;
            j = CharNextW(v17);
          }
          else
          {
            *(_WORD *)v15 = *j++;
          }
        }
        *(_DWORD *)v15 = 0;
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
        v22 = RegSetValueExW(*v14, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v22 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_34:
      v6 = v38;
LABEL_80:
      if ( v22 )
      {
        return ATL::AtlHresultFromWin32(v22);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v46);
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
0x180009fbc  push    rbx
0x180009fbe  push    rsi
0x180009fbf  push    rdi
0x180009fc0  push    r12
0x180009fc2  push    r13
0x180009fc4  push    r14
0x180009fc6  push    r15
0x180009fc8  mov     eax, 22D0h
0x180009fcd  call    _alloca_probe
0x180009fd2  sub     rsp, rax
0x180009fd5  mov     rax, cs:__security_cookie
0x180009fdc  xor     rax, rsp
0x180009fdf  mov     [rsp+2308h+var_48], rax
0x180009fe7  mov     r14, r8
0x180009fea  mov     [rsp+2308h+lpValueName], r8
0x180009fef  mov     r12, rdx
0x180009ff2  mov     [rsp+2308h+var_22A0], rdx
0x180009ff7  mov     r15, rcx
0x180009ffa  mov     [rsp+2308h+var_22C0], rcx
0x180009fff  mov     [rsp+2308h+var_22B0], rdx
0x18000a004  mov     [rsp+2308h+var_2298], rcx
0x18000a009  mov     [rsp+2308h+var_2278], rdx
0x18000a011  mov     [rsp+2308h+var_2288], r8
0x18000a019  mov     [rsp+2308h+var_2270], r9
0x18000a021  lea     rdx, [rsp+2308h+String1]; unsigned __int16 *
0x18000a029  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a02e  xor     ebx, ebx
0x18000a030  test    eax, eax
0x18000a032  js      loc_18000A51F
0x18000a038  mov     edi, ebx
0x18000a03a  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000a041  cmp     edi, 4
0x18000a044  jnb     loc_18000A51A
0x18000a04a  movsxd  rsi, edi
0x18000a04d  add     rsi, rsi
0x18000a050  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000a055  lea     rcx, [rsp+2308h+String1]; lpString1
0x18000a05d  call    cs:__imp_lstrcmpiW
0x18000a063  test    eax, eax
0x18000a065  jz      short loc_18000A06B
0x18000a067  inc     edi
0x18000a069  jmp     short loc_18000A041
0x18000a06b  movzx   edi, word ptr [r13+rsi*8+8]
0x18000a071  mov     rcx, r15; this
0x18000a074  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000a079  lea     rdx, [rsp+2308h+String1]; unsigned __int16 *
0x18000a081  mov     rcx, r15; this
0x18000a084  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a089  test    eax, eax
0x18000a08b  js      loc_18000A51F
0x18000a091  mov     r13d, 8
0x18000a097  cmp     di, r13w
0x18000a09b  jz      loc_18000A4AF
0x18000a0a1  cmp     di, 11h
0x18000a0a5  jz      loc_18000A2A9
0x18000a0ab  cmp     di, 13h
0x18000a0af  jz      loc_18000A230
0x18000a0b5  mov     eax, 4008h
0x18000a0ba  cmp     di, ax
0x18000a0bd  jnz     loc_18000A501
0x18000a0c3  lea     rcx, [rsp+2308h+String1]
0x18000a0cb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a0cf  mov     rax, rdi
0x18000a0d2  inc     rax
0x18000a0d5  cmp     [rcx+rax*2], bx
0x18000a0d9  jnz     short loc_18000A0D2
0x18000a0db  add     eax, 2
0x18000a0de  mov     [rsp+2308h+var_2158], rbx
0x18000a0e6  movsxd  rcx, eax
0x18000a0e9  mov     r15d, 2
0x18000a0ef  mov     edx, r15d
0x18000a0f2  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000a0f7  cmp     rax, 100h
0x18000a0fd  jbe     short loc_18000A111
0x18000a0ff  mov     rdx, rax
0x18000a102  lea     rcx, [rsp+2308h+var_2158]
0x18000a10a  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000a10f  jmp     short loc_18000A121
0x18000a111  lea     rax, [rsp+2308h+var_2150]
0x18000a119  mov     [rsp+2308h+var_2158], rax
0x18000a121  mov     r13, [rsp+2308h+var_22A0]
0x18000a126  jmp     short loc_18000A14E
0x18000a128  xor     ebx, ebx
0x18000a12a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a12e  lea     r15d, [rbx+2]
0x18000a132  mov     r13, [rsp+2308h+var_22B0]
0x18000a137  mov     rax, [rsp+2308h+var_2298]
0x18000a13c  mov     [rsp+2308h+var_22C0], rax
0x18000a141  mov     rax, [rsp+2308h+var_2288]
0x18000a149  mov     [rsp+2308h+lpValueName], rax
0x18000a14e  mov     rsi, [rsp+2308h+var_2158]
0x18000a156  test    rsi, rsi
0x18000a159  jz      loc_18000A214
0x18000a15f  lea     r14, [rsp+2308h+String1]
0x18000a167  cmp     [rsp+2308h+String1], bx
0x18000a16f  jz      short loc_18000A1B0
0x18000a171  mov     r12d, 30h ; '0'
0x18000a177  mov     rcx, r14; lpsz
0x18000a17a  call    cs:__imp_CharNextW
0x18000a180  movzx   ecx, word ptr [r14]
0x18000a184  cmp     cx, 5Ch ; '\'
0x18000a188  jnz     short loc_18000A1A1
0x18000a18a  cmp     [rax], r12w
0x18000a18e  jnz     short loc_18000A1A1
0x18000a190  mov     [rsi], bx
0x18000a193  mov     rcx, rax; lpsz
0x18000a196  call    cs:__imp_CharNextW
0x18000a19c  mov     r14, rax
0x18000a19f  jmp     short loc_18000A1A7
0x18000a1a1  mov     [rsi], cx
0x18000a1a4  add     r14, r15
0x18000a1a7  add     rsi, r15
0x18000a1aa  cmp     [r14], bx
0x18000a1ae  jnz     short loc_18000A177
0x18000a1b0  mov     dword ptr [rsi], 0
0x18000a1b6  mov     r8, [rsp+2308h+var_2158]
0x18000a1be  test    r8, r8
0x18000a1c1  jz      short loc_18000A209
0x18000a1c3  mov     r10d, ebx
0x18000a1c6  mov     r9, r8
0x18000a1c9  mov     rcx, rdi
0x18000a1cc  inc     rcx
0x18000a1cf  cmp     [r9+rcx*2], bx
0x18000a1d4  jnz     short loc_18000A1CC
0x18000a1d6  inc     ecx
0x18000a1d8  lea     r9, [r9+rcx*2]
0x18000a1dc  lea     r10d, [r10+rcx*2]
0x18000a1e0  cmp     ecx, 1
0x18000a1e3  jnz     short loc_18000A1C9
0x18000a1e5  mov     [rsp+2308h+cbData], r10d; cbData
0x18000a1ea  mov     [rsp+2308h+lpData], r8; lpData
0x18000a1ef  lea     r9d, [rcx+6]; dwType
0x18000a1f3  xor     r8d, r8d; Reserved
0x18000a1f6  mov     rdx, [rsp+2308h+lpValueName]; lpValueName
0x18000a1fb  mov     rcx, [r13+0]; hKey
0x18000a1ff  call    cs:__imp_RegSetValueExW
0x18000a205  mov     edi, eax
0x18000a207  jmp     short loc_18000A219
0x18000a209  mov     ecx, 80004005h; int
0x18000a20e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000a214  mov     edi, 0Eh
0x18000a219  lea     rcx, [rsp+2308h+var_2158]
0x18000a221  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000a226  mov     r15, [rsp+2308h+var_22C0]
0x18000a22b  jmp     loc_18000A4F4
0x18000a230  mov     [rsp+2308h+pulOut], ebx
0x18000a234  mov     [rsp+2308h+var_22A8], rbx
0x18000a239  lea     r9, [rsp+2308h+pulOut]; pulOut
0x18000a23e  xor     r8d, r8d; dwFlags
0x18000a241  xor     edx, edx; lcid
0x18000a243  lea     rcx, [rsp+2308h+String1]; strIn
0x18000a24b  call    cs:__imp_VarUI4FromStr
0x18000a251  mov     edi, eax
0x18000a253  test    eax, eax
0x18000a255  jns     short loc_18000A268
0x18000a257  lea     rcx, [rsp+2308h+var_22A8]
0x18000a25c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000a261  mov     eax, edi
0x18000a263  jmp     loc_18000A51F
0x18000a268  mov     eax, [rsp+2308h+pulOut]
0x18000a26c  mov     dword ptr [rsp+2308h+Data], eax
0x18000a270  mov     [rsp+2308h+cbData], 4; cbData
0x18000a278  lea     rax, [rsp+2308h+Data]
0x18000a27d  mov     [rsp+2308h+lpData], rax; lpData
0x18000a282  mov     r9d, 4; dwType
0x18000a288  xor     r8d, r8d; Reserved
0x18000a28b  mov     rdx, r14; lpValueName
0x18000a28e  mov     rcx, [r12]; hKey
0x18000a292  call    cs:__imp_RegSetValueExW
0x18000a298  mov     edi, eax
0x18000a29a  lea     rcx, [rsp+2308h+var_22A8]
0x18000a29f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000a2a4  jmp     loc_18000A4F4
0x18000a2a9  lea     rax, [rsp+2308h+String1]
0x18000a2b1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a2b5  inc     rdi
0x18000a2b8  cmp     [rax+rdi*2], bx
0x18000a2bc  jnz     short loc_18000A2B5
0x18000a2be  mov     [rsp+2308h+var_22B8], edi
0x18000a2c2  test    dil, 1
0x18000a2c6  jz      short loc_18000A2D2
0x18000a2c8  mov     eax, 80004005h
0x18000a2cd  jmp     loc_18000A51F
0x18000a2d2  mov     eax, edi
0x18000a2d4  cdq
0x18000a2d5  mov     r15d, 2
0x18000a2db  idiv    r15d
0x18000a2de  movsxd  r14, eax
0x18000a2e1  mov     dword ptr [rsp+2308h+Data], r14d
0x18000a2e6  mov     dword ptr [rsp+2308h+var_22B0], r14d
0x18000a2eb  mov     [rsp+2308h+var_2268], rbx
0x18000a2f3  mov     rsi, r14
0x18000a2f6  lea     edx, [r15-1]
0x18000a2fa  mov     rcx, r14
0x18000a2fd  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000a302  cmp     rax, 100h
0x18000a308  jbe     short loc_18000A31C
0x18000a30a  mov     rdx, rax
0x18000a30d  lea     rcx, [rsp+2308h+var_2268]
0x18000a315  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000a31a  jmp     short loc_18000A32C
0x18000a31c  lea     rax, [rsp+2308h+var_2260]
0x18000a324  mov     [rsp+2308h+var_2268], rax
0x18000a32c  mov     r15, [rsp+2308h+var_22A0]
0x18000a331  jmp     short loc_18000A366
0x18000a333  movsxd  rsi, dword ptr [rsp+2308h+Data]
0x18000a338  xor     ebx, ebx
0x18000a33a  lea     r13d, [rbx+8]
0x18000a33e  mov     edi, [rsp+2308h+var_22B8]
0x18000a342  mov     r14d, dword ptr [rsp+2308h+var_22B0]
0x18000a347  mov     rax, [rsp+2308h+var_2298]
0x18000a34c  mov     [rsp+2308h+var_22C0], rax
0x18000a351  mov     r15, [rsp+2308h+var_2278]
0x18000a359  mov     rax, [rsp+2308h+var_2288]
0x18000a361  mov     [rsp+2308h+lpValueName], rax
0x18000a366  mov     rcx, [rsp+2308h+var_2268]; void *
0x18000a36e  test    rcx, rcx
0x18000a371  jnz     short loc_18000A385
0x18000a373  lea     rcx, [rsp+2308h+var_2268]
0x18000a37b  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000a380  jmp     loc_18000A2C8
0x18000a385  mov     r8, rsi; Size
0x18000a388  xor     edx, edx; Val
0x18000a38a  call    memset_0
0x18000a38f  mov     r10d, ebx
0x18000a392  test    edi, edi
0x18000a394  jle     loc_18000A472
0x18000a39a  mov     r12d, 30h ; '0'
0x18000a3a0  mov     eax, r10d
0x18000a3a3  movzx   edx, [rsp+rax*2+2308h+String1]
0x18000a3ab  cmp     edx, 61h ; 'a'
0x18000a3ae  ja      short loc_18000A41D
0x18000a3b0  jz      loc_18000A43D
0x18000a3b6  cmp     edx, 38h ; '8'
0x18000a3b9  ja      short loc_18000A3EF
0x18000a3bb  jz      short loc_18000A3E7
0x18000a3bd  mov     ecx, edx
0x18000a3bf  sub     ecx, r12d
0x18000a3c2  jz      short loc_18000A3E7
0x18000a3c4  sub     ecx, 1
0x18000a3c7  jz      short loc_18000A3E7
0x18000a3c9  sub     ecx, 1
0x18000a3cc  jz      short loc_18000A3E7
0x18000a3ce  sub     ecx, 1
0x18000a3d1  jz      short loc_18000A3E7
0x18000a3d3  sub     ecx, 1
0x18000a3d6  jz      short loc_18000A3E7
0x18000a3d8  sub     ecx, 1
0x18000a3db  jz      short loc_18000A3E7
0x18000a3dd  sub     ecx, 1
0x18000a3e0  jz      short loc_18000A3E7
0x18000a3e2  cmp     ecx, 1
0x18000a3e5  jnz     short loc_18000A438
0x18000a3e7  mov     r9d, edx
0x18000a3ea  sub     r9d, r12d
0x18000a3ed  jmp     short loc_18000A441
0x18000a3ef  mov     r9d, edx
0x18000a3f2  mov     ecx, edx
0x18000a3f4  sub     ecx, 39h ; '9'
0x18000a3f7  jz      short loc_18000A3E7
0x18000a3f9  sub     ecx, r13d
0x18000a3fc  jz      short loc_18000A417
0x18000a3fe  sub     ecx, 1
0x18000a401  jz      short loc_18000A417
0x18000a403  sub     ecx, 1
0x18000a406  jz      short loc_18000A417
0x18000a408  sub     ecx, 1
0x18000a40b  jz      short loc_18000A417
0x18000a40d  sub     ecx, 1
0x18000a410  jz      short loc_18000A417
0x18000a412  cmp     ecx, 1
0x18000a415  jnz     short loc_18000A438
0x18000a417  add     r9d, 0FFFFFFC9h
0x18000a41b  jmp     short loc_18000A441
0x18000a41d  mov     ecx, edx
0x18000a41f  sub     ecx, 62h ; 'b'
0x18000a422  jz      short loc_18000A43D
0x18000a424  sub     ecx, 1
0x18000a427  jz      short loc_18000A43D
0x18000a429  sub     ecx, 1
0x18000a42c  jz      short loc_18000A43D
0x18000a42e  sub     ecx, 1
0x18000a431  jz      short loc_18000A43D
0x18000a433  cmp     ecx, 1
0x18000a436  jz      short loc_18000A43D
0x18000a438  mov     r9d, ebx
0x18000a43b  jmp     short loc_18000A441
0x18000a43d  lea     r9d, [rdx-57h]
0x18000a441  mov     r8d, r10d
0x18000a444  shr     r8, 1
0x18000a447  mov     rdx, [rsp+2308h+var_2268]
0x18000a44f  mov     eax, r10d
0x18000a452  and     eax, 1
0x18000a455  shl     eax, 2
0x18000a458  mov     ecx, 4
0x18000a45d  sub     ecx, eax
0x18000a45f  shl     r9b, cl
0x18000a462  or      [r8+rdx], r9b
0x18000a466  inc     r10d
0x18000a469  cmp     r10d, edi
  ... truncated ...
```
