# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18009aafc`
- end: `0x18009b07c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18009cc90`

## callees

- `0x180078070`
- `0x180087e80`
- `0x180088ce8`
- `0x18008bf38`
- `0x180099090`
- `0x180099d3c`
- `0x18009aafc`
- `0x18009b084`
- `0x18009b194`
- `0x18009bf68`
- `0x18009d634`
- `0x18011ddd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009ad3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009add1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009afcf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009b026`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009ad3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009add1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009afcf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009b026`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009acb9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009acd5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009acb9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18009acd5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009ab97`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18009ab97`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18009ad8a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18009ad8a`

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
0x18009aafc  push    rbx
0x18009aafe  push    rsi
0x18009aaff  push    rdi
0x18009ab00  push    r12
0x18009ab02  push    r13
0x18009ab04  push    r14
0x18009ab06  push    r15
0x18009ab08  mov     eax, 21B0h
0x18009ab0d  call    _alloca_probe
0x18009ab12  sub     rsp, rax
0x18009ab15  mov     rax, cs:__security_cookie
0x18009ab1c  xor     rax, rsp
0x18009ab1f  mov     [rsp+21E8h+var_48], rax
0x18009ab27  mov     r14, r8
0x18009ab2a  mov     [rsp+21E8h+lpValueName], r8
0x18009ab2f  mov     r12, rdx
0x18009ab32  mov     [rsp+21E8h+var_2198], rdx
0x18009ab37  mov     r15, rcx
0x18009ab3a  mov     [rsp+21E8h+var_21B0], rcx
0x18009ab3f  mov     qword ptr [rsp+21E8h+Data], rdx
0x18009ab44  mov     [rsp+21E8h+var_2190], rcx
0x18009ab49  mov     [rsp+21E8h+var_2170], rdx
0x18009ab4e  mov     [rsp+21E8h+var_2188], r8
0x18009ab53  mov     [rsp+21E8h+var_2168], r9
0x18009ab5b  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18009ab63  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009ab68  xor     ebx, ebx
0x18009ab6a  test    eax, eax
0x18009ab6c  js      loc_18009B059
0x18009ab72  mov     edi, ebx
0x18009ab74  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18009ab7b  cmp     edi, 4
0x18009ab7e  jnb     loc_18009B054
0x18009ab84  movsxd  rsi, edi
0x18009ab87  add     rsi, rsi
0x18009ab8a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18009ab8f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x18009ab97  call    cs:__imp_lstrcmpiW
0x18009ab9d  test    eax, eax
0x18009ab9f  jz      short loc_18009ABA5
0x18009aba1  inc     edi
0x18009aba3  jmp     short loc_18009AB7B
0x18009aba5  movzx   edi, word ptr [r13+rsi*8+8]
0x18009abab  mov     rcx, r15; this
0x18009abae  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18009abb3  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18009abbb  mov     rcx, r15; this
0x18009abbe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009abc3  test    eax, eax
0x18009abc5  js      loc_18009B059
0x18009abcb  mov     r13d, 8
0x18009abd1  cmp     di, r13w
0x18009abd5  jz      loc_18009AFE9
0x18009abdb  cmp     di, 11h
0x18009abdf  jz      loc_18009ADE8
0x18009abe5  cmp     di, 13h
0x18009abe9  jz      loc_18009AD6F
0x18009abef  mov     eax, 4008h
0x18009abf4  cmp     di, ax
0x18009abf7  jnz     loc_18009B03B
0x18009abfd  lea     rcx, [rsp+21E8h+String1]
0x18009ac05  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18009ac09  mov     rax, rsi
0x18009ac0c  inc     rax
0x18009ac0f  cmp     [rcx+rax*2], bx
0x18009ac13  jnz     short loc_18009AC0C
0x18009ac15  add     eax, 2
0x18009ac18  mov     [rsp+21E8h+var_2158], rbx
0x18009ac20  movsxd  rcx, eax
0x18009ac23  mov     r15d, 2
0x18009ac29  mov     edx, r15d
0x18009ac2c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18009ac31  cmp     rax, 100h
0x18009ac37  jbe     short loc_18009AC53
0x18009ac39  mov     rdx, rax
0x18009ac3c  lea     rcx, [rsp+21E8h+var_2158]
0x18009ac44  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18009ac49  mov     rdi, [rsp+21E8h+var_2158]
0x18009ac51  jmp     short loc_18009AC63
0x18009ac53  lea     rdi, [rsp+21E8h+var_2150]
0x18009ac5b  mov     [rsp+21E8h+var_2158], rdi
0x18009ac63  mov     r13, [rsp+21E8h+var_2198]
0x18009ac68  jmp     short loc_18009AC95
0x18009ac6a  xor     ebx, ebx
0x18009ac6c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18009ac70  lea     r15d, [rbx+2]
0x18009ac74  mov     rdi, [rsp+21E8h+var_2158]
0x18009ac7c  mov     r13, qword ptr [rsp+21E8h+Data]
0x18009ac81  mov     rax, [rsp+21E8h+var_2190]
0x18009ac86  mov     [rsp+21E8h+var_21B0], rax
0x18009ac8b  mov     rax, [rsp+21E8h+var_2188]
0x18009ac90  mov     [rsp+21E8h+lpValueName], rax
0x18009ac95  test    rdi, rdi
0x18009ac98  jz      loc_18009AD53
0x18009ac9e  lea     r14, [rsp+21E8h+String1]
0x18009aca6  cmp     [rsp+21E8h+String1], bx
0x18009acae  jz      short loc_18009ACEF
0x18009acb0  mov     r12d, 30h ; '0'
0x18009acb6  mov     rcx, r14; lpsz
0x18009acb9  call    cs:__imp_CharNextW
0x18009acbf  movzx   ecx, word ptr [r14]
0x18009acc3  cmp     cx, 5Ch ; '\'
0x18009acc7  jnz     short loc_18009ACE0
0x18009acc9  cmp     [rax], r12w
0x18009accd  jnz     short loc_18009ACE0
0x18009accf  mov     [rdi], bx
0x18009acd2  mov     rcx, rax; lpsz
0x18009acd5  call    cs:__imp_CharNextW
0x18009acdb  mov     r14, rax
0x18009acde  jmp     short loc_18009ACE6
0x18009ace0  mov     [rdi], cx
0x18009ace3  add     r14, r15
0x18009ace6  add     rdi, r15
0x18009ace9  cmp     [r14], bx
0x18009aced  jnz     short loc_18009ACB6
0x18009acef  mov     dword ptr [rdi], 0
0x18009acf5  mov     r8, [rsp+21E8h+var_2158]
0x18009acfd  test    r8, r8
0x18009ad00  jz      short loc_18009AD48
0x18009ad02  mov     r10d, ebx
0x18009ad05  mov     r9, r8
0x18009ad08  mov     rcx, rsi
0x18009ad0b  inc     rcx
0x18009ad0e  cmp     [r9+rcx*2], bx
0x18009ad13  jnz     short loc_18009AD0B
0x18009ad15  inc     ecx
0x18009ad17  lea     r9, [r9+rcx*2]
0x18009ad1b  lea     r10d, [r10+rcx*2]
0x18009ad1f  cmp     ecx, 1
0x18009ad22  jnz     short loc_18009AD08
0x18009ad24  mov     [rsp+21E8h+cbData], r10d; cbData
0x18009ad29  mov     [rsp+21E8h+lpData], r8; lpData
0x18009ad2e  lea     r9d, [rcx+6]; dwType
0x18009ad32  xor     r8d, r8d; Reserved
0x18009ad35  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18009ad3a  mov     rcx, [r13+0]; hKey
0x18009ad3e  call    cs:__imp_RegSetValueExW
0x18009ad44  mov     edi, eax
0x18009ad46  jmp     short loc_18009AD58
0x18009ad48  mov     ecx, 80004005h; int
0x18009ad4d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18009ad53  mov     edi, 0Eh
0x18009ad58  lea     rcx, [rsp+21E8h+var_2158]
0x18009ad60  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18009ad65  mov     r15, [rsp+21E8h+var_21B0]
0x18009ad6a  jmp     loc_18009B02E
0x18009ad6f  mov     [rsp+21E8h+pulOut], ebx
0x18009ad73  mov     [rsp+21E8h+var_21B0], rbx
0x18009ad78  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18009ad7d  xor     r8d, r8d; dwFlags
0x18009ad80  xor     edx, edx; lcid
0x18009ad82  lea     rcx, [rsp+21E8h+String1]; strIn
0x18009ad8a  call    cs:__imp_VarUI4FromStr
0x18009ad90  mov     edi, eax
0x18009ad92  test    eax, eax
0x18009ad94  jns     short loc_18009ADA7
0x18009ad96  lea     rcx, [rsp+21E8h+var_21B0]
0x18009ad9b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18009ada0  mov     eax, edi
0x18009ada2  jmp     loc_18009B059
0x18009ada7  mov     eax, [rsp+21E8h+pulOut]
0x18009adab  mov     dword ptr [rsp+21E8h+Data], eax
0x18009adaf  mov     [rsp+21E8h+cbData], 4; cbData
0x18009adb7  lea     rax, [rsp+21E8h+Data]
0x18009adbc  mov     [rsp+21E8h+lpData], rax; lpData
0x18009adc1  mov     r9d, 4; dwType
0x18009adc7  xor     r8d, r8d; Reserved
0x18009adca  mov     rdx, r14; lpValueName
0x18009adcd  mov     rcx, [r12]; hKey
0x18009add1  call    cs:__imp_RegSetValueExW
0x18009add7  mov     edi, eax
0x18009add9  lea     rcx, [rsp+21E8h+var_21B0]
0x18009adde  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18009ade3  jmp     loc_18009B02E
0x18009ade8  lea     rax, [rsp+21E8h+String1]
0x18009adf0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18009adf4  inc     rsi
0x18009adf7  cmp     [rax+rsi*2], bx
0x18009adfb  jnz     short loc_18009ADF4
0x18009adfd  mov     dword ptr [rsp+21E8h+Data], esi
0x18009ae01  test    sil, 1
0x18009ae05  jz      short loc_18009AE11
0x18009ae07  mov     eax, 80004005h
0x18009ae0c  jmp     loc_18009B059
0x18009ae11  mov     eax, esi
0x18009ae13  cdq
0x18009ae14  mov     r15d, 2
0x18009ae1a  idiv    r15d
0x18009ae1d  movsxd  r14, eax
0x18009ae20  mov     [rsp+21E8h+var_2158], rbx
0x18009ae28  mov     rdi, r14
0x18009ae2b  mov     [rsp+21E8h+var_2178], r14
0x18009ae30  lea     edx, [r15-1]
0x18009ae34  mov     rcx, r14
0x18009ae37  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18009ae3c  cmp     rax, 100h
0x18009ae42  jbe     short loc_18009AE5E
0x18009ae44  mov     rdx, rax
0x18009ae47  lea     rcx, [rsp+21E8h+var_2158]
0x18009ae4f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18009ae54  mov     rcx, [rsp+21E8h+var_2158]
0x18009ae5c  jmp     short loc_18009AE6E
0x18009ae5e  lea     rcx, [rsp+21E8h+var_2150]
0x18009ae66  mov     [rsp+21E8h+var_2158], rcx
0x18009ae6e  mov     r15, [rsp+21E8h+var_2198]
0x18009ae73  jmp     short loc_18009AEA8
0x18009ae75  xor     ebx, ebx
0x18009ae77  lea     r13d, [rbx+8]
0x18009ae7b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18009ae7f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x18009ae87  mov     rdi, [rsp+21E8h+var_2178]
0x18009ae8c  mov     rax, [rsp+21E8h+var_2190]
0x18009ae91  mov     [rsp+21E8h+var_21B0], rax
0x18009ae96  mov     r15, [rsp+21E8h+var_2170]
0x18009ae9b  mov     rax, [rsp+21E8h+var_2188]
0x18009aea0  mov     [rsp+21E8h+lpValueName], rax
0x18009aea5  mov     r14d, edi
0x18009aea8  test    rcx, rcx
0x18009aeab  jnz     short loc_18009AEBF
0x18009aead  lea     rcx, [rsp+21E8h+var_2158]
0x18009aeb5  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18009aeba  jmp     loc_18009AE07
0x18009aebf  mov     r8, rdi; Size
0x18009aec2  xor     edx, edx; Val
0x18009aec4  call    memset_0
0x18009aec9  mov     r10d, ebx
0x18009aecc  test    esi, esi
0x18009aece  jle     loc_18009AFAC
0x18009aed4  mov     r12d, 30h ; '0'
0x18009aeda  mov     eax, r10d
0x18009aedd  movzx   edx, [rsp+rax*2+21E8h+String1]
0x18009aee5  cmp     edx, 61h ; 'a'
0x18009aee8  ja      short loc_18009AF57
0x18009aeea  jz      loc_18009AF77
0x18009aef0  cmp     edx, 38h ; '8'
0x18009aef3  ja      short loc_18009AF29
0x18009aef5  jz      short loc_18009AF21
0x18009aef7  mov     ecx, edx
0x18009aef9  sub     ecx, r12d
0x18009aefc  jz      short loc_18009AF21
0x18009aefe  sub     ecx, 1
0x18009af01  jz      short loc_18009AF21
0x18009af03  sub     ecx, 1
0x18009af06  jz      short loc_18009AF21
0x18009af08  sub     ecx, 1
0x18009af0b  jz      short loc_18009AF21
0x18009af0d  sub     ecx, 1
0x18009af10  jz      short loc_18009AF21
0x18009af12  sub     ecx, 1
0x18009af15  jz      short loc_18009AF21
0x18009af17  sub     ecx, 1
0x18009af1a  jz      short loc_18009AF21
0x18009af1c  cmp     ecx, 1
0x18009af1f  jnz     short loc_18009AF72
0x18009af21  mov     r9d, edx
0x18009af24  sub     r9d, r12d
0x18009af27  jmp     short loc_18009AF7B
0x18009af29  mov     r9d, edx
0x18009af2c  mov     ecx, edx
0x18009af2e  sub     ecx, 39h ; '9'
0x18009af31  jz      short loc_18009AF21
0x18009af33  sub     ecx, r13d
0x18009af36  jz      short loc_18009AF51
0x18009af38  sub     ecx, 1
0x18009af3b  jz      short loc_18009AF51
0x18009af3d  sub     ecx, 1
0x18009af40  jz      short loc_18009AF51
0x18009af42  sub     ecx, 1
0x18009af45  jz      short loc_18009AF51
0x18009af47  sub     ecx, 1
0x18009af4a  jz      short loc_18009AF51
0x18009af4c  cmp     ecx, 1
0x18009af4f  jnz     short loc_18009AF72
0x18009af51  add     r9d, 0FFFFFFC9h
0x18009af55  jmp     short loc_18009AF7B
0x18009af57  mov     ecx, edx
0x18009af59  sub     ecx, 62h ; 'b'
0x18009af5c  jz      short loc_18009AF77
0x18009af5e  sub     ecx, 1
0x18009af61  jz      short loc_18009AF77
0x18009af63  sub     ecx, 1
0x18009af66  jz      short loc_18009AF77
0x18009af68  sub     ecx, 1
0x18009af6b  jz      short loc_18009AF77
0x18009af6d  cmp     ecx, 1
0x18009af70  jz      short loc_18009AF77
0x18009af72  mov     r9d, ebx
0x18009af75  jmp     short loc_18009AF7B
0x18009af77  lea     r9d, [rdx-57h]
0x18009af7b  mov     r8d, r10d
0x18009af7e  shr     r8, 1
0x18009af81  mov     rdx, [rsp+21E8h+var_2158]
0x18009af89  mov     eax, r10d
0x18009af8c  and     eax, 1
0x18009af8f  shl     eax, 2
0x18009af92  mov     ecx, 4
0x18009af97  sub     ecx, eax
0x18009af99  shl     r9b, cl
0x18009af9c  or      [r8+rdx], r9b
0x18009afa0  inc     r10d
  ... truncated ...
```
