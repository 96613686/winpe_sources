# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18002a870`
- end: `0x18002ae26`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1462`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18002d414`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x18002a0a8`
- `0x18002a140`
- `0x18002a304`
- `0x18002a870`
- `0x18002ae2c`
- `0x18002b1d0`
- `0x18002b964`
- `0x18002ca80`
- `0x18002dbf8`
- `0x18005b620`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002aa45`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002aa61`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002aa45`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002aa61`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002aaca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ab63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ad7c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002add3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002aaca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ab63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ad7c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002add3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002a90b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002a90b`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002ab16`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002ab16`

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
  ATL::CRegParser *v34; // [rsp+30h] [rbp-21B8h] BYREF
  LPCWSTR lpValueName; // [rsp+38h] [rbp-21B0h]
  HKEY *v36; // [rsp+40h] [rbp-21A8h]
  ATL::CRegParser *v37; // [rsp+48h] [rbp-21A0h]
  const WCHAR *v38; // [rsp+50h] [rbp-2198h]
  size_t v39; // [rsp+60h] [rbp-2188h]
  HKEY *v40; // [rsp+68h] [rbp-2180h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-2178h]
  ULONG pulOut; // [rsp+78h] [rbp-2170h] BYREF
  BYTE Data[16]; // [rsp+80h] [rbp-2168h] BYREF
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v36 = a2;
  v6 = this;
  v34 = this;
  *(_QWORD *)Data = a2;
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
      memset_0(&lpData, 0, 0x108u);
      lpData = 0;
      v25 = (int)v23 / 2;
      v39 = v25;
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
        v25 = v39;
        v34 = v37;
        v28 = v40;
        lpValueName = v38;
        v24 = v39;
        goto LABEL_47;
      }
      v28 = v36;
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
      v34 = 0;
      v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v22 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v21 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v34);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v34);
      return (unsigned int)v22;
    case 16392:
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      memset_0(&lpData, 0, 0x108u);
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
        v34 = v37;
        lpValueName = v38;
        goto LABEL_18;
      }
      v14 = v36;
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
      v6 = v34;
LABEL_80:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v41);
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
0x18002a870  push    rbx
0x18002a872  push    rsi
0x18002a873  push    rdi
0x18002a874  push    r12
0x18002a876  push    r13
0x18002a878  push    r14
0x18002a87a  push    r15
0x18002a87c  mov     eax, 21B0h
0x18002a881  call    _alloca_probe
0x18002a886  sub     rsp, rax
0x18002a889  mov     rax, cs:__security_cookie
0x18002a890  xor     rax, rsp
0x18002a893  mov     [rsp+21E8h+var_48], rax
0x18002a89b  mov     r14, r8
0x18002a89e  mov     [rsp+21E8h+lpValueName], r8
0x18002a8a3  mov     r12, rdx
0x18002a8a6  mov     [rsp+21E8h+var_21A8], rdx
0x18002a8ab  mov     r15, rcx
0x18002a8ae  mov     [rsp+21E8h+var_21B8], rcx
0x18002a8b3  mov     qword ptr [rsp+21E8h+Data], rdx
0x18002a8bb  mov     [rsp+21E8h+var_21A0], rcx
0x18002a8c0  mov     [rsp+21E8h+var_2180], rdx
0x18002a8c5  mov     [rsp+21E8h+var_2198], r8
0x18002a8ca  mov     [rsp+21E8h+var_2178], r9
0x18002a8cf  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18002a8d7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a8dc  xor     ebx, ebx
0x18002a8de  test    eax, eax
0x18002a8e0  js      loc_18002AE03
0x18002a8e6  mov     edi, ebx
0x18002a8e8  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18002a8ef  cmp     edi, 4
0x18002a8f2  jnb     loc_18002ADFE
0x18002a8f8  movsxd  rsi, edi
0x18002a8fb  add     rsi, rsi
0x18002a8fe  mov     rdx, [r13+rsi*8+0]; lpString2
0x18002a903  lea     rcx, [rsp+21E8h+String1]; lpString1
0x18002a90b  call    cs:__imp_lstrcmpiW
0x18002a911  test    eax, eax
0x18002a913  jz      short loc_18002A919
0x18002a915  inc     edi
0x18002a917  jmp     short loc_18002A8EF
0x18002a919  movzx   edi, word ptr [r13+rsi*8+8]
0x18002a91f  mov     rcx, r15; this
0x18002a922  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18002a927  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18002a92f  mov     rcx, r15; this
0x18002a932  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a937  test    eax, eax
0x18002a939  js      loc_18002AE03
0x18002a93f  mov     r13d, 8
0x18002a945  cmp     di, r13w
0x18002a949  jz      loc_18002AD96
0x18002a94f  cmp     di, 11h
0x18002a953  jz      loc_18002AB7A
0x18002a959  cmp     di, 13h
0x18002a95d  jz      loc_18002AAFB
0x18002a963  mov     eax, 4008h
0x18002a968  cmp     di, ax
0x18002a96b  jnz     loc_18002ADE8
0x18002a971  lea     rcx, [rsp+21E8h+String1]
0x18002a979  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002a97d  mov     rax, rsi
0x18002a980  inc     rax
0x18002a983  cmp     [rcx+rax*2], bx
0x18002a987  jnz     short loc_18002A980
0x18002a989  lea     edi, [rax+2]
0x18002a98c  xor     edx, edx; Val
0x18002a98e  mov     r8d, 108h; Size
0x18002a994  lea     rcx, [rsp+21E8h+var_2158]; void *
0x18002a99c  call    memset_0
0x18002a9a1  mov     [rsp+21E8h+var_2158], rbx
0x18002a9a9  movsxd  rcx, edi
0x18002a9ac  mov     r15d, 2
0x18002a9b2  mov     edx, r15d
0x18002a9b5  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002a9ba  cmp     rax, 100h
0x18002a9c0  jbe     short loc_18002A9DC
0x18002a9c2  mov     rdx, rax
0x18002a9c5  lea     rcx, [rsp+21E8h+var_2158]
0x18002a9cd  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002a9d2  mov     rdi, [rsp+21E8h+var_2158]
0x18002a9da  jmp     short loc_18002A9EC
0x18002a9dc  lea     rdi, [rsp+21E8h+var_2150]
0x18002a9e4  mov     [rsp+21E8h+var_2158], rdi
0x18002a9ec  mov     r13, [rsp+21E8h+var_21A8]
0x18002a9f1  jmp     short loc_18002AA21
0x18002a9f3  xor     ebx, ebx
0x18002a9f5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002a9f9  lea     r15d, [rbx+2]
0x18002a9fd  mov     rdi, [rsp+21E8h+var_2158]
0x18002aa05  mov     r13, qword ptr [rsp+21E8h+Data]
0x18002aa0d  mov     rax, [rsp+21E8h+var_21A0]
0x18002aa12  mov     [rsp+21E8h+var_21B8], rax
0x18002aa17  mov     rax, [rsp+21E8h+var_2198]
0x18002aa1c  mov     [rsp+21E8h+lpValueName], rax
0x18002aa21  test    rdi, rdi
0x18002aa24  jz      loc_18002AADF
0x18002aa2a  lea     r14, [rsp+21E8h+String1]
0x18002aa32  cmp     [rsp+21E8h+String1], bx
0x18002aa3a  jz      short loc_18002AA7B
0x18002aa3c  mov     r12d, 30h ; '0'
0x18002aa42  mov     rcx, r14; lpsz
0x18002aa45  call    cs:__imp_CharNextW
0x18002aa4b  movzx   ecx, word ptr [r14]
0x18002aa4f  cmp     cx, 5Ch ; '\'
0x18002aa53  jnz     short loc_18002AA6C
0x18002aa55  cmp     [rax], r12w
0x18002aa59  jnz     short loc_18002AA6C
0x18002aa5b  mov     [rdi], bx
0x18002aa5e  mov     rcx, rax; lpsz
0x18002aa61  call    cs:__imp_CharNextW
0x18002aa67  mov     r14, rax
0x18002aa6a  jmp     short loc_18002AA72
0x18002aa6c  mov     [rdi], cx
0x18002aa6f  add     r14, r15
0x18002aa72  add     rdi, r15
0x18002aa75  cmp     [r14], bx
0x18002aa79  jnz     short loc_18002AA42
0x18002aa7b  mov     dword ptr [rdi], 0
0x18002aa81  mov     r8, [rsp+21E8h+var_2158]
0x18002aa89  test    r8, r8
0x18002aa8c  jz      short loc_18002AAD4
0x18002aa8e  mov     r10d, ebx
0x18002aa91  mov     r9, r8
0x18002aa94  mov     rcx, rsi
0x18002aa97  inc     rcx
0x18002aa9a  cmp     [r9+rcx*2], bx
0x18002aa9f  jnz     short loc_18002AA97
0x18002aaa1  inc     ecx
0x18002aaa3  lea     r9, [r9+rcx*2]
0x18002aaa7  lea     r10d, [r10+rcx*2]
0x18002aaab  cmp     ecx, 1
0x18002aaae  jnz     short loc_18002AA94
0x18002aab0  mov     [rsp+21E8h+cbData], r10d; cbData
0x18002aab5  mov     [rsp+21E8h+lpData], r8; lpData
0x18002aaba  lea     r9d, [rcx+6]; dwType
0x18002aabe  xor     r8d, r8d; Reserved
0x18002aac1  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18002aac6  mov     rcx, [r13+0]; hKey
0x18002aaca  call    cs:__imp_RegSetValueExW
0x18002aad0  mov     edi, eax
0x18002aad2  jmp     short loc_18002AAE4
0x18002aad4  mov     ecx, 80004005h; int
0x18002aad9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002aadf  mov     edi, 0Eh
0x18002aae4  lea     rcx, [rsp+21E8h+var_2158]
0x18002aaec  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002aaf1  mov     r15, [rsp+21E8h+var_21B8]
0x18002aaf6  jmp     loc_18002ADDB
0x18002aafb  mov     [rsp+21E8h+pulOut], ebx
0x18002aaff  mov     [rsp+21E8h+var_21B8], rbx
0x18002ab04  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18002ab09  xor     r8d, r8d; dwFlags
0x18002ab0c  xor     edx, edx; lcid
0x18002ab0e  lea     rcx, [rsp+21E8h+String1]; strIn
0x18002ab16  call    cs:__imp_VarUI4FromStr
0x18002ab1c  mov     edi, eax
0x18002ab1e  test    eax, eax
0x18002ab20  jns     short loc_18002AB33
0x18002ab22  lea     rcx, [rsp+21E8h+var_21B8]
0x18002ab27  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002ab2c  mov     eax, edi
0x18002ab2e  jmp     loc_18002AE03
0x18002ab33  mov     eax, [rsp+21E8h+pulOut]
0x18002ab37  mov     dword ptr [rsp+21E8h+Data], eax
0x18002ab3e  mov     [rsp+21E8h+cbData], 4; cbData
0x18002ab46  lea     rax, [rsp+21E8h+Data]
0x18002ab4e  mov     [rsp+21E8h+lpData], rax; lpData
0x18002ab53  mov     r9d, 4; dwType
0x18002ab59  xor     r8d, r8d; Reserved
0x18002ab5c  mov     rdx, r14; lpValueName
0x18002ab5f  mov     rcx, [r12]; hKey
0x18002ab63  call    cs:__imp_RegSetValueExW
0x18002ab69  mov     edi, eax
0x18002ab6b  lea     rcx, [rsp+21E8h+var_21B8]
0x18002ab70  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002ab75  jmp     loc_18002ADDB
0x18002ab7a  lea     rax, [rsp+21E8h+String1]
0x18002ab82  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002ab86  inc     rsi
0x18002ab89  cmp     [rax+rsi*2], bx
0x18002ab8d  jnz     short loc_18002AB86
0x18002ab8f  mov     dword ptr [rsp+21E8h+Data], esi
0x18002ab96  test    sil, 1
0x18002ab9a  jz      short loc_18002ABA6
0x18002ab9c  mov     eax, 80004005h
0x18002aba1  jmp     loc_18002AE03
0x18002aba6  mov     eax, esi
0x18002aba8  cdq
0x18002aba9  mov     r15d, 2
0x18002abaf  idiv    r15d
0x18002abb2  movsxd  r14, eax
0x18002abb5  xor     edx, edx; Val
0x18002abb7  mov     r8d, 108h; Size
0x18002abbd  lea     rcx, [rsp+21E8h+var_2158]; void *
0x18002abc5  call    memset_0
0x18002abca  mov     [rsp+21E8h+var_2158], rbx
0x18002abd2  mov     rdi, r14
0x18002abd5  mov     [rsp+21E8h+var_2188], r14
0x18002abda  lea     edx, [r15-1]
0x18002abde  mov     rcx, r14
0x18002abe1  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002abe6  cmp     rax, 100h
0x18002abec  jbe     short loc_18002AC08
0x18002abee  mov     rdx, rax
0x18002abf1  lea     rcx, [rsp+21E8h+var_2158]
0x18002abf9  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002abfe  mov     rcx, [rsp+21E8h+var_2158]
0x18002ac06  jmp     short loc_18002AC18
0x18002ac08  lea     rcx, [rsp+21E8h+var_2150]
0x18002ac10  mov     [rsp+21E8h+var_2158], rcx
0x18002ac18  mov     r15, [rsp+21E8h+var_21A8]
0x18002ac1d  jmp     short loc_18002AC55
0x18002ac1f  xor     ebx, ebx
0x18002ac21  lea     r13d, [rbx+8]
0x18002ac25  mov     esi, dword ptr [rsp+21E8h+Data]
0x18002ac2c  mov     rcx, [rsp+21E8h+var_2158]; void *
0x18002ac34  mov     rdi, [rsp+21E8h+var_2188]
0x18002ac39  mov     rax, [rsp+21E8h+var_21A0]
0x18002ac3e  mov     [rsp+21E8h+var_21B8], rax
0x18002ac43  mov     r15, [rsp+21E8h+var_2180]
0x18002ac48  mov     rax, [rsp+21E8h+var_2198]
0x18002ac4d  mov     [rsp+21E8h+lpValueName], rax
0x18002ac52  mov     r14d, edi
0x18002ac55  test    rcx, rcx
0x18002ac58  jnz     short loc_18002AC6C
0x18002ac5a  lea     rcx, [rsp+21E8h+var_2158]
0x18002ac62  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002ac67  jmp     loc_18002AB9C
0x18002ac6c  mov     r8, rdi; Size
0x18002ac6f  xor     edx, edx; Val
0x18002ac71  call    memset_0
0x18002ac76  mov     r10d, ebx
0x18002ac79  test    esi, esi
0x18002ac7b  jle     loc_18002AD59
0x18002ac81  mov     r12d, 30h ; '0'
0x18002ac87  mov     eax, r10d
0x18002ac8a  movzx   edx, [rsp+rax*2+21E8h+String1]
0x18002ac92  cmp     edx, 61h ; 'a'
0x18002ac95  ja      short loc_18002AD04
0x18002ac97  jz      loc_18002AD24
0x18002ac9d  cmp     edx, 38h ; '8'
0x18002aca0  ja      short loc_18002ACD6
0x18002aca2  jz      short loc_18002ACCE
0x18002aca4  mov     ecx, edx
0x18002aca6  sub     ecx, r12d
0x18002aca9  jz      short loc_18002ACCE
0x18002acab  sub     ecx, 1
0x18002acae  jz      short loc_18002ACCE
0x18002acb0  sub     ecx, 1
0x18002acb3  jz      short loc_18002ACCE
0x18002acb5  sub     ecx, 1
0x18002acb8  jz      short loc_18002ACCE
0x18002acba  sub     ecx, 1
0x18002acbd  jz      short loc_18002ACCE
0x18002acbf  sub     ecx, 1
0x18002acc2  jz      short loc_18002ACCE
0x18002acc4  sub     ecx, 1
0x18002acc7  jz      short loc_18002ACCE
0x18002acc9  cmp     ecx, 1
0x18002accc  jnz     short loc_18002AD1F
0x18002acce  mov     r9d, edx
0x18002acd1  sub     r9d, r12d
0x18002acd4  jmp     short loc_18002AD28
0x18002acd6  mov     r9d, edx
0x18002acd9  mov     ecx, edx
0x18002acdb  sub     ecx, 39h ; '9'
0x18002acde  jz      short loc_18002ACCE
0x18002ace0  sub     ecx, r13d
0x18002ace3  jz      short loc_18002ACFE
0x18002ace5  sub     ecx, 1
0x18002ace8  jz      short loc_18002ACFE
0x18002acea  sub     ecx, 1
0x18002aced  jz      short loc_18002ACFE
0x18002acef  sub     ecx, 1
0x18002acf2  jz      short loc_18002ACFE
0x18002acf4  sub     ecx, 1
0x18002acf7  jz      short loc_18002ACFE
0x18002acf9  cmp     ecx, 1
0x18002acfc  jnz     short loc_18002AD1F
0x18002acfe  add     r9d, 0FFFFFFC9h
0x18002ad02  jmp     short loc_18002AD28
0x18002ad04  mov     ecx, edx
0x18002ad06  sub     ecx, 62h ; 'b'
0x18002ad09  jz      short loc_18002AD24
0x18002ad0b  sub     ecx, 1
0x18002ad0e  jz      short loc_18002AD24
0x18002ad10  sub     ecx, 1
0x18002ad13  jz      short loc_18002AD24
0x18002ad15  sub     ecx, 1
0x18002ad18  jz      short loc_18002AD24
0x18002ad1a  cmp     ecx, 1
0x18002ad1d  jz      short loc_18002AD24
0x18002ad1f  mov     r9d, ebx
0x18002ad22  jmp     short loc_18002AD28
0x18002ad24  lea     r9d, [rdx-57h]
0x18002ad28  mov     r8d, r10d
0x18002ad2b  shr     r8, 1
0x18002ad2e  mov     rdx, [rsp+21E8h+var_2158]
  ... truncated ...
```
