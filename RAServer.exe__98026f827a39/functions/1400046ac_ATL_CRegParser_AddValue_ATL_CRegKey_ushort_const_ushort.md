# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1400046ac`
- end: `0x140004c2c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140009754`

## callees

- `0x1400022d3`
- `0x140002640`
- `0x140003340`
- `0x1400035ec`
- `0x1400046ac`
- `0x140004c34`
- `0x140004da0`
- `0x140004f54`
- `0x1400080e8`
- `0x14000a938`
- `0x140015aa0`
- `0x140015b60`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1400048ee`
- `ADVAPI32!RegSetValueExW` at `0x140004981`
- `ADVAPI32!RegSetValueExW` at `0x140004b7f`
- `ADVAPI32!RegSetValueExW` at `0x140004bd6`
- `ADVAPI32!RegSetValueExW` at `0x1400048ee`
- `ADVAPI32!RegSetValueExW` at `0x140004981`
- `ADVAPI32!RegSetValueExW` at `0x140004b7f`
- `ADVAPI32!RegSetValueExW` at `0x140004bd6`
- `KERNEL32!lstrcmpiW` at `0x140004747`
- `KERNEL32!lstrcmpiW` at `0x140004747`
- `USER32!CharNextW` at `0x140004869`
- `USER32!CharNextW` at `0x140004885`
- `USER32!CharNextW` at `0x140004869`
- `USER32!CharNextW` at `0x140004885`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000493a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000493a`

## pseudocode

```c
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
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
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
0x1400046ac  push    rbx
0x1400046ae  push    rsi
0x1400046af  push    rdi
0x1400046b0  push    r12
0x1400046b2  push    r13
0x1400046b4  push    r14
0x1400046b6  push    r15
0x1400046b8  mov     eax, 21B0h
0x1400046bd  call    _alloca_probe
0x1400046c2  sub     rsp, rax
0x1400046c5  mov     rax, cs:__security_cookie
0x1400046cc  xor     rax, rsp
0x1400046cf  mov     [rsp+21E8h+var_48], rax
0x1400046d7  mov     r14, r8
0x1400046da  mov     [rsp+21E8h+lpValueName], r8
0x1400046df  mov     r12, rdx
0x1400046e2  mov     [rsp+21E8h+var_2198], rdx
0x1400046e7  mov     r15, rcx
0x1400046ea  mov     [rsp+21E8h+var_21B0], rcx
0x1400046ef  mov     qword ptr [rsp+21E8h+Data], rdx
0x1400046f4  mov     [rsp+21E8h+var_2190], rcx
0x1400046f9  mov     [rsp+21E8h+var_2170], rdx
0x1400046fe  mov     [rsp+21E8h+var_2188], r8
0x140004703  mov     [rsp+21E8h+var_2168], r9
0x14000470b  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x140004713  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004718  xor     ebx, ebx
0x14000471a  test    eax, eax
0x14000471c  js      loc_140004C09
0x140004722  mov     edi, ebx
0x140004724  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000472b  cmp     edi, 4
0x14000472e  jnb     loc_140004C04
0x140004734  movsxd  rsi, edi
0x140004737  add     rsi, rsi
0x14000473a  mov     rdx, [r13+rsi*8+0]; lpString2
0x14000473f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x140004747  call    cs:__imp_lstrcmpiW
0x14000474d  test    eax, eax
0x14000474f  jz      short loc_140004755
0x140004751  inc     edi
0x140004753  jmp     short loc_14000472B
0x140004755  movzx   edi, word ptr [r13+rsi*8+8]
0x14000475b  mov     rcx, r15; this
0x14000475e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x140004763  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x14000476b  mov     rcx, r15; this
0x14000476e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004773  test    eax, eax
0x140004775  js      loc_140004C09
0x14000477b  mov     r13d, 8
0x140004781  cmp     di, r13w
0x140004785  jz      loc_140004B99
0x14000478b  cmp     di, 11h
0x14000478f  jz      loc_140004998
0x140004795  cmp     di, 13h
0x140004799  jz      loc_14000491F
0x14000479f  mov     eax, 4008h
0x1400047a4  cmp     di, ax
0x1400047a7  jnz     loc_140004BEB
0x1400047ad  lea     rcx, [rsp+21E8h+String1]
0x1400047b5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400047b9  mov     rax, rsi
0x1400047bc  inc     rax
0x1400047bf  cmp     [rcx+rax*2], bx
0x1400047c3  jnz     short loc_1400047BC
0x1400047c5  add     eax, 2
0x1400047c8  mov     [rsp+21E8h+var_2158], rbx
0x1400047d0  movsxd  rcx, eax
0x1400047d3  mov     r15d, 2
0x1400047d9  mov     edx, r15d
0x1400047dc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1400047e1  cmp     rax, 100h
0x1400047e7  jbe     short loc_140004803
0x1400047e9  mov     rdx, rax
0x1400047ec  lea     rcx, [rsp+21E8h+var_2158]
0x1400047f4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1400047f9  mov     rdi, [rsp+21E8h+var_2158]
0x140004801  jmp     short loc_140004813
0x140004803  lea     rdi, [rsp+21E8h+var_2150]
0x14000480b  mov     [rsp+21E8h+var_2158], rdi
0x140004813  mov     r13, [rsp+21E8h+var_2198]
0x140004818  jmp     short loc_140004845
0x14000481a  xor     ebx, ebx
0x14000481c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140004820  lea     r15d, [rbx+2]
0x140004824  mov     rdi, [rsp+21E8h+var_2158]
0x14000482c  mov     r13, qword ptr [rsp+21E8h+Data]
0x140004831  mov     rax, [rsp+21E8h+var_2190]
0x140004836  mov     [rsp+21E8h+var_21B0], rax
0x14000483b  mov     rax, [rsp+21E8h+var_2188]
0x140004840  mov     [rsp+21E8h+lpValueName], rax
0x140004845  test    rdi, rdi
0x140004848  jz      loc_140004903
0x14000484e  lea     r14, [rsp+21E8h+String1]
0x140004856  cmp     [rsp+21E8h+String1], bx
0x14000485e  jz      short loc_14000489F
0x140004860  mov     r12d, 30h ; '0'
0x140004866  mov     rcx, r14; lpsz
0x140004869  call    cs:__imp_CharNextW
0x14000486f  movzx   ecx, word ptr [r14]
0x140004873  cmp     cx, 5Ch ; '\'
0x140004877  jnz     short loc_140004890
0x140004879  cmp     [rax], r12w
0x14000487d  jnz     short loc_140004890
0x14000487f  mov     [rdi], bx
0x140004882  mov     rcx, rax; lpsz
0x140004885  call    cs:__imp_CharNextW
0x14000488b  mov     r14, rax
0x14000488e  jmp     short loc_140004896
0x140004890  mov     [rdi], cx
0x140004893  add     r14, r15
0x140004896  add     rdi, r15
0x140004899  cmp     [r14], bx
0x14000489d  jnz     short loc_140004866
0x14000489f  mov     dword ptr [rdi], 0
0x1400048a5  mov     r8, [rsp+21E8h+var_2158]
0x1400048ad  test    r8, r8
0x1400048b0  jz      short loc_1400048F8
0x1400048b2  mov     r10d, ebx
0x1400048b5  mov     r9, r8
0x1400048b8  mov     rcx, rsi
0x1400048bb  inc     rcx
0x1400048be  cmp     [r9+rcx*2], bx
0x1400048c3  jnz     short loc_1400048BB
0x1400048c5  inc     ecx
0x1400048c7  lea     r9, [r9+rcx*2]
0x1400048cb  lea     r10d, [r10+rcx*2]
0x1400048cf  cmp     ecx, 1
0x1400048d2  jnz     short loc_1400048B8
0x1400048d4  mov     [rsp+21E8h+cbData], r10d; cbData
0x1400048d9  mov     [rsp+21E8h+lpData], r8; lpData
0x1400048de  lea     r9d, [rcx+6]; dwType
0x1400048e2  xor     r8d, r8d; Reserved
0x1400048e5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x1400048ea  mov     rcx, [r13+0]; hKey
0x1400048ee  call    cs:__imp_RegSetValueExW
0x1400048f4  mov     edi, eax
0x1400048f6  jmp     short loc_140004908
0x1400048f8  mov     ecx, 80004005h; int
0x1400048fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140004903  mov     edi, 0Eh
0x140004908  lea     rcx, [rsp+21E8h+var_2158]
0x140004910  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140004915  mov     r15, [rsp+21E8h+var_21B0]
0x14000491a  jmp     loc_140004BDE
0x14000491f  mov     [rsp+21E8h+pulOut], ebx
0x140004923  mov     [rsp+21E8h+var_21B0], rbx
0x140004928  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x14000492d  xor     r8d, r8d; dwFlags
0x140004930  xor     edx, edx; lcid
0x140004932  lea     rcx, [rsp+21E8h+String1]; strIn
0x14000493a  call    cs:__imp_VarUI4FromStr
0x140004940  mov     edi, eax
0x140004942  test    eax, eax
0x140004944  jns     short loc_140004957
0x140004946  lea     rcx, [rsp+21E8h+var_21B0]
0x14000494b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140004950  mov     eax, edi
0x140004952  jmp     loc_140004C09
0x140004957  mov     eax, [rsp+21E8h+pulOut]
0x14000495b  mov     dword ptr [rsp+21E8h+Data], eax
0x14000495f  mov     [rsp+21E8h+cbData], 4; cbData
0x140004967  lea     rax, [rsp+21E8h+Data]
0x14000496c  mov     [rsp+21E8h+lpData], rax; lpData
0x140004971  mov     r9d, 4; dwType
0x140004977  xor     r8d, r8d; Reserved
0x14000497a  mov     rdx, r14; lpValueName
0x14000497d  mov     rcx, [r12]; hKey
0x140004981  call    cs:__imp_RegSetValueExW
0x140004987  mov     edi, eax
0x140004989  lea     rcx, [rsp+21E8h+var_21B0]
0x14000498e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140004993  jmp     loc_140004BDE
0x140004998  lea     rax, [rsp+21E8h+String1]
0x1400049a0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400049a4  inc     rsi
0x1400049a7  cmp     [rax+rsi*2], bx
0x1400049ab  jnz     short loc_1400049A4
0x1400049ad  mov     dword ptr [rsp+21E8h+Data], esi
0x1400049b1  test    sil, 1
0x1400049b5  jz      short loc_1400049C1
0x1400049b7  mov     eax, 80004005h
0x1400049bc  jmp     loc_140004C09
0x1400049c1  mov     eax, esi
0x1400049c3  cdq
0x1400049c4  mov     r15d, 2
0x1400049ca  idiv    r15d
0x1400049cd  movsxd  r14, eax
0x1400049d0  mov     [rsp+21E8h+var_2158], rbx
0x1400049d8  mov     rdi, r14
0x1400049db  mov     [rsp+21E8h+var_2178], r14
0x1400049e0  lea     edx, [r15-1]
0x1400049e4  mov     rcx, r14
0x1400049e7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1400049ec  cmp     rax, 100h
0x1400049f2  jbe     short loc_140004A0E
0x1400049f4  mov     rdx, rax
0x1400049f7  lea     rcx, [rsp+21E8h+var_2158]
0x1400049ff  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140004a04  mov     rcx, [rsp+21E8h+var_2158]
0x140004a0c  jmp     short loc_140004A1E
0x140004a0e  lea     rcx, [rsp+21E8h+var_2150]
0x140004a16  mov     [rsp+21E8h+var_2158], rcx
0x140004a1e  mov     r15, [rsp+21E8h+var_2198]
0x140004a23  jmp     short loc_140004A58
0x140004a25  xor     ebx, ebx
0x140004a27  lea     r13d, [rbx+8]
0x140004a2b  mov     esi, dword ptr [rsp+21E8h+Data]
0x140004a2f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x140004a37  mov     rdi, [rsp+21E8h+var_2178]
0x140004a3c  mov     rax, [rsp+21E8h+var_2190]
0x140004a41  mov     [rsp+21E8h+var_21B0], rax
0x140004a46  mov     r15, [rsp+21E8h+var_2170]
0x140004a4b  mov     rax, [rsp+21E8h+var_2188]
0x140004a50  mov     [rsp+21E8h+lpValueName], rax
0x140004a55  mov     r14d, edi
0x140004a58  test    rcx, rcx
0x140004a5b  jnz     short loc_140004A6F
0x140004a5d  lea     rcx, [rsp+21E8h+var_2158]
0x140004a65  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140004a6a  jmp     loc_1400049B7
0x140004a6f  mov     r8, rdi; Size
0x140004a72  xor     edx, edx; Val
0x140004a74  call    memset_0
0x140004a79  mov     r10d, ebx
0x140004a7c  test    esi, esi
0x140004a7e  jle     loc_140004B5C
0x140004a84  mov     r12d, 30h ; '0'
0x140004a8a  mov     eax, r10d
0x140004a8d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x140004a95  cmp     edx, 61h ; 'a'
0x140004a98  ja      short loc_140004B07
0x140004a9a  jz      loc_140004B27
0x140004aa0  cmp     edx, 38h ; '8'
0x140004aa3  ja      short loc_140004AD9
0x140004aa5  jz      short loc_140004AD1
0x140004aa7  mov     ecx, edx
0x140004aa9  sub     ecx, r12d
0x140004aac  jz      short loc_140004AD1
0x140004aae  sub     ecx, 1
0x140004ab1  jz      short loc_140004AD1
0x140004ab3  sub     ecx, 1
0x140004ab6  jz      short loc_140004AD1
0x140004ab8  sub     ecx, 1
0x140004abb  jz      short loc_140004AD1
0x140004abd  sub     ecx, 1
0x140004ac0  jz      short loc_140004AD1
0x140004ac2  sub     ecx, 1
0x140004ac5  jz      short loc_140004AD1
0x140004ac7  sub     ecx, 1
0x140004aca  jz      short loc_140004AD1
0x140004acc  cmp     ecx, 1
0x140004acf  jnz     short loc_140004B22
0x140004ad1  mov     r9d, edx
0x140004ad4  sub     r9d, r12d
0x140004ad7  jmp     short loc_140004B2B
0x140004ad9  mov     r9d, edx
0x140004adc  mov     ecx, edx
0x140004ade  sub     ecx, 39h ; '9'
0x140004ae1  jz      short loc_140004AD1
0x140004ae3  sub     ecx, r13d
0x140004ae6  jz      short loc_140004B01
0x140004ae8  sub     ecx, 1
0x140004aeb  jz      short loc_140004B01
0x140004aed  sub     ecx, 1
0x140004af0  jz      short loc_140004B01
0x140004af2  sub     ecx, 1
0x140004af5  jz      short loc_140004B01
0x140004af7  sub     ecx, 1
0x140004afa  jz      short loc_140004B01
0x140004afc  cmp     ecx, 1
0x140004aff  jnz     short loc_140004B22
0x140004b01  add     r9d, 0FFFFFFC9h
0x140004b05  jmp     short loc_140004B2B
0x140004b07  mov     ecx, edx
0x140004b09  sub     ecx, 62h ; 'b'
0x140004b0c  jz      short loc_140004B27
0x140004b0e  sub     ecx, 1
0x140004b11  jz      short loc_140004B27
0x140004b13  sub     ecx, 1
0x140004b16  jz      short loc_140004B27
0x140004b18  sub     ecx, 1
0x140004b1b  jz      short loc_140004B27
0x140004b1d  cmp     ecx, 1
0x140004b20  jz      short loc_140004B27
0x140004b22  mov     r9d, ebx
0x140004b25  jmp     short loc_140004B2B
0x140004b27  lea     r9d, [rdx-57h]
0x140004b2b  mov     r8d, r10d
0x140004b2e  shr     r8, 1
0x140004b31  mov     rdx, [rsp+21E8h+var_2158]
0x140004b39  mov     eax, r10d
0x140004b3c  and     eax, 1
0x140004b3f  shl     eax, 2
0x140004b42  mov     ecx, 4
0x140004b47  sub     ecx, eax
0x140004b49  shl     r9b, cl
0x140004b4c  or      [r8+rdx], r9b
0x140004b50  inc     r10d
  ... truncated ...
```
