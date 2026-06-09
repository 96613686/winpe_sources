# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180014f74`
- end: `0x18001544d`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1241`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180018fb0`

## callees

- `0x180013e69`
- `0x180013e9c`
- `0x180013f48`
- `0x1800144ac`
- `0x180014f74`
- `0x180015454`
- `0x18001579c`
- `0x180015f4c`
- `0x180015fe0`
- `0x180018170`
- `0x180019a38`
- `0x180019b10`
- `0x18002fb50`
- `0x18002fc10`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180015204`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180015204`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800151b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015394`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800153ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800151b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015394`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800153ee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015125`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015147`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015125`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015147`
- `KERNEL32!lstrcmpiW` at `0x180015005`
- `KERNEL32!lstrcmpiW` at `0x180015005`

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
  ATL::CRegParser *v6; // r15
  __int64 result; // rax
  unsigned int v8; // ebx
  int v9; // edi
  LPCWSTR *i; // rsi
  __int16 v11; // di
  __int64 v12; // rax
  unsigned __int64 v13; // rax
  BYTE *v14; // rdi
  WCHAR *j; // r15
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
  __int64 v28; // r9
  unsigned __int8 v29; // al
  unsigned int v30; // r10d
  __int64 v31; // r9
  __int64 v32; // r11
  __int64 v33; // rsi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21B8h] BYREF
  __int64 v36; // [rsp+38h] [rbp-21B0h] BYREF
  ATL::CRegParser *v37; // [rsp+40h] [rbp-21A8h]
  ATL::CRegParser *v38; // [rsp+48h] [rbp-21A0h]
  struct ATL::CRegKey *v39; // [rsp+50h] [rbp-2198h]
  const unsigned __int16 *v40; // [rsp+60h] [rbp-2188h]
  size_t v41; // [rsp+70h] [rbp-2178h]
  unsigned __int16 *v42; // [rsp+78h] [rbp-2170h]
  __int64 v43; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  WCHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  v43 = -2;
  v4 = a3;
  v5 = a2;
  v6 = this;
  v37 = this;
  v38 = this;
  v39 = (struct ATL::CRegKey *)a2;
  v40 = a3;
  v42 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( (int)result < 0 )
    return result;
  v9 = 0;
  for ( i = (LPCWSTR *)&`ATL::CRegParser::VTFromRegType'::`2'::map; ; i += 2 )
  {
    if ( (unsigned __int64)v9 >= 4 )
      return 2147614729LL;
    if ( !lstrcmpiW(String1, *i) )
      break;
    ++v9;
  }
  v11 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
  ATL::CRegParser::SkipWhiteSpace(v6);
  result = ATL::CRegParser::NextToken(v6, String1);
  if ( (int)result < 0 )
    return result;
  if ( v11 == 8 )
  {
    v33 = -1;
    do
      ++v33;
    while ( String1[v33] );
    v21 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
    goto LABEL_53;
  }
  if ( v11 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( String1[v23] );
    pulOut = v23;
    if ( (v23 & 1) == 0 )
    {
      v24 = (int)v23 / 2;
      LODWORD(v36) = (int)v23 / 2;
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
        LODWORD(v23) = pulOut;
        v24 = v36;
        v27 = lpData;
        v25 = v41;
        v37 = v38;
        v5 = (HKEY *)v39;
        v4 = v40;
      }
      if ( v27 )
      {
        memset_0(v27, 0, v25);
        if ( (int)v23 > 0 )
        {
          v28 = 0;
          do
          {
            v29 = ATL::CRegParser::ChToByte(String1[v28]);
            lpData[(unsigned __int64)v30 >> 1] |= v29 << (4 - 4 * (v30 & 1));
            v28 = v31 + 1;
          }
          while ( v28 < v32 );
        }
        v21 = RegSetValueExW(*v5, v4, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_53;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
    }
    return 2147500037LL;
  }
  if ( v11 != 19 )
  {
    if ( v11 == 16392 )
    {
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
          v14 = v45;
          lpData = v45;
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
        v37 = v38;
        v5 = (HKEY *)v39;
        v4 = v40;
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
        *(_WORD *)v14 = 0;
        *((_WORD *)v14 + 1) = 0;
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
        v21 = RegSetValueExW(*v5, v4, 0, 7u, lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      goto LABEL_53;
    }
LABEL_56:
    Token = ATL::CRegParser::NextToken(v6, v42);
    if ( Token < 0 )
      return (unsigned int)Token;
    return v8;
  }
  pulOut = 0;
  v36 = 0;
  v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
  if ( v22 < 0 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v36);
    return (unsigned int)v22;
  }
  v21 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v5, v4, pulOut);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v36);
LABEL_53:
  if ( !v21 )
  {
    v6 = v37;
    goto LABEL_56;
  }
  return ATL::AtlHresultFromWin32(v21);
}

```

## disassembly

```asm
0x180014f74  push    rbx
0x180014f76  push    rsi
0x180014f77  push    rdi
0x180014f78  push    r12
0x180014f7a  push    r13
0x180014f7c  push    r14
0x180014f7e  push    r15
0x180014f80  mov     eax, 21B0h
0x180014f85  call    _alloca_probe
0x180014f8a  sub     rsp, rax
0x180014f8d  mov     [rsp+21E8h+var_2168], 0FFFFFFFFFFFFFFFEh
0x180014f99  mov     rax, cs:__security_cookie
0x180014fa0  xor     rax, rsp
0x180014fa3  mov     [rsp+21E8h+var_48], rax
0x180014fab  mov     r13, r8
0x180014fae  mov     r12, rdx
0x180014fb1  mov     r15, rcx
0x180014fb4  mov     [rsp+21E8h+var_21A8], rcx
0x180014fb9  mov     [rsp+21E8h+var_21A0], rcx
0x180014fbe  mov     [rsp+21E8h+var_2198], rdx
0x180014fc3  mov     [rsp+21E8h+var_2188], r8
0x180014fc8  mov     [rsp+21E8h+var_2170], r9
0x180014fcd  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180014fd5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014fda  xor     ebx, ebx
0x180014fdc  test    eax, eax
0x180014fde  js      loc_180015429
0x180014fe4  mov     edi, ebx
0x180014fe6  lea     rsi, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180014fed  movsxd  r14, edi
0x180014ff0  cmp     r14, 4
0x180014ff4  jnb     loc_180015424
0x180014ffa  mov     rdx, [rsi]; lpString2
0x180014ffd  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180015005  call    cs:__imp_lstrcmpiW
0x18001500c  nop     dword ptr [rax+rax+00h]
0x180015011  test    eax, eax
0x180015013  jz      short loc_18001501D
0x180015015  inc     edi
0x180015017  add     rsi, 10h
0x18001501b  jmp     short loc_180014FED
0x18001501d  add     r14, r14
0x180015020  lea     rdi, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180015027  movzx   edi, word ptr [rdi+r14*8+8]
0x18001502d  mov     rcx, r15; this
0x180015030  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180015035  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18001503d  mov     rcx, r15; this
0x180015040  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015045  test    eax, eax
0x180015047  js      loc_180015429
0x18001504d  cmp     di, 8
0x180015051  jz      loc_1800153B1
0x180015057  cmp     di, 11h
0x18001505b  jz      loc_180015248
0x180015061  cmp     di, 13h
0x180015065  jz      loc_1800151E9
0x18001506b  mov     eax, 4008h
0x180015070  cmp     di, ax
0x180015073  jnz     loc_18001540E
0x180015079  lea     rcx, [rsp+21E8h+String1]
0x180015081  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180015085  mov     rax, rsi
0x180015088  inc     rax
0x18001508b  cmp     [rcx+rax*2], bx
0x18001508f  jnz     short loc_180015088
0x180015091  mov     r14d, 2
0x180015097  add     eax, r14d
0x18001509a  mov     [rsp+21E8h+var_2158], rbx
0x1800150a2  movsxd  rcx, eax
0x1800150a5  mov     edx, r14d
0x1800150a8  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800150ad  cmp     rax, 100h
0x1800150b3  jbe     short loc_1800150CF
0x1800150b5  mov     rdx, rax
0x1800150b8  lea     rcx, [rsp+21E8h+var_2158]
0x1800150c0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800150c5  mov     rdi, [rsp+21E8h+var_2158]
0x1800150cd  jmp     short loc_1800150DF
0x1800150cf  lea     rdi, [rsp+21E8h+var_2150]
0x1800150d7  mov     [rsp+21E8h+var_2158], rdi
0x1800150df  jmp     short loc_180015107
0x1800150e1  xor     ebx, ebx
0x1800150e3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800150e7  lea     r14d, [rbx+2]
0x1800150eb  mov     rdi, [rsp+21E8h+var_2158]
0x1800150f3  mov     rax, [rsp+21E8h+var_21A0]
0x1800150f8  mov     [rsp+21E8h+var_21A8], rax
0x1800150fd  mov     r12, [rsp+21E8h+var_2198]
0x180015102  mov     r13, [rsp+21E8h+var_2188]
0x180015107  test    rdi, rdi
0x18001510a  jz      loc_1800151D2
0x180015110  lea     r15, [rsp+21E8h+String1]
0x180015118  cmp     [rsp+21E8h+String1], bx
0x180015120  jz      short loc_180015168
0x180015122  mov     rcx, r15; lpsz
0x180015125  call    cs:__imp_CharNextW
0x18001512c  nop     dword ptr [rax+rax+00h]
0x180015131  movzx   ecx, word ptr [r15]
0x180015135  cmp     cx, 5Ch ; '\'
0x180015139  jnz     short loc_180015158
0x18001513b  cmp     word ptr [rax], 30h ; '0'
0x18001513f  jnz     short loc_180015158
0x180015141  mov     [rdi], bx
0x180015144  mov     rcx, rax; lpsz
0x180015147  call    cs:__imp_CharNextW
0x18001514e  nop     dword ptr [rax+rax+00h]
0x180015153  mov     r15, rax
0x180015156  jmp     short loc_18001515E
0x180015158  mov     [rdi], cx
0x18001515b  add     r15, r14
0x18001515e  add     rdi, 2
0x180015162  cmp     [r15], bx
0x180015166  jnz     short loc_180015122
0x180015168  mov     [rdi], bx
0x18001516b  mov     [rdi+r14], bx
0x180015170  mov     r8, [rsp+21E8h+var_2158]
0x180015178  test    r8, r8
0x18001517b  jz      short loc_1800151C7
0x18001517d  mov     r10d, ebx
0x180015180  mov     r9, r8
0x180015183  mov     rcx, rsi
0x180015186  inc     rcx
0x180015189  cmp     [r9+rcx*2], bx
0x18001518e  jnz     short loc_180015186
0x180015190  inc     ecx
0x180015192  lea     r9, [r9+rcx*2]
0x180015196  lea     r10d, [r10+rcx*2]
0x18001519a  cmp     ecx, 1
0x18001519d  jnz     short loc_180015183
0x18001519f  mov     [rsp+21E8h+cbData], r10d; cbData
0x1800151a4  mov     [rsp+21E8h+lpData], r8; lpData
0x1800151a9  lea     r9d, [rcx+6]; dwType
0x1800151ad  xor     r8d, r8d; Reserved
0x1800151b0  mov     rdx, r13; lpValueName
0x1800151b3  mov     rcx, [r12]; hKey
0x1800151b7  call    cs:__imp_RegSetValueExW
0x1800151be  nop     dword ptr [rax+rax+00h]
0x1800151c3  mov     edi, eax
0x1800151c5  jmp     short loc_1800151D7
0x1800151c7  mov     ecx, 80004005h; int
0x1800151cc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800151d2  mov     edi, 0Eh
0x1800151d7  lea     rcx, [rsp+21E8h+var_2158]
0x1800151df  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800151e4  jmp     loc_1800153FC
0x1800151e9  mov     [rsp+21E8h+pulOut], ebx
0x1800151ed  mov     [rsp+21E8h+var_21B0], rbx
0x1800151f2  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x1800151f7  xor     r8d, r8d; dwFlags
0x1800151fa  xor     edx, edx; lcid
0x1800151fc  lea     rcx, [rsp+21E8h+String1]; strIn
0x180015204  call    cs:__imp_VarUI4FromStr
0x18001520b  nop     dword ptr [rax+rax+00h]
0x180015210  mov     edi, eax
0x180015212  test    eax, eax
0x180015214  jns     short loc_180015227
0x180015216  lea     rcx, [rsp+21E8h+var_21B0]
0x18001521b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180015220  mov     eax, edi
0x180015222  jmp     loc_180015429
0x180015227  mov     r8d, [rsp+21E8h+pulOut]; unsigned int
0x18001522c  mov     rdx, r13; unsigned __int16 *
0x18001522f  mov     rcx, r12; this
0x180015232  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180015237  mov     edi, eax
0x180015239  lea     rcx, [rsp+21E8h+var_21B0]
0x18001523e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180015243  jmp     loc_1800153FC
0x180015248  lea     rax, [rsp+21E8h+String1]
0x180015250  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180015254  inc     rsi
0x180015257  cmp     [rax+rsi*2], bx
0x18001525b  jnz     short loc_180015254
0x18001525d  mov     [rsp+21E8h+pulOut], esi
0x180015261  test    sil, 1
0x180015265  jz      short loc_180015271
0x180015267  mov     eax, 80004005h
0x18001526c  jmp     loc_180015429
0x180015271  mov     eax, esi
0x180015273  cdq
0x180015274  mov     r14d, 2
0x18001527a  idiv    r14d
0x18001527d  movsxd  r14, eax
0x180015280  mov     dword ptr [rsp+21E8h+var_21B0], r14d
0x180015285  mov     [rsp+21E8h+var_2158], rbx
0x18001528d  mov     rdi, r14
0x180015290  mov     [rsp+21E8h+var_2178], r14
0x180015295  mov     edx, 1
0x18001529a  mov     rcx, r14
0x18001529d  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800152a2  cmp     rax, 100h
0x1800152a8  jbe     short loc_1800152C4
0x1800152aa  mov     rdx, rax
0x1800152ad  lea     rcx, [rsp+21E8h+var_2158]
0x1800152b5  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800152ba  mov     rcx, [rsp+21E8h+var_2158]
0x1800152c2  jmp     short loc_1800152D4
0x1800152c4  lea     rcx, [rsp+21E8h+var_2150]
0x1800152cc  mov     [rsp+21E8h+var_2158], rcx
0x1800152d4  jmp     short loc_180015302
0x1800152d6  xor     ebx, ebx
0x1800152d8  mov     esi, [rsp+21E8h+pulOut]
0x1800152dc  mov     r14d, dword ptr [rsp+21E8h+var_21B0]
0x1800152e1  mov     rcx, [rsp+21E8h+var_2158]; void *
0x1800152e9  mov     rdi, [rsp+21E8h+var_2178]
0x1800152ee  mov     rax, [rsp+21E8h+var_21A0]
0x1800152f3  mov     [rsp+21E8h+var_21A8], rax
0x1800152f8  mov     r12, [rsp+21E8h+var_2198]
0x1800152fd  mov     r13, [rsp+21E8h+var_2188]
0x180015302  test    rcx, rcx
0x180015305  jnz     short loc_180015319
0x180015307  lea     rcx, [rsp+21E8h+var_2158]
0x18001530f  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180015314  jmp     loc_180015267
0x180015319  mov     r8, rdi; Size
0x18001531c  xor     edx, edx; Val
0x18001531e  call    memset_0
0x180015323  mov     r10d, ebx
0x180015326  movsxd  r11, esi
0x180015329  test    esi, esi
0x18001532b  jle     short loc_180015372
0x18001532d  mov     r9, rbx
0x180015330  movzx   ecx, [rsp+r9*2+21E8h+String1]; unsigned __int16
0x180015339  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18001533e  movzx   r8d, al
0x180015342  mov     eax, r10d
0x180015345  and     eax, 1
0x180015348  shl     eax, 2
0x18001534b  mov     ecx, 4
0x180015350  sub     ecx, eax
0x180015352  shl     r8d, cl
0x180015355  mov     ecx, r10d
0x180015358  shr     rcx, 1
0x18001535b  mov     rax, [rsp+21E8h+var_2158]
0x180015363  or      [rcx+rax], r8b
0x180015367  inc     r10d
0x18001536a  inc     r9
0x18001536d  cmp     r9, r11
0x180015370  jl      short loc_180015330
0x180015372  mov     [rsp+21E8h+cbData], r14d; cbData
0x180015377  mov     rax, [rsp+21E8h+var_2158]
0x18001537f  mov     [rsp+21E8h+lpData], rax; lpData
0x180015384  mov     r9d, 3; dwType
0x18001538a  xor     r8d, r8d; Reserved
0x18001538d  mov     rdx, r13; lpValueName
0x180015390  mov     rcx, [r12]; hKey
0x180015394  call    cs:__imp_RegSetValueExW
0x18001539b  nop     dword ptr [rax+rax+00h]
0x1800153a0  mov     edi, eax
0x1800153a2  lea     rcx, [rsp+21E8h+var_2158]
0x1800153aa  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800153af  jmp     short loc_1800153FC
0x1800153b1  lea     rax, [rsp+21E8h+String1]
0x1800153b9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800153bd  inc     rsi
0x1800153c0  cmp     [rax+rsi*2], bx
0x1800153c4  jnz     short loc_1800153BD
0x1800153c6  lea     eax, ds:2[rsi*2]
0x1800153cd  mov     [rsp+21E8h+cbData], eax; cbData
0x1800153d1  lea     rax, [rsp+21E8h+String1]
0x1800153d9  mov     [rsp+21E8h+lpData], rax; lpData
0x1800153de  mov     r9d, 1; dwType
0x1800153e4  xor     r8d, r8d; Reserved
0x1800153e7  mov     rdx, r13; lpValueName
0x1800153ea  mov     rcx, [r12]; hKey
0x1800153ee  call    cs:__imp_RegSetValueExW
0x1800153f5  nop     dword ptr [rax+rax+00h]
0x1800153fa  mov     edi, eax
0x1800153fc  test    edi, edi
0x1800153fe  jz      short loc_180015409
0x180015400  mov     ecx, edi; unsigned int
0x180015402  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180015407  jmp     short loc_180015429
0x180015409  mov     r15, [rsp+21E8h+var_21A8]
0x18001540e  mov     rdx, [rsp+21E8h+var_2170]; unsigned __int16 *
0x180015413  mov     rcx, r15; this
0x180015416  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001541b  test    eax, eax
0x18001541d  cmovs   ebx, eax
0x180015420  mov     eax, ebx
0x180015422  jmp     short loc_180015429
0x180015424  mov     eax, 80020009h
0x180015429  mov     rcx, [rsp+21E8h+var_48]
0x180015431  xor     rcx, rsp; StackCookie
0x180015434  call    __security_check_cookie
0x180015439  add     rsp, 21B0h
0x180015440  pop     r15
0x180015442  pop     r14
0x180015444  pop     r13
0x180015446  pop     r12
0x180015448  pop     rdi
0x180015449  pop     rsi
0x18001544a  pop     rbx
0x18001544b  retn
```
