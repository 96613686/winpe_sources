# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180077248`
- end: `0x18007765e`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1046`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180079b40`

## callees

- `0x180051550`
- `0x180074160`
- `0x180076924`
- `0x180076b00`
- `0x180076c60`
- `0x180077248`
- `0x180077664`
- `0x180077914`
- `0x180077cbc`
- `0x1800790f4`
- `0x18007a898`
- `0x1800c8220`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180077550`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180077550`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18007732b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800773f0`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800774d6`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800775d5`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18007732b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800773f0`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800774d6`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800775d5`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180077469`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180077469`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007738f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800773b1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007738f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800773b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077421`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800774b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800775b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077604`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077421`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800774b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800775b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077604`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800772bf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800772bf`

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
  unsigned int i; // ebx
  __int16 v10; // bx
  int v11; // eax
  unsigned __int64 v12; // rax
  wchar_t *v13; // rbx
  WCHAR *v14; // rdi
  const WCHAR *v15; // rax
  wchar_t *lpData; // rbx
  DWORD cbData; // edi
  wchar_t *v18; // rsi
  int v19; // eax
  __int64 v20; // rcx
  LSTATUS v21; // ebx
  HRESULT v22; // ebx
  HKEY v23; // rcx
  int v24; // eax
  int v25; // ebx
  size_t v26; // rsi
  unsigned __int64 v27; // rax
  wchar_t *v28; // rcx
  __int64 j; // r10
  unsigned __int8 v30; // al
  int v31; // r10d
  char v32; // dl
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // eax
  int Token; // eax
  unsigned int v37; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  ATL::CRegParser *v39; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v42[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v39 = this;
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
    v35 = wcslen(String1);
    v21 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v35 + 2);
    goto LABEL_44;
  }
  if ( v10 == 17 )
  {
    v24 = wcslen(String1);
    v25 = v24;
    if ( (v24 & 1) == 0 )
    {
      String = 0;
      v26 = v24 / 2;
      v27 = ATL::AtlMultiplyThrow<unsigned __int64>(v26, 1);
      if ( v27 <= 0x100 )
      {
        v28 = (wchar_t *)v42;
        String = (wchar_t *)v42;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&String, v27);
        v28 = String;
      }
      if ( v28 )
      {
        memset(v28, 0, v26);
        for ( j = 0; (int)j < v25; *(_BYTE *)(v34 + v33) |= v30 << (4 - 4 * v32) )
        {
          v30 = ATL::CRegParser::ChToByte(String1[j]);
          v32 = v31 & 1;
          j = (unsigned int)(v31 + 1);
        }
        v21 = RegSetValueExW(*a2, a3, 0, 3u, (const BYTE *)String, v26);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&String);
        goto LABEL_44;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&String);
    }
    return 2147500037LL;
  }
  if ( v10 != 19 )
  {
    if ( v10 == 16392 )
    {
      v11 = wcslen(String1);
      String = 0;
      v12 = ATL::AtlMultiplyThrow<unsigned __int64>(v11 + 2, 2);
      if ( v12 <= 0x100 )
      {
        v13 = (wchar_t *)v42;
        String = (wchar_t *)v42;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&String, v12);
        v13 = String;
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
              *v13 = 0;
              v14 = CharNextW(v15);
            }
            else
            {
              *v13 = *v14++;
            }
            ++v13;
          }
          while ( *v14 );
          v7 = v39;
        }
        *(_DWORD *)v13 = 0;
        lpData = String;
        if ( !String )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v18 = String;
        do
        {
          v19 = wcslen(v18);
          v20 = (unsigned int)(v19 + 1);
          v18 += v20;
          cbData += 2 * v20;
        }
        while ( v19 );
        v21 = RegSetValueExW(*a2, a3, 0, 7u, (const BYTE *)lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&String);
      goto LABEL_44;
    }
LABEL_46:
    Token = ATL::CRegParser::NextToken(v7, a4);
    v37 = 0;
    if ( Token < 0 )
      return (unsigned int)Token;
    return v37;
  }
  pulOut = 0;
  v39 = 0;
  v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
  if ( v22 < 0 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v39);
    return (unsigned int)v22;
  }
  v23 = *a2;
  *(_DWORD *)Data = pulOut;
  v21 = RegSetValueExW(v23, a3, 0, 4u, Data, 4u);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v39);
LABEL_44:
  if ( !v21 )
    goto LABEL_46;
  return ATL::AtlHresultFromWin32(v21);
}

```

## disassembly

```asm
0x180077248  push    rbp
0x18007724a  push    rbx
0x18007724b  push    rsi
0x18007724c  push    rdi
0x18007724d  push    r12
0x18007724f  push    r13
0x180077251  push    r14
0x180077253  push    r15
0x180077255  lea     rbp, [rsp-2078h]
0x18007725d  mov     eax, 2178h
0x180077262  call    _alloca_probe
0x180077267  sub     rsp, rax
0x18007726a  mov     rax, cs:__security_cookie
0x180077271  xor     rax, rsp
0x180077274  mov     [rbp+20B0h+var_50], rax
0x18007727b  mov     r14, rdx
0x18007727e  mov     [rsp+21B0h+var_2178], rcx
0x180077283  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180077287  mov     r13, r9
0x18007728a  mov     r15, r8
0x18007728d  mov     r12, rcx
0x180077290  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180077295  xor     esi, esi
0x180077297  test    eax, eax
0x180077299  js      loc_18007763A
0x18007729f  mov     ebx, esi
0x1800772a1  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800772a8  cmp     ebx, 4
0x1800772ab  jnb     loc_180077635
0x1800772b1  movsxd  rdi, ebx
0x1800772b4  lea     rcx, [rbp+20B0h+String1]; lpString1
0x1800772b8  add     rdi, rdi
0x1800772bb  mov     rdx, [rax+rdi*8]; lpString2
0x1800772bf  call    cs:__imp_lstrcmpiW
0x1800772c6  nop     dword ptr [rax+rax+00h]
0x1800772cb  test    eax, eax
0x1800772cd  jz      short loc_1800772D3
0x1800772cf  inc     ebx
0x1800772d1  jmp     short loc_1800772A1
0x1800772d3  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800772da  mov     rcx, r12; this
0x1800772dd  movzx   ebx, word ptr [rbx+rdi*8+8]
0x1800772e2  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800772e7  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x1800772eb  mov     rcx, r12; this
0x1800772ee  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800772f3  test    eax, eax
0x1800772f5  js      loc_18007763A
0x1800772fb  cmp     bx, 8
0x1800772ff  jz      loc_1800775D1
0x180077305  cmp     bx, 11h
0x180077309  jz      loc_1800774D2
0x18007730f  cmp     bx, 13h
0x180077313  jz      loc_180077452
0x180077319  mov     eax, 4008h
0x18007731e  cmp     bx, ax
0x180077321  jnz     loc_18007761F
0x180077327  lea     rcx, [rbp+20B0h+String1]; String
0x18007732b  call    cs:__imp_wcslen
0x180077332  nop     dword ptr [rax+rax+00h]
0x180077337  mov     [rsp+21B0h+String], rsi
0x18007733c  add     eax, 2
0x18007733f  mov     esi, 2
0x180077344  movsxd  rcx, eax
0x180077347  mov     edx, esi
0x180077349  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18007734e  cmp     rax, 100h
0x180077354  jbe     short loc_18007736A
0x180077356  mov     rdx, rax
0x180077359  lea     rcx, [rsp+21B0h+String]
0x18007735e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180077363  mov     rbx, [rsp+21B0h+String]
0x180077368  jmp     short loc_180077374
0x18007736a  lea     rbx, [rsp+21B0h+var_2158]
0x18007736f  mov     [rsp+21B0h+String], rbx
0x180077374  xor     ecx, ecx
0x180077376  test    rbx, rbx
0x180077379  jz      loc_18007743C
0x18007737f  lea     rdi, [rbp+20B0h+String1]
0x180077383  cmp     [rbp+20B0h+String1], cx
0x180077387  jz      short loc_1800773D8
0x180077389  xor     r12d, r12d
0x18007738c  mov     rcx, rdi; lpsz
0x18007738f  call    cs:__imp_CharNextW
0x180077396  nop     dword ptr [rax+rax+00h]
0x18007739b  movzx   ecx, word ptr [rdi]
0x18007739e  cmp     cx, 5Ch ; '\'
0x1800773a2  jnz     short loc_1800773C2
0x1800773a4  cmp     word ptr [rax], 30h ; '0'
0x1800773a8  jnz     short loc_1800773C2
0x1800773aa  mov     rcx, rax; lpsz
0x1800773ad  mov     [rbx], r12w
0x1800773b1  call    cs:__imp_CharNextW
0x1800773b8  nop     dword ptr [rax+rax+00h]
0x1800773bd  mov     rdi, rax
0x1800773c0  jmp     short loc_1800773C8
0x1800773c2  mov     [rbx], cx
0x1800773c5  add     rdi, rsi
0x1800773c8  add     rbx, rsi
0x1800773cb  cmp     [rdi], r12w
0x1800773cf  jnz     short loc_18007738C
0x1800773d1  mov     r12, [rsp+21B0h+var_2178]
0x1800773d6  xor     ecx, ecx
0x1800773d8  mov     dword ptr [rbx], 0
0x1800773de  mov     rbx, [rsp+21B0h+String]
0x1800773e3  test    rbx, rbx
0x1800773e6  jz      short loc_180077431
0x1800773e8  mov     edi, ecx
0x1800773ea  mov     rsi, rbx
0x1800773ed  mov     rcx, rsi; String
0x1800773f0  call    cs:__imp_wcslen
0x1800773f7  nop     dword ptr [rax+rax+00h]
0x1800773fc  lea     ecx, [rax+1]
0x1800773ff  lea     rsi, [rsi+rcx*2]
0x180077403  lea     edi, [rdi+rcx*2]
0x180077406  cmp     ecx, 1
0x180077409  jnz     short loc_1800773ED
0x18007740b  lea     r9d, [rcx+6]; dwType
0x18007740f  mov     [rsp+21B0h+cbData], edi; cbData
0x180077413  mov     rcx, [r14]; hKey
0x180077416  xor     r8d, r8d; Reserved
0x180077419  mov     rdx, r15; lpValueName
0x18007741c  mov     [rsp+21B0h+lpData], rbx; lpData
0x180077421  call    cs:__imp_RegSetValueExW
0x180077428  nop     dword ptr [rax+rax+00h]
0x18007742d  mov     ebx, eax
0x18007742f  jmp     short loc_180077441
0x180077431  mov     ecx, 80004005h; int
0x180077436  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18007743c  mov     ebx, 0Eh
0x180077441  lea     rcx, [rsp+21B0h+String]
0x180077446  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18007744b  xor     esi, esi
0x18007744d  jmp     loc_180077612
0x180077452  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x180077457  mov     [rsp+21B0h+pulOut], esi
0x18007745b  xor     r8d, r8d; dwFlags
0x18007745e  mov     [rsp+21B0h+var_2178], rsi
0x180077463  xor     edx, edx; lcid
0x180077465  lea     rcx, [rbp+20B0h+String1]; strIn
0x180077469  call    cs:__imp_VarUI4FromStr
0x180077470  nop     dword ptr [rax+rax+00h]
0x180077475  mov     ebx, eax
0x180077477  test    eax, eax
0x180077479  jns     short loc_18007748C
0x18007747b  lea     rcx, [rsp+21B0h+var_2178]
0x180077480  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180077485  mov     eax, ebx
0x180077487  jmp     loc_18007763A
0x18007748c  mov     eax, [rsp+21B0h+pulOut]
0x180077490  mov     r9d, 4; dwType
0x180077496  mov     rcx, [r14]; hKey
0x180077499  xor     r8d, r8d; Reserved
0x18007749c  mov     dword ptr [rsp+21B0h+Data], eax
0x1800774a0  mov     rdx, r15; lpValueName
0x1800774a3  lea     rax, [rsp+21B0h+Data]
0x1800774a8  mov     [rsp+21B0h+cbData], 4; cbData
0x1800774b0  mov     [rsp+21B0h+lpData], rax; lpData
0x1800774b5  call    cs:__imp_RegSetValueExW
0x1800774bc  nop     dword ptr [rax+rax+00h]
0x1800774c1  lea     rcx, [rsp+21B0h+var_2178]
0x1800774c6  mov     ebx, eax
0x1800774c8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800774cd  jmp     loc_180077612
0x1800774d2  lea     rcx, [rbp+20B0h+String1]; String
0x1800774d6  call    cs:__imp_wcslen
0x1800774dd  nop     dword ptr [rax+rax+00h]
0x1800774e2  mov     rbx, rax
0x1800774e5  test    al, 1
0x1800774e7  jz      short loc_1800774F3
0x1800774e9  mov     eax, 80004005h
0x1800774ee  jmp     loc_18007763A
0x1800774f3  cdq
0x1800774f4  mov     [rsp+21B0h+String], 0
0x1800774fd  mov     esi, 2
0x180077502  idiv    esi
0x180077504  mov     edx, 1
0x180077509  movsxd  rsi, eax
0x18007750c  mov     rcx, rsi
0x18007750f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180077514  cmp     rax, 100h
0x18007751a  jbe     short loc_180077530
0x18007751c  mov     rdx, rax
0x18007751f  lea     rcx, [rsp+21B0h+String]
0x180077524  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180077529  mov     rcx, [rsp+21B0h+String]
0x18007752e  jmp     short loc_18007753A
0x180077530  lea     rcx, [rsp+21B0h+var_2158]; void *
0x180077535  mov     [rsp+21B0h+String], rcx
0x18007753a  test    rcx, rcx
0x18007753d  jnz     short loc_18007754B
0x18007753f  lea     rcx, [rsp+21B0h+String]
0x180077544  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180077549  jmp     short loc_1800774E9
0x18007754b  mov     r8, rsi; Size
0x18007754e  xor     edx, edx; Val
0x180077550  call    cs:__imp_memset
0x180077557  nop     dword ptr [rax+rax+00h]
0x18007755c  xor     r10d, r10d
0x18007755f  test    ebx, ebx
0x180077561  jle     short loc_180077597
0x180077563  movzx   ecx, [rbp+r10*2+20B0h+String1]; unsigned __int16
0x180077569  mov     r8, [rsp+21B0h+String]
0x18007756e  mov     r9d, r10d
0x180077571  shr     r9, 1
0x180077574  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180077579  mov     edx, r10d
0x18007757c  mov     ecx, 4
0x180077581  and     edx, 1
0x180077584  inc     r10d
0x180077587  shl     edx, 2
0x18007758a  sub     ecx, edx
0x18007758c  shl     al, cl
0x18007758e  or      [r9+r8], al
0x180077592  cmp     r10d, ebx
0x180077595  jl      short loc_180077563
0x180077597  mov     rax, [rsp+21B0h+String]
0x18007759c  mov     r9d, 3; dwType
0x1800775a2  mov     rcx, [r14]; hKey
0x1800775a5  xor     r8d, r8d; Reserved
0x1800775a8  mov     [rsp+21B0h+cbData], esi; cbData
0x1800775ac  mov     rdx, r15; lpValueName
0x1800775af  mov     [rsp+21B0h+lpData], rax; lpData
0x1800775b4  call    cs:__imp_RegSetValueExW
0x1800775bb  nop     dword ptr [rax+rax+00h]
0x1800775c0  lea     rcx, [rsp+21B0h+String]
0x1800775c5  mov     ebx, eax
0x1800775c7  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800775cc  jmp     loc_18007744B
0x1800775d1  lea     rcx, [rbp+20B0h+String1]; String
0x1800775d5  call    cs:__imp_wcslen
0x1800775dc  nop     dword ptr [rax+rax+00h]
0x1800775e1  mov     rcx, [r14]; hKey
0x1800775e4  mov     r9d, 1; dwType
0x1800775ea  xor     r8d, r8d; Reserved
0x1800775ed  mov     rdx, r15; lpValueName
0x1800775f0  lea     eax, ds:2[rax*2]
0x1800775f7  mov     [rsp+21B0h+cbData], eax; cbData
0x1800775fb  lea     rax, [rbp+20B0h+String1]
0x1800775ff  mov     [rsp+21B0h+lpData], rax; lpData
0x180077604  call    cs:__imp_RegSetValueExW
0x18007760b  nop     dword ptr [rax+rax+00h]
0x180077610  mov     ebx, eax
0x180077612  test    ebx, ebx
0x180077614  jz      short loc_18007761F
0x180077616  mov     ecx, ebx; unsigned int
0x180077618  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18007761d  jmp     short loc_18007763A
0x18007761f  mov     rdx, r13; unsigned __int16 *
0x180077622  mov     rcx, r12; this
0x180077625  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18007762a  test    eax, eax
0x18007762c  mov     ecx, esi
0x18007762e  cmovs   ecx, eax
0x180077631  mov     eax, ecx
0x180077633  jmp     short loc_18007763A
0x180077635  mov     eax, 80020009h
0x18007763a  mov     rcx, [rbp+20B0h+var_50]
0x180077641  xor     rcx, rsp; StackCookie
0x180077644  call    __security_check_cookie
0x180077649  add     rsp, 2178h
0x180077650  pop     r15
0x180077652  pop     r14
0x180077654  pop     r13
0x180077656  pop     r12
0x180077658  pop     rdi
0x180077659  pop     rsi
0x18007765a  pop     rbx
0x18007765b  pop     rbp
0x18007765c  retn
```
