# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180006784`
- end: `0x180006c80`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009884`

## callees

- `0x180006784`
- `0x180006c88`
- `0x180006ddc`
- `0x180006df4`
- `0x180007f30`
- `0x180008930`
- `0x18000c966`
- `0x18000c990`
- `0x18000ca20`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800069ed`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800069ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800069aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006a23`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006bc5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800069aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006a23`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006bc5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000684d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000691d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006939`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000684d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000691d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006939`
- `KERNEL32!lstrcmpiW` at `0x1800067fd`
- `KERNEL32!lstrcmpiW` at `0x1800067fd`

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
0x180006784  push    rbp
0x180006786  push    rbx
0x180006787  push    rsi
0x180006788  push    rdi
0x180006789  push    r12
0x18000678b  push    r13
0x18000678d  push    r14
0x18000678f  push    r15
0x180006791  lea     rbp, [rsp-2178h]
0x180006799  mov     eax, 2278h
0x18000679e  call    _alloca_probe
0x1800067a3  sub     rsp, rax
0x1800067a6  mov     rax, cs:__security_cookie
0x1800067ad  xor     rax, rsp
0x1800067b0  mov     [rbp+21B0h+var_50], rax
0x1800067b7  mov     r13, rdx
0x1800067ba  mov     qword ptr [rsp+22B0h+Data], r9
0x1800067bf  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x1800067c6  mov     qword ptr [rsp+22B0h+pulOut], r8
0x1800067cb  mov     r15, r9
0x1800067ce  mov     r14, r8
0x1800067d1  mov     r12, rcx
0x1800067d4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800067d9  xor     esi, esi
0x1800067db  test    eax, eax
0x1800067dd  js      loc_180006C3C
0x1800067e3  mov     ebx, esi
0x1800067e5  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800067ec  movsxd  rdi, ebx
0x1800067ef  lea     rcx, [rbp+21B0h+String1]; lpString1
0x1800067f6  add     rdi, rdi
0x1800067f9  mov     rdx, [rax+rdi*8]; lpString2
0x1800067fd  call    cs:__imp_lstrcmpiW
0x180006803  test    eax, eax
0x180006805  jz      short loc_18000681F
0x180006807  inc     ebx
0x180006809  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180006810  cmp     ebx, 4
0x180006813  jb      short loc_1800067EC
0x180006815  mov     eax, 80020009h
0x18000681a  jmp     loc_180006C3C
0x18000681f  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180006826  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18000682b  mov     edi, 13h
0x180006830  mov     rdx, [r12]
0x180006834  movzx   ecx, word ptr [rdx]
0x180006837  sub     ecx, 9
0x18000683a  jz      short loc_18000684A
0x18000683c  sub     ecx, 1
0x18000683f  jz      short loc_18000684A
0x180006841  sub     ecx, 3
0x180006844  jz      short loc_18000684A
0x180006846  cmp     ecx, edi
0x180006848  jnz     short loc_180006859
0x18000684a  mov     rcx, rdx; lpsz
0x18000684d  call    cs:__imp_CharNextW
0x180006853  mov     [r12], rax
0x180006857  jmp     short loc_180006830
0x180006859  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180006860  mov     rcx, r12; this
0x180006863  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006868  test    eax, eax
0x18000686a  js      loc_180006C3C
0x180006870  mov     eax, 8
0x180006875  cmp     bx, ax
0x180006878  jz      loc_180006BF7
0x18000687e  cmp     bx, 11h
0x180006882  jz      loc_180006A30
0x180006888  cmp     bx, di
0x18000688b  jz      loc_1800069D8
0x180006891  mov     eax, 4008h
0x180006896  cmp     bx, ax
0x180006899  jnz     loc_180006C28
0x18000689f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800068a3  mov     [rbp+21B0h+var_2160], rsi
0x1800068a7  mov     rax, rdi
0x1800068aa  lea     rcx, [rbp+21B0h+String1]
0x1800068b1  inc     rax
0x1800068b4  cmp     [rcx+rax*2], si
0x1800068b8  jnz     short loc_1800068B1
0x1800068ba  add     eax, 2
0x1800068bd  movsxd  rcx, eax
0x1800068c0  jz      short loc_1800068F0
0x1800068c2  xor     edx, edx
0x1800068c4  mov     rax, rdi
0x1800068c7  div     rcx
0x1800068ca  cmp     rax, 2
0x1800068ce  jb      loc_180006C6A
0x1800068d4  lea     rdx, [rcx+rcx]
0x1800068d8  cmp     rdx, 100h
0x1800068df  jbe     short loc_1800068F0
0x1800068e1  lea     rcx, [rbp+21B0h+var_2160]
0x1800068e5  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800068ea  mov     rbx, [rbp+21B0h+var_2160]
0x1800068ee  jmp     short loc_1800068F8
0x1800068f0  lea     rbx, [rbp+21B0h+var_2158]
0x1800068f4  mov     [rbp+21B0h+var_2160], rbx
0x1800068f8  test    rbx, rbx
0x1800068fb  jz      loc_1800069B8
0x180006901  xor     eax, eax
0x180006903  lea     rsi, [rbp+21B0h+String1]
0x18000690a  cmp     [rbp+21B0h+String1], ax
0x180006911  jz      short loc_18000695F
0x180006913  lea     r14d, [rax+30h]
0x180006917  xor     r15d, r15d
0x18000691a  mov     rcx, rsi; lpsz
0x18000691d  call    cs:__imp_CharNextW
0x180006923  movzx   ecx, word ptr [rsi]
0x180006926  cmp     cx, 5Ch ; '\'
0x18000692a  jnz     short loc_180006944
0x18000692c  cmp     [rax], r14w
0x180006930  jnz     short loc_180006944
0x180006932  mov     rcx, rax; lpsz
0x180006935  mov     [rbx], r15w
0x180006939  call    cs:__imp_CharNextW
0x18000693f  mov     rsi, rax
0x180006942  jmp     short loc_18000694B
0x180006944  mov     [rbx], cx
0x180006947  add     rsi, 2
0x18000694b  add     rbx, 2
0x18000694f  cmp     [rsi], r15w
0x180006953  jnz     short loc_18000691A
0x180006955  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x18000695a  mov     r15, qword ptr [rsp+22B0h+Data]
0x18000695f  xor     esi, esi
0x180006961  mov     [rbx], esi
0x180006963  mov     r8, [rbp+21B0h+var_2160]
0x180006967  test    r8, r8
0x18000696a  jz      loc_180006C75
0x180006970  mov     r10d, esi
0x180006973  mov     r9, r8
0x180006976  mov     rcx, rdi
0x180006979  inc     rcx
0x18000697c  cmp     [r9+rcx*2], si
0x180006981  jnz     short loc_180006979
0x180006983  inc     ecx
0x180006985  lea     r9, [r9+rcx*2]
0x180006989  lea     r10d, [r10+rcx*2]
0x18000698d  cmp     ecx, 1
0x180006990  jnz     short loc_180006976
0x180006992  mov     [rsp+22B0h+cbData], r10d; cbData
0x180006997  lea     r9d, [rcx+6]; dwType
0x18000699b  mov     rcx, [r13+0]; hKey
0x18000699f  mov     rdx, r14; lpValueName
0x1800069a2  mov     [rsp+22B0h+lpData], r8; lpData
0x1800069a7  xor     r8d, r8d; Reserved
0x1800069aa  call    cs:__imp_RegSetValueExW
0x1800069b0  mov     rbx, [rbp+21B0h+var_2160]
0x1800069b4  mov     edi, eax
0x1800069b6  jmp     short loc_1800069BD
0x1800069b8  mov     edi, 0Eh
0x1800069bd  lea     rax, [rbp+21B0h+var_2158]
0x1800069c1  cmp     rbx, rax
0x1800069c4  jz      loc_180006BEA
0x1800069ca  lea     rcx, [rbp+21B0h+var_2160]
0x1800069ce  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800069d3  jmp     loc_180006BEA
0x1800069d8  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x1800069dd  mov     [rsp+22B0h+pulOut], esi
0x1800069e1  xor     r8d, r8d; dwFlags
0x1800069e4  lea     rcx, [rbp+21B0h+String1]; strIn
0x1800069eb  xor     edx, edx; lcid
0x1800069ed  call    cs:__imp_VarUI4FromStr
0x1800069f3  test    eax, eax
0x1800069f5  js      loc_180006C3C
0x1800069fb  mov     eax, [rsp+22B0h+pulOut]
0x1800069ff  mov     ecx, 4
0x180006a04  mov     dword ptr [rsp+22B0h+Data], eax
0x180006a08  mov     r9d, ecx; dwType
0x180006a0b  mov     [rsp+22B0h+cbData], ecx; cbData
0x180006a0f  lea     rax, [rsp+22B0h+Data]
0x180006a14  mov     rcx, [r13+0]; hKey
0x180006a18  xor     r8d, r8d; Reserved
0x180006a1b  mov     rdx, r14; lpValueName
0x180006a1e  mov     [rsp+22B0h+lpData], rax; lpData
0x180006a23  call    cs:__imp_RegSetValueExW
0x180006a29  mov     edi, eax
0x180006a2b  jmp     loc_180006BEA
0x180006a30  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006a34  lea     rax, [rbp+21B0h+String1]
0x180006a3b  mov     rsi, rdi
0x180006a3e  xor     ecx, ecx
0x180006a40  inc     rsi
0x180006a43  cmp     [rax+rsi*2], cx
0x180006a47  jnz     short loc_180006A40
0x180006a49  test    sil, 1
0x180006a4d  jnz     short loc_180006AAD
0x180006a4f  mov     eax, esi
0x180006a51  mov     [rsp+22B0h+var_2270], rcx
0x180006a56  cdq
0x180006a57  sub     eax, edx
0x180006a59  sar     eax, 1
0x180006a5b  movsxd  r15, eax
0x180006a5e  mov     rbx, r15
0x180006a61  jz      short loc_180006A92
0x180006a63  xor     edx, edx
0x180006a65  mov     rax, rdi
0x180006a68  div     rbx
0x180006a6b  cmp     rax, 1
0x180006a6f  jb      loc_180006C5F
0x180006a75  cmp     rbx, 100h
0x180006a7c  jbe     short loc_180006A92
0x180006a7e  mov     rdx, rbx
0x180006a81  lea     rcx, [rsp+22B0h+var_2270]
0x180006a86  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006a8b  mov     rcx, [rsp+22B0h+var_2270]
0x180006a90  jmp     short loc_180006A9C
0x180006a92  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180006a97  mov     [rsp+22B0h+var_2270], rcx
0x180006a9c  xor     edi, edi
0x180006a9e  test    rcx, rcx
0x180006aa1  jnz     short loc_180006AB7
0x180006aa3  lea     rcx, [rsp+22B0h+var_2270]
0x180006aa8  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006aad  mov     eax, 80004005h
0x180006ab2  jmp     loc_180006C3C
0x180006ab7  mov     r8, rbx; Size
0x180006aba  xor     edx, edx; Val
0x180006abc  call    memset_0
0x180006ac1  mov     r10d, edi
0x180006ac4  test    esi, esi
0x180006ac6  jle     loc_180006BA6
0x180006acc  mov     r14d, 30h ; '0'
0x180006ad2  mov     eax, r10d
0x180006ad5  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x180006ade  cmp     r9d, 61h ; 'a'
0x180006ae2  ja      short loc_180006B4E
0x180006ae4  jz      loc_180006B6F
0x180006aea  cmp     r9d, 38h ; '8'
0x180006aee  ja      short loc_180006B22
0x180006af0  jz      short loc_180006B1D
0x180006af2  mov     ecx, r9d
0x180006af5  sub     ecx, r14d
0x180006af8  jz      short loc_180006B1D
0x180006afa  sub     ecx, 1
0x180006afd  jz      short loc_180006B1D
0x180006aff  sub     ecx, 1
0x180006b02  jz      short loc_180006B1D
0x180006b04  sub     ecx, 1
0x180006b07  jz      short loc_180006B1D
0x180006b09  sub     ecx, 1
0x180006b0c  jz      short loc_180006B1D
0x180006b0e  sub     ecx, 1
0x180006b11  jz      short loc_180006B1D
0x180006b13  sub     ecx, 1
0x180006b16  jz      short loc_180006B1D
0x180006b18  cmp     ecx, 1
0x180006b1b  jnz     short loc_180006B6A
0x180006b1d  sub     r9b, r14b
0x180006b20  jmp     short loc_180006B73
0x180006b22  mov     ecx, r9d
0x180006b25  sub     ecx, 39h ; '9'
0x180006b28  jz      short loc_180006B1D
0x180006b2a  sub     ecx, 8
0x180006b2d  jz      short loc_180006B48
0x180006b2f  sub     ecx, 1
0x180006b32  jz      short loc_180006B48
0x180006b34  sub     ecx, 1
0x180006b37  jz      short loc_180006B48
0x180006b39  sub     ecx, 1
0x180006b3c  jz      short loc_180006B48
0x180006b3e  sub     ecx, 1
0x180006b41  jz      short loc_180006B48
0x180006b43  cmp     ecx, 1
0x180006b46  jnz     short loc_180006B6A
0x180006b48  sub     r9b, 37h ; '7'
0x180006b4c  jmp     short loc_180006B73
0x180006b4e  mov     ecx, r9d
0x180006b51  sub     ecx, 62h ; 'b'
0x180006b54  jz      short loc_180006B6F
0x180006b56  sub     ecx, 1
0x180006b59  jz      short loc_180006B6F
0x180006b5b  sub     ecx, 1
0x180006b5e  jz      short loc_180006B6F
0x180006b60  sub     ecx, 1
0x180006b63  jz      short loc_180006B6F
0x180006b65  cmp     ecx, 1
0x180006b68  jz      short loc_180006B6F
0x180006b6a  mov     r9b, dil
0x180006b6d  jmp     short loc_180006B73
0x180006b6f  sub     r9b, 57h ; 'W'
0x180006b73  mov     rdx, [rsp+22B0h+var_2270]
0x180006b78  mov     eax, r10d
0x180006b7b  and     eax, 1
0x180006b7e  mov     r8d, r10d
0x180006b81  shl     eax, 2
0x180006b84  mov     ecx, 4
0x180006b89  shr     r8, 1
0x180006b8c  sub     ecx, eax
0x180006b8e  shl     r9b, cl
0x180006b91  inc     r10d
0x180006b94  or      [r8+rdx], r9b
0x180006b98  cmp     r10d, esi
0x180006b9b  jl      loc_180006AD2
0x180006ba1  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180006ba6  mov     rax, [rsp+22B0h+var_2270]
0x180006bab  mov     r9d, 3; dwType
0x180006bb1  mov     rcx, [r13+0]; hKey
0x180006bb5  xor     r8d, r8d; Reserved
0x180006bb8  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
