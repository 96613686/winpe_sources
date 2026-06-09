# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1801f2bf0`
- end: `0x1801f2fe3`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1011`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1801f56c8`

## callees

- `0x1801e8320`
- `0x1801e9258`
- `0x1801ef320`
- `0x1801f1a5c`
- `0x1801f1dfc`
- `0x1801f20b8`
- `0x1801f2bf0`
- `0x1801f2fec`
- `0x1801f3344`
- `0x1801f3bec`
- `0x1801f4ac0`
- `0x1801f6280`
- `0x1801f6440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801f2e1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801f2f47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801f2f97`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801f2e1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801f2f47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801f2f97`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f2d59`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f2d74`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f2d59`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801f2d74`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f2c6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f2c6a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1801f2dd8`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1801f2dd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r12
  HKEY *v5; // r15
  ATL::CRegParser *v6; // r13
  __int64 result; // rax
  unsigned int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  WCHAR *i; // rsi
  const WCHAR *v15; // rax
  LSTATUS v16; // edi
  HRESULT v17; // edi
  __int64 v18; // rdi
  DWORD cbData; // esi
  size_t v20; // r14
  unsigned __int64 v21; // rax
  BYTE *v22; // rcx
  int j; // r10d
  unsigned __int8 v24; // al
  int v25; // r10d
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-2198h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-2190h] BYREF
  ATL::CRegParser *v32; // [rsp+40h] [rbp-2188h] BYREF
  struct ATL::CRegKey *v33; // [rsp+48h] [rbp-2180h]
  const unsigned __int16 *v34; // [rsp+50h] [rbp-2178h]
  size_t v35; // [rsp+60h] [rbp-2168h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-2160h]
  BYTE *lpData; // [rsp+70h] [rbp-2158h] BYREF
  _BYTE v38[264]; // [rsp+78h] [rbp-2150h] BYREF
  WCHAR String1[4096]; // [rsp+180h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v32 = this;
  v33 = (struct ATL::CRegKey *)a2;
  v34 = a3;
  v36 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(v6);
    result = ATL::CRegParser::NextToken(v6, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v28 = -1;
        do
          ++v28;
        while ( String1[v28] );
        v16 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v28 + 2);
        goto LABEL_46;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v32 = 0;
          v17 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v17 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
            return (unsigned int)v17;
          }
          *(_DWORD *)Data = pulOut;
          v16 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_48:
            Token = ATL::CRegParser::NextToken(v6, v36);
            if ( Token < 0 )
              return (unsigned int)Token;
            return v8;
          }
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
              v13 = v38;
              lpData = v38;
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
            v6 = v32;
            v5 = (HKEY *)v33;
            v4 = v34;
          }
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v15 = CharNextW(i);
              if ( *i == 92 && *v15 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v15);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            v16 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)v5, v4, (const unsigned __int16 *)lpData);
          }
          else
          {
            v16 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_46:
        if ( v16 )
          return ATL::AtlHresultFromWin32(v16);
        goto LABEL_48;
      }
      v18 = -1;
      do
        ++v18;
      while ( String1[v18] );
      *(_DWORD *)Data = v18;
      if ( (v18 & 1) == 0 )
      {
        cbData = (int)v18 / 2;
        lpData = 0;
        v20 = (int)v18 / 2;
        v35 = v20;
        try
        {
          v21 = ATL::AtlMultiplyThrow<unsigned __int64>();
          if ( v21 <= 0x100 )
          {
            v22 = v38;
            lpData = v38;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v21);
            v22 = lpData;
          }
        }
        catch ( ... )
        {
          v8 = 0;
          LODWORD(v18) = *(_DWORD *)Data;
          v22 = lpData;
          v20 = v35;
          v6 = v32;
          v5 = (HKEY *)v33;
          v4 = v34;
          cbData = v35;
        }
        if ( v22 )
        {
          memset_0(v22, 0, v20);
          for ( j = 0; j < (int)v18; j = v25 + 1 )
          {
            v24 = ATL::CRegParser::ChToByte(String1[j]);
            *(_BYTE *)(v27 + v26) |= v24 << (4 - 4 * (v25 & 1));
          }
          v16 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_46;
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
0x1801f2bf0  push    rbx
0x1801f2bf2  push    rsi
0x1801f2bf3  push    rdi
0x1801f2bf4  push    r12
0x1801f2bf6  push    r13
0x1801f2bf8  push    r14
0x1801f2bfa  push    r15
0x1801f2bfc  mov     eax, 2190h
0x1801f2c01  call    _alloca_probe
0x1801f2c06  sub     rsp, rax
0x1801f2c09  mov     rax, cs:__security_cookie
0x1801f2c10  xor     rax, rsp
0x1801f2c13  mov     [rsp+21C8h+var_48], rax
0x1801f2c1b  mov     r12, r8
0x1801f2c1e  mov     r15, rdx
0x1801f2c21  mov     r13, rcx
0x1801f2c24  mov     [rsp+21C8h+var_2188], rcx
0x1801f2c29  mov     [rsp+21C8h+var_2180], rdx
0x1801f2c2e  mov     [rsp+21C8h+var_2178], r8
0x1801f2c33  mov     [rsp+21C8h+var_2160], r9
0x1801f2c38  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x1801f2c40  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f2c45  xor     ebx, ebx
0x1801f2c47  test    eax, eax
0x1801f2c49  js      loc_1801F2FC0
0x1801f2c4f  mov     edi, ebx
0x1801f2c51  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1801f2c58  movsxd  rsi, edi
0x1801f2c5b  add     rsi, rsi
0x1801f2c5e  mov     rdx, [r14+rsi*8]; lpString2
0x1801f2c62  lea     rcx, [rsp+21C8h+String1]; lpString1
0x1801f2c6a  call    cs:__imp_lstrcmpiW
0x1801f2c70  test    eax, eax
0x1801f2c72  jz      short loc_1801F2C85
0x1801f2c74  inc     edi
0x1801f2c76  cmp     edi, 4
0x1801f2c79  jb      short loc_1801F2C58
0x1801f2c7b  mov     eax, 80020009h
0x1801f2c80  jmp     loc_1801F2FC0
0x1801f2c85  movzx   edi, word ptr [r14+rsi*8+8]
0x1801f2c8b  mov     rcx, r13; this
0x1801f2c8e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1801f2c93  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x1801f2c9b  mov     rcx, r13; this
0x1801f2c9e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f2ca3  test    eax, eax
0x1801f2ca5  js      loc_1801F2FC0
0x1801f2cab  cmp     di, 8
0x1801f2caf  jz      loc_1801F2F5B
0x1801f2cb5  cmp     di, 11h
0x1801f2cb9  jz      loc_1801F2E35
0x1801f2cbf  cmp     di, 13h
0x1801f2cc3  jz      loc_1801F2DBD
0x1801f2cc9  mov     eax, 4008h
0x1801f2cce  cmp     di, ax
0x1801f2cd1  jnz     loc_1801F2FAC
0x1801f2cd7  lea     rax, [rsp+21C8h+String1]
0x1801f2cdf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801f2ce3  inc     rdi
0x1801f2ce6  cmp     [rax+rdi*2], bx
0x1801f2cea  jnz     short loc_1801F2CE3
0x1801f2cec  add     edi, 2
0x1801f2cef  mov     [rsp+21C8h+var_2158], rbx
0x1801f2cf4  movsxd  rcx, edi
0x1801f2cf7  mov     edx, 2
0x1801f2cfc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1801f2d01  cmp     rax, 100h
0x1801f2d07  jbe     short loc_1801F2D1D
0x1801f2d09  mov     rdx, rax
0x1801f2d0c  lea     rcx, [rsp+21C8h+var_2158]
0x1801f2d11  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1801f2d16  mov     rdi, [rsp+21C8h+var_2158]
0x1801f2d1b  jmp     short loc_1801F2D27
0x1801f2d1d  lea     rdi, [rsp+21C8h+var_2150]
0x1801f2d22  mov     [rsp+21C8h+var_2158], rdi
0x1801f2d27  jmp     short loc_1801F2D3F
0x1801f2d29  xor     ebx, ebx
0x1801f2d2b  mov     rdi, [rsp+21C8h+var_2158]
0x1801f2d30  mov     r13, [rsp+21C8h+var_2188]
0x1801f2d35  mov     r15, [rsp+21C8h+var_2180]
0x1801f2d3a  mov     r12, [rsp+21C8h+var_2178]
0x1801f2d3f  test    rdi, rdi
0x1801f2d42  jz      short loc_1801F2DA9
0x1801f2d44  lea     rsi, [rsp+21C8h+String1]
0x1801f2d4c  cmp     [rsp+21C8h+String1], bx
0x1801f2d54  jz      short loc_1801F2D8F
0x1801f2d56  mov     rcx, rsi; lpsz
0x1801f2d59  call    cs:__imp_CharNextW
0x1801f2d5f  movzx   ecx, word ptr [rsi]
0x1801f2d62  cmp     cx, 5Ch ; '\'
0x1801f2d66  jnz     short loc_1801F2D7F
0x1801f2d68  cmp     word ptr [rax], 30h ; '0'
0x1801f2d6c  jnz     short loc_1801F2D7F
0x1801f2d6e  mov     [rdi], bx
0x1801f2d71  mov     rcx, rax; lpsz
0x1801f2d74  call    cs:__imp_CharNextW
0x1801f2d7a  mov     rsi, rax
0x1801f2d7d  jmp     short loc_1801F2D86
0x1801f2d7f  mov     [rdi], cx
0x1801f2d82  add     rsi, 2
0x1801f2d86  add     rdi, 2
0x1801f2d8a  cmp     [rsi], bx
0x1801f2d8d  jnz     short loc_1801F2D56
0x1801f2d8f  mov     dword ptr [rdi], 0
0x1801f2d95  mov     r8, [rsp+21C8h+var_2158]; unsigned __int16 *
0x1801f2d9a  mov     rdx, r12; unsigned __int16 *
0x1801f2d9d  mov     rcx, r15; this
0x1801f2da0  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x1801f2da5  mov     edi, eax
0x1801f2da7  jmp     short loc_1801F2DAE
0x1801f2da9  mov     edi, 0Eh
0x1801f2dae  lea     rcx, [rsp+21C8h+var_2158]
0x1801f2db3  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1801f2db8  jmp     loc_1801F2F9F
0x1801f2dbd  mov     [rsp+21C8h+pulOut], ebx
0x1801f2dc1  mov     [rsp+21C8h+var_2188], rbx
0x1801f2dc6  lea     r9, [rsp+21C8h+pulOut]; pulOut
0x1801f2dcb  xor     r8d, r8d; dwFlags
0x1801f2dce  xor     edx, edx; lcid
0x1801f2dd0  lea     rcx, [rsp+21C8h+String1]; strIn
0x1801f2dd8  call    cs:__imp_VarUI4FromStr
0x1801f2dde  mov     edi, eax
0x1801f2de0  test    eax, eax
0x1801f2de2  jns     short loc_1801F2DF5
0x1801f2de4  lea     rcx, [rsp+21C8h+var_2188]
0x1801f2de9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1801f2dee  mov     eax, edi
0x1801f2df0  jmp     loc_1801F2FC0
0x1801f2df5  mov     eax, [rsp+21C8h+pulOut]
0x1801f2df9  mov     dword ptr [rsp+21C8h+Data], eax
0x1801f2dfd  mov     [rsp+21C8h+cbData], 4; cbData
0x1801f2e05  lea     rax, [rsp+21C8h+Data]
0x1801f2e0a  mov     [rsp+21C8h+lpData], rax; lpData
0x1801f2e0f  mov     r9d, 4; dwType
0x1801f2e15  xor     r8d, r8d; Reserved
0x1801f2e18  mov     rdx, r12; lpValueName
0x1801f2e1b  mov     rcx, [r15]; hKey
0x1801f2e1e  call    cs:__imp_RegSetValueExW
0x1801f2e24  mov     edi, eax
0x1801f2e26  lea     rcx, [rsp+21C8h+var_2188]
0x1801f2e2b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1801f2e30  jmp     loc_1801F2F9F
0x1801f2e35  lea     rax, [rsp+21C8h+String1]
0x1801f2e3d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801f2e41  inc     rdi
0x1801f2e44  cmp     [rax+rdi*2], bx
0x1801f2e48  jnz     short loc_1801F2E41
0x1801f2e4a  mov     dword ptr [rsp+21C8h+Data], edi
0x1801f2e4e  test    dil, 1
0x1801f2e52  jz      short loc_1801F2E5E
0x1801f2e54  mov     eax, 80004005h
0x1801f2e59  jmp     loc_1801F2FC0
0x1801f2e5e  mov     eax, edi
0x1801f2e60  cdq
0x1801f2e61  sub     eax, edx
0x1801f2e63  sar     eax, 1
0x1801f2e65  movsxd  rsi, eax
0x1801f2e68  mov     [rsp+21C8h+var_2158], rbx
0x1801f2e6d  mov     r14, rsi
0x1801f2e70  mov     [rsp+21C8h+var_2168], rsi
0x1801f2e75  mov     edx, 1
0x1801f2e7a  mov     rcx, rsi
0x1801f2e7d  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1801f2e82  cmp     rax, 100h
0x1801f2e88  jbe     short loc_1801F2E9E
0x1801f2e8a  mov     rdx, rax
0x1801f2e8d  lea     rcx, [rsp+21C8h+var_2158]
0x1801f2e92  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1801f2e97  mov     rcx, [rsp+21C8h+var_2158]
0x1801f2e9c  jmp     short loc_1801F2EA8
0x1801f2e9e  lea     rcx, [rsp+21C8h+var_2150]
0x1801f2ea3  mov     [rsp+21C8h+var_2158], rcx
0x1801f2ea8  jmp     short loc_1801F2ECC
0x1801f2eaa  xor     ebx, ebx
0x1801f2eac  mov     edi, dword ptr [rsp+21C8h+Data]
0x1801f2eb0  mov     rcx, [rsp+21C8h+var_2158]; void *
0x1801f2eb5  mov     r14, [rsp+21C8h+var_2168]
0x1801f2eba  mov     r13, [rsp+21C8h+var_2188]
0x1801f2ebf  mov     r15, [rsp+21C8h+var_2180]
0x1801f2ec4  mov     r12, [rsp+21C8h+var_2178]
0x1801f2ec9  mov     esi, r14d
0x1801f2ecc  test    rcx, rcx
0x1801f2ecf  jnz     short loc_1801F2EE0
0x1801f2ed1  lea     rcx, [rsp+21C8h+var_2158]
0x1801f2ed6  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1801f2edb  jmp     loc_1801F2E54
0x1801f2ee0  mov     r8, r14; Size
0x1801f2ee3  xor     edx, edx; Val
0x1801f2ee5  call    memset_0
0x1801f2eea  mov     r10d, ebx
0x1801f2eed  test    edi, edi
0x1801f2eef  jle     short loc_1801F2F2A
0x1801f2ef1  mov     r9d, r10d
0x1801f2ef4  shr     r9, 1
0x1801f2ef7  mov     r8, [rsp+21C8h+var_2158]
0x1801f2efc  mov     ecx, r10d
0x1801f2eff  movzx   ecx, [rsp+rcx*2+21C8h+String1]; unsigned __int16
0x1801f2f07  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x1801f2f0c  mov     edx, r10d
0x1801f2f0f  and     edx, 1
0x1801f2f12  shl     edx, 2
0x1801f2f15  mov     ecx, 4
0x1801f2f1a  sub     ecx, edx
0x1801f2f1c  shl     al, cl
0x1801f2f1e  or      [r9+r8], al
0x1801f2f22  inc     r10d
0x1801f2f25  cmp     r10d, edi
0x1801f2f28  jl      short loc_1801F2EF1
0x1801f2f2a  mov     rax, [rsp+21C8h+var_2158]
0x1801f2f2f  mov     [rsp+21C8h+cbData], esi; cbData
0x1801f2f33  mov     [rsp+21C8h+lpData], rax; lpData
0x1801f2f38  mov     r9d, 3; dwType
0x1801f2f3e  xor     r8d, r8d; Reserved
0x1801f2f41  mov     rdx, r12; lpValueName
0x1801f2f44  mov     rcx, [r15]; hKey
0x1801f2f47  call    cs:__imp_RegSetValueExW
0x1801f2f4d  mov     edi, eax
0x1801f2f4f  lea     rcx, [rsp+21C8h+var_2158]
0x1801f2f54  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1801f2f59  jmp     short loc_1801F2F9F
0x1801f2f5b  lea     rax, [rsp+21C8h+String1]
0x1801f2f63  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801f2f67  inc     rdi
0x1801f2f6a  cmp     [rax+rdi*2], bx
0x1801f2f6e  jnz     short loc_1801F2F67
0x1801f2f70  lea     eax, ds:2[rdi*2]
0x1801f2f77  mov     [rsp+21C8h+cbData], eax; cbData
0x1801f2f7b  lea     rax, [rsp+21C8h+String1]
0x1801f2f83  mov     [rsp+21C8h+lpData], rax; lpData
0x1801f2f88  mov     r9d, 1; dwType
0x1801f2f8e  xor     r8d, r8d; Reserved
0x1801f2f91  mov     rdx, r12; lpValueName
0x1801f2f94  mov     rcx, [r15]; hKey
0x1801f2f97  call    cs:__imp_RegSetValueExW
0x1801f2f9d  mov     edi, eax
0x1801f2f9f  test    edi, edi
0x1801f2fa1  jz      short loc_1801F2FAC
0x1801f2fa3  mov     ecx, edi; unsigned int
0x1801f2fa5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1801f2faa  jmp     short loc_1801F2FC0
0x1801f2fac  mov     rdx, [rsp+21C8h+var_2160]; unsigned __int16 *
0x1801f2fb1  mov     rcx, r13; this
0x1801f2fb4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f2fb9  test    eax, eax
0x1801f2fbb  cmovs   ebx, eax
0x1801f2fbe  mov     eax, ebx
0x1801f2fc0  mov     rcx, [rsp+21C8h+var_48]
0x1801f2fc8  xor     rcx, rsp; StackCookie
0x1801f2fcb  call    __security_check_cookie
0x1801f2fd0  add     rsp, 2190h
0x1801f2fd7  pop     r15
0x1801f2fd9  pop     r14
0x1801f2fdb  pop     r13
0x1801f2fdd  pop     r12
0x1801f2fdf  pop     rdi
0x1801f2fe0  pop     rsi
0x1801f2fe1  pop     rbx
0x1801f2fe2  retn
```
