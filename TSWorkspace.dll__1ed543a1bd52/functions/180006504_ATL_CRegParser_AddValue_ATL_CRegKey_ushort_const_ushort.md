# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180006504`
- end: `0x180006a96`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1426`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000b7ec`

## callees

- `0x1800044bf`
- `0x180004818`
- `0x180004a18`
- `0x18000540c`
- `0x180006504`
- `0x180006a9c`
- `0x180006d40`
- `0x180007598`
- `0x18000a760`
- `0x18000c494`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180006753`
- `ADVAPI32!RegSetValueExW` at `0x1800067e6`
- `ADVAPI32!RegSetValueExW` at `0x1800069e9`
- `ADVAPI32!RegSetValueExW` at `0x180006a40`
- `ADVAPI32!RegSetValueExW` at `0x180006753`
- `ADVAPI32!RegSetValueExW` at `0x1800067e6`
- `ADVAPI32!RegSetValueExW` at `0x1800069e9`
- `ADVAPI32!RegSetValueExW` at `0x180006a40`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000679f`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000679f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800066ce`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800066ea`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800066ce`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800066ea`
- `KERNEL32!lstrcmpiW` at `0x1800065b1`
- `KERNEL32!lstrcmpiW` at `0x1800065b1`

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
  BYTE Data[4]; // [rsp+30h] [rbp-22E8h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp-22E0h] BYREF
  LPCWSTR lpValueName; // [rsp+40h] [rbp-22D8h]
  ATL::CRegParser *v38; // [rsp+48h] [rbp-22D0h]
  int v39; // [rsp+50h] [rbp-22C8h]
  HKEY *v40; // [rsp+58h] [rbp-22C0h]
  __int64 v41; // [rsp+60h] [rbp-22B8h] BYREF
  HKEY *v42; // [rsp+68h] [rbp-22B0h]
  ATL::CRegParser *v43; // [rsp+70h] [rbp-22A8h]
  const WCHAR *v44; // [rsp+80h] [rbp-2298h]
  HKEY *v45; // [rsp+90h] [rbp-2288h]
  unsigned __int16 *v46; // [rsp+98h] [rbp-2280h]
  __int64 v47; // [rsp+A0h] [rbp-2278h]
  BYTE *v48; // [rsp+B0h] [rbp-2268h] BYREF
  char v49; // [rsp+B8h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1C0h] [rbp-2158h] BYREF
  char v51; // [rsp+1C8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2D0h] [rbp-2048h] BYREF

  v47 = -2;
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
      v48 = 0;
      try
      {
        v27 = v25;
        v28 = ATL::AtlMultiplyThrow<unsigned __int64>(v25, 1);
        if ( v28 <= 0x100 )
          v48 = (BYTE *)&v49;
        else
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v48, v28);
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
      if ( !v48 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v48);
        return 2147500037LL;
      }
      memset_0(v48, 0, v27);
      v30 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_76:
        v22 = RegSetValueExW(*v29, lpValueName, 0, 3u, v48, v26);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v48);
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
        v48[(unsigned __int64)v30 >> 1] |= v32 << (4 - 4 * (v30 & 1));
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
          lpData = (BYTE *)&v51;
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
0x180006504  push    rbx
0x180006506  push    rsi
0x180006507  push    rdi
0x180006508  push    r12
0x18000650a  push    r13
0x18000650c  push    r14
0x18000650e  push    r15
0x180006510  mov     eax, 22E0h
0x180006515  call    _alloca_probe
0x18000651a  sub     rsp, rax
0x18000651d  mov     [rsp+2318h+var_2278], 0FFFFFFFFFFFFFFFEh
0x180006529  mov     rax, cs:__security_cookie
0x180006530  xor     rax, rsp
0x180006533  mov     [rsp+2318h+var_48], rax
0x18000653b  mov     r14, r8
0x18000653e  mov     [rsp+2318h+lpValueName], r8
0x180006543  mov     r12, rdx
0x180006546  mov     [rsp+2318h+var_22B0], rdx
0x18000654b  mov     r15, rcx
0x18000654e  mov     [rsp+2318h+var_22D0], rcx
0x180006553  mov     [rsp+2318h+var_22C0], rdx
0x180006558  mov     [rsp+2318h+var_22A8], rcx
0x18000655d  mov     [rsp+2318h+var_2288], rdx
0x180006565  mov     [rsp+2318h+var_2298], r8
0x18000656d  mov     [rsp+2318h+var_2280], r9
0x180006575  lea     rdx, [rsp+2318h+String1]; unsigned __int16 *
0x18000657d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006582  xor     ebx, ebx
0x180006584  test    eax, eax
0x180006586  js      loc_180006A73
0x18000658c  mov     edi, ebx
0x18000658e  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180006595  cmp     edi, 4
0x180006598  jnb     loc_180006A6E
0x18000659e  movsxd  rsi, edi
0x1800065a1  add     rsi, rsi
0x1800065a4  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800065a9  lea     rcx, [rsp+2318h+String1]; lpString1
0x1800065b1  call    cs:__imp_lstrcmpiW
0x1800065b7  test    eax, eax
0x1800065b9  jz      short loc_1800065BF
0x1800065bb  inc     edi
0x1800065bd  jmp     short loc_180006595
0x1800065bf  movzx   edi, word ptr [r13+rsi*8+8]
0x1800065c5  mov     rcx, r15; this
0x1800065c8  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800065cd  lea     rdx, [rsp+2318h+String1]; unsigned __int16 *
0x1800065d5  mov     rcx, r15; this
0x1800065d8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800065dd  test    eax, eax
0x1800065df  js      loc_180006A73
0x1800065e5  mov     r13d, 8
0x1800065eb  cmp     di, r13w
0x1800065ef  jz      loc_180006A03
0x1800065f5  cmp     di, 11h
0x1800065f9  jz      loc_1800067FD
0x1800065ff  cmp     di, 13h
0x180006603  jz      loc_180006784
0x180006609  mov     eax, 4008h
0x18000660e  cmp     di, ax
0x180006611  jnz     loc_180006A55
0x180006617  lea     rcx, [rsp+2318h+String1]
0x18000661f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006623  mov     rax, rdi
0x180006626  inc     rax
0x180006629  cmp     [rcx+rax*2], bx
0x18000662d  jnz     short loc_180006626
0x18000662f  add     eax, 2
0x180006632  mov     [rsp+2318h+var_2158], rbx
0x18000663a  movsxd  rcx, eax
0x18000663d  mov     r15d, 2
0x180006643  mov     edx, r15d
0x180006646  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000664b  cmp     rax, 100h
0x180006651  jbe     short loc_180006665
0x180006653  mov     rdx, rax
0x180006656  lea     rcx, [rsp+2318h+var_2158]
0x18000665e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006663  jmp     short loc_180006675
0x180006665  lea     rax, [rsp+2318h+var_2150]
0x18000666d  mov     [rsp+2318h+var_2158], rax
0x180006675  mov     r13, [rsp+2318h+var_22B0]
0x18000667a  jmp     short loc_1800066A2
0x18000667c  xor     ebx, ebx
0x18000667e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006682  lea     r15d, [rbx+2]
0x180006686  mov     r13, [rsp+2318h+var_22C0]
0x18000668b  mov     rax, [rsp+2318h+var_22A8]
0x180006690  mov     [rsp+2318h+var_22D0], rax
0x180006695  mov     rax, [rsp+2318h+var_2298]
0x18000669d  mov     [rsp+2318h+lpValueName], rax
0x1800066a2  mov     rsi, [rsp+2318h+var_2158]
0x1800066aa  test    rsi, rsi
0x1800066ad  jz      loc_180006768
0x1800066b3  lea     r14, [rsp+2318h+String1]
0x1800066bb  cmp     [rsp+2318h+String1], bx
0x1800066c3  jz      short loc_180006704
0x1800066c5  mov     r12d, 30h ; '0'
0x1800066cb  mov     rcx, r14; lpsz
0x1800066ce  call    cs:__imp_CharNextW
0x1800066d4  movzx   ecx, word ptr [r14]
0x1800066d8  cmp     cx, 5Ch ; '\'
0x1800066dc  jnz     short loc_1800066F5
0x1800066de  cmp     [rax], r12w
0x1800066e2  jnz     short loc_1800066F5
0x1800066e4  mov     [rsi], bx
0x1800066e7  mov     rcx, rax; lpsz
0x1800066ea  call    cs:__imp_CharNextW
0x1800066f0  mov     r14, rax
0x1800066f3  jmp     short loc_1800066FB
0x1800066f5  mov     [rsi], cx
0x1800066f8  add     r14, r15
0x1800066fb  add     rsi, r15
0x1800066fe  cmp     [r14], bx
0x180006702  jnz     short loc_1800066CB
0x180006704  mov     dword ptr [rsi], 0
0x18000670a  mov     r8, [rsp+2318h+var_2158]
0x180006712  test    r8, r8
0x180006715  jz      short loc_18000675D
0x180006717  mov     r10d, ebx
0x18000671a  mov     r9, r8
0x18000671d  mov     rcx, rdi
0x180006720  inc     rcx
0x180006723  cmp     [r9+rcx*2], bx
0x180006728  jnz     short loc_180006720
0x18000672a  inc     ecx
0x18000672c  lea     r9, [r9+rcx*2]
0x180006730  lea     r10d, [r10+rcx*2]
0x180006734  cmp     ecx, 1
0x180006737  jnz     short loc_18000671D
0x180006739  mov     [rsp+2318h+cbData], r10d; cbData
0x18000673e  mov     [rsp+2318h+lpData], r8; lpData
0x180006743  lea     r9d, [rcx+6]; dwType
0x180006747  xor     r8d, r8d; Reserved
0x18000674a  mov     rdx, [rsp+2318h+lpValueName]; lpValueName
0x18000674f  mov     rcx, [r13+0]; hKey
0x180006753  call    cs:__imp_RegSetValueExW
0x180006759  mov     edi, eax
0x18000675b  jmp     short loc_18000676D
0x18000675d  mov     ecx, 80004005h; int
0x180006762  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006768  mov     edi, 0Eh
0x18000676d  lea     rcx, [rsp+2318h+var_2158]
0x180006775  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000677a  mov     r15, [rsp+2318h+var_22D0]
0x18000677f  jmp     loc_180006A48
0x180006784  mov     [rsp+2318h+pulOut], ebx
0x180006788  mov     [rsp+2318h+var_22B8], rbx
0x18000678d  lea     r9, [rsp+2318h+pulOut]; pulOut
0x180006792  xor     r8d, r8d; dwFlags
0x180006795  xor     edx, edx; lcid
0x180006797  lea     rcx, [rsp+2318h+String1]; strIn
0x18000679f  call    cs:__imp_VarUI4FromStr
0x1800067a5  mov     edi, eax
0x1800067a7  test    eax, eax
0x1800067a9  jns     short loc_1800067BC
0x1800067ab  lea     rcx, [rsp+2318h+var_22B8]
0x1800067b0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800067b5  mov     eax, edi
0x1800067b7  jmp     loc_180006A73
0x1800067bc  mov     eax, [rsp+2318h+pulOut]
0x1800067c0  mov     dword ptr [rsp+2318h+Data], eax
0x1800067c4  mov     [rsp+2318h+cbData], 4; cbData
0x1800067cc  lea     rax, [rsp+2318h+Data]
0x1800067d1  mov     [rsp+2318h+lpData], rax; lpData
0x1800067d6  mov     r9d, 4; dwType
0x1800067dc  xor     r8d, r8d; Reserved
0x1800067df  mov     rdx, r14; lpValueName
0x1800067e2  mov     rcx, [r12]; hKey
0x1800067e6  call    cs:__imp_RegSetValueExW
0x1800067ec  mov     edi, eax
0x1800067ee  lea     rcx, [rsp+2318h+var_22B8]
0x1800067f3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800067f8  jmp     loc_180006A48
0x1800067fd  lea     rax, [rsp+2318h+String1]
0x180006805  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006809  inc     rdi
0x18000680c  cmp     [rax+rdi*2], bx
0x180006810  jnz     short loc_180006809
0x180006812  mov     [rsp+2318h+var_22C8], edi
0x180006816  test    dil, 1
0x18000681a  jz      short loc_180006826
0x18000681c  mov     eax, 80004005h
0x180006821  jmp     loc_180006A73
0x180006826  mov     eax, edi
0x180006828  cdq
0x180006829  mov     r15d, 2
0x18000682f  idiv    r15d
0x180006832  movsxd  r14, eax
0x180006835  mov     dword ptr [rsp+2318h+Data], r14d
0x18000683a  mov     dword ptr [rsp+2318h+var_22C0], r14d
0x18000683f  mov     [rsp+2318h+var_2268], rbx
0x180006847  mov     rsi, r14
0x18000684a  lea     edx, [r15-1]
0x18000684e  mov     rcx, r14
0x180006851  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180006856  cmp     rax, 100h
0x18000685c  jbe     short loc_180006870
0x18000685e  mov     rdx, rax
0x180006861  lea     rcx, [rsp+2318h+var_2268]
0x180006869  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000686e  jmp     short loc_180006880
0x180006870  lea     rax, [rsp+2318h+var_2260]
0x180006878  mov     [rsp+2318h+var_2268], rax
0x180006880  mov     r15, [rsp+2318h+var_22B0]
0x180006885  jmp     short loc_1800068BA
0x180006887  movsxd  rsi, dword ptr [rsp+2318h+Data]
0x18000688c  xor     ebx, ebx
0x18000688e  lea     r13d, [rbx+8]
0x180006892  mov     edi, [rsp+2318h+var_22C8]
0x180006896  mov     r14d, dword ptr [rsp+2318h+var_22C0]
0x18000689b  mov     rax, [rsp+2318h+var_22A8]
0x1800068a0  mov     [rsp+2318h+var_22D0], rax
0x1800068a5  mov     r15, [rsp+2318h+var_2288]
0x1800068ad  mov     rax, [rsp+2318h+var_2298]
0x1800068b5  mov     [rsp+2318h+lpValueName], rax
0x1800068ba  mov     rcx, [rsp+2318h+var_2268]; void *
0x1800068c2  test    rcx, rcx
0x1800068c5  jnz     short loc_1800068D9
0x1800068c7  lea     rcx, [rsp+2318h+var_2268]
0x1800068cf  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800068d4  jmp     loc_18000681C
0x1800068d9  mov     r8, rsi; Size
0x1800068dc  xor     edx, edx; Val
0x1800068de  call    memset_0
0x1800068e3  mov     r10d, ebx
0x1800068e6  test    edi, edi
0x1800068e8  jle     loc_1800069C6
0x1800068ee  mov     r12d, 30h ; '0'
0x1800068f4  mov     eax, r10d
0x1800068f7  movzx   edx, [rsp+rax*2+2318h+String1]
0x1800068ff  cmp     edx, 61h ; 'a'
0x180006902  ja      short loc_180006971
0x180006904  jz      loc_180006991
0x18000690a  cmp     edx, 38h ; '8'
0x18000690d  ja      short loc_180006943
0x18000690f  jz      short loc_18000693B
0x180006911  mov     ecx, edx
0x180006913  sub     ecx, r12d
0x180006916  jz      short loc_18000693B
0x180006918  sub     ecx, 1
0x18000691b  jz      short loc_18000693B
0x18000691d  sub     ecx, 1
0x180006920  jz      short loc_18000693B
0x180006922  sub     ecx, 1
0x180006925  jz      short loc_18000693B
0x180006927  sub     ecx, 1
0x18000692a  jz      short loc_18000693B
0x18000692c  sub     ecx, 1
0x18000692f  jz      short loc_18000693B
0x180006931  sub     ecx, 1
0x180006934  jz      short loc_18000693B
0x180006936  cmp     ecx, 1
0x180006939  jnz     short loc_18000698C
0x18000693b  mov     r9d, edx
0x18000693e  sub     r9d, r12d
0x180006941  jmp     short loc_180006995
0x180006943  mov     r9d, edx
0x180006946  mov     ecx, edx
0x180006948  sub     ecx, 39h ; '9'
0x18000694b  jz      short loc_18000693B
0x18000694d  sub     ecx, r13d
0x180006950  jz      short loc_18000696B
0x180006952  sub     ecx, 1
0x180006955  jz      short loc_18000696B
0x180006957  sub     ecx, 1
0x18000695a  jz      short loc_18000696B
0x18000695c  sub     ecx, 1
0x18000695f  jz      short loc_18000696B
0x180006961  sub     ecx, 1
0x180006964  jz      short loc_18000696B
0x180006966  cmp     ecx, 1
0x180006969  jnz     short loc_18000698C
0x18000696b  add     r9d, 0FFFFFFC9h
0x18000696f  jmp     short loc_180006995
0x180006971  mov     ecx, edx
0x180006973  sub     ecx, 62h ; 'b'
0x180006976  jz      short loc_180006991
0x180006978  sub     ecx, 1
0x18000697b  jz      short loc_180006991
0x18000697d  sub     ecx, 1
0x180006980  jz      short loc_180006991
0x180006982  sub     ecx, 1
0x180006985  jz      short loc_180006991
0x180006987  cmp     ecx, 1
0x18000698a  jz      short loc_180006991
0x18000698c  mov     r9d, ebx
0x18000698f  jmp     short loc_180006995
0x180006991  lea     r9d, [rdx-57h]
0x180006995  mov     r8d, r10d
0x180006998  shr     r8, 1
0x18000699b  mov     rdx, [rsp+2318h+var_2268]
0x1800069a3  mov     eax, r10d
0x1800069a6  and     eax, 1
0x1800069a9  shl     eax, 2
0x1800069ac  mov     ecx, 4
0x1800069b1  sub     ecx, eax
0x1800069b3  shl     r9b, cl
0x1800069b6  or      [r8+rdx], r9b
0x1800069ba  inc     r10d
  ... truncated ...
```
