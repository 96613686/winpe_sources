# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18001f0a0`
- end: `0x18001f54c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1196`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18002062c`

## callees

- `0x18001ea8c`
- `0x18001ec8c`
- `0x18001ecbc`
- `0x18001f0a0`
- `0x18001f554`
- `0x18001f6d4`
- `0x18001f6ec`
- `0x18001fda4`
- `0x180021758`
- `0x1800582a2`
- `0x1800582e0`
- `0x1800583a0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001f2c6`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001f2c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f281`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f30d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f4a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f4f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f281`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f30d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f4a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f4f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001f1f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001f215`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001f1f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001f215`
- `KERNEL32!lstrcmpiW` at `0x18001f121`
- `KERNEL32!lstrcmpiW` at `0x18001f121`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  HKEY *v4; // r12
  unsigned __int16 *v5; // r15
  ATL::CRegParser *v7; // r14
  __int64 result; // rax
  unsigned int i; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // ebx
  HRESULT v21; // ebx
  HKEY v22; // rcx
  __int64 v23; // rdi
  size_t v24; // rsi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int v27; // r10d
  unsigned int v28; // r9d
  char v29; // r9
  unsigned __int64 v30; // r8
  char v31; // r9
  __int64 v32; // rdi
  int Token; // eax
  unsigned int v34; // ecx
  unsigned __int16 *v35; // [rsp+30h] [rbp-D0h] BYREF
  ULONG pulOut[2]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v39[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v4 = a2;
  *(_QWORD *)pulOut = a2;
  v35 = a4;
  v5 = a4;
  *(_QWORD *)Data = this;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, String1);
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
  ATL::CRegParser::SkipWhiteSpace(v7);
  result = ATL::CRegParser::NextToken(v7, String1);
  if ( (int)result < 0 )
    return result;
  if ( v10 == 8 )
  {
    v32 = -1;
    do
      ++v32;
    while ( String1[v32] );
    v20 = RegSetValueExW(*v4, a3, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
    goto LABEL_77;
  }
  if ( v10 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( String1[v23] );
    if ( (v23 & 1) != 0 )
      return 2147500037LL;
    v24 = (int)v23 / 2;
    lpData = 0;
    v25 = ATL::AtlMultiplyThrow<unsigned __int64>(v24, 1);
    if ( v25 <= 0x100 )
    {
      v26 = v39;
      lpData = v39;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
      v26 = lpData;
    }
    if ( !v26 )
    {
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      return 2147500037LL;
    }
    memset_0(v26, 0, v24);
    v27 = 0;
    if ( (int)v23 <= 0 )
      goto LABEL_73;
    while ( 1 )
    {
      v28 = String1[v27];
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
      lpData[v30] |= v31;
      if ( v27 >= (int)v23 )
      {
        v5 = v35;
LABEL_73:
        v20 = RegSetValueExW(*v4, a3, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        v7 = *(ATL::CRegParser **)Data;
LABEL_77:
        if ( v20 )
          return ATL::AtlHresultFromWin32(v20);
LABEL_79:
        Token = ATL::CRegParser::NextToken(v7, v5);
        v34 = 0;
        if ( Token < 0 )
          return (unsigned int)Token;
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
      while ( String1[v11] );
      lpData = 0;
      v12 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v11 + 2, 2);
      if ( v12 <= 0x100 )
      {
        v13 = v39;
        lpData = v39;
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
          v4 = *(HKEY **)pulOut;
          v5 = v35;
        }
        *(_DWORD *)v13 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
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
        v20 = RegSetValueExW(*v4, a3, 0, 7u, lpData, cbData);
      }
      else
      {
        v20 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      v7 = *(ATL::CRegParser **)Data;
      goto LABEL_77;
    }
    goto LABEL_79;
  }
  pulOut[0] = 0;
  v35 = 0;
  v21 = VarUI4FromStr(String1, 0, 0, pulOut);
  if ( v21 >= 0 )
  {
    v22 = *v4;
    *(_DWORD *)Data = pulOut[0];
    v20 = RegSetValueExW(v22, a3, 0, 4u, Data, 4u);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
    goto LABEL_77;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18001f0a0  push    rbp
0x18001f0a2  push    rbx
0x18001f0a3  push    rsi
0x18001f0a4  push    rdi
0x18001f0a5  push    r12
0x18001f0a7  push    r13
0x18001f0a9  push    r14
0x18001f0ab  push    r15
0x18001f0ad  lea     rbp, [rsp-2078h]
0x18001f0b5  mov     eax, 2178h
0x18001f0ba  call    _alloca_probe
0x18001f0bf  sub     rsp, rax
0x18001f0c2  mov     rax, cs:__security_cookie
0x18001f0c9  xor     rax, rsp
0x18001f0cc  mov     [rbp+20B0h+var_50], rax
0x18001f0d3  mov     r12, rdx
0x18001f0d6  mov     qword ptr [rsp+21B0h+pulOut], rdx
0x18001f0db  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18001f0df  mov     [rsp+21B0h+var_2180], r9
0x18001f0e4  mov     r15, r9
0x18001f0e7  mov     qword ptr [rsp+21B0h+Data], rcx
0x18001f0ec  mov     r13, r8
0x18001f0ef  mov     r14, rcx
0x18001f0f2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f0f7  xor     esi, esi
0x18001f0f9  test    eax, eax
0x18001f0fb  js      loc_18001F529
0x18001f101  mov     ebx, esi
0x18001f103  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001f10a  cmp     ebx, 4
0x18001f10d  jnb     loc_18001F524
0x18001f113  movsxd  rdi, ebx
0x18001f116  lea     rcx, [rbp+20B0h+String1]; lpString1
0x18001f11a  add     rdi, rdi
0x18001f11d  mov     rdx, [rax+rdi*8]; lpString2
0x18001f121  call    cs:__imp_lstrcmpiW
0x18001f127  test    eax, eax
0x18001f129  jz      short loc_18001F12F
0x18001f12b  inc     ebx
0x18001f12d  jmp     short loc_18001F103
0x18001f12f  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001f136  mov     rcx, r14; this
0x18001f139  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18001f13e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001f143  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18001f147  mov     rcx, r14; this
0x18001f14a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f14f  test    eax, eax
0x18001f151  js      loc_18001F529
0x18001f157  mov     eax, 8
0x18001f15c  cmp     bx, ax
0x18001f15f  jz      loc_18001F4C4
0x18001f165  cmp     bx, 11h
0x18001f169  jz      loc_18001F324
0x18001f16f  cmp     bx, 13h
0x18001f173  jz      loc_18001F2AF
0x18001f179  mov     eax, 4008h
0x18001f17e  cmp     bx, ax
0x18001f181  jnz     loc_18001F50E
0x18001f187  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f18b  lea     rcx, [rbp+20B0h+String1]
0x18001f18f  mov     rax, rdi
0x18001f192  inc     rax
0x18001f195  cmp     [rcx+rax*2], si
0x18001f199  jnz     short loc_18001F192
0x18001f19b  add     eax, 2
0x18001f19e  mov     [rsp+21B0h+var_2160], rsi
0x18001f1a3  mov     r14d, 2
0x18001f1a9  movsxd  rcx, eax
0x18001f1ac  mov     edx, r14d
0x18001f1af  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001f1b4  cmp     rax, 100h
0x18001f1ba  jbe     short loc_18001F1D0
0x18001f1bc  mov     rdx, rax
0x18001f1bf  lea     rcx, [rsp+21B0h+var_2160]
0x18001f1c4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001f1c9  mov     rbx, [rsp+21B0h+var_2160]
0x18001f1ce  jmp     short loc_18001F1DA
0x18001f1d0  lea     rbx, [rsp+21B0h+var_2158]
0x18001f1d5  mov     [rsp+21B0h+var_2160], rbx
0x18001f1da  test    rbx, rbx
0x18001f1dd  jz      loc_18001F296
0x18001f1e3  xor     eax, eax
0x18001f1e5  lea     rsi, [rbp+20B0h+String1]
0x18001f1e9  cmp     [rbp+20B0h+String1], ax
0x18001f1ed  jz      short loc_18001F239
0x18001f1ef  lea     r15d, [rax+30h]
0x18001f1f3  xor     r12d, r12d
0x18001f1f6  mov     rcx, rsi; lpsz
0x18001f1f9  call    cs:__imp_CharNextW
0x18001f1ff  movzx   ecx, word ptr [rsi]
0x18001f202  cmp     cx, 5Ch ; '\'
0x18001f206  jnz     short loc_18001F220
0x18001f208  cmp     [rax], r15w
0x18001f20c  jnz     short loc_18001F220
0x18001f20e  mov     rcx, rax; lpsz
0x18001f211  mov     [rbx], r12w
0x18001f215  call    cs:__imp_CharNextW
0x18001f21b  mov     rsi, rax
0x18001f21e  jmp     short loc_18001F226
0x18001f220  mov     [rbx], cx
0x18001f223  add     rsi, r14
0x18001f226  add     rbx, r14
0x18001f229  cmp     [rsi], r12w
0x18001f22d  jnz     short loc_18001F1F6
0x18001f22f  mov     r12, qword ptr [rsp+21B0h+pulOut]
0x18001f234  mov     r15, [rsp+21B0h+var_2180]
0x18001f239  xor     esi, esi
0x18001f23b  mov     [rbx], esi
0x18001f23d  mov     r8, [rsp+21B0h+var_2160]
0x18001f242  test    r8, r8
0x18001f245  jz      short loc_18001F28B
0x18001f247  mov     r10d, esi
0x18001f24a  mov     r9, r8
0x18001f24d  mov     rcx, rdi
0x18001f250  inc     rcx
0x18001f253  cmp     [r9+rcx*2], si
0x18001f258  jnz     short loc_18001F250
0x18001f25a  inc     ecx
0x18001f25c  lea     r9, [r9+rcx*2]
0x18001f260  lea     r10d, [r10+rcx*2]
0x18001f264  cmp     ecx, 1
0x18001f267  jnz     short loc_18001F24D
0x18001f269  mov     [rsp+21B0h+cbData], r10d; cbData
0x18001f26e  lea     r9d, [rcx+6]; dwType
0x18001f272  mov     rcx, [r12]; hKey
0x18001f276  mov     rdx, r13; lpValueName
0x18001f279  mov     [rsp+21B0h+lpData], r8; lpData
0x18001f27e  xor     r8d, r8d; Reserved
0x18001f281  call    cs:__imp_RegSetValueExW
0x18001f287  mov     ebx, eax
0x18001f289  jmp     short loc_18001F29B
0x18001f28b  mov     ecx, 80004005h; int
0x18001f290  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001f296  mov     ebx, 0Eh
0x18001f29b  lea     rcx, [rsp+21B0h+var_2160]
0x18001f2a0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001f2a5  mov     r14, qword ptr [rsp+21B0h+Data]
0x18001f2aa  jmp     loc_18001F501
0x18001f2af  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x18001f2b4  mov     [rsp+21B0h+pulOut], esi
0x18001f2b8  xor     r8d, r8d; dwFlags
0x18001f2bb  mov     [rsp+21B0h+var_2180], rsi
0x18001f2c0  xor     edx, edx; lcid
0x18001f2c2  lea     rcx, [rbp+20B0h+String1]; strIn
0x18001f2c6  call    cs:__imp_VarUI4FromStr
0x18001f2cc  mov     ebx, eax
0x18001f2ce  test    eax, eax
0x18001f2d0  jns     short loc_18001F2E3
0x18001f2d2  lea     rcx, [rsp+21B0h+var_2180]
0x18001f2d7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f2dc  mov     eax, ebx
0x18001f2de  jmp     loc_18001F529
0x18001f2e3  mov     eax, [rsp+21B0h+pulOut]
0x18001f2e7  mov     r9d, 4; dwType
0x18001f2ed  mov     rcx, [r12]; hKey
0x18001f2f1  xor     r8d, r8d; Reserved
0x18001f2f4  mov     dword ptr [rsp+21B0h+Data], eax
0x18001f2f8  mov     rdx, r13; lpValueName
0x18001f2fb  lea     rax, [rsp+21B0h+Data]
0x18001f300  mov     [rsp+21B0h+cbData], 4; cbData
0x18001f308  mov     [rsp+21B0h+lpData], rax; lpData
0x18001f30d  call    cs:__imp_RegSetValueExW
0x18001f313  lea     rcx, [rsp+21B0h+var_2180]
0x18001f318  mov     ebx, eax
0x18001f31a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f31f  jmp     loc_18001F501
0x18001f324  lea     rax, [rbp+20B0h+String1]
0x18001f328  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f32c  inc     rdi
0x18001f32f  cmp     [rax+rdi*2], si
0x18001f333  jnz     short loc_18001F32C
0x18001f335  test    dil, 1
0x18001f339  jz      short loc_18001F345
0x18001f33b  mov     eax, 80004005h
0x18001f340  jmp     loc_18001F529
0x18001f345  mov     eax, edi
0x18001f347  mov     r14d, 2
0x18001f34d  cdq
0x18001f34e  idiv    r14d
0x18001f351  xor     r14d, r14d
0x18001f354  movsxd  rsi, eax
0x18001f357  mov     rcx, rsi
0x18001f35a  mov     [rsp+21B0h+var_2160], r14
0x18001f35f  lea     edx, [r14+1]
0x18001f363  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001f368  cmp     rax, 100h
0x18001f36e  jbe     short loc_18001F384
0x18001f370  mov     rdx, rax
0x18001f373  lea     rcx, [rsp+21B0h+var_2160]
0x18001f378  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001f37d  mov     rcx, [rsp+21B0h+var_2160]
0x18001f382  jmp     short loc_18001F38E
0x18001f384  lea     rcx, [rsp+21B0h+var_2158]; void *
0x18001f389  mov     [rsp+21B0h+var_2160], rcx
0x18001f38e  test    rcx, rcx
0x18001f391  jnz     short loc_18001F39F
0x18001f393  lea     rcx, [rsp+21B0h+var_2160]
0x18001f398  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001f39d  jmp     short loc_18001F33B
0x18001f39f  mov     r8, rsi; Size
0x18001f3a2  xor     edx, edx; Val
0x18001f3a4  call    memset_0
0x18001f3a9  mov     r10d, r14d
0x18001f3ac  test    edi, edi
0x18001f3ae  jle     loc_18001F48B
0x18001f3b4  mov     r15d, 30h ; '0'
0x18001f3ba  mov     eax, r10d
0x18001f3bd  movzx   r9d, [rbp+rax*2+20B0h+String1]
0x18001f3c3  cmp     r9d, 61h ; 'a'
0x18001f3c7  ja      short loc_18001F433
0x18001f3c9  jz      loc_18001F454
0x18001f3cf  cmp     r9d, 38h ; '8'
0x18001f3d3  ja      short loc_18001F407
0x18001f3d5  jz      short loc_18001F402
0x18001f3d7  mov     ecx, r9d
0x18001f3da  sub     ecx, r15d
0x18001f3dd  jz      short loc_18001F402
0x18001f3df  sub     ecx, 1
0x18001f3e2  jz      short loc_18001F402
0x18001f3e4  sub     ecx, 1
0x18001f3e7  jz      short loc_18001F402
0x18001f3e9  sub     ecx, 1
0x18001f3ec  jz      short loc_18001F402
0x18001f3ee  sub     ecx, 1
0x18001f3f1  jz      short loc_18001F402
0x18001f3f3  sub     ecx, 1
0x18001f3f6  jz      short loc_18001F402
0x18001f3f8  sub     ecx, 1
0x18001f3fb  jz      short loc_18001F402
0x18001f3fd  cmp     ecx, 1
0x18001f400  jnz     short loc_18001F44F
0x18001f402  sub     r9b, r15b
0x18001f405  jmp     short loc_18001F458
0x18001f407  mov     ecx, r9d
0x18001f40a  sub     ecx, 39h ; '9'
0x18001f40d  jz      short loc_18001F402
0x18001f40f  sub     ecx, 8
0x18001f412  jz      short loc_18001F42D
0x18001f414  sub     ecx, 1
0x18001f417  jz      short loc_18001F42D
0x18001f419  sub     ecx, 1
0x18001f41c  jz      short loc_18001F42D
0x18001f41e  sub     ecx, 1
0x18001f421  jz      short loc_18001F42D
0x18001f423  sub     ecx, 1
0x18001f426  jz      short loc_18001F42D
0x18001f428  cmp     ecx, 1
0x18001f42b  jnz     short loc_18001F44F
0x18001f42d  sub     r9b, 37h ; '7'
0x18001f431  jmp     short loc_18001F458
0x18001f433  mov     ecx, r9d
0x18001f436  sub     ecx, 62h ; 'b'
0x18001f439  jz      short loc_18001F454
0x18001f43b  sub     ecx, 1
0x18001f43e  jz      short loc_18001F454
0x18001f440  sub     ecx, 1
0x18001f443  jz      short loc_18001F454
0x18001f445  sub     ecx, 1
0x18001f448  jz      short loc_18001F454
0x18001f44a  cmp     ecx, 1
0x18001f44d  jz      short loc_18001F454
0x18001f44f  mov     r9b, r14b
0x18001f452  jmp     short loc_18001F458
0x18001f454  sub     r9b, 57h ; 'W'
0x18001f458  mov     rdx, [rsp+21B0h+var_2160]
0x18001f45d  mov     eax, r10d
0x18001f460  and     eax, 1
0x18001f463  mov     r8d, r10d
0x18001f466  shl     eax, 2
0x18001f469  mov     ecx, 4
0x18001f46e  shr     r8, 1
0x18001f471  sub     ecx, eax
0x18001f473  shl     r9b, cl
0x18001f476  inc     r10d
0x18001f479  or      [r8+rdx], r9b
0x18001f47d  cmp     r10d, edi
0x18001f480  jl      loc_18001F3BA
0x18001f486  mov     r15, [rsp+21B0h+var_2180]
0x18001f48b  mov     rax, [rsp+21B0h+var_2160]
0x18001f490  mov     r9d, 3; dwType
0x18001f496  mov     rcx, [r12]; hKey
0x18001f49a  xor     r8d, r8d; Reserved
0x18001f49d  mov     [rsp+21B0h+cbData], esi; cbData
0x18001f4a1  mov     rdx, r13; lpValueName
0x18001f4a4  mov     [rsp+21B0h+lpData], rax; lpData
0x18001f4a9  call    cs:__imp_RegSetValueExW
0x18001f4af  lea     rcx, [rsp+21B0h+var_2160]
0x18001f4b4  mov     ebx, eax
0x18001f4b6  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001f4bb  mov     r14, qword ptr [rsp+21B0h+Data]
0x18001f4c0  xor     esi, esi
0x18001f4c2  jmp     short loc_18001F501
0x18001f4c4  lea     rax, [rbp+20B0h+String1]
0x18001f4c8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f4cc  inc     rdi
0x18001f4cf  cmp     [rax+rdi*2], si
0x18001f4d3  jnz     short loc_18001F4CC
0x18001f4d5  mov     rcx, [r12]; hKey
0x18001f4d9  lea     eax, ds:2[rdi*2]
  ... truncated ...
```
