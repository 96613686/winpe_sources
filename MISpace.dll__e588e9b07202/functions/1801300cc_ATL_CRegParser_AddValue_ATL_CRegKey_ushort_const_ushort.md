# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1801300cc`
- end: `0x18013049d`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `977`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180132614`

## callees

- `0x180006290`
- `0x180006cf4`
- `0x18012f9ac`
- `0x18012fa80`
- `0x18012fb20`
- `0x1801300cc`
- `0x1801304a4`
- `0x180130620`
- `0x180130728`
- `0x180131d24`
- `0x180132e28`
- `0x1801f2c00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180130299`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180130312`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180130407`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180130451`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180130299`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180130312`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180130407`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180130451`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1801302ce`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1801302ce`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013021a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180130236`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013021a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180130236`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013013a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18013013a`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegParser *v7; // r12
  __int64 result; // rax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r9d
  BYTE *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // ebx
  HRESULT v21; // ebx
  HKEY v22; // rcx
  __int64 v23; // rdi
  size_t v24; // rsi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int i; // r10d
  unsigned __int8 v28; // al
  int v29; // r10d
  char v30; // dl
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdi
  int Token; // eax
  unsigned int v35; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  ATL::CRegParser *v37; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v37 = this;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(v7);
    result = ATL::CRegParser::NextToken(v7, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v33 = -1;
        do
          ++v33;
        while ( String1[v33] );
        v20 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
        goto LABEL_49;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v37 = 0;
          v21 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v21 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
            return (unsigned int)v21;
          }
          v22 = *a2;
          *(_DWORD *)Data = pulOut;
          v20 = RegSetValueExW(v22, a3, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_51:
            Token = ATL::CRegParser::NextToken(v7, a4);
            v35 = 0;
            if ( Token < 0 )
              return (unsigned int)Token;
            return v35;
          }
          lpData = 0;
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v11 + 2, 2);
          if ( v12 <= 0x100 )
          {
            v13 = v40;
            lpData = v40;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
            v13 = lpData;
          }
          if ( v13 )
          {
            v14 = String1;
            if ( String1[0] )
            {
              do
              {
                v15 = CharNextW(v14);
                if ( *v14 == 92 && *v15 == 48 )
                {
                  *(_WORD *)v13 = 0;
                  v14 = CharNextW(v15);
                }
                else
                {
                  *(_WORD *)v13 = *v14++;
                }
                v13 += 2;
              }
              while ( *v14 );
              v7 = v37;
            }
            *(_DWORD *)v13 = 0;
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
            v20 = RegSetValueExW(*a2, a3, 0, 7u, lpData, cbData);
          }
          else
          {
            v20 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_49:
        if ( v20 )
          return ATL::AtlHresultFromWin32(v20);
        goto LABEL_51;
      }
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      if ( (v23 & 1) == 0 )
      {
        lpData = 0;
        v24 = (int)v23 / 2;
        v25 = ATL::AtlMultiplyThrow<unsigned __int64>(v24, 1);
        if ( v25 <= 0x100 )
        {
          v26 = v40;
          lpData = v40;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
          v26 = lpData;
        }
        if ( v26 )
        {
          memset_0(v26, 0, v24);
          for ( i = 0; i < (int)v23; *(_BYTE *)(v32 + v31) |= v28 << (4 - 4 * v30) )
          {
            v28 = ATL::CRegParser::ChToByte(String1[i]);
            v30 = v29 & 1;
            i = v29 + 1;
          }
          v20 = RegSetValueExW(*a2, a3, 0, 3u, lpData, v24);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_49;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801300cc  push    rbp
0x1801300ce  push    rbx
0x1801300cf  push    rsi
0x1801300d0  push    rdi
0x1801300d1  push    r12
0x1801300d3  push    r13
0x1801300d5  push    r14
0x1801300d7  push    r15
0x1801300d9  lea     rbp, [rsp-2078h]
0x1801300e1  mov     eax, 2178h
0x1801300e6  call    _alloca_probe
0x1801300eb  sub     rsp, rax
0x1801300ee  mov     rax, cs:__security_cookie
0x1801300f5  xor     rax, rsp
0x1801300f8  mov     [rbp+20B0h+var_50], rax
0x1801300ff  mov     r14, rdx
0x180130102  mov     [rsp+21B0h+var_2178], rcx
0x180130107  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18013010b  mov     r13, r9
0x18013010e  mov     r15, r8
0x180130111  mov     r12, rcx
0x180130114  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180130119  xor     esi, esi
0x18013011b  test    eax, eax
0x18013011d  js      loc_18013047A
0x180130123  mov     ebx, esi
0x180130125  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18013012c  movsxd  rdi, ebx
0x18013012f  lea     rcx, [rbp+20B0h+String1]; lpString1
0x180130133  add     rdi, rdi
0x180130136  mov     rdx, [rax+rdi*8]; lpString2
0x18013013a  call    cs:__imp_lstrcmpiW
0x180130140  test    eax, eax
0x180130142  jz      short loc_18013015C
0x180130144  inc     ebx
0x180130146  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18013014d  cmp     ebx, 4
0x180130150  jb      short loc_18013012C
0x180130152  mov     eax, 80020009h
0x180130157  jmp     loc_18013047A
0x18013015c  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180130163  mov     rcx, r12; this
0x180130166  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18013016b  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180130170  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180130174  mov     rcx, r12; this
0x180130177  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18013017c  test    eax, eax
0x18013017e  js      loc_18013047A
0x180130184  cmp     bx, 8
0x180130188  jz      loc_18013041D
0x18013018e  cmp     bx, 11h
0x180130192  jz      loc_180130329
0x180130198  cmp     bx, 13h
0x18013019c  jz      loc_1801302B7
0x1801301a2  mov     eax, 4008h
0x1801301a7  cmp     bx, ax
0x1801301aa  jnz     loc_180130466
0x1801301b0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801301b4  mov     [rsp+21B0h+var_2160], rsi
0x1801301b9  mov     rax, rdi
0x1801301bc  lea     rcx, [rbp+20B0h+String1]
0x1801301c0  inc     rax
0x1801301c3  cmp     [rcx+rax*2], si
0x1801301c7  jnz     short loc_1801301C0
0x1801301c9  add     eax, 2
0x1801301cc  mov     edx, 2
0x1801301d1  movsxd  rcx, eax
0x1801301d4  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1801301d9  cmp     rax, 100h
0x1801301df  jbe     short loc_1801301F5
0x1801301e1  mov     rdx, rax
0x1801301e4  lea     rcx, [rsp+21B0h+var_2160]
0x1801301e9  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1801301ee  mov     rbx, [rsp+21B0h+var_2160]
0x1801301f3  jmp     short loc_1801301FF
0x1801301f5  lea     rbx, [rsp+21B0h+var_2158]
0x1801301fa  mov     [rsp+21B0h+var_2160], rbx
0x1801301ff  test    rbx, rbx
0x180130202  jz      loc_1801302A3
0x180130208  xor     eax, eax
0x18013020a  lea     rsi, [rbp+20B0h+String1]
0x18013020e  cmp     [rbp+20B0h+String1], ax
0x180130212  jz      short loc_180130257
0x180130214  xor     r12d, r12d
0x180130217  mov     rcx, rsi; lpsz
0x18013021a  call    cs:__imp_CharNextW
0x180130220  movzx   ecx, word ptr [rsi]
0x180130223  cmp     cx, 5Ch ; '\'
0x180130227  jnz     short loc_180130241
0x180130229  cmp     word ptr [rax], 30h ; '0'
0x18013022d  jnz     short loc_180130241
0x18013022f  mov     rcx, rax; lpsz
0x180130232  mov     [rbx], r12w
0x180130236  call    cs:__imp_CharNextW
0x18013023c  mov     rsi, rax
0x18013023f  jmp     short loc_180130248
0x180130241  mov     [rbx], cx
0x180130244  add     rsi, 2
0x180130248  add     rbx, 2
0x18013024c  cmp     [rsi], r12w
0x180130250  jnz     short loc_180130217
0x180130252  mov     r12, [rsp+21B0h+var_2178]
0x180130257  xor     esi, esi
0x180130259  mov     [rbx], esi
0x18013025b  mov     r9d, esi
0x18013025e  mov     r10, [rsp+21B0h+var_2160]
0x180130263  mov     r8, r10
0x180130266  mov     rcx, rdi
0x180130269  inc     rcx
0x18013026c  cmp     [r8+rcx*2], si
0x180130271  jnz     short loc_180130269
0x180130273  inc     ecx
0x180130275  lea     r8, [r8+rcx*2]
0x180130279  lea     r9d, [r9+rcx*2]
0x18013027d  cmp     ecx, 1
0x180130280  jnz     short loc_180130266
0x180130282  mov     [rsp+21B0h+cbData], r9d; cbData
0x180130287  xor     r8d, r8d; Reserved
0x18013028a  lea     r9d, [rcx+6]; dwType
0x18013028e  mov     [rsp+21B0h+lpData], r10; lpData
0x180130293  mov     rcx, [r14]; hKey
0x180130296  mov     rdx, r15; lpValueName
0x180130299  call    cs:__imp_RegSetValueExW
0x18013029f  mov     ebx, eax
0x1801302a1  jmp     short loc_1801302A8
0x1801302a3  mov     ebx, 0Eh
0x1801302a8  lea     rcx, [rsp+21B0h+var_2160]
0x1801302ad  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1801302b2  jmp     loc_180130459
0x1801302b7  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x1801302bc  mov     [rsp+21B0h+pulOut], esi
0x1801302c0  xor     r8d, r8d; dwFlags
0x1801302c3  mov     [rsp+21B0h+var_2178], rsi
0x1801302c8  xor     edx, edx; lcid
0x1801302ca  lea     rcx, [rbp+20B0h+String1]; strIn
0x1801302ce  call    cs:__imp_VarUI4FromStr
0x1801302d4  mov     ebx, eax
0x1801302d6  test    eax, eax
0x1801302d8  jns     short loc_1801302EB
0x1801302da  lea     rcx, [rsp+21B0h+var_2178]
0x1801302df  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1801302e4  mov     eax, ebx
0x1801302e6  jmp     loc_18013047A
0x1801302eb  mov     eax, [rsp+21B0h+pulOut]
0x1801302ef  mov     ecx, 4
0x1801302f4  mov     [rsp+21B0h+cbData], ecx; cbData
0x1801302f8  mov     r9d, ecx; dwType
0x1801302fb  mov     rcx, [r14]; hKey
0x1801302fe  xor     r8d, r8d; Reserved
0x180130301  mov     dword ptr [rsp+21B0h+Data], eax
0x180130305  mov     rdx, r15; lpValueName
0x180130308  lea     rax, [rsp+21B0h+Data]
0x18013030d  mov     [rsp+21B0h+lpData], rax; lpData
0x180130312  call    cs:__imp_RegSetValueExW
0x180130318  lea     rcx, [rsp+21B0h+var_2178]
0x18013031d  mov     ebx, eax
0x18013031f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180130324  jmp     loc_180130459
0x180130329  lea     rax, [rbp+20B0h+String1]
0x18013032d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180130331  inc     rdi
0x180130334  cmp     [rax+rdi*2], si
0x180130338  jnz     short loc_180130331
0x18013033a  test    dil, 1
0x18013033e  jz      short loc_18013034A
0x180130340  mov     eax, 80004005h
0x180130345  jmp     loc_18013047A
0x18013034a  mov     eax, edi
0x18013034c  mov     [rsp+21B0h+var_2160], 0
0x180130355  cdq
0x180130356  sub     eax, edx
0x180130358  mov     edx, 1
0x18013035d  sar     eax, 1
0x18013035f  movsxd  rsi, eax
0x180130362  mov     rcx, rsi
0x180130365  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18013036a  cmp     rax, 100h
0x180130370  jbe     short loc_180130386
0x180130372  mov     rdx, rax
0x180130375  lea     rcx, [rsp+21B0h+var_2160]
0x18013037a  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18013037f  mov     rcx, [rsp+21B0h+var_2160]
0x180130384  jmp     short loc_180130390
0x180130386  lea     rcx, [rsp+21B0h+var_2158]; void *
0x18013038b  mov     [rsp+21B0h+var_2160], rcx
0x180130390  test    rcx, rcx
0x180130393  jnz     short loc_1801303A1
0x180130395  lea     rcx, [rsp+21B0h+var_2160]
0x18013039a  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18013039f  jmp     short loc_180130340
0x1801303a1  mov     r8, rsi; Size
0x1801303a4  xor     edx, edx; Val
0x1801303a6  call    memset_0
0x1801303ab  xor     eax, eax
0x1801303ad  mov     r10d, eax
0x1801303b0  test    edi, edi
0x1801303b2  jle     short loc_1801303EA
0x1801303b4  mov     r8, [rsp+21B0h+var_2160]
0x1801303b9  mov     ecx, r10d
0x1801303bc  mov     r9d, r10d
0x1801303bf  shr     r9, 1
0x1801303c2  movzx   ecx, [rbp+rcx*2+20B0h+String1]; unsigned __int16
0x1801303c7  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x1801303cc  mov     edx, r10d
0x1801303cf  mov     ecx, 4
0x1801303d4  and     edx, 1
0x1801303d7  inc     r10d
0x1801303da  shl     edx, 2
0x1801303dd  sub     ecx, edx
0x1801303df  shl     al, cl
0x1801303e1  or      [r9+r8], al
0x1801303e5  cmp     r10d, edi
0x1801303e8  jl      short loc_1801303B4
0x1801303ea  mov     rax, [rsp+21B0h+var_2160]
0x1801303ef  mov     r9d, 3; dwType
0x1801303f5  mov     rcx, [r14]; hKey
0x1801303f8  xor     r8d, r8d; Reserved
0x1801303fb  mov     [rsp+21B0h+cbData], esi; cbData
0x1801303ff  mov     rdx, r15; lpValueName
0x180130402  mov     [rsp+21B0h+lpData], rax; lpData
0x180130407  call    cs:__imp_RegSetValueExW
0x18013040d  lea     rcx, [rsp+21B0h+var_2160]
0x180130412  mov     ebx, eax
0x180130414  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180130419  xor     esi, esi
0x18013041b  jmp     short loc_180130459
0x18013041d  lea     rax, [rbp+20B0h+String1]
0x180130421  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180130425  inc     rdi
0x180130428  cmp     [rax+rdi*2], si
0x18013042c  jnz     short loc_180130425
0x18013042e  mov     rcx, [r14]; hKey
0x180130431  lea     eax, ds:2[rdi*2]
0x180130438  mov     [rsp+21B0h+cbData], eax; cbData
0x18013043c  mov     r9d, 1; dwType
0x180130442  lea     rax, [rbp+20B0h+String1]
0x180130446  xor     r8d, r8d; Reserved
0x180130449  mov     rdx, r15; lpValueName
0x18013044c  mov     [rsp+21B0h+lpData], rax; lpData
0x180130451  call    cs:__imp_RegSetValueExW
0x180130457  mov     ebx, eax
0x180130459  test    ebx, ebx
0x18013045b  jz      short loc_180130466
0x18013045d  mov     ecx, ebx; unsigned int
0x18013045f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180130464  jmp     short loc_18013047A
0x180130466  mov     rdx, r13; unsigned __int16 *
0x180130469  mov     rcx, r12; this
0x18013046c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180130471  test    eax, eax
0x180130473  mov     ecx, esi
0x180130475  cmovs   ecx, eax
0x180130478  mov     eax, ecx
0x18013047a  mov     rcx, [rbp+20B0h+var_50]
0x180130481  xor     rcx, rsp; StackCookie
0x180130484  call    __security_check_cookie
0x180130489  add     rsp, 2178h
0x180130490  pop     r15
0x180130492  pop     r14
0x180130494  pop     r13
0x180130496  pop     r12
0x180130498  pop     rdi
0x180130499  pop     rsi
0x18013049a  pop     rbx
0x18013049b  pop     rbp
0x18013049c  retn
```
