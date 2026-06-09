# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180005b14`
- end: `0x180006010`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007c4c`

## callees

- `0x180005b14`
- `0x180006018`
- `0x180006290`
- `0x180006764`
- `0x180006ebc`
- `0x1800070f0`
- `0x180012dce`
- `0x180012e00`
- `0x180012e90`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180005b8d`
- `KERNEL32!lstrcmpiW` at `0x180005b8d`
- `ADVAPI32!RegSetValueExW` at `0x180005d3a`
- `ADVAPI32!RegSetValueExW` at `0x180005db3`
- `ADVAPI32!RegSetValueExW` at `0x180005f55`
- `ADVAPI32!RegSetValueExW` at `0x180005d3a`
- `ADVAPI32!RegSetValueExW` at `0x180005db3`
- `ADVAPI32!RegSetValueExW` at `0x180005f55`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180005d7d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180005d7d`
- `USER32!CharNextW` at `0x180005bdd`
- `USER32!CharNextW` at `0x180005cad`
- `USER32!CharNextW` at `0x180005cc9`
- `USER32!CharNextW` at `0x180005bdd`
- `USER32!CharNextW` at `0x180005cad`
- `USER32!CharNextW` at `0x180005cc9`

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
0x180005b14  push    rbp
0x180005b16  push    rbx
0x180005b17  push    rsi
0x180005b18  push    rdi
0x180005b19  push    r12
0x180005b1b  push    r13
0x180005b1d  push    r14
0x180005b1f  push    r15
0x180005b21  lea     rbp, [rsp-2178h]
0x180005b29  mov     eax, 2278h
0x180005b2e  call    _alloca_probe
0x180005b33  sub     rsp, rax
0x180005b36  mov     rax, cs:__security_cookie
0x180005b3d  xor     rax, rsp
0x180005b40  mov     [rbp+21B0h+var_50], rax
0x180005b47  mov     r13, rdx
0x180005b4a  mov     qword ptr [rsp+22B0h+Data], r9
0x180005b4f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180005b56  mov     qword ptr [rsp+22B0h+pulOut], r8
0x180005b5b  mov     r15, r9
0x180005b5e  mov     r14, r8
0x180005b61  mov     r12, rcx
0x180005b64  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005b69  xor     esi, esi
0x180005b6b  test    eax, eax
0x180005b6d  js      loc_180005FCC
0x180005b73  mov     ebx, esi
0x180005b75  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180005b7c  movsxd  rdi, ebx
0x180005b7f  lea     rcx, [rbp+21B0h+String1]; lpString1
0x180005b86  add     rdi, rdi
0x180005b89  mov     rdx, [rax+rdi*8]; lpString2
0x180005b8d  call    cs:__imp_lstrcmpiW
0x180005b93  test    eax, eax
0x180005b95  jz      short loc_180005BAF
0x180005b97  inc     ebx
0x180005b99  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180005ba0  cmp     ebx, 4
0x180005ba3  jb      short loc_180005B7C
0x180005ba5  mov     eax, 80020009h
0x180005baa  jmp     loc_180005FCC
0x180005baf  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180005bb6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x180005bbb  mov     edi, 13h
0x180005bc0  mov     rdx, [r12]
0x180005bc4  movzx   ecx, word ptr [rdx]
0x180005bc7  sub     ecx, 9
0x180005bca  jz      short loc_180005BDA
0x180005bcc  sub     ecx, 1
0x180005bcf  jz      short loc_180005BDA
0x180005bd1  sub     ecx, 3
0x180005bd4  jz      short loc_180005BDA
0x180005bd6  cmp     ecx, edi
0x180005bd8  jnz     short loc_180005BE9
0x180005bda  mov     rcx, rdx; lpsz
0x180005bdd  call    cs:__imp_CharNextW
0x180005be3  mov     [r12], rax
0x180005be7  jmp     short loc_180005BC0
0x180005be9  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180005bf0  mov     rcx, r12; this
0x180005bf3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005bf8  test    eax, eax
0x180005bfa  js      loc_180005FCC
0x180005c00  mov     eax, 8
0x180005c05  cmp     bx, ax
0x180005c08  jz      loc_180005F87
0x180005c0e  cmp     bx, 11h
0x180005c12  jz      loc_180005DC0
0x180005c18  cmp     bx, di
0x180005c1b  jz      loc_180005D68
0x180005c21  mov     eax, 4008h
0x180005c26  cmp     bx, ax
0x180005c29  jnz     loc_180005FB8
0x180005c2f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180005c33  mov     [rbp+21B0h+var_2160], rsi
0x180005c37  mov     rax, rdi
0x180005c3a  lea     rcx, [rbp+21B0h+String1]
0x180005c41  inc     rax
0x180005c44  cmp     [rcx+rax*2], si
0x180005c48  jnz     short loc_180005C41
0x180005c4a  add     eax, 2
0x180005c4d  movsxd  rcx, eax
0x180005c50  jz      short loc_180005C80
0x180005c52  xor     edx, edx
0x180005c54  mov     rax, rdi
0x180005c57  div     rcx
0x180005c5a  cmp     rax, 2
0x180005c5e  jb      loc_180005FFA
0x180005c64  lea     rdx, [rcx+rcx]
0x180005c68  cmp     rdx, 100h
0x180005c6f  jbe     short loc_180005C80
0x180005c71  lea     rcx, [rbp+21B0h+var_2160]
0x180005c75  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005c7a  mov     rbx, [rbp+21B0h+var_2160]
0x180005c7e  jmp     short loc_180005C88
0x180005c80  lea     rbx, [rbp+21B0h+var_2158]
0x180005c84  mov     [rbp+21B0h+var_2160], rbx
0x180005c88  test    rbx, rbx
0x180005c8b  jz      loc_180005D48
0x180005c91  xor     eax, eax
0x180005c93  lea     rsi, [rbp+21B0h+String1]
0x180005c9a  cmp     [rbp+21B0h+String1], ax
0x180005ca1  jz      short loc_180005CEF
0x180005ca3  lea     r14d, [rax+30h]
0x180005ca7  xor     r15d, r15d
0x180005caa  mov     rcx, rsi; lpsz
0x180005cad  call    cs:__imp_CharNextW
0x180005cb3  movzx   ecx, word ptr [rsi]
0x180005cb6  cmp     cx, 5Ch ; '\'
0x180005cba  jnz     short loc_180005CD4
0x180005cbc  cmp     [rax], r14w
0x180005cc0  jnz     short loc_180005CD4
0x180005cc2  mov     rcx, rax; lpsz
0x180005cc5  mov     [rbx], r15w
0x180005cc9  call    cs:__imp_CharNextW
0x180005ccf  mov     rsi, rax
0x180005cd2  jmp     short loc_180005CDB
0x180005cd4  mov     [rbx], cx
0x180005cd7  add     rsi, 2
0x180005cdb  add     rbx, 2
0x180005cdf  cmp     [rsi], r15w
0x180005ce3  jnz     short loc_180005CAA
0x180005ce5  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180005cea  mov     r15, qword ptr [rsp+22B0h+Data]
0x180005cef  xor     esi, esi
0x180005cf1  mov     [rbx], esi
0x180005cf3  mov     r8, [rbp+21B0h+var_2160]
0x180005cf7  test    r8, r8
0x180005cfa  jz      loc_180006005
0x180005d00  mov     r10d, esi
0x180005d03  mov     r9, r8
0x180005d06  mov     rcx, rdi
0x180005d09  inc     rcx
0x180005d0c  cmp     [r9+rcx*2], si
0x180005d11  jnz     short loc_180005D09
0x180005d13  inc     ecx
0x180005d15  lea     r9, [r9+rcx*2]
0x180005d19  lea     r10d, [r10+rcx*2]
0x180005d1d  cmp     ecx, 1
0x180005d20  jnz     short loc_180005D06
0x180005d22  mov     [rsp+22B0h+cbData], r10d; cbData
0x180005d27  lea     r9d, [rcx+6]; dwType
0x180005d2b  mov     rcx, [r13+0]; hKey
0x180005d2f  mov     rdx, r14; lpValueName
0x180005d32  mov     [rsp+22B0h+lpData], r8; lpData
0x180005d37  xor     r8d, r8d; Reserved
0x180005d3a  call    cs:__imp_RegSetValueExW
0x180005d40  mov     rbx, [rbp+21B0h+var_2160]
0x180005d44  mov     edi, eax
0x180005d46  jmp     short loc_180005D4D
0x180005d48  mov     edi, 0Eh
0x180005d4d  lea     rax, [rbp+21B0h+var_2158]
0x180005d51  cmp     rbx, rax
0x180005d54  jz      loc_180005F7A
0x180005d5a  lea     rcx, [rbp+21B0h+var_2160]
0x180005d5e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005d63  jmp     loc_180005F7A
0x180005d68  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x180005d6d  mov     [rsp+22B0h+pulOut], esi
0x180005d71  xor     r8d, r8d; dwFlags
0x180005d74  lea     rcx, [rbp+21B0h+String1]; strIn
0x180005d7b  xor     edx, edx; lcid
0x180005d7d  call    cs:__imp_VarUI4FromStr
0x180005d83  test    eax, eax
0x180005d85  js      loc_180005FCC
0x180005d8b  mov     eax, [rsp+22B0h+pulOut]
0x180005d8f  mov     ecx, 4
0x180005d94  mov     dword ptr [rsp+22B0h+Data], eax
0x180005d98  mov     r9d, ecx; dwType
0x180005d9b  mov     [rsp+22B0h+cbData], ecx; cbData
0x180005d9f  lea     rax, [rsp+22B0h+Data]
0x180005da4  mov     rcx, [r13+0]; hKey
0x180005da8  xor     r8d, r8d; Reserved
0x180005dab  mov     rdx, r14; lpValueName
0x180005dae  mov     [rsp+22B0h+lpData], rax; lpData
0x180005db3  call    cs:__imp_RegSetValueExW
0x180005db9  mov     edi, eax
0x180005dbb  jmp     loc_180005F7A
0x180005dc0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180005dc4  lea     rax, [rbp+21B0h+String1]
0x180005dcb  mov     rsi, rdi
0x180005dce  xor     ecx, ecx
0x180005dd0  inc     rsi
0x180005dd3  cmp     [rax+rsi*2], cx
0x180005dd7  jnz     short loc_180005DD0
0x180005dd9  test    sil, 1
0x180005ddd  jnz     short loc_180005E3D
0x180005ddf  mov     eax, esi
0x180005de1  mov     [rsp+22B0h+var_2270], rcx
0x180005de6  cdq
0x180005de7  sub     eax, edx
0x180005de9  sar     eax, 1
0x180005deb  movsxd  r15, eax
0x180005dee  mov     rbx, r15
0x180005df1  jz      short loc_180005E22
0x180005df3  xor     edx, edx
0x180005df5  mov     rax, rdi
0x180005df8  div     rbx
0x180005dfb  cmp     rax, 1
0x180005dff  jb      loc_180005FEF
0x180005e05  cmp     rbx, 100h
0x180005e0c  jbe     short loc_180005E22
0x180005e0e  mov     rdx, rbx
0x180005e11  lea     rcx, [rsp+22B0h+var_2270]
0x180005e16  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005e1b  mov     rcx, [rsp+22B0h+var_2270]
0x180005e20  jmp     short loc_180005E2C
0x180005e22  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180005e27  mov     [rsp+22B0h+var_2270], rcx
0x180005e2c  xor     edi, edi
0x180005e2e  test    rcx, rcx
0x180005e31  jnz     short loc_180005E47
0x180005e33  lea     rcx, [rsp+22B0h+var_2270]
0x180005e38  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005e3d  mov     eax, 80004005h
0x180005e42  jmp     loc_180005FCC
0x180005e47  mov     r8, rbx; Size
0x180005e4a  xor     edx, edx; Val
0x180005e4c  call    memset_0
0x180005e51  mov     r10d, edi
0x180005e54  test    esi, esi
0x180005e56  jle     loc_180005F36
0x180005e5c  mov     r14d, 30h ; '0'
0x180005e62  mov     eax, r10d
0x180005e65  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x180005e6e  cmp     r9d, 61h ; 'a'
0x180005e72  ja      short loc_180005EDE
0x180005e74  jz      loc_180005EFF
0x180005e7a  cmp     r9d, 38h ; '8'
0x180005e7e  ja      short loc_180005EB2
0x180005e80  jz      short loc_180005EAD
0x180005e82  mov     ecx, r9d
0x180005e85  sub     ecx, r14d
0x180005e88  jz      short loc_180005EAD
0x180005e8a  sub     ecx, 1
0x180005e8d  jz      short loc_180005EAD
0x180005e8f  sub     ecx, 1
0x180005e92  jz      short loc_180005EAD
0x180005e94  sub     ecx, 1
0x180005e97  jz      short loc_180005EAD
0x180005e99  sub     ecx, 1
0x180005e9c  jz      short loc_180005EAD
0x180005e9e  sub     ecx, 1
0x180005ea1  jz      short loc_180005EAD
0x180005ea3  sub     ecx, 1
0x180005ea6  jz      short loc_180005EAD
0x180005ea8  cmp     ecx, 1
0x180005eab  jnz     short loc_180005EFA
0x180005ead  sub     r9b, r14b
0x180005eb0  jmp     short loc_180005F03
0x180005eb2  mov     ecx, r9d
0x180005eb5  sub     ecx, 39h ; '9'
0x180005eb8  jz      short loc_180005EAD
0x180005eba  sub     ecx, 8
0x180005ebd  jz      short loc_180005ED8
0x180005ebf  sub     ecx, 1
0x180005ec2  jz      short loc_180005ED8
0x180005ec4  sub     ecx, 1
0x180005ec7  jz      short loc_180005ED8
0x180005ec9  sub     ecx, 1
0x180005ecc  jz      short loc_180005ED8
0x180005ece  sub     ecx, 1
0x180005ed1  jz      short loc_180005ED8
0x180005ed3  cmp     ecx, 1
0x180005ed6  jnz     short loc_180005EFA
0x180005ed8  sub     r9b, 37h ; '7'
0x180005edc  jmp     short loc_180005F03
0x180005ede  mov     ecx, r9d
0x180005ee1  sub     ecx, 62h ; 'b'
0x180005ee4  jz      short loc_180005EFF
0x180005ee6  sub     ecx, 1
0x180005ee9  jz      short loc_180005EFF
0x180005eeb  sub     ecx, 1
0x180005eee  jz      short loc_180005EFF
0x180005ef0  sub     ecx, 1
0x180005ef3  jz      short loc_180005EFF
0x180005ef5  cmp     ecx, 1
0x180005ef8  jz      short loc_180005EFF
0x180005efa  mov     r9b, dil
0x180005efd  jmp     short loc_180005F03
0x180005eff  sub     r9b, 57h ; 'W'
0x180005f03  mov     rdx, [rsp+22B0h+var_2270]
0x180005f08  mov     eax, r10d
0x180005f0b  and     eax, 1
0x180005f0e  mov     r8d, r10d
0x180005f11  shl     eax, 2
0x180005f14  mov     ecx, 4
0x180005f19  shr     r8, 1
0x180005f1c  sub     ecx, eax
0x180005f1e  shl     r9b, cl
0x180005f21  inc     r10d
0x180005f24  or      [r8+rdx], r9b
0x180005f28  cmp     r10d, esi
0x180005f2b  jl      loc_180005E62
0x180005f31  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180005f36  mov     rax, [rsp+22B0h+var_2270]
0x180005f3b  mov     r9d, 3; dwType
0x180005f41  mov     rcx, [r13+0]; hKey
0x180005f45  xor     r8d, r8d; Reserved
0x180005f48  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
