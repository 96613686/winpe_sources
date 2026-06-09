# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x14001cd84`
- end: `0x14001d310`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1420`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140022e00`

## callees

- `0x1400030a0`
- `0x140003c74`
- `0x140019e6c`
- `0x14001b6ec`
- `0x14001b888`
- `0x14001cd84`
- `0x14001d318`
- `0x14001d50c`
- `0x14001d62c`
- `0x140021cc4`
- `0x140024064`
- `0x140049bf0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x14001d01e`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14001d01e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001cfd2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001d065`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001d263`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001d2ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001cfd2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001d065`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001d263`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001d2ba`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14001cf4d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14001cf69`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14001cf4d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14001cf69`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14001ce2b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14001ce2b`

## pseudocode

```c
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
0x14001cd84  push    rbx
0x14001cd86  push    rsi
0x14001cd87  push    rdi
0x14001cd88  push    r12
0x14001cd8a  push    r13
0x14001cd8c  push    r14
0x14001cd8e  push    r15
0x14001cd90  mov     eax, 21B0h
0x14001cd95  call    _alloca_probe
0x14001cd9a  sub     rsp, rax
0x14001cd9d  mov     [rsp+21E8h+var_2160], 0FFFFFFFFFFFFFFFEh
0x14001cda9  mov     rax, cs:__security_cookie
0x14001cdb0  xor     rax, rsp
0x14001cdb3  mov     [rsp+21E8h+var_48], rax
0x14001cdbb  mov     r14, r8
0x14001cdbe  mov     [rsp+21E8h+lpValueName], r8
0x14001cdc3  mov     r12, rdx
0x14001cdc6  mov     [rsp+21E8h+var_2198], rdx
0x14001cdcb  mov     r15, rcx
0x14001cdce  mov     [rsp+21E8h+var_21B0], rcx
0x14001cdd3  mov     qword ptr [rsp+21E8h+Data], rdx
0x14001cdd8  mov     [rsp+21E8h+var_2190], rcx
0x14001cddd  mov     [rsp+21E8h+var_2170], rdx
0x14001cde2  mov     [rsp+21E8h+var_2188], r8
0x14001cde7  mov     [rsp+21E8h+var_2168], r9
0x14001cdef  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x14001cdf7  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x14001cdfc  xor     ebx, ebx
0x14001cdfe  test    eax, eax
0x14001ce00  js      loc_14001D2ED
0x14001ce06  mov     edi, ebx
0x14001ce08  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x14001ce0f  cmp     edi, 4
0x14001ce12  jnb     loc_14001D2E8
0x14001ce18  movsxd  rsi, edi
0x14001ce1b  add     rsi, rsi
0x14001ce1e  mov     rdx, [r13+rsi*8+0]; lpString2
0x14001ce23  lea     rcx, [rsp+21E8h+String1]; lpString1
0x14001ce2b  call    cs:__imp_lstrcmpiW
0x14001ce31  test    eax, eax
0x14001ce33  jz      short loc_14001CE39
0x14001ce35  inc     edi
0x14001ce37  jmp     short loc_14001CE0F
0x14001ce39  movzx   edi, word ptr [r13+rsi*8+8]
0x14001ce3f  mov     rcx, r15; this
0x14001ce42  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x14001ce47  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x14001ce4f  mov     rcx, r15; this
0x14001ce52  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x14001ce57  test    eax, eax
0x14001ce59  js      loc_14001D2ED
0x14001ce5f  mov     r13d, 8
0x14001ce65  cmp     di, r13w
0x14001ce69  jz      loc_14001D27D
0x14001ce6f  cmp     di, 11h
0x14001ce73  jz      loc_14001D07C
0x14001ce79  cmp     di, 13h
0x14001ce7d  jz      loc_14001D003
0x14001ce83  mov     eax, 4008h
0x14001ce88  cmp     di, ax
0x14001ce8b  jnz     loc_14001D2CF
0x14001ce91  lea     rcx, [rsp+21E8h+String1]
0x14001ce99  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001ce9d  mov     rax, rsi
0x14001cea0  inc     rax
0x14001cea3  cmp     [rcx+rax*2], bx
0x14001cea7  jnz     short loc_14001CEA0
0x14001cea9  add     eax, 2
0x14001ceac  mov     [rsp+21E8h+var_2158], rbx
0x14001ceb4  movsxd  rcx, eax
0x14001ceb7  mov     r15d, 2
0x14001cebd  mov     edx, r15d
0x14001cec0  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x14001cec5  cmp     rax, 100h
0x14001cecb  jbe     short loc_14001CEE7
0x14001cecd  mov     rdx, rax
0x14001ced0  lea     rcx, [rsp+21E8h+var_2158]
0x14001ced8  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14001cedd  mov     rdi, [rsp+21E8h+var_2158]
0x14001cee5  jmp     short loc_14001CEF7
0x14001cee7  lea     rdi, [rsp+21E8h+var_2150]
0x14001ceef  mov     [rsp+21E8h+var_2158], rdi
0x14001cef7  mov     r13, [rsp+21E8h+var_2198]
0x14001cefc  jmp     short loc_14001CF29
0x14001cefe  xor     ebx, ebx
0x14001cf00  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001cf04  lea     r15d, [rbx+2]
0x14001cf08  mov     rdi, [rsp+21E8h+var_2158]
0x14001cf10  mov     r13, qword ptr [rsp+21E8h+Data]
0x14001cf15  mov     rax, [rsp+21E8h+var_2190]
0x14001cf1a  mov     [rsp+21E8h+var_21B0], rax
0x14001cf1f  mov     rax, [rsp+21E8h+var_2188]
0x14001cf24  mov     [rsp+21E8h+lpValueName], rax
0x14001cf29  test    rdi, rdi
0x14001cf2c  jz      loc_14001CFE7
0x14001cf32  lea     r14, [rsp+21E8h+String1]
0x14001cf3a  cmp     [rsp+21E8h+String1], bx
0x14001cf42  jz      short loc_14001CF83
0x14001cf44  mov     r12d, 30h ; '0'
0x14001cf4a  mov     rcx, r14; lpsz
0x14001cf4d  call    cs:__imp_CharNextW
0x14001cf53  movzx   ecx, word ptr [r14]
0x14001cf57  cmp     cx, 5Ch ; '\'
0x14001cf5b  jnz     short loc_14001CF74
0x14001cf5d  cmp     [rax], r12w
0x14001cf61  jnz     short loc_14001CF74
0x14001cf63  mov     [rdi], bx
0x14001cf66  mov     rcx, rax; lpsz
0x14001cf69  call    cs:__imp_CharNextW
0x14001cf6f  mov     r14, rax
0x14001cf72  jmp     short loc_14001CF7A
0x14001cf74  mov     [rdi], cx
0x14001cf77  add     r14, r15
0x14001cf7a  add     rdi, r15
0x14001cf7d  cmp     [r14], bx
0x14001cf81  jnz     short loc_14001CF4A
0x14001cf83  mov     dword ptr [rdi], 0
0x14001cf89  mov     r8, [rsp+21E8h+var_2158]
0x14001cf91  test    r8, r8
0x14001cf94  jz      short loc_14001CFDC
0x14001cf96  mov     r10d, ebx
0x14001cf99  mov     r9, r8
0x14001cf9c  mov     rcx, rsi
0x14001cf9f  inc     rcx
0x14001cfa2  cmp     [r9+rcx*2], bx
0x14001cfa7  jnz     short loc_14001CF9F
0x14001cfa9  inc     ecx
0x14001cfab  lea     r9, [r9+rcx*2]
0x14001cfaf  lea     r10d, [r10+rcx*2]
0x14001cfb3  cmp     ecx, 1
0x14001cfb6  jnz     short loc_14001CF9C
0x14001cfb8  mov     [rsp+21E8h+cbData], r10d; cbData
0x14001cfbd  mov     [rsp+21E8h+lpData], r8; lpData
0x14001cfc2  lea     r9d, [rcx+6]; dwType
0x14001cfc6  xor     r8d, r8d; Reserved
0x14001cfc9  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x14001cfce  mov     rcx, [r13+0]; hKey
0x14001cfd2  call    cs:__imp_RegSetValueExW
0x14001cfd8  mov     edi, eax
0x14001cfda  jmp     short loc_14001CFEC
0x14001cfdc  mov     ecx, 80004005h; int
0x14001cfe1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001cfe7  mov     edi, 0Eh
0x14001cfec  lea     rcx, [rsp+21E8h+var_2158]
0x14001cff4  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x14001cff9  mov     r15, [rsp+21E8h+var_21B0]
0x14001cffe  jmp     loc_14001D2C2
0x14001d003  mov     [rsp+21E8h+pulOut], ebx
0x14001d007  mov     [rsp+21E8h+var_21B0], rbx
0x14001d00c  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x14001d011  xor     r8d, r8d; dwFlags
0x14001d014  xor     edx, edx; lcid
0x14001d016  lea     rcx, [rsp+21E8h+String1]; strIn
0x14001d01e  call    cs:__imp_VarUI4FromStr
0x14001d024  mov     edi, eax
0x14001d026  test    eax, eax
0x14001d028  jns     short loc_14001D03B
0x14001d02a  lea     rcx, [rsp+21E8h+var_21B0]
0x14001d02f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14001d034  mov     eax, edi
0x14001d036  jmp     loc_14001D2ED
0x14001d03b  mov     eax, [rsp+21E8h+pulOut]
0x14001d03f  mov     dword ptr [rsp+21E8h+Data], eax
0x14001d043  mov     [rsp+21E8h+cbData], 4; cbData
0x14001d04b  lea     rax, [rsp+21E8h+Data]
0x14001d050  mov     [rsp+21E8h+lpData], rax; lpData
0x14001d055  mov     r9d, 4; dwType
0x14001d05b  xor     r8d, r8d; Reserved
0x14001d05e  mov     rdx, r14; lpValueName
0x14001d061  mov     rcx, [r12]; hKey
0x14001d065  call    cs:__imp_RegSetValueExW
0x14001d06b  mov     edi, eax
0x14001d06d  lea     rcx, [rsp+21E8h+var_21B0]
0x14001d072  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14001d077  jmp     loc_14001D2C2
0x14001d07c  lea     rax, [rsp+21E8h+String1]
0x14001d084  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001d088  inc     rsi
0x14001d08b  cmp     [rax+rsi*2], bx
0x14001d08f  jnz     short loc_14001D088
0x14001d091  mov     dword ptr [rsp+21E8h+Data], esi
0x14001d095  test    sil, 1
0x14001d099  jz      short loc_14001D0A5
0x14001d09b  mov     eax, 80004005h
0x14001d0a0  jmp     loc_14001D2ED
0x14001d0a5  mov     eax, esi
0x14001d0a7  cdq
0x14001d0a8  mov     r15d, 2
0x14001d0ae  idiv    r15d
0x14001d0b1  movsxd  r14, eax
0x14001d0b4  mov     [rsp+21E8h+var_2158], rbx
0x14001d0bc  mov     rdi, r14
0x14001d0bf  mov     [rsp+21E8h+var_2178], r14
0x14001d0c4  lea     edx, [r15-1]
0x14001d0c8  mov     rcx, r14
0x14001d0cb  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x14001d0d0  cmp     rax, 100h
0x14001d0d6  jbe     short loc_14001D0F2
0x14001d0d8  mov     rdx, rax
0x14001d0db  lea     rcx, [rsp+21E8h+var_2158]
0x14001d0e3  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14001d0e8  mov     rcx, [rsp+21E8h+var_2158]
0x14001d0f0  jmp     short loc_14001D102
0x14001d0f2  lea     rcx, [rsp+21E8h+var_2150]
0x14001d0fa  mov     [rsp+21E8h+var_2158], rcx
0x14001d102  mov     r15, [rsp+21E8h+var_2198]
0x14001d107  jmp     short loc_14001D13C
0x14001d109  xor     ebx, ebx
0x14001d10b  lea     r13d, [rbx+8]
0x14001d10f  mov     esi, dword ptr [rsp+21E8h+Data]
0x14001d113  mov     rcx, [rsp+21E8h+var_2158]; void *
0x14001d11b  mov     rdi, [rsp+21E8h+var_2178]
0x14001d120  mov     rax, [rsp+21E8h+var_2190]
0x14001d125  mov     [rsp+21E8h+var_21B0], rax
0x14001d12a  mov     r15, [rsp+21E8h+var_2170]
0x14001d12f  mov     rax, [rsp+21E8h+var_2188]
0x14001d134  mov     [rsp+21E8h+lpValueName], rax
0x14001d139  mov     r14d, edi
0x14001d13c  test    rcx, rcx
0x14001d13f  jnz     short loc_14001D153
0x14001d141  lea     rcx, [rsp+21E8h+var_2158]
0x14001d149  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x14001d14e  jmp     loc_14001D09B
0x14001d153  mov     r8, rdi; Size
0x14001d156  xor     edx, edx; Val
0x14001d158  call    memset_0
0x14001d15d  mov     r10d, ebx
0x14001d160  test    esi, esi
0x14001d162  jle     loc_14001D240
0x14001d168  mov     r12d, 30h ; '0'
0x14001d16e  mov     eax, r10d
0x14001d171  movzx   edx, [rsp+rax*2+21E8h+String1]
0x14001d179  cmp     edx, 61h ; 'a'
0x14001d17c  ja      short loc_14001D1EB
0x14001d17e  jz      loc_14001D20B
0x14001d184  cmp     edx, 38h ; '8'
0x14001d187  ja      short loc_14001D1BD
0x14001d189  jz      short loc_14001D1B5
0x14001d18b  mov     ecx, edx
0x14001d18d  sub     ecx, r12d
0x14001d190  jz      short loc_14001D1B5
0x14001d192  sub     ecx, 1
0x14001d195  jz      short loc_14001D1B5
0x14001d197  sub     ecx, 1
0x14001d19a  jz      short loc_14001D1B5
0x14001d19c  sub     ecx, 1
0x14001d19f  jz      short loc_14001D1B5
0x14001d1a1  sub     ecx, 1
0x14001d1a4  jz      short loc_14001D1B5
0x14001d1a6  sub     ecx, 1
0x14001d1a9  jz      short loc_14001D1B5
0x14001d1ab  sub     ecx, 1
0x14001d1ae  jz      short loc_14001D1B5
0x14001d1b0  cmp     ecx, 1
0x14001d1b3  jnz     short loc_14001D206
0x14001d1b5  mov     r9d, edx
0x14001d1b8  sub     r9d, r12d
0x14001d1bb  jmp     short loc_14001D20F
0x14001d1bd  mov     r9d, edx
0x14001d1c0  mov     ecx, edx
0x14001d1c2  sub     ecx, 39h ; '9'
0x14001d1c5  jz      short loc_14001D1B5
0x14001d1c7  sub     ecx, r13d
0x14001d1ca  jz      short loc_14001D1E5
0x14001d1cc  sub     ecx, 1
0x14001d1cf  jz      short loc_14001D1E5
0x14001d1d1  sub     ecx, 1
0x14001d1d4  jz      short loc_14001D1E5
0x14001d1d6  sub     ecx, 1
0x14001d1d9  jz      short loc_14001D1E5
0x14001d1db  sub     ecx, 1
0x14001d1de  jz      short loc_14001D1E5
0x14001d1e0  cmp     ecx, 1
0x14001d1e3  jnz     short loc_14001D206
0x14001d1e5  add     r9d, 0FFFFFFC9h
0x14001d1e9  jmp     short loc_14001D20F
0x14001d1eb  mov     ecx, edx
0x14001d1ed  sub     ecx, 62h ; 'b'
0x14001d1f0  jz      short loc_14001D20B
0x14001d1f2  sub     ecx, 1
0x14001d1f5  jz      short loc_14001D20B
0x14001d1f7  sub     ecx, 1
0x14001d1fa  jz      short loc_14001D20B
0x14001d1fc  sub     ecx, 1
0x14001d1ff  jz      short loc_14001D20B
0x14001d201  cmp     ecx, 1
0x14001d204  jz      short loc_14001D20B
0x14001d206  mov     r9d, ebx
0x14001d209  jmp     short loc_14001D20F
0x14001d20b  lea     r9d, [rdx-57h]
0x14001d20f  mov     r8d, r10d
0x14001d212  shr     r8, 1
0x14001d215  mov     rdx, [rsp+21E8h+var_2158]
0x14001d21d  mov     eax, r10d
0x14001d220  and     eax, 1
0x14001d223  shl     eax, 2
0x14001d226  mov     ecx, 4
0x14001d22b  sub     ecx, eax
0x14001d22d  shl     r9b, cl
0x14001d230  or      [r8+rdx], r9b
  ... truncated ...
```
