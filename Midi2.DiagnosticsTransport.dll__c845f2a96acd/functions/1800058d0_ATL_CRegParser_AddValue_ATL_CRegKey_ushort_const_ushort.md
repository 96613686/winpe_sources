# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800058d0`
- end: `0x180005ea4`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000842c`

## callees

- `0x1800033d0`
- `0x180004170`
- `0x1800058d0`
- `0x180005eac`
- `0x180006000`
- `0x180006018`
- `0x18000680c`
- `0x1800078fc`
- `0x180011f90`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180005bb9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180005bb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005b59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005bf1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005df2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005b59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005bf1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005df2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005ad0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005aec`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005e74`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005ad0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005aec`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005e74`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005961`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005961`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  HKEY *v5; // r12
  LPCWSTR *v6; // r15
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rax
  int v12; // eax
  BYTE *v13; // rdi
  const WCHAR *v14; // r13
  WCHAR *i; // r14
  const WCHAR *v16; // rax
  DWORD v17; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // esi
  const BYTE *v22; // rax
  DWORD v23; // r9d
  __int64 v24; // r14
  DWORD v25; // r12d
  size_t v26; // rdi
  BYTE *v27; // rcx
  HKEY *v28; // rsi
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  __int64 v32; // rsi
  int Token; // eax
  DWORD cbData; // [rsp+28h] [rbp-22D0h]
  ULONG pulOut; // [rsp+30h] [rbp-22C8h] BYREF
  ATL::CRegParser *v36; // [rsp+38h] [rbp-22C0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22B8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22B0h]
  ATL::CRegParser *v39; // [rsp+50h] [rbp-22A8h]
  const WCHAR *v40; // [rsp+60h] [rbp-2298h]
  struct ATL::CRegKey *v41; // [rsp+70h] [rbp-2288h]
  size_t v42; // [rsp+78h] [rbp-2280h]
  struct ATL::CRegKey *v43; // [rsp+80h] [rbp-2278h]
  unsigned __int16 *v44; // [rsp+88h] [rbp-2270h]
  BYTE *v45; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v46[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v48[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v41 = (struct ATL::CRegKey *)a2;
  v6 = this;
  v36 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v39 = (ATL::CRegParser *)this;
  v43 = (struct ATL::CRegKey *)a2;
  v40 = a3;
  v44 = a4;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  v8 = 0;
  if ( result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return -2147352567;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
      *v6 = CharNextW(*v6);
    result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
    if ( result >= 0 )
    {
      if ( v10 == 8 )
      {
        v32 = -1;
        do
          ++v32;
        while ( String1[v32] );
        cbData = 2 * v32 + 2;
        v22 = (const BYTE *)String1;
        v23 = 1;
        goto LABEL_47;
      }
      if ( v10 != 17 )
      {
        if ( v10 != 19 )
        {
          if ( v10 != 16392 )
          {
LABEL_93:
            Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v44);
            if ( Token < 0 )
              return Token;
            return v8;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = v11 + 2;
          lpData = 0;
          try
          {
            if ( !v12 )
              goto LABEL_24;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
              ATL::AtlThrowImpl(-2147024809);
            if ( (unsigned __int64)(2LL * v12) > 0x100 )
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v12);
              v13 = lpData;
            }
            else
            {
LABEL_24:
              v13 = v48;
              lpData = v48;
            }
          }
          catch ( ... )
          {
            v8 = 0;
            v13 = lpData;
            v5 = *(HKEY **)Data;
            v36 = v39;
            v14 = v40;
            goto LABEL_26;
          }
          v14 = lpValueName;
LABEL_26:
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v16 = CharNextW(i);
              if ( *i == 92 && *v16 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v16);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            if ( !lpData )
              ATL::AtlThrowImpl(-2147467259);
            v17 = 0;
            v18 = lpData;
            do
            {
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)&v18[2 * v19] );
              v20 = (unsigned int)(v19 + 1);
              v18 += 2 * v20;
              v17 += 2 * v20;
            }
            while ( (_DWORD)v20 != 1 );
            v21 = RegSetValueExW(*v5, v14, 0, 7u, lpData, v17);
            v13 = lpData;
          }
          else
          {
            v21 = 14;
          }
          if ( v13 != v48 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
          goto LABEL_42;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v22 = Data;
        v23 = 4;
LABEL_47:
        v21 = RegSetValueExW(*v5, a3, 0, v23, v22, cbData);
LABEL_43:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
        goto LABEL_93;
      }
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      *(_DWORD *)Data = v24;
      if ( (v24 & 1) != 0 )
        return -2147467259;
      try
      {
        v25 = (int)v24 / 2;
        v45 = 0;
        v26 = (int)v24 / 2;
        v42 = v26;
        if ( !((int)v24 / 2) )
          goto LABEL_56;
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v26) )
          ATL::AtlThrowImpl(-2147024809);
        if ( v26 > 0x100 )
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v45, v26);
          v27 = v45;
        }
        else
        {
LABEL_56:
          v27 = v46;
          v45 = v46;
        }
        v28 = (HKEY *)v41;
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v24) = *(_DWORD *)Data;
        v27 = v45;
        v26 = v42;
        v36 = v39;
        v28 = (HKEY *)v43;
        lpValueName = v40;
        v25 = v42;
      }
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v45);
        return -2147467259;
      }
      memset_0(v27, 0, v26);
      v29 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_88:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, v45, v25);
        if ( v45 != v46 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v45);
LABEL_42:
        v6 = (LPCWSTR *)v36;
        goto LABEL_43;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_86:
            v31 = v30 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v31 = 0;
          goto LABEL_87;
        }
        if ( v30 == 97 )
          goto LABEL_86;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_73;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_85;
        v31 = v30 - 55;
LABEL_87:
        v45[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v24 )
          goto LABEL_88;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v31 = v30 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800058d0  push    rbx
0x1800058d2  push    rsi
0x1800058d3  push    rdi
0x1800058d4  push    r12
0x1800058d6  push    r13
0x1800058d8  push    r14
0x1800058da  push    r15
0x1800058dc  mov     eax, 22C0h
0x1800058e1  call    _alloca_probe
0x1800058e6  sub     rsp, rax
0x1800058e9  mov     rax, cs:__security_cookie
0x1800058f0  xor     rax, rsp
0x1800058f3  mov     [rsp+22F8h+var_48], rax
0x1800058fb  mov     r14, r8
0x1800058fe  mov     [rsp+22F8h+lpValueName], r8
0x180005903  mov     r12, rdx
0x180005906  mov     [rsp+22F8h+var_2288], rdx
0x18000590b  mov     r15, rcx
0x18000590e  mov     [rsp+22F8h+var_22C0], rcx
0x180005913  mov     qword ptr [rsp+22F8h+Data], rdx
0x180005918  mov     [rsp+22F8h+var_22A8], rcx
0x18000591d  mov     [rsp+22F8h+var_2278], rdx
0x180005925  mov     [rsp+22F8h+var_2298], r8
0x18000592a  mov     [rsp+22F8h+var_2270], r9
0x180005932  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18000593a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000593f  xor     ebx, ebx
0x180005941  test    eax, eax
0x180005943  js      short loc_180005977
0x180005945  mov     edi, ebx
0x180005947  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000594e  movsxd  rsi, edi
0x180005951  add     rsi, rsi
0x180005954  mov     rdx, [r13+rsi*8+0]; lpString2
0x180005959  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180005961  call    cs:__imp_lstrcmpiW
0x180005967  test    eax, eax
0x180005969  jz      short loc_18000599A
0x18000596b  inc     edi
0x18000596d  cmp     edi, 4
0x180005970  jb      short loc_18000594E
0x180005972  mov     eax, 80020009h
0x180005977  mov     rcx, [rsp+22F8h+var_48]
0x18000597f  xor     rcx, rsp; StackCookie
0x180005982  call    __security_check_cookie
0x180005987  add     rsp, 22C0h
0x18000598e  pop     r15
0x180005990  pop     r14
0x180005992  pop     r13
0x180005994  pop     r12
0x180005996  pop     rdi
0x180005997  pop     rsi
0x180005998  pop     rbx
0x180005999  retn
0x18000599a  movzx   edi, word ptr [r13+rsi*8+8]
0x1800059a0  mov     esi, 13h
0x1800059a5  mov     rdx, [r15]
0x1800059a8  movzx   ecx, word ptr [rdx]
0x1800059ab  sub     ecx, 9
0x1800059ae  jz      loc_180005E71
0x1800059b4  sub     ecx, 1
0x1800059b7  jz      loc_180005E71
0x1800059bd  sub     ecx, 3
0x1800059c0  jz      loc_180005E71
0x1800059c6  cmp     ecx, esi
0x1800059c8  jz      loc_180005E71
0x1800059ce  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800059d6  mov     rcx, r15; this
0x1800059d9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800059de  test    eax, eax
0x1800059e0  js      short loc_180005977
0x1800059e2  mov     r13d, 8
0x1800059e8  cmp     di, r13w
0x1800059ec  jz      loc_180005E22
0x1800059f2  cmp     di, 11h
0x1800059f6  jz      loc_180005BFB
0x1800059fc  cmp     di, si
0x1800059ff  jz      loc_180005BA3
0x180005a05  mov     eax, 4008h
0x180005a0a  cmp     di, ax
0x180005a0d  jnz     loc_180005E55
0x180005a13  lea     rcx, [rsp+22F8h+String1]
0x180005a1b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005a1f  mov     rax, rsi
0x180005a22  inc     rax
0x180005a25  cmp     [rcx+rax*2], bx
0x180005a29  jnz     short loc_180005A22
0x180005a2b  add     eax, 2
0x180005a2e  mov     [rsp+22F8h+var_2158], rbx
0x180005a36  test    eax, eax
0x180005a38  jz      short loc_180005A73
0x180005a3a  movsxd  rcx, eax
0x180005a3d  xor     edx, edx
0x180005a3f  mov     rax, rsi
0x180005a42  div     rcx
0x180005a45  cmp     rax, 2
0x180005a49  jb      loc_180005E82
0x180005a4f  lea     rdx, [rcx+rcx]
0x180005a53  cmp     rdx, 100h
0x180005a5a  jbe     short loc_180005A73
0x180005a5c  lea     rcx, [rsp+22F8h+var_2158]
0x180005a64  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005a69  mov     rdi, [rsp+22F8h+var_2158]
0x180005a71  jmp     short loc_180005A83
0x180005a73  lea     rdi, [rsp+22F8h+var_2150]
0x180005a7b  mov     [rsp+22F8h+var_2158], rdi
0x180005a83  mov     r13, [rsp+22F8h+lpValueName]
0x180005a88  jmp     short loc_180005AAC
0x180005a8a  xor     ebx, ebx
0x180005a8c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005a90  mov     rdi, [rsp+22F8h+var_2158]
0x180005a98  mov     r12, qword ptr [rsp+22F8h+Data]
0x180005a9d  mov     rax, [rsp+22F8h+var_22A8]
0x180005aa2  mov     [rsp+22F8h+var_22C0], rax
0x180005aa7  mov     r13, [rsp+22F8h+var_2298]
0x180005aac  test    rdi, rdi
0x180005aaf  jz      loc_180005B6B
0x180005ab5  lea     r14, [rsp+22F8h+String1]
0x180005abd  cmp     [rsp+22F8h+String1], bx
0x180005ac5  jz      short loc_180005B08
0x180005ac7  mov     r15d, 30h ; '0'
0x180005acd  mov     rcx, r14; lpsz
0x180005ad0  call    cs:__imp_CharNextW
0x180005ad6  movzx   ecx, word ptr [r14]
0x180005ada  cmp     cx, 5Ch ; '\'
0x180005ade  jnz     short loc_180005AF7
0x180005ae0  cmp     [rax], r15w
0x180005ae4  jnz     short loc_180005AF7
0x180005ae6  mov     [rdi], bx
0x180005ae9  mov     rcx, rax; lpsz
0x180005aec  call    cs:__imp_CharNextW
0x180005af2  mov     r14, rax
0x180005af5  jmp     short loc_180005AFE
0x180005af7  mov     [rdi], cx
0x180005afa  add     r14, 2
0x180005afe  add     rdi, 2
0x180005b02  cmp     [r14], bx
0x180005b06  jnz     short loc_180005ACD
0x180005b08  mov     dword ptr [rdi], 0
0x180005b0e  mov     r8, [rsp+22F8h+var_2158]
0x180005b16  test    r8, r8
0x180005b19  jz      loc_180005E8D
0x180005b1f  mov     r10d, ebx
0x180005b22  mov     r9, r8
0x180005b25  mov     rcx, rsi
0x180005b28  inc     rcx
0x180005b2b  cmp     [r9+rcx*2], bx
0x180005b30  jnz     short loc_180005B28
0x180005b32  inc     ecx
0x180005b34  lea     r9, [r9+rcx*2]
0x180005b38  lea     r10d, [r10+rcx*2]
0x180005b3c  cmp     ecx, 1
0x180005b3f  jnz     short loc_180005B25
0x180005b41  mov     [rsp+22F8h+cbData], r10d; cbData
0x180005b46  mov     [rsp+22F8h+lpData], r8; lpData
0x180005b4b  lea     r9d, [rcx+6]; dwType
0x180005b4f  xor     r8d, r8d; Reserved
0x180005b52  mov     rdx, r13; lpValueName
0x180005b55  mov     rcx, [r12]; hKey
0x180005b59  call    cs:__imp_RegSetValueExW
0x180005b5f  mov     esi, eax
0x180005b61  mov     rdi, [rsp+22F8h+var_2158]
0x180005b69  jmp     short loc_180005B70
0x180005b6b  mov     esi, 0Eh
0x180005b70  lea     rax, [rsp+22F8h+var_2150]
0x180005b78  cmp     rdi, rax
0x180005b7b  jz      short loc_180005B8A
0x180005b7d  lea     rcx, [rsp+22F8h+var_2158]
0x180005b85  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005b8a  mov     r15, [rsp+22F8h+var_22C0]
0x180005b8f  test    esi, esi
0x180005b91  jz      loc_180005E55
0x180005b97  mov     ecx, esi; unsigned int
0x180005b99  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180005b9e  jmp     loc_180005977
0x180005ba3  mov     [rsp+22F8h+pulOut], ebx
0x180005ba7  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180005bac  xor     r8d, r8d; dwFlags
0x180005baf  xor     edx, edx; lcid
0x180005bb1  lea     rcx, [rsp+22F8h+String1]; strIn
0x180005bb9  call    cs:__imp_VarUI4FromStr
0x180005bbf  test    eax, eax
0x180005bc1  js      loc_180005977
0x180005bc7  mov     eax, [rsp+22F8h+pulOut]
0x180005bcb  mov     dword ptr [rsp+22F8h+Data], eax
0x180005bcf  mov     [rsp+22F8h+cbData], 4; cbData
0x180005bd7  lea     rax, [rsp+22F8h+Data]
0x180005bdc  mov     r9d, 4; dwType
0x180005be2  mov     [rsp+22F8h+lpData], rax; lpData
0x180005be7  xor     r8d, r8d; Reserved
0x180005bea  mov     rdx, r14; lpValueName
0x180005bed  mov     rcx, [r12]; hKey
0x180005bf1  call    cs:__imp_RegSetValueExW
0x180005bf7  mov     esi, eax
0x180005bf9  jmp     short loc_180005B8F
0x180005bfb  lea     rax, [rsp+22F8h+String1]
0x180005c03  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005c07  mov     r14, rsi
0x180005c0a  inc     r14
0x180005c0d  cmp     [rax+r14*2], bx
0x180005c12  jnz     short loc_180005C0A
0x180005c14  mov     dword ptr [rsp+22F8h+Data], r14d
0x180005c19  test    r14b, 1
0x180005c1d  jnz     loc_180005CD7
0x180005c23  mov     eax, r14d
0x180005c26  cdq
0x180005c27  sub     eax, edx
0x180005c29  sar     eax, 1
0x180005c2b  movsxd  r12, eax
0x180005c2e  mov     [rsp+22F8h+var_2268], rbx
0x180005c36  mov     rdi, r12
0x180005c39  mov     [rsp+22F8h+var_2280], r12
0x180005c3e  test    eax, eax
0x180005c40  jz      short loc_180005C77
0x180005c42  xor     edx, edx
0x180005c44  mov     rax, rsi
0x180005c47  div     rdi
0x180005c4a  cmp     rax, 1
0x180005c4e  jb      loc_180005E98
0x180005c54  cmp     rdi, 100h
0x180005c5b  jbe     short loc_180005C77
0x180005c5d  mov     rdx, rdi
0x180005c60  lea     rcx, [rsp+22F8h+var_2268]
0x180005c68  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005c6d  mov     rcx, [rsp+22F8h+var_2268]
0x180005c75  jmp     short loc_180005C87
0x180005c77  lea     rcx, [rsp+22F8h+var_2260]
0x180005c7f  mov     [rsp+22F8h+var_2268], rcx
0x180005c87  mov     rsi, [rsp+22F8h+var_2288]
0x180005c8c  jmp     short loc_180005CC5
0x180005c8e  xor     ebx, ebx
0x180005c90  lea     r13d, [rbx+8]
0x180005c94  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180005c99  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180005ca1  mov     rdi, [rsp+22F8h+var_2280]
0x180005ca6  mov     rax, [rsp+22F8h+var_22A8]
0x180005cab  mov     [rsp+22F8h+var_22C0], rax
0x180005cb0  mov     rsi, [rsp+22F8h+var_2278]
0x180005cb8  mov     rax, [rsp+22F8h+var_2298]
0x180005cbd  mov     [rsp+22F8h+lpValueName], rax
0x180005cc2  mov     r12d, edi
0x180005cc5  test    rcx, rcx
0x180005cc8  jnz     short loc_180005CE1
0x180005cca  lea     rcx, [rsp+22F8h+var_2268]
0x180005cd2  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005cd7  mov     eax, 80004005h
0x180005cdc  jmp     loc_180005977
0x180005ce1  mov     r8, rdi; Size
0x180005ce4  xor     edx, edx; Val
0x180005ce6  call    memset_0
0x180005ceb  mov     r10d, ebx
0x180005cee  test    r14d, r14d
0x180005cf1  jle     loc_180005DCF
0x180005cf7  mov     r15d, 30h ; '0'
0x180005cfd  mov     eax, r10d
0x180005d00  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180005d08  cmp     edx, 61h ; 'a'
0x180005d0b  ja      short loc_180005D7A
0x180005d0d  jz      loc_180005D9A
0x180005d13  cmp     edx, 38h ; '8'
0x180005d16  ja      short loc_180005D4C
0x180005d18  jz      short loc_180005D44
0x180005d1a  mov     ecx, edx
0x180005d1c  sub     ecx, r15d
0x180005d1f  jz      short loc_180005D44
0x180005d21  sub     ecx, 1
0x180005d24  jz      short loc_180005D44
0x180005d26  sub     ecx, 1
0x180005d29  jz      short loc_180005D44
0x180005d2b  sub     ecx, 1
0x180005d2e  jz      short loc_180005D44
0x180005d30  sub     ecx, 1
0x180005d33  jz      short loc_180005D44
0x180005d35  sub     ecx, 1
0x180005d38  jz      short loc_180005D44
0x180005d3a  sub     ecx, 1
0x180005d3d  jz      short loc_180005D44
0x180005d3f  cmp     ecx, 1
0x180005d42  jnz     short loc_180005D95
0x180005d44  mov     r9d, edx
0x180005d47  sub     r9d, r15d
0x180005d4a  jmp     short loc_180005D9E
0x180005d4c  mov     r9d, edx
0x180005d4f  mov     ecx, edx
0x180005d51  sub     ecx, 39h ; '9'
0x180005d54  jz      short loc_180005D44
0x180005d56  sub     ecx, r13d
0x180005d59  jz      short loc_180005D74
0x180005d5b  sub     ecx, 1
0x180005d5e  jz      short loc_180005D74
0x180005d60  sub     ecx, 1
0x180005d63  jz      short loc_180005D74
0x180005d65  sub     ecx, 1
0x180005d68  jz      short loc_180005D74
0x180005d6a  sub     ecx, 1
0x180005d6d  jz      short loc_180005D74
0x180005d6f  cmp     ecx, 1
0x180005d72  jnz     short loc_180005D95
0x180005d74  add     r9d, 0FFFFFFC9h
0x180005d78  jmp     short loc_180005D9E
  ... truncated ...
```
