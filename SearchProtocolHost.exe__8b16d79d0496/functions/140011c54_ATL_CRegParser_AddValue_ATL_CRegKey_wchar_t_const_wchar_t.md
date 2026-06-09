# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x140011c54`
- end: `0x1400121e0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1420`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140024a44`

## callees

- `0x140005240`
- `0x140006210`
- `0x140007d44`
- `0x14000e534`
- `0x14000e6ec`
- `0x140011c54`
- `0x1400121e8`
- `0x1400124f0`
- `0x1400125fc`
- `0x140020960`
- `0x140029044`
- `0x140069b10`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x140011eee`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140011eee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011ea2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011f35`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140012133`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001218a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011ea2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011f35`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140012133`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001218a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140011e1d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140011e39`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140011e1d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140011e39`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140011cfb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140011cfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(ATL::CRegParser *this, HKEY *a2, const wchar_t *a3, wchar_t *a4)
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
  wchar_t *v43; // [rsp+80h] [rbp-2168h]
  __int64 v44; // [rsp+88h] [rbp-2160h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v46[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  v44 = -2;
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
          v27 = v46;
          lpData = v46;
        }
        else
        {
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v26);
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
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v27, 0, v25);
      v29 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_76:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, lpData, v24);
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
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
          v13 = v46;
          lpData = v46;
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
      ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
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
0x140011c54  push    rbx
0x140011c56  push    rsi
0x140011c57  push    rdi
0x140011c58  push    r12
0x140011c5a  push    r13
0x140011c5c  push    r14
0x140011c5e  push    r15
0x140011c60  mov     eax, 21B0h
0x140011c65  call    _alloca_probe
0x140011c6a  sub     rsp, rax
0x140011c6d  mov     [rsp+21E8h+var_2160], 0FFFFFFFFFFFFFFFEh
0x140011c79  mov     rax, cs:__security_cookie
0x140011c80  xor     rax, rsp
0x140011c83  mov     [rsp+21E8h+var_48], rax
0x140011c8b  mov     r14, r8
0x140011c8e  mov     [rsp+21E8h+lpValueName], r8
0x140011c93  mov     r12, rdx
0x140011c96  mov     [rsp+21E8h+var_2198], rdx
0x140011c9b  mov     r15, rcx
0x140011c9e  mov     [rsp+21E8h+var_21B0], rcx
0x140011ca3  mov     qword ptr [rsp+21E8h+Data], rdx
0x140011ca8  mov     [rsp+21E8h+var_2190], rcx
0x140011cad  mov     [rsp+21E8h+var_2170], rdx
0x140011cb2  mov     [rsp+21E8h+var_2188], r8
0x140011cb7  mov     [rsp+21E8h+var_2168], r9
0x140011cbf  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x140011cc7  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140011ccc  xor     ebx, ebx
0x140011cce  test    eax, eax
0x140011cd0  js      loc_1400121BD
0x140011cd6  mov     edi, ebx
0x140011cd8  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x140011cdf  cmp     edi, 4
0x140011ce2  jnb     loc_1400121B8
0x140011ce8  movsxd  rsi, edi
0x140011ceb  add     rsi, rsi
0x140011cee  mov     rdx, [r13+rsi*8+0]; lpString2
0x140011cf3  lea     rcx, [rsp+21E8h+String1]; lpString1
0x140011cfb  call    cs:__imp_lstrcmpiW
0x140011d01  test    eax, eax
0x140011d03  jz      short loc_140011D09
0x140011d05  inc     edi
0x140011d07  jmp     short loc_140011CDF
0x140011d09  movzx   edi, word ptr [r13+rsi*8+8]
0x140011d0f  mov     rcx, r15; this
0x140011d12  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x140011d17  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x140011d1f  mov     rcx, r15; this
0x140011d22  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140011d27  test    eax, eax
0x140011d29  js      loc_1400121BD
0x140011d2f  mov     r13d, 8
0x140011d35  cmp     di, r13w
0x140011d39  jz      loc_14001214D
0x140011d3f  cmp     di, 11h
0x140011d43  jz      loc_140011F4C
0x140011d49  cmp     di, 13h
0x140011d4d  jz      loc_140011ED3
0x140011d53  mov     eax, 4008h
0x140011d58  cmp     di, ax
0x140011d5b  jnz     loc_14001219F
0x140011d61  lea     rcx, [rsp+21E8h+String1]
0x140011d69  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140011d6d  mov     rax, rsi
0x140011d70  inc     rax
0x140011d73  cmp     [rcx+rax*2], bx
0x140011d77  jnz     short loc_140011D70
0x140011d79  add     eax, 2
0x140011d7c  mov     [rsp+21E8h+var_2158], rbx
0x140011d84  movsxd  rcx, eax
0x140011d87  mov     r15d, 2
0x140011d8d  mov     edx, r15d
0x140011d90  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140011d95  cmp     rax, 100h
0x140011d9b  jbe     short loc_140011DB7
0x140011d9d  mov     rdx, rax
0x140011da0  lea     rcx, [rsp+21E8h+var_2158]
0x140011da8  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140011dad  mov     rdi, [rsp+21E8h+var_2158]
0x140011db5  jmp     short loc_140011DC7
0x140011db7  lea     rdi, [rsp+21E8h+var_2150]
0x140011dbf  mov     [rsp+21E8h+var_2158], rdi
0x140011dc7  mov     r13, [rsp+21E8h+var_2198]
0x140011dcc  jmp     short loc_140011DF9
0x140011dce  xor     ebx, ebx
0x140011dd0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140011dd4  lea     r15d, [rbx+2]
0x140011dd8  mov     rdi, [rsp+21E8h+var_2158]
0x140011de0  mov     r13, qword ptr [rsp+21E8h+Data]
0x140011de5  mov     rax, [rsp+21E8h+var_2190]
0x140011dea  mov     [rsp+21E8h+var_21B0], rax
0x140011def  mov     rax, [rsp+21E8h+var_2188]
0x140011df4  mov     [rsp+21E8h+lpValueName], rax
0x140011df9  test    rdi, rdi
0x140011dfc  jz      loc_140011EB7
0x140011e02  lea     r14, [rsp+21E8h+String1]
0x140011e0a  cmp     [rsp+21E8h+String1], bx
0x140011e12  jz      short loc_140011E53
0x140011e14  mov     r12d, 30h ; '0'
0x140011e1a  mov     rcx, r14; lpsz
0x140011e1d  call    cs:__imp_CharNextW
0x140011e23  movzx   ecx, word ptr [r14]
0x140011e27  cmp     cx, 5Ch ; '\'
0x140011e2b  jnz     short loc_140011E44
0x140011e2d  cmp     [rax], r12w
0x140011e31  jnz     short loc_140011E44
0x140011e33  mov     [rdi], bx
0x140011e36  mov     rcx, rax; lpsz
0x140011e39  call    cs:__imp_CharNextW
0x140011e3f  mov     r14, rax
0x140011e42  jmp     short loc_140011E4A
0x140011e44  mov     [rdi], cx
0x140011e47  add     r14, r15
0x140011e4a  add     rdi, r15
0x140011e4d  cmp     [r14], bx
0x140011e51  jnz     short loc_140011E1A
0x140011e53  mov     dword ptr [rdi], 0
0x140011e59  mov     r8, [rsp+21E8h+var_2158]
0x140011e61  test    r8, r8
0x140011e64  jz      short loc_140011EAC
0x140011e66  mov     r10d, ebx
0x140011e69  mov     r9, r8
0x140011e6c  mov     rcx, rsi
0x140011e6f  inc     rcx
0x140011e72  cmp     [r9+rcx*2], bx
0x140011e77  jnz     short loc_140011E6F
0x140011e79  inc     ecx
0x140011e7b  lea     r9, [r9+rcx*2]
0x140011e7f  lea     r10d, [r10+rcx*2]
0x140011e83  cmp     ecx, 1
0x140011e86  jnz     short loc_140011E6C
0x140011e88  mov     [rsp+21E8h+cbData], r10d; cbData
0x140011e8d  mov     [rsp+21E8h+lpData], r8; lpData
0x140011e92  lea     r9d, [rcx+6]; dwType
0x140011e96  xor     r8d, r8d; Reserved
0x140011e99  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x140011e9e  mov     rcx, [r13+0]; hKey
0x140011ea2  call    cs:__imp_RegSetValueExW
0x140011ea8  mov     edi, eax
0x140011eaa  jmp     short loc_140011EBC
0x140011eac  mov     ecx, 80004005h; int
0x140011eb1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140011eb7  mov     edi, 0Eh
0x140011ebc  lea     rcx, [rsp+21E8h+var_2158]
0x140011ec4  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x140011ec9  mov     r15, [rsp+21E8h+var_21B0]
0x140011ece  jmp     loc_140012192
0x140011ed3  mov     [rsp+21E8h+pulOut], ebx
0x140011ed7  mov     [rsp+21E8h+var_21B0], rbx
0x140011edc  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x140011ee1  xor     r8d, r8d; dwFlags
0x140011ee4  xor     edx, edx; lcid
0x140011ee6  lea     rcx, [rsp+21E8h+String1]; strIn
0x140011eee  call    cs:__imp_VarUI4FromStr
0x140011ef4  mov     edi, eax
0x140011ef6  test    eax, eax
0x140011ef8  jns     short loc_140011F0B
0x140011efa  lea     rcx, [rsp+21E8h+var_21B0]
0x140011eff  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140011f04  mov     eax, edi
0x140011f06  jmp     loc_1400121BD
0x140011f0b  mov     eax, [rsp+21E8h+pulOut]
0x140011f0f  mov     dword ptr [rsp+21E8h+Data], eax
0x140011f13  mov     [rsp+21E8h+cbData], 4; cbData
0x140011f1b  lea     rax, [rsp+21E8h+Data]
0x140011f20  mov     [rsp+21E8h+lpData], rax; lpData
0x140011f25  mov     r9d, 4; dwType
0x140011f2b  xor     r8d, r8d; Reserved
0x140011f2e  mov     rdx, r14; lpValueName
0x140011f31  mov     rcx, [r12]; hKey
0x140011f35  call    cs:__imp_RegSetValueExW
0x140011f3b  mov     edi, eax
0x140011f3d  lea     rcx, [rsp+21E8h+var_21B0]
0x140011f42  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140011f47  jmp     loc_140012192
0x140011f4c  lea     rax, [rsp+21E8h+String1]
0x140011f54  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140011f58  inc     rsi
0x140011f5b  cmp     [rax+rsi*2], bx
0x140011f5f  jnz     short loc_140011F58
0x140011f61  mov     dword ptr [rsp+21E8h+Data], esi
0x140011f65  test    sil, 1
0x140011f69  jz      short loc_140011F75
0x140011f6b  mov     eax, 80004005h
0x140011f70  jmp     loc_1400121BD
0x140011f75  mov     eax, esi
0x140011f77  cdq
0x140011f78  mov     r15d, 2
0x140011f7e  idiv    r15d
0x140011f81  movsxd  r14, eax
0x140011f84  mov     [rsp+21E8h+var_2158], rbx
0x140011f8c  mov     rdi, r14
0x140011f8f  mov     [rsp+21E8h+var_2178], r14
0x140011f94  lea     edx, [r15-1]
0x140011f98  mov     rcx, r14
0x140011f9b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140011fa0  cmp     rax, 100h
0x140011fa6  jbe     short loc_140011FC2
0x140011fa8  mov     rdx, rax
0x140011fab  lea     rcx, [rsp+21E8h+var_2158]
0x140011fb3  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140011fb8  mov     rcx, [rsp+21E8h+var_2158]
0x140011fc0  jmp     short loc_140011FD2
0x140011fc2  lea     rcx, [rsp+21E8h+var_2150]
0x140011fca  mov     [rsp+21E8h+var_2158], rcx
0x140011fd2  mov     r15, [rsp+21E8h+var_2198]
0x140011fd7  jmp     short loc_14001200C
0x140011fd9  xor     ebx, ebx
0x140011fdb  lea     r13d, [rbx+8]
0x140011fdf  mov     esi, dword ptr [rsp+21E8h+Data]
0x140011fe3  mov     rcx, [rsp+21E8h+var_2158]; void *
0x140011feb  mov     rdi, [rsp+21E8h+var_2178]
0x140011ff0  mov     rax, [rsp+21E8h+var_2190]
0x140011ff5  mov     [rsp+21E8h+var_21B0], rax
0x140011ffa  mov     r15, [rsp+21E8h+var_2170]
0x140011fff  mov     rax, [rsp+21E8h+var_2188]
0x140012004  mov     [rsp+21E8h+lpValueName], rax
0x140012009  mov     r14d, edi
0x14001200c  test    rcx, rcx
0x14001200f  jnz     short loc_140012023
0x140012011  lea     rcx, [rsp+21E8h+var_2158]
0x140012019  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x14001201e  jmp     loc_140011F6B
0x140012023  mov     r8, rdi; Size
0x140012026  xor     edx, edx; Val
0x140012028  call    memset_0
0x14001202d  mov     r10d, ebx
0x140012030  test    esi, esi
0x140012032  jle     loc_140012110
0x140012038  mov     r12d, 30h ; '0'
0x14001203e  mov     eax, r10d
0x140012041  movzx   edx, [rsp+rax*2+21E8h+String1]
0x140012049  cmp     edx, 61h ; 'a'
0x14001204c  ja      short loc_1400120BB
0x14001204e  jz      loc_1400120DB
0x140012054  cmp     edx, 38h ; '8'
0x140012057  ja      short loc_14001208D
0x140012059  jz      short loc_140012085
0x14001205b  mov     ecx, edx
0x14001205d  sub     ecx, r12d
0x140012060  jz      short loc_140012085
0x140012062  sub     ecx, 1
0x140012065  jz      short loc_140012085
0x140012067  sub     ecx, 1
0x14001206a  jz      short loc_140012085
0x14001206c  sub     ecx, 1
0x14001206f  jz      short loc_140012085
0x140012071  sub     ecx, 1
0x140012074  jz      short loc_140012085
0x140012076  sub     ecx, 1
0x140012079  jz      short loc_140012085
0x14001207b  sub     ecx, 1
0x14001207e  jz      short loc_140012085
0x140012080  cmp     ecx, 1
0x140012083  jnz     short loc_1400120D6
0x140012085  mov     r9d, edx
0x140012088  sub     r9d, r12d
0x14001208b  jmp     short loc_1400120DF
0x14001208d  mov     r9d, edx
0x140012090  mov     ecx, edx
0x140012092  sub     ecx, 39h ; '9'
0x140012095  jz      short loc_140012085
0x140012097  sub     ecx, r13d
0x14001209a  jz      short loc_1400120B5
0x14001209c  sub     ecx, 1
0x14001209f  jz      short loc_1400120B5
0x1400120a1  sub     ecx, 1
0x1400120a4  jz      short loc_1400120B5
0x1400120a6  sub     ecx, 1
0x1400120a9  jz      short loc_1400120B5
0x1400120ab  sub     ecx, 1
0x1400120ae  jz      short loc_1400120B5
0x1400120b0  cmp     ecx, 1
0x1400120b3  jnz     short loc_1400120D6
0x1400120b5  add     r9d, 0FFFFFFC9h
0x1400120b9  jmp     short loc_1400120DF
0x1400120bb  mov     ecx, edx
0x1400120bd  sub     ecx, 62h ; 'b'
0x1400120c0  jz      short loc_1400120DB
0x1400120c2  sub     ecx, 1
0x1400120c5  jz      short loc_1400120DB
0x1400120c7  sub     ecx, 1
0x1400120ca  jz      short loc_1400120DB
0x1400120cc  sub     ecx, 1
0x1400120cf  jz      short loc_1400120DB
0x1400120d1  cmp     ecx, 1
0x1400120d4  jz      short loc_1400120DB
0x1400120d6  mov     r9d, ebx
0x1400120d9  jmp     short loc_1400120DF
0x1400120db  lea     r9d, [rdx-57h]
0x1400120df  mov     r8d, r10d
0x1400120e2  shr     r8, 1
0x1400120e5  mov     rdx, [rsp+21E8h+var_2158]
0x1400120ed  mov     eax, r10d
0x1400120f0  and     eax, 1
0x1400120f3  shl     eax, 2
0x1400120f6  mov     ecx, 4
0x1400120fb  sub     ecx, eax
0x1400120fd  shl     r9b, cl
0x140012100  or      [r8+rdx], r9b
  ... truncated ...
```
