# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x180134cbc`
- end: `0x18013523c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18013ba2c`

## callees

- `0x1800f63e4`
- `0x1801244c0`
- `0x18012540e`
- `0x1801323d4`
- `0x180132bb0`
- `0x1801334bc`
- `0x180134cbc`
- `0x180135244`
- `0x180135504`
- `0x18013a418`
- `0x18013dbe4`
- `0x180222f70`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180134f4a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180134f4a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180134efe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180134f91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18013518f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801351e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180134efe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180134f91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18013518f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801351e6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180134e79`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180134e95`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180134e79`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180134e95`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180134d57`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180134d57`

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
          v13 = v45;
          lpData = v45;
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
0x180134cbc  push    rbx
0x180134cbe  push    rsi
0x180134cbf  push    rdi
0x180134cc0  push    r12
0x180134cc2  push    r13
0x180134cc4  push    r14
0x180134cc6  push    r15
0x180134cc8  mov     eax, 21B0h
0x180134ccd  call    _alloca_probe
0x180134cd2  sub     rsp, rax
0x180134cd5  mov     rax, cs:__security_cookie
0x180134cdc  xor     rax, rsp
0x180134cdf  mov     [rsp+21E8h+var_48], rax
0x180134ce7  mov     r14, r8
0x180134cea  mov     [rsp+21E8h+lpValueName], r8
0x180134cef  mov     r12, rdx
0x180134cf2  mov     [rsp+21E8h+var_2198], rdx
0x180134cf7  mov     r15, rcx
0x180134cfa  mov     [rsp+21E8h+var_21B0], rcx
0x180134cff  mov     qword ptr [rsp+21E8h+Data], rdx
0x180134d04  mov     [rsp+21E8h+var_2190], rcx
0x180134d09  mov     [rsp+21E8h+var_2170], rdx
0x180134d0e  mov     [rsp+21E8h+var_2188], r8
0x180134d13  mov     [rsp+21E8h+var_2168], r9
0x180134d1b  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x180134d23  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180134d28  xor     ebx, ebx
0x180134d2a  test    eax, eax
0x180134d2c  js      loc_180135219
0x180134d32  mov     edi, ebx
0x180134d34  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x180134d3b  cmp     edi, 4
0x180134d3e  jnb     loc_180135214
0x180134d44  movsxd  rsi, edi
0x180134d47  add     rsi, rsi
0x180134d4a  mov     rdx, [r13+rsi*8+0]; lpString2
0x180134d4f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180134d57  call    cs:__imp_lstrcmpiW
0x180134d5d  test    eax, eax
0x180134d5f  jz      short loc_180134D65
0x180134d61  inc     edi
0x180134d63  jmp     short loc_180134D3B
0x180134d65  movzx   edi, word ptr [r13+rsi*8+8]
0x180134d6b  mov     rcx, r15; this
0x180134d6e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180134d73  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x180134d7b  mov     rcx, r15; this
0x180134d7e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180134d83  test    eax, eax
0x180134d85  js      loc_180135219
0x180134d8b  mov     r13d, 8
0x180134d91  cmp     di, r13w
0x180134d95  jz      loc_1801351A9
0x180134d9b  cmp     di, 11h
0x180134d9f  jz      loc_180134FA8
0x180134da5  cmp     di, 13h
0x180134da9  jz      loc_180134F2F
0x180134daf  mov     eax, 4008h
0x180134db4  cmp     di, ax
0x180134db7  jnz     loc_1801351FB
0x180134dbd  lea     rcx, [rsp+21E8h+String1]
0x180134dc5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180134dc9  mov     rax, rsi
0x180134dcc  inc     rax
0x180134dcf  cmp     [rcx+rax*2], bx
0x180134dd3  jnz     short loc_180134DCC
0x180134dd5  add     eax, 2
0x180134dd8  mov     [rsp+21E8h+var_2158], rbx
0x180134de0  movsxd  rcx, eax
0x180134de3  mov     r15d, 2
0x180134de9  mov     edx, r15d
0x180134dec  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180134df1  cmp     rax, 100h
0x180134df7  jbe     short loc_180134E13
0x180134df9  mov     rdx, rax
0x180134dfc  lea     rcx, [rsp+21E8h+var_2158]
0x180134e04  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180134e09  mov     rdi, [rsp+21E8h+var_2158]
0x180134e11  jmp     short loc_180134E23
0x180134e13  lea     rdi, [rsp+21E8h+var_2150]
0x180134e1b  mov     [rsp+21E8h+var_2158], rdi
0x180134e23  mov     r13, [rsp+21E8h+var_2198]
0x180134e28  jmp     short loc_180134E55
0x180134e2a  xor     ebx, ebx
0x180134e2c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180134e30  lea     r15d, [rbx+2]
0x180134e34  mov     rdi, [rsp+21E8h+var_2158]
0x180134e3c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180134e41  mov     rax, [rsp+21E8h+var_2190]
0x180134e46  mov     [rsp+21E8h+var_21B0], rax
0x180134e4b  mov     rax, [rsp+21E8h+var_2188]
0x180134e50  mov     [rsp+21E8h+lpValueName], rax
0x180134e55  test    rdi, rdi
0x180134e58  jz      loc_180134F13
0x180134e5e  lea     r14, [rsp+21E8h+String1]
0x180134e66  cmp     [rsp+21E8h+String1], bx
0x180134e6e  jz      short loc_180134EAF
0x180134e70  mov     r12d, 30h ; '0'
0x180134e76  mov     rcx, r14; lpsz
0x180134e79  call    cs:__imp_CharNextW
0x180134e7f  movzx   ecx, word ptr [r14]
0x180134e83  cmp     cx, 5Ch ; '\'
0x180134e87  jnz     short loc_180134EA0
0x180134e89  cmp     [rax], r12w
0x180134e8d  jnz     short loc_180134EA0
0x180134e8f  mov     [rdi], bx
0x180134e92  mov     rcx, rax; lpsz
0x180134e95  call    cs:__imp_CharNextW
0x180134e9b  mov     r14, rax
0x180134e9e  jmp     short loc_180134EA6
0x180134ea0  mov     [rdi], cx
0x180134ea3  add     r14, r15
0x180134ea6  add     rdi, r15
0x180134ea9  cmp     [r14], bx
0x180134ead  jnz     short loc_180134E76
0x180134eaf  mov     dword ptr [rdi], 0
0x180134eb5  mov     r8, [rsp+21E8h+var_2158]
0x180134ebd  test    r8, r8
0x180134ec0  jz      short loc_180134F08
0x180134ec2  mov     r10d, ebx
0x180134ec5  mov     r9, r8
0x180134ec8  mov     rcx, rsi
0x180134ecb  inc     rcx
0x180134ece  cmp     [r9+rcx*2], bx
0x180134ed3  jnz     short loc_180134ECB
0x180134ed5  inc     ecx
0x180134ed7  lea     r9, [r9+rcx*2]
0x180134edb  lea     r10d, [r10+rcx*2]
0x180134edf  cmp     ecx, 1
0x180134ee2  jnz     short loc_180134EC8
0x180134ee4  mov     [rsp+21E8h+cbData], r10d; cbData
0x180134ee9  mov     [rsp+21E8h+lpData], r8; lpData
0x180134eee  lea     r9d, [rcx+6]; dwType
0x180134ef2  xor     r8d, r8d; Reserved
0x180134ef5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x180134efa  mov     rcx, [r13+0]; hKey
0x180134efe  call    cs:__imp_RegSetValueExW
0x180134f04  mov     edi, eax
0x180134f06  jmp     short loc_180134F18
0x180134f08  mov     ecx, 80004005h; int
0x180134f0d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180134f13  mov     edi, 0Eh
0x180134f18  lea     rcx, [rsp+21E8h+var_2158]
0x180134f20  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x180134f25  mov     r15, [rsp+21E8h+var_21B0]
0x180134f2a  jmp     loc_1801351EE
0x180134f2f  mov     [rsp+21E8h+pulOut], ebx
0x180134f33  mov     [rsp+21E8h+var_21B0], rbx
0x180134f38  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x180134f3d  xor     r8d, r8d; dwFlags
0x180134f40  xor     edx, edx; lcid
0x180134f42  lea     rcx, [rsp+21E8h+String1]; strIn
0x180134f4a  call    cs:__imp_VarUI4FromStr
0x180134f50  mov     edi, eax
0x180134f52  test    eax, eax
0x180134f54  jns     short loc_180134F67
0x180134f56  lea     rcx, [rsp+21E8h+var_21B0]
0x180134f5b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180134f60  mov     eax, edi
0x180134f62  jmp     loc_180135219
0x180134f67  mov     eax, [rsp+21E8h+pulOut]
0x180134f6b  mov     dword ptr [rsp+21E8h+Data], eax
0x180134f6f  mov     [rsp+21E8h+cbData], 4; cbData
0x180134f77  lea     rax, [rsp+21E8h+Data]
0x180134f7c  mov     [rsp+21E8h+lpData], rax; lpData
0x180134f81  mov     r9d, 4; dwType
0x180134f87  xor     r8d, r8d; Reserved
0x180134f8a  mov     rdx, r14; lpValueName
0x180134f8d  mov     rcx, [r12]; hKey
0x180134f91  call    cs:__imp_RegSetValueExW
0x180134f97  mov     edi, eax
0x180134f99  lea     rcx, [rsp+21E8h+var_21B0]
0x180134f9e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180134fa3  jmp     loc_1801351EE
0x180134fa8  lea     rax, [rsp+21E8h+String1]
0x180134fb0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180134fb4  inc     rsi
0x180134fb7  cmp     [rax+rsi*2], bx
0x180134fbb  jnz     short loc_180134FB4
0x180134fbd  mov     dword ptr [rsp+21E8h+Data], esi
0x180134fc1  test    sil, 1
0x180134fc5  jz      short loc_180134FD1
0x180134fc7  mov     eax, 80004005h
0x180134fcc  jmp     loc_180135219
0x180134fd1  mov     eax, esi
0x180134fd3  cdq
0x180134fd4  mov     r15d, 2
0x180134fda  idiv    r15d
0x180134fdd  movsxd  r14, eax
0x180134fe0  mov     [rsp+21E8h+var_2158], rbx
0x180134fe8  mov     rdi, r14
0x180134feb  mov     [rsp+21E8h+var_2178], r14
0x180134ff0  lea     edx, [r15-1]
0x180134ff4  mov     rcx, r14
0x180134ff7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180134ffc  cmp     rax, 100h
0x180135002  jbe     short loc_18013501E
0x180135004  mov     rdx, rax
0x180135007  lea     rcx, [rsp+21E8h+var_2158]
0x18013500f  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180135014  mov     rcx, [rsp+21E8h+var_2158]
0x18013501c  jmp     short loc_18013502E
0x18013501e  lea     rcx, [rsp+21E8h+var_2150]
0x180135026  mov     [rsp+21E8h+var_2158], rcx
0x18013502e  mov     r15, [rsp+21E8h+var_2198]
0x180135033  jmp     short loc_180135068
0x180135035  xor     ebx, ebx
0x180135037  lea     r13d, [rbx+8]
0x18013503b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18013503f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180135047  mov     rdi, [rsp+21E8h+var_2178]
0x18013504c  mov     rax, [rsp+21E8h+var_2190]
0x180135051  mov     [rsp+21E8h+var_21B0], rax
0x180135056  mov     r15, [rsp+21E8h+var_2170]
0x18013505b  mov     rax, [rsp+21E8h+var_2188]
0x180135060  mov     [rsp+21E8h+lpValueName], rax
0x180135065  mov     r14d, edi
0x180135068  test    rcx, rcx
0x18013506b  jnz     short loc_18013507F
0x18013506d  lea     rcx, [rsp+21E8h+var_2158]
0x180135075  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18013507a  jmp     loc_180134FC7
0x18013507f  mov     r8, rdi; Size
0x180135082  xor     edx, edx; Val
0x180135084  call    memset_0
0x180135089  mov     r10d, ebx
0x18013508c  test    esi, esi
0x18013508e  jle     loc_18013516C
0x180135094  mov     r12d, 30h ; '0'
0x18013509a  mov     eax, r10d
0x18013509d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x1801350a5  cmp     edx, 61h ; 'a'
0x1801350a8  ja      short loc_180135117
0x1801350aa  jz      loc_180135137
0x1801350b0  cmp     edx, 38h ; '8'
0x1801350b3  ja      short loc_1801350E9
0x1801350b5  jz      short loc_1801350E1
0x1801350b7  mov     ecx, edx
0x1801350b9  sub     ecx, r12d
0x1801350bc  jz      short loc_1801350E1
0x1801350be  sub     ecx, 1
0x1801350c1  jz      short loc_1801350E1
0x1801350c3  sub     ecx, 1
0x1801350c6  jz      short loc_1801350E1
0x1801350c8  sub     ecx, 1
0x1801350cb  jz      short loc_1801350E1
0x1801350cd  sub     ecx, 1
0x1801350d0  jz      short loc_1801350E1
0x1801350d2  sub     ecx, 1
0x1801350d5  jz      short loc_1801350E1
0x1801350d7  sub     ecx, 1
0x1801350da  jz      short loc_1801350E1
0x1801350dc  cmp     ecx, 1
0x1801350df  jnz     short loc_180135132
0x1801350e1  mov     r9d, edx
0x1801350e4  sub     r9d, r12d
0x1801350e7  jmp     short loc_18013513B
0x1801350e9  mov     r9d, edx
0x1801350ec  mov     ecx, edx
0x1801350ee  sub     ecx, 39h ; '9'
0x1801350f1  jz      short loc_1801350E1
0x1801350f3  sub     ecx, r13d
0x1801350f6  jz      short loc_180135111
0x1801350f8  sub     ecx, 1
0x1801350fb  jz      short loc_180135111
0x1801350fd  sub     ecx, 1
0x180135100  jz      short loc_180135111
0x180135102  sub     ecx, 1
0x180135105  jz      short loc_180135111
0x180135107  sub     ecx, 1
0x18013510a  jz      short loc_180135111
0x18013510c  cmp     ecx, 1
0x18013510f  jnz     short loc_180135132
0x180135111  add     r9d, 0FFFFFFC9h
0x180135115  jmp     short loc_18013513B
0x180135117  mov     ecx, edx
0x180135119  sub     ecx, 62h ; 'b'
0x18013511c  jz      short loc_180135137
0x18013511e  sub     ecx, 1
0x180135121  jz      short loc_180135137
0x180135123  sub     ecx, 1
0x180135126  jz      short loc_180135137
0x180135128  sub     ecx, 1
0x18013512b  jz      short loc_180135137
0x18013512d  cmp     ecx, 1
0x180135130  jz      short loc_180135137
0x180135132  mov     r9d, ebx
0x180135135  jmp     short loc_18013513B
0x180135137  lea     r9d, [rdx-57h]
0x18013513b  mov     r8d, r10d
0x18013513e  shr     r8, 1
0x180135141  mov     rdx, [rsp+21E8h+var_2158]
0x180135149  mov     eax, r10d
0x18013514c  and     eax, 1
0x18013514f  shl     eax, 2
0x180135152  mov     ecx, 4
0x180135157  sub     ecx, eax
0x180135159  shl     r9b, cl
0x18013515c  or      [r8+rdx], r9b
0x180135160  inc     r10d
  ... truncated ...
```
