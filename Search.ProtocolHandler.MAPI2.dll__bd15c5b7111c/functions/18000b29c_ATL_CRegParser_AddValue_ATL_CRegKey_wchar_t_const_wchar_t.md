# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x18000b29c`
- end: `0x18000b77a`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1246`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18000d0b8`

## callees

- `0x180002300`
- `0x18000306c`
- `0x18000aa18`
- `0x18000ac10`
- `0x18000ad38`
- `0x18000b29c`
- `0x18000b780`
- `0x18000ba14`
- `0x18000c740`
- `0x18000d7c0`
- `0x18000d7f4`
- `0x18000d8f4`
- `0x18003a060`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000b4b9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000b4b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b324`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b324`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b6d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b727`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b6d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b727`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b431`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b44c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b431`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b44c`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(ATL::CRegParser *this, HKEY *a2, const wchar_t *a3, wchar_t *a4)
{
  const WCHAR *v4; // r13
  HKEY *v5; // r12
  ATL::CRegParser *v6; // r14
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  WCHAR *j; // rsi
  const WCHAR *v15; // rax
  LSTATUS v16; // edi
  HRESULT v17; // edi
  __int64 v18; // rdi
  DWORD cbData; // r14d
  size_t v20; // rsi
  unsigned __int64 v21; // rax
  BYTE *v22; // rcx
  unsigned int v23; // r10d
  unsigned int v24; // edx
  char v25; // r9
  __int64 v26; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21A8h] BYREF
  _QWORD v29[2]; // [rsp+38h] [rbp-21A0h] BYREF
  ATL::CRegParser *v30; // [rsp+48h] [rbp-2190h]
  struct ATL::CRegKey *v31; // [rsp+50h] [rbp-2188h]
  const wchar_t *v32; // [rsp+60h] [rbp-2178h]
  size_t v33; // [rsp+70h] [rbp-2168h]
  wchar_t *v34; // [rsp+78h] [rbp-2160h]
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v36[264]; // [rsp+88h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v29[0] = this;
  v30 = this;
  v31 = (struct ATL::CRegKey *)a2;
  v32 = a3;
  v34 = a4;
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
      v26 = -1;
      do
        ++v26;
      while ( String1[v26] );
      v16 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v26 + 2);
      goto LABEL_72;
    case 17:
      v18 = -1;
      do
        ++v18;
      while ( String1[v18] );
      pulOut = v18;
      if ( (v18 & 1) != 0 )
        return 2147500037LL;
      cbData = (int)v18 / 2;
      lpData = 0;
      v20 = (int)v18 / 2;
      v33 = v20;
      try
      {
        v21 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v21 <= 0x100 )
        {
          v22 = v36;
          lpData = v36;
        }
        else
        {
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v21);
          v22 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v18) = pulOut;
        v22 = lpData;
        v20 = v33;
        v29[0] = v30;
        v5 = (HKEY *)v31;
        v4 = v32;
        cbData = v33;
      }
      if ( !v22 )
      {
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v22, 0, v20);
      v23 = 0;
      if ( (int)v18 <= 0 )
      {
LABEL_68:
        v16 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_27;
      }
      while ( 1 )
      {
        v24 = String1[v23];
        if ( v24 > 0x61 )
        {
          if ( v24 == 98 || v24 == 99 || v24 == 100 || v24 - 101 < 2 )
          {
LABEL_66:
            v25 = v24 - 87;
            goto LABEL_67;
          }
LABEL_65:
          v25 = 0;
          goto LABEL_67;
        }
        if ( v24 == 97 )
          goto LABEL_66;
        if ( v24 <= 0x38 )
          break;
        if ( v24 == 57 )
          goto LABEL_53;
        if ( v24 != 65 && v24 != 66 && v24 != 67 && v24 != 68 && v24 - 69 > 1 )
          goto LABEL_65;
        v25 = v24 - 55;
LABEL_67:
        lpData[(unsigned __int64)v23 >> 1] |= v25 << (4 - 4 * (v23 & 1));
        if ( (int)++v23 >= (int)v18 )
          goto LABEL_68;
      }
      if ( v24 != 56 && v24 != 48 && v24 != 49 && v24 != 50 && v24 != 51 && v24 != 52 && v24 != 53 && v24 - 54 > 1 )
        goto LABEL_65;
LABEL_53:
      v25 = v24 - 48;
      goto LABEL_67;
    case 19:
      pulOut = 0;
      v29[0] = 0;
      v17 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v17 >= 0 )
      {
        v16 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v5, v4, pulOut);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v29);
        goto LABEL_72;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v29);
      return (unsigned int)v17;
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
          v13 = v36;
          lpData = v36;
        }
        else
        {
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
          v13 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        v13 = lpData;
        v29[0] = v30;
        v5 = (HKEY *)v31;
        v4 = v32;
      }
      if ( v13 )
      {
        for ( j = String1; *j; v13 += 2 )
        {
          v15 = CharNextW(j);
          if ( *j == 92 && *v15 == 48 )
          {
            *(_WORD *)v13 = 0;
            j = CharNextW(v15);
          }
          else
          {
            *(_WORD *)v13 = *j++;
          }
        }
        *(_DWORD *)v13 = 0;
        v16 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)v5, v4, (const wchar_t *)lpData);
      }
      else
      {
        v16 = 14;
      }
      ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
LABEL_27:
      v6 = (ATL::CRegParser *)v29[0];
LABEL_72:
      if ( v16 )
      {
        return ATL::AtlHresultFromWin32(v16);
      }
      else
      {
LABEL_74:
        Token = ATL::CRegParser::NextToken(v6, v34);
        if ( Token < 0 )
          return (unsigned int)Token;
        return v8;
      }
    default:
      goto LABEL_74;
  }
}

```

## disassembly

```asm
0x18000b29c  push    rbx
0x18000b29e  push    rsi
0x18000b29f  push    rdi
0x18000b2a0  push    r12
0x18000b2a2  push    r13
0x18000b2a4  push    r14
0x18000b2a6  push    r15
0x18000b2a8  mov     eax, 21A0h
0x18000b2ad  call    _alloca_probe
0x18000b2b2  sub     rsp, rax
0x18000b2b5  mov     rax, cs:__security_cookie
0x18000b2bc  xor     rax, rsp
0x18000b2bf  mov     [rsp+21D8h+var_48], rax
0x18000b2c7  mov     r13, r8
0x18000b2ca  mov     r12, rdx
0x18000b2cd  mov     r14, rcx
0x18000b2d0  mov     [rsp+21D8h+var_21A0], rcx
0x18000b2d5  mov     [rsp+21D8h+var_2190], rcx
0x18000b2da  mov     [rsp+21D8h+var_2188], rdx
0x18000b2df  mov     [rsp+21D8h+var_2178], r8
0x18000b2e4  mov     [rsp+21D8h+var_2160], r9
0x18000b2e9  lea     rdx, [rsp+21D8h+String1]; wchar_t *
0x18000b2f1  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000b2f6  xor     ebx, ebx
0x18000b2f8  test    eax, eax
0x18000b2fa  js      loc_18000B757
0x18000b300  mov     edi, ebx
0x18000b302  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18000b309  cmp     edi, 4
0x18000b30c  jnb     loc_18000B752
0x18000b312  movsxd  rsi, edi
0x18000b315  add     rsi, rsi
0x18000b318  mov     rdx, [r15+rsi*8]; lpString2
0x18000b31c  lea     rcx, [rsp+21D8h+String1]; lpString1
0x18000b324  call    cs:__imp_lstrcmpiW
0x18000b32a  test    eax, eax
0x18000b32c  jz      short loc_18000B332
0x18000b32e  inc     edi
0x18000b330  jmp     short loc_18000B309
0x18000b332  movzx   edi, word ptr [r15+rsi*8+8]
0x18000b338  mov     rcx, r14; this
0x18000b33b  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000b340  lea     rdx, [rsp+21D8h+String1]; wchar_t *
0x18000b348  mov     rcx, r14; this
0x18000b34b  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000b350  test    eax, eax
0x18000b352  js      loc_18000B757
0x18000b358  mov     r15d, 8
0x18000b35e  cmp     di, r15w
0x18000b362  jz      loc_18000B6EA
0x18000b368  cmp     di, 11h
0x18000b36c  jz      loc_18000B4F7
0x18000b372  cmp     di, 13h
0x18000b376  jz      loc_18000B49E
0x18000b37c  mov     eax, 4008h
0x18000b381  cmp     di, ax
0x18000b384  jnz     loc_18000B73C
0x18000b38a  lea     rax, [rsp+21D8h+String1]
0x18000b392  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b396  inc     rdi
0x18000b399  cmp     [rax+rdi*2], bx
0x18000b39d  jnz     short loc_18000B396
0x18000b39f  add     edi, 2
0x18000b3a2  mov     [rsp+21D8h+var_2158], rbx
0x18000b3aa  movsxd  rcx, edi
0x18000b3ad  mov     r14d, 2
0x18000b3b3  mov     edx, r14d
0x18000b3b6  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000b3bb  cmp     rax, 100h
0x18000b3c1  jbe     short loc_18000B3DD
0x18000b3c3  mov     rdx, rax
0x18000b3c6  lea     rcx, [rsp+21D8h+var_2158]
0x18000b3ce  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000b3d3  mov     rdi, [rsp+21D8h+var_2158]
0x18000b3db  jmp     short loc_18000B3ED
0x18000b3dd  lea     rdi, [rsp+21D8h+var_2150]
0x18000b3e5  mov     [rsp+21D8h+var_2158], rdi
0x18000b3ed  jmp     short loc_18000B411
0x18000b3ef  xor     ebx, ebx
0x18000b3f1  lea     r14d, [rbx+2]
0x18000b3f5  mov     rdi, [rsp+21D8h+var_2158]
0x18000b3fd  mov     rax, [rsp+21D8h+var_2190]
0x18000b402  mov     [rsp+21D8h+var_21A0], rax
0x18000b407  mov     r12, [rsp+21D8h+var_2188]
0x18000b40c  mov     r13, [rsp+21D8h+var_2178]
0x18000b411  test    rdi, rdi
0x18000b414  jz      short loc_18000B482
0x18000b416  lea     rsi, [rsp+21D8h+String1]
0x18000b41e  cmp     [rsp+21D8h+String1], bx
0x18000b426  jz      short loc_18000B465
0x18000b428  mov     r15d, 30h ; '0'
0x18000b42e  mov     rcx, rsi; lpsz
0x18000b431  call    cs:__imp_CharNextW
0x18000b437  movzx   ecx, word ptr [rsi]
0x18000b43a  cmp     cx, 5Ch ; '\'
0x18000b43e  jnz     short loc_18000B457
0x18000b440  cmp     [rax], r15w
0x18000b444  jnz     short loc_18000B457
0x18000b446  mov     [rdi], bx
0x18000b449  mov     rcx, rax; lpsz
0x18000b44c  call    cs:__imp_CharNextW
0x18000b452  mov     rsi, rax
0x18000b455  jmp     short loc_18000B45D
0x18000b457  mov     [rdi], cx
0x18000b45a  add     rsi, r14
0x18000b45d  add     rdi, r14
0x18000b460  cmp     [rsi], bx
0x18000b463  jnz     short loc_18000B42E
0x18000b465  mov     dword ptr [rdi], 0
0x18000b46b  mov     r8, [rsp+21D8h+var_2158]; wchar_t *
0x18000b473  mov     rdx, r13; wchar_t *
0x18000b476  mov     rcx, r12; this
0x18000b479  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEB_W0@Z; ATL::CRegKey::SetMultiStringValue(wchar_t const *,wchar_t const *)
0x18000b47e  mov     edi, eax
0x18000b480  jmp     short loc_18000B487
0x18000b482  mov     edi, 0Eh
0x18000b487  lea     rcx, [rsp+21D8h+var_2158]
0x18000b48f  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000b494  mov     r14, [rsp+21D8h+var_21A0]
0x18000b499  jmp     loc_18000B72F
0x18000b49e  mov     [rsp+21D8h+pulOut], ebx
0x18000b4a2  mov     [rsp+21D8h+var_21A0], rbx
0x18000b4a7  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x18000b4ac  xor     r8d, r8d; dwFlags
0x18000b4af  xor     edx, edx; lcid
0x18000b4b1  lea     rcx, [rsp+21D8h+String1]; strIn
0x18000b4b9  call    cs:__imp_VarUI4FromStr
0x18000b4bf  mov     edi, eax
0x18000b4c1  test    eax, eax
0x18000b4c3  jns     short loc_18000B4D6
0x18000b4c5  lea     rcx, [rsp+21D8h+var_21A0]
0x18000b4ca  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b4cf  mov     eax, edi
0x18000b4d1  jmp     loc_18000B757
0x18000b4d6  mov     r8d, [rsp+21D8h+pulOut]; unsigned int
0x18000b4db  mov     rdx, r13; wchar_t *
0x18000b4de  mov     rcx, r12; this
0x18000b4e1  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEB_WK@Z; ATL::CRegKey::SetDWORDValue(wchar_t const *,ulong)
0x18000b4e6  mov     edi, eax
0x18000b4e8  lea     rcx, [rsp+21D8h+var_21A0]
0x18000b4ed  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b4f2  jmp     loc_18000B72F
0x18000b4f7  lea     rax, [rsp+21D8h+String1]
0x18000b4ff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b503  inc     rdi
0x18000b506  cmp     [rax+rdi*2], bx
0x18000b50a  jnz     short loc_18000B503
0x18000b50c  mov     [rsp+21D8h+pulOut], edi
0x18000b510  test    dil, 1
0x18000b514  jz      short loc_18000B520
0x18000b516  mov     eax, 80004005h
0x18000b51b  jmp     loc_18000B757
0x18000b520  mov     eax, edi
0x18000b522  cdq
0x18000b523  mov     r14d, 2
0x18000b529  idiv    r14d
0x18000b52c  movsxd  r14, eax
0x18000b52f  mov     [rsp+21D8h+var_2158], rbx
0x18000b537  mov     rsi, r14
0x18000b53a  mov     [rsp+21D8h+var_2168], r14
0x18000b53f  mov     edx, 1
0x18000b544  mov     rcx, r14
0x18000b547  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000b54c  cmp     rax, 100h
0x18000b552  jbe     short loc_18000B56E
0x18000b554  mov     rdx, rax
0x18000b557  lea     rcx, [rsp+21D8h+var_2158]
0x18000b55f  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000b564  mov     rcx, [rsp+21D8h+var_2158]
0x18000b56c  jmp     short loc_18000B57E
0x18000b56e  lea     rcx, [rsp+21D8h+var_2150]
0x18000b576  mov     [rsp+21D8h+var_2158], rcx
0x18000b57e  jmp     short loc_18000B5AA
0x18000b580  xor     ebx, ebx
0x18000b582  mov     edi, [rsp+21D8h+pulOut]
0x18000b586  mov     rcx, [rsp+21D8h+var_2158]; void *
0x18000b58e  mov     rsi, [rsp+21D8h+var_2168]
0x18000b593  mov     rax, [rsp+21D8h+var_2190]
0x18000b598  mov     [rsp+21D8h+var_21A0], rax
0x18000b59d  mov     r12, [rsp+21D8h+var_2188]
0x18000b5a2  mov     r13, [rsp+21D8h+var_2178]
0x18000b5a7  mov     r14d, esi
0x18000b5aa  test    rcx, rcx
0x18000b5ad  jnz     short loc_18000B5C1
0x18000b5af  lea     rcx, [rsp+21D8h+var_2158]
0x18000b5b7  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000b5bc  jmp     loc_18000B516
0x18000b5c1  mov     r8, rsi; Size
0x18000b5c4  xor     edx, edx; Val
0x18000b5c6  call    memset_0
0x18000b5cb  mov     r10d, ebx
0x18000b5ce  test    edi, edi
0x18000b5d0  jle     loc_18000B6AE
0x18000b5d6  mov     r15d, 30h ; '0'
0x18000b5dc  mov     eax, r10d
0x18000b5df  movzx   edx, [rsp+rax*2+21D8h+String1]
0x18000b5e7  cmp     edx, 61h ; 'a'
0x18000b5ea  ja      short loc_18000B659
0x18000b5ec  jz      loc_18000B679
0x18000b5f2  cmp     edx, 38h ; '8'
0x18000b5f5  ja      short loc_18000B62B
0x18000b5f7  jz      short loc_18000B623
0x18000b5f9  mov     ecx, edx
0x18000b5fb  sub     ecx, r15d
0x18000b5fe  jz      short loc_18000B623
0x18000b600  sub     ecx, 1
0x18000b603  jz      short loc_18000B623
0x18000b605  sub     ecx, 1
0x18000b608  jz      short loc_18000B623
0x18000b60a  sub     ecx, 1
0x18000b60d  jz      short loc_18000B623
0x18000b60f  sub     ecx, 1
0x18000b612  jz      short loc_18000B623
0x18000b614  sub     ecx, 1
0x18000b617  jz      short loc_18000B623
0x18000b619  sub     ecx, 1
0x18000b61c  jz      short loc_18000B623
0x18000b61e  cmp     ecx, 1
0x18000b621  jnz     short loc_18000B674
0x18000b623  mov     r9d, edx
0x18000b626  sub     r9d, r15d
0x18000b629  jmp     short loc_18000B67D
0x18000b62b  mov     r9d, edx
0x18000b62e  mov     ecx, edx
0x18000b630  sub     ecx, 39h ; '9'
0x18000b633  jz      short loc_18000B623
0x18000b635  sub     ecx, 8
0x18000b638  jz      short loc_18000B653
0x18000b63a  sub     ecx, 1
0x18000b63d  jz      short loc_18000B653
0x18000b63f  sub     ecx, 1
0x18000b642  jz      short loc_18000B653
0x18000b644  sub     ecx, 1
0x18000b647  jz      short loc_18000B653
0x18000b649  sub     ecx, 1
0x18000b64c  jz      short loc_18000B653
0x18000b64e  cmp     ecx, 1
0x18000b651  jnz     short loc_18000B674
0x18000b653  add     r9d, 0FFFFFFC9h
0x18000b657  jmp     short loc_18000B67D
0x18000b659  mov     ecx, edx
0x18000b65b  sub     ecx, 62h ; 'b'
0x18000b65e  jz      short loc_18000B679
0x18000b660  sub     ecx, 1
0x18000b663  jz      short loc_18000B679
0x18000b665  sub     ecx, 1
0x18000b668  jz      short loc_18000B679
0x18000b66a  sub     ecx, 1
0x18000b66d  jz      short loc_18000B679
0x18000b66f  cmp     ecx, 1
0x18000b672  jz      short loc_18000B679
0x18000b674  mov     r9d, ebx
0x18000b677  jmp     short loc_18000B67D
0x18000b679  lea     r9d, [rdx-57h]
0x18000b67d  mov     r8d, r10d
0x18000b680  shr     r8, 1
0x18000b683  mov     rdx, [rsp+21D8h+var_2158]
0x18000b68b  mov     eax, r10d
0x18000b68e  and     eax, 1
0x18000b691  shl     eax, 2
0x18000b694  mov     ecx, 4
0x18000b699  sub     ecx, eax
0x18000b69b  shl     r9b, cl
0x18000b69e  or      [r8+rdx], r9b
0x18000b6a2  inc     r10d
0x18000b6a5  cmp     r10d, edi
0x18000b6a8  jl      loc_18000B5DC
0x18000b6ae  mov     rax, [rsp+21D8h+var_2158]
0x18000b6b6  mov     [rsp+21D8h+cbData], r14d; cbData
0x18000b6bb  mov     [rsp+21D8h+lpData], rax; lpData
0x18000b6c0  mov     r9d, 3; dwType
0x18000b6c6  xor     r8d, r8d; Reserved
0x18000b6c9  mov     rdx, r13; lpValueName
0x18000b6cc  mov     rcx, [r12]; hKey
0x18000b6d0  call    cs:__imp_RegSetValueExW
0x18000b6d6  mov     edi, eax
0x18000b6d8  lea     rcx, [rsp+21D8h+var_2158]
0x18000b6e0  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000b6e5  jmp     loc_18000B494
0x18000b6ea  lea     rax, [rsp+21D8h+String1]
0x18000b6f2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b6f6  inc     rdi
0x18000b6f9  cmp     [rax+rdi*2], bx
0x18000b6fd  jnz     short loc_18000B6F6
0x18000b6ff  lea     eax, ds:2[rdi*2]
0x18000b706  mov     [rsp+21D8h+cbData], eax; cbData
0x18000b70a  lea     rax, [rsp+21D8h+String1]
0x18000b712  mov     [rsp+21D8h+lpData], rax; lpData
0x18000b717  mov     r9d, 1; dwType
0x18000b71d  xor     r8d, r8d; Reserved
0x18000b720  mov     rdx, r13; lpValueName
0x18000b723  mov     rcx, [r12]; hKey
0x18000b727  call    cs:__imp_RegSetValueExW
0x18000b72d  mov     edi, eax
0x18000b72f  test    edi, edi
0x18000b731  jz      short loc_18000B73C
0x18000b733  mov     ecx, edi; unsigned int
0x18000b735  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000b73a  jmp     short loc_18000B757
0x18000b73c  mov     rdx, [rsp+21D8h+var_2160]; wchar_t *
  ... truncated ...
```
