# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800026a4`
- end: `0x180002ba0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800041fc`

## callees

- `0x1800026a4`
- `0x180002ba8`
- `0x180002cfc`
- `0x180003558`
- `0x180003808`
- `0x1800038f4`
- `0x180005f36`
- `0x180005f60`
- `0x180005ff0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800028ca`
- `ADVAPI32!RegSetValueExW` at `0x180002943`
- `ADVAPI32!RegSetValueExW` at `0x180002ae5`
- `ADVAPI32!RegSetValueExW` at `0x1800028ca`
- `ADVAPI32!RegSetValueExW` at `0x180002943`
- `ADVAPI32!RegSetValueExW` at `0x180002ae5`
- `KERNEL32!lstrcmpiW` at `0x18000271d`
- `KERNEL32!lstrcmpiW` at `0x18000271d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000290d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000290d`
- `USER32!CharNextW` at `0x18000276d`
- `USER32!CharNextW` at `0x18000283d`
- `USER32!CharNextW` at `0x180002859`
- `USER32!CharNextW` at `0x18000276d`
- `USER32!CharNextW` at `0x18000283d`
- `USER32!CharNextW` at `0x180002859`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v5; // r15
  const WCHAR *v6; // r14
  HRESULT result; // eax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // eax
  LSTATUS v21; // edi
  LSTATUS v22; // eax
  __int64 v23; // rsi
  size_t v24; // rbx
  BYTE *v25; // rcx
  int v26; // r10d
  unsigned int v27; // r9d
  char v28; // r9
  unsigned __int64 v29; // r8
  char v30; // r9
  __int64 v31; // rdi
  int Token; // eax
  int v33; // ecx
  ULONG pulOut[2]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE *v36; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v37[264]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE *lpData; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v39[264]; // [rsp+158h] [rbp+58h] BYREF
  OLECHAR String1[4096]; // [rsp+260h] [rbp+160h] BYREF

  *(_QWORD *)Data = a4;
  *(_QWORD *)pulOut = a3;
  v5 = a4;
  v6 = a3;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( result < 0 )
    return result;
  v9 = 0;
  while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
  {
    if ( (unsigned int)++v9 >= 4 )
      return -2147352567;
  }
  v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
  while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
    *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  result = ATL::CRegParser::NextToken(this, String1);
  if ( result < 0 )
    return result;
  if ( v10 == 8 )
  {
    v31 = -1;
    do
      ++v31;
    while ( String1[v31] );
    v22 = RegSetValueExW(*a2, v6, 0, 1u, (const BYTE *)String1, 2 * v31 + 2);
    goto LABEL_43;
  }
  if ( v10 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( String1[v23] );
    if ( (v23 & 1) != 0 )
      return -2147467259;
    v36 = 0;
    v24 = (int)v23 / 2;
    if ( !((int)v23 / 2) )
      goto LABEL_51;
    if ( !(0xFFFFFFFFFFFFFFFFuLL / v24) )
      ATL::AtlThrowImpl(-2147024809);
    if ( v24 > 0x100 )
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v36, v24);
      v25 = v36;
    }
    else
    {
LABEL_51:
      v25 = v37;
      v36 = v37;
    }
    if ( !v25 )
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
      return -2147467259;
    }
    memset_0(v25, 0, v24);
    v26 = 0;
    if ( (int)v23 <= 0 )
      goto LABEL_83;
    while ( 1 )
    {
      v27 = String1[v26];
      if ( v27 > 0x61 )
      {
        if ( v27 == 98 || v27 == 99 || v27 == 100 || v27 - 101 < 2 )
        {
LABEL_80:
          v28 = v27 - 87;
          goto LABEL_81;
        }
LABEL_79:
        v28 = 0;
        goto LABEL_81;
      }
      if ( v27 == 97 )
        goto LABEL_80;
      if ( v27 <= 0x38 )
        break;
      if ( v27 == 57 )
        goto LABEL_67;
      if ( v27 != 65 && v27 != 66 && v27 != 67 && v27 != 68 && v27 - 69 > 1 )
        goto LABEL_79;
      v28 = v27 - 55;
LABEL_81:
      v29 = (unsigned __int64)(unsigned int)v26 >> 1;
      v30 = v28 << (4 - 4 * (v26++ & 1));
      v36[v29] |= v30;
      if ( v26 >= (int)v23 )
      {
        v6 = *(const WCHAR **)pulOut;
LABEL_83:
        v21 = RegSetValueExW(*a2, v6, 0, 3u, v36, (int)v23 / 2);
        if ( v36 != v37 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
        v5 = *(unsigned __int16 **)Data;
LABEL_86:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
LABEL_91:
        Token = ATL::CRegParser::NextToken(this, v5);
        v33 = 0;
        if ( Token < 0 )
          return Token;
        return v33;
      }
    }
    if ( v27 != 56 && v27 != 48 && v27 != 49 && v27 != 50 && v27 != 51 && v27 != 52 && v27 != 53 && v27 - 54 > 1 )
      goto LABEL_79;
LABEL_67:
    v28 = v27 - 48;
    goto LABEL_81;
  }
  if ( v10 != 19 )
  {
    if ( v10 == 16392 )
    {
      lpData = 0;
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      v12 = (int)v11 + 2;
      if ( (_DWORD)v11 == -2 )
        goto LABEL_23;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * v12 <= 0x100 )
      {
LABEL_23:
        v13 = v39;
        lpData = v39;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2 * v12);
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
          v6 = *(const WCHAR **)pulOut;
          v5 = *(unsigned __int16 **)Data;
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
        v20 = RegSetValueExW(*a2, v6, 0, 7u, lpData, cbData);
        v13 = lpData;
        v21 = v20;
      }
      else
      {
        v21 = 14;
      }
      if ( v13 != v39 )
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
      goto LABEL_86;
    }
    goto LABEL_91;
  }
  pulOut[0] = 0;
  result = VarUI4FromStr(String1, 0, 0, pulOut);
  if ( result >= 0 )
  {
    *(_DWORD *)Data = pulOut[0];
    v22 = RegSetValueExW(*a2, v6, 0, 4u, Data, 4u);
LABEL_43:
    v21 = v22;
    goto LABEL_86;
  }
  return result;
}

```

## disassembly

```asm
0x1800026a4  push    rbp
0x1800026a6  push    rbx
0x1800026a7  push    rsi
0x1800026a8  push    rdi
0x1800026a9  push    r12
0x1800026ab  push    r13
0x1800026ad  push    r14
0x1800026af  push    r15
0x1800026b1  lea     rbp, [rsp-2178h]
0x1800026b9  mov     eax, 2278h
0x1800026be  call    _alloca_probe
0x1800026c3  sub     rsp, rax
0x1800026c6  mov     rax, cs:__security_cookie
0x1800026cd  xor     rax, rsp
0x1800026d0  mov     [rbp+21B0h+var_50], rax
0x1800026d7  mov     r13, rdx
0x1800026da  mov     qword ptr [rsp+22B0h+Data], r9
0x1800026df  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x1800026e6  mov     qword ptr [rsp+22B0h+pulOut], r8
0x1800026eb  mov     r15, r9
0x1800026ee  mov     r14, r8
0x1800026f1  mov     r12, rcx
0x1800026f4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800026f9  xor     esi, esi
0x1800026fb  test    eax, eax
0x1800026fd  js      loc_180002B5C
0x180002703  mov     ebx, esi
0x180002705  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000270c  movsxd  rdi, ebx
0x18000270f  lea     rcx, [rbp+21B0h+String1]; lpString1
0x180002716  add     rdi, rdi
0x180002719  mov     rdx, [rax+rdi*8]; lpString2
0x18000271d  call    cs:__imp_lstrcmpiW
0x180002723  test    eax, eax
0x180002725  jz      short loc_18000273F
0x180002727  inc     ebx
0x180002729  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180002730  cmp     ebx, 4
0x180002733  jb      short loc_18000270C
0x180002735  mov     eax, 80020009h
0x18000273a  jmp     loc_180002B5C
0x18000273f  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180002746  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18000274b  mov     edi, 13h
0x180002750  mov     rdx, [r12]
0x180002754  movzx   ecx, word ptr [rdx]
0x180002757  sub     ecx, 9
0x18000275a  jz      short loc_18000276A
0x18000275c  sub     ecx, 1
0x18000275f  jz      short loc_18000276A
0x180002761  sub     ecx, 3
0x180002764  jz      short loc_18000276A
0x180002766  cmp     ecx, edi
0x180002768  jnz     short loc_180002779
0x18000276a  mov     rcx, rdx; lpsz
0x18000276d  call    cs:__imp_CharNextW
0x180002773  mov     [r12], rax
0x180002777  jmp     short loc_180002750
0x180002779  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180002780  mov     rcx, r12; this
0x180002783  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002788  test    eax, eax
0x18000278a  js      loc_180002B5C
0x180002790  mov     eax, 8
0x180002795  cmp     bx, ax
0x180002798  jz      loc_180002B17
0x18000279e  cmp     bx, 11h
0x1800027a2  jz      loc_180002950
0x1800027a8  cmp     bx, di
0x1800027ab  jz      loc_1800028F8
0x1800027b1  mov     eax, 4008h
0x1800027b6  cmp     bx, ax
0x1800027b9  jnz     loc_180002B48
0x1800027bf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800027c3  mov     [rbp+21B0h+var_2160], rsi
0x1800027c7  mov     rax, rdi
0x1800027ca  lea     rcx, [rbp+21B0h+String1]
0x1800027d1  inc     rax
0x1800027d4  cmp     [rcx+rax*2], si
0x1800027d8  jnz     short loc_1800027D1
0x1800027da  add     eax, 2
0x1800027dd  movsxd  rcx, eax
0x1800027e0  jz      short loc_180002810
0x1800027e2  xor     edx, edx
0x1800027e4  mov     rax, rdi
0x1800027e7  div     rcx
0x1800027ea  cmp     rax, 2
0x1800027ee  jb      loc_180002B8A
0x1800027f4  lea     rdx, [rcx+rcx]
0x1800027f8  cmp     rdx, 100h
0x1800027ff  jbe     short loc_180002810
0x180002801  lea     rcx, [rbp+21B0h+var_2160]
0x180002805  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000280a  mov     rbx, [rbp+21B0h+var_2160]
0x18000280e  jmp     short loc_180002818
0x180002810  lea     rbx, [rbp+21B0h+var_2158]
0x180002814  mov     [rbp+21B0h+var_2160], rbx
0x180002818  test    rbx, rbx
0x18000281b  jz      loc_1800028D8
0x180002821  xor     eax, eax
0x180002823  lea     rsi, [rbp+21B0h+String1]
0x18000282a  cmp     [rbp+21B0h+String1], ax
0x180002831  jz      short loc_18000287F
0x180002833  lea     r14d, [rax+30h]
0x180002837  xor     r15d, r15d
0x18000283a  mov     rcx, rsi; lpsz
0x18000283d  call    cs:__imp_CharNextW
0x180002843  movzx   ecx, word ptr [rsi]
0x180002846  cmp     cx, 5Ch ; '\'
0x18000284a  jnz     short loc_180002864
0x18000284c  cmp     [rax], r14w
0x180002850  jnz     short loc_180002864
0x180002852  mov     rcx, rax; lpsz
0x180002855  mov     [rbx], r15w
0x180002859  call    cs:__imp_CharNextW
0x18000285f  mov     rsi, rax
0x180002862  jmp     short loc_18000286B
0x180002864  mov     [rbx], cx
0x180002867  add     rsi, 2
0x18000286b  add     rbx, 2
0x18000286f  cmp     [rsi], r15w
0x180002873  jnz     short loc_18000283A
0x180002875  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x18000287a  mov     r15, qword ptr [rsp+22B0h+Data]
0x18000287f  xor     esi, esi
0x180002881  mov     [rbx], esi
0x180002883  mov     r8, [rbp+21B0h+var_2160]
0x180002887  test    r8, r8
0x18000288a  jz      loc_180002B95
0x180002890  mov     r10d, esi
0x180002893  mov     r9, r8
0x180002896  mov     rcx, rdi
0x180002899  inc     rcx
0x18000289c  cmp     [r9+rcx*2], si
0x1800028a1  jnz     short loc_180002899
0x1800028a3  inc     ecx
0x1800028a5  lea     r9, [r9+rcx*2]
0x1800028a9  lea     r10d, [r10+rcx*2]
0x1800028ad  cmp     ecx, 1
0x1800028b0  jnz     short loc_180002896
0x1800028b2  mov     [rsp+22B0h+cbData], r10d; cbData
0x1800028b7  lea     r9d, [rcx+6]; dwType
0x1800028bb  mov     rcx, [r13+0]; hKey
0x1800028bf  mov     rdx, r14; lpValueName
0x1800028c2  mov     [rsp+22B0h+lpData], r8; lpData
0x1800028c7  xor     r8d, r8d; Reserved
0x1800028ca  call    cs:__imp_RegSetValueExW
0x1800028d0  mov     rbx, [rbp+21B0h+var_2160]
0x1800028d4  mov     edi, eax
0x1800028d6  jmp     short loc_1800028DD
0x1800028d8  mov     edi, 0Eh
0x1800028dd  lea     rax, [rbp+21B0h+var_2158]
0x1800028e1  cmp     rbx, rax
0x1800028e4  jz      loc_180002B0A
0x1800028ea  lea     rcx, [rbp+21B0h+var_2160]
0x1800028ee  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800028f3  jmp     loc_180002B0A
0x1800028f8  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x1800028fd  mov     [rsp+22B0h+pulOut], esi
0x180002901  xor     r8d, r8d; dwFlags
0x180002904  lea     rcx, [rbp+21B0h+String1]; strIn
0x18000290b  xor     edx, edx; lcid
0x18000290d  call    cs:__imp_VarUI4FromStr
0x180002913  test    eax, eax
0x180002915  js      loc_180002B5C
0x18000291b  mov     eax, [rsp+22B0h+pulOut]
0x18000291f  mov     ecx, 4
0x180002924  mov     dword ptr [rsp+22B0h+Data], eax
0x180002928  mov     r9d, ecx; dwType
0x18000292b  mov     [rsp+22B0h+cbData], ecx; cbData
0x18000292f  lea     rax, [rsp+22B0h+Data]
0x180002934  mov     rcx, [r13+0]; hKey
0x180002938  xor     r8d, r8d; Reserved
0x18000293b  mov     rdx, r14; lpValueName
0x18000293e  mov     [rsp+22B0h+lpData], rax; lpData
0x180002943  call    cs:__imp_RegSetValueExW
0x180002949  mov     edi, eax
0x18000294b  jmp     loc_180002B0A
0x180002950  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002954  lea     rax, [rbp+21B0h+String1]
0x18000295b  mov     rsi, rdi
0x18000295e  xor     ecx, ecx
0x180002960  inc     rsi
0x180002963  cmp     [rax+rsi*2], cx
0x180002967  jnz     short loc_180002960
0x180002969  test    sil, 1
0x18000296d  jnz     short loc_1800029CD
0x18000296f  mov     eax, esi
0x180002971  mov     [rsp+22B0h+var_2270], rcx
0x180002976  cdq
0x180002977  sub     eax, edx
0x180002979  sar     eax, 1
0x18000297b  movsxd  r15, eax
0x18000297e  mov     rbx, r15
0x180002981  jz      short loc_1800029B2
0x180002983  xor     edx, edx
0x180002985  mov     rax, rdi
0x180002988  div     rbx
0x18000298b  cmp     rax, 1
0x18000298f  jb      loc_180002B7F
0x180002995  cmp     rbx, 100h
0x18000299c  jbe     short loc_1800029B2
0x18000299e  mov     rdx, rbx
0x1800029a1  lea     rcx, [rsp+22B0h+var_2270]
0x1800029a6  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800029ab  mov     rcx, [rsp+22B0h+var_2270]
0x1800029b0  jmp     short loc_1800029BC
0x1800029b2  lea     rcx, [rsp+22B0h+var_2268]; void *
0x1800029b7  mov     [rsp+22B0h+var_2270], rcx
0x1800029bc  xor     edi, edi
0x1800029be  test    rcx, rcx
0x1800029c1  jnz     short loc_1800029D7
0x1800029c3  lea     rcx, [rsp+22B0h+var_2270]
0x1800029c8  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800029cd  mov     eax, 80004005h
0x1800029d2  jmp     loc_180002B5C
0x1800029d7  mov     r8, rbx; Size
0x1800029da  xor     edx, edx; Val
0x1800029dc  call    memset_0
0x1800029e1  mov     r10d, edi
0x1800029e4  test    esi, esi
0x1800029e6  jle     loc_180002AC6
0x1800029ec  mov     r14d, 30h ; '0'
0x1800029f2  mov     eax, r10d
0x1800029f5  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x1800029fe  cmp     r9d, 61h ; 'a'
0x180002a02  ja      short loc_180002A6E
0x180002a04  jz      loc_180002A8F
0x180002a0a  cmp     r9d, 38h ; '8'
0x180002a0e  ja      short loc_180002A42
0x180002a10  jz      short loc_180002A3D
0x180002a12  mov     ecx, r9d
0x180002a15  sub     ecx, r14d
0x180002a18  jz      short loc_180002A3D
0x180002a1a  sub     ecx, 1
0x180002a1d  jz      short loc_180002A3D
0x180002a1f  sub     ecx, 1
0x180002a22  jz      short loc_180002A3D
0x180002a24  sub     ecx, 1
0x180002a27  jz      short loc_180002A3D
0x180002a29  sub     ecx, 1
0x180002a2c  jz      short loc_180002A3D
0x180002a2e  sub     ecx, 1
0x180002a31  jz      short loc_180002A3D
0x180002a33  sub     ecx, 1
0x180002a36  jz      short loc_180002A3D
0x180002a38  cmp     ecx, 1
0x180002a3b  jnz     short loc_180002A8A
0x180002a3d  sub     r9b, r14b
0x180002a40  jmp     short loc_180002A93
0x180002a42  mov     ecx, r9d
0x180002a45  sub     ecx, 39h ; '9'
0x180002a48  jz      short loc_180002A3D
0x180002a4a  sub     ecx, 8
0x180002a4d  jz      short loc_180002A68
0x180002a4f  sub     ecx, 1
0x180002a52  jz      short loc_180002A68
0x180002a54  sub     ecx, 1
0x180002a57  jz      short loc_180002A68
0x180002a59  sub     ecx, 1
0x180002a5c  jz      short loc_180002A68
0x180002a5e  sub     ecx, 1
0x180002a61  jz      short loc_180002A68
0x180002a63  cmp     ecx, 1
0x180002a66  jnz     short loc_180002A8A
0x180002a68  sub     r9b, 37h ; '7'
0x180002a6c  jmp     short loc_180002A93
0x180002a6e  mov     ecx, r9d
0x180002a71  sub     ecx, 62h ; 'b'
0x180002a74  jz      short loc_180002A8F
0x180002a76  sub     ecx, 1
0x180002a79  jz      short loc_180002A8F
0x180002a7b  sub     ecx, 1
0x180002a7e  jz      short loc_180002A8F
0x180002a80  sub     ecx, 1
0x180002a83  jz      short loc_180002A8F
0x180002a85  cmp     ecx, 1
0x180002a88  jz      short loc_180002A8F
0x180002a8a  mov     r9b, dil
0x180002a8d  jmp     short loc_180002A93
0x180002a8f  sub     r9b, 57h ; 'W'
0x180002a93  mov     rdx, [rsp+22B0h+var_2270]
0x180002a98  mov     eax, r10d
0x180002a9b  and     eax, 1
0x180002a9e  mov     r8d, r10d
0x180002aa1  shl     eax, 2
0x180002aa4  mov     ecx, 4
0x180002aa9  shr     r8, 1
0x180002aac  sub     ecx, eax
0x180002aae  shl     r9b, cl
0x180002ab1  inc     r10d
0x180002ab4  or      [r8+rdx], r9b
0x180002ab8  cmp     r10d, esi
0x180002abb  jl      loc_1800029F2
0x180002ac1  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180002ac6  mov     rax, [rsp+22B0h+var_2270]
0x180002acb  mov     r9d, 3; dwType
0x180002ad1  mov     rcx, [r13+0]; hKey
0x180002ad5  xor     r8d, r8d; Reserved
0x180002ad8  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
