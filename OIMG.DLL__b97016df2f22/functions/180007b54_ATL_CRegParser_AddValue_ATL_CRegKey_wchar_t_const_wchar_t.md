# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x180007b54`
- end: `0x180008156`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1538`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800087c4`

## callees

- `0x180006d60`
- `0x1800079bc`
- `0x180007b54`
- `0x18000ae7c`
- `0x18000b508`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056d14c`
- `0x18056dbe0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180007bd1`
- `KERNEL32!lstrcmpiW` at `0x180007bef`
- `KERNEL32!lstrcmpiW` at `0x180007c0f`
- `KERNEL32!lstrcmpiW` at `0x180007c2d`
- `KERNEL32!lstrcmpiW` at `0x180007bd1`
- `KERNEL32!lstrcmpiW` at `0x180007bef`
- `KERNEL32!lstrcmpiW` at `0x180007c0f`
- `KERNEL32!lstrcmpiW` at `0x180007c2d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180007e49`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180007e49`
- `USER32!CharNextW` at `0x180007d5f`
- `USER32!CharNextW` at `0x180007d7b`
- `USER32!CharNextW` at `0x180008106`
- `USER32!CharNextW` at `0x180007d5f`
- `USER32!CharNextW` at `0x180007d7b`
- `USER32!CharNextW` at `0x180008106`
- `ADVAPI32!RegSetValueExW` at `0x180007de9`
- `ADVAPI32!RegSetValueExW` at `0x180007e81`
- `ADVAPI32!RegSetValueExW` at `0x18000808a`
- `ADVAPI32!RegSetValueExW` at `0x180007de9`
- `ADVAPI32!RegSetValueExW` at `0x180007e81`
- `ADVAPI32!RegSetValueExW` at `0x18000808a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const wchar_t *a3, wchar_t *a4)
{
  const WCHAR *v4; // r12
  HKEY *v5; // r13
  LPCWSTR *v6; // r15
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  BYTE *v13; // rdi
  WCHAR *i; // r14
  const WCHAR *v15; // rax
  unsigned int v16; // esi
  DWORD v17; // r9d
  BYTE *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rcx
  const BYTE *v21; // rax
  DWORD v22; // r9d
  __int64 v23; // rdi
  size_t v24; // r12
  BYTE *v25; // rcx
  const WCHAR *v26; // rsi
  int v27; // r10d
  __int64 v28; // r11
  unsigned int v29; // edx
  char v30; // r9
  __int64 v31; // rsi
  int Token; // eax
  __int64 v33; // [rsp+0h] [rbp-22E8h] BYREF
  DWORD cbData; // [rsp+28h] [rbp-22C0h]
  ULONG pulOut; // [rsp+30h] [rbp-22B8h] BYREF
  ATL::CRegParser *v36; // [rsp+38h] [rbp-22B0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22A8h] BYREF
  ATL::CRegParser *v38; // [rsp+48h] [rbp-22A0h]
  const wchar_t *v39; // [rsp+50h] [rbp-2298h]
  LPCWSTR lpValueName; // [rsp+60h] [rbp-2288h]
  size_t v41; // [rsp+68h] [rbp-2280h]
  struct ATL::CRegKey *v42; // [rsp+70h] [rbp-2278h]
  wchar_t *v43; // [rsp+78h] [rbp-2270h]
  BYTE *v44; // [rsp+80h] [rbp-2268h] BYREF
  _BYTE v45[264]; // [rsp+88h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+190h] [rbp-2158h] BYREF
  _BYTE v47[264]; // [rsp+198h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2A0h] [rbp-2048h] BYREF

  v4 = a3;
  lpValueName = a3;
  v5 = a2;
  v6 = this;
  v36 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v38 = (ATL::CRegParser *)this;
  v42 = (struct ATL::CRegKey *)a2;
  v39 = a3;
  v43 = a4;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  v8 = 0;
  if ( result >= 0 )
  {
    if ( lstrcmpiW(String1, L"S") )
    {
      if ( lstrcmpiW(String1, L"M") )
      {
        if ( lstrcmpiW(String1, L"D") )
        {
          if ( lstrcmpiW(String1, L"B") )
            return -2147352567;
          v9 = 17;
        }
        else
        {
          v9 = 19;
        }
      }
      else
      {
        v9 = 16392;
      }
    }
    else
    {
      v9 = 8;
    }
    while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
      *v6 = CharNextW(*v6);
    result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
    if ( result >= 0 )
    {
      if ( v9 == 8 )
      {
        v31 = -1;
        do
          ++v31;
        while ( String1[v31] );
        cbData = 2 * v31 + 2;
        v21 = (const BYTE *)String1;
        v22 = 1;
        goto LABEL_48;
      }
      if ( v9 != 17 )
      {
        if ( v9 != 19 )
        {
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          try
          {
            v12 = v11 + 2;
            lpData = 0;
            if ( !v12 )
              goto LABEL_25;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
              ATL::BaseAtlThrow(-2147024362);
            v10 = (__int64 *)(2LL * v12);
            if ( (unsigned __int64)v10 > 0x100 )
            {
              ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v10);
              v13 = lpData;
            }
            else
            {
LABEL_25:
              v13 = v47;
              lpData = v47;
            }
          }
          catch ( ... )
          {
            v10 = &v33;
            v8 = 0;
            v13 = lpData;
            v5 = *(HKEY **)Data;
            v36 = v38;
            v4 = v39;
          }
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v15 = CharNextW(i);
              if ( *i == 92 && *v15 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v15);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            v13 = lpData;
            if ( lpData )
            {
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
              v16 = RegSetValueExW(*v5, v4, 0, 7u, lpData, v17);
              v13 = lpData;
            }
            else
            {
              v16 = 13;
            }
          }
          else
          {
            v16 = 14;
          }
          if ( v13 != v47 )
            ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&lpData);
LABEL_43:
          v6 = (LPCWSTR *)v36;
          goto LABEL_44;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v21 = Data;
        v22 = 4;
LABEL_48:
        v16 = RegSetValueExW(*v5, v4, 0, v22, v21, cbData);
LABEL_44:
        if ( v16 )
          return winrt::impl::hresult_from_win32((winrt::impl *)v16, (unsigned int)v10);
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v43);
        if ( Token < 0 )
          return Token;
        return v8;
      }
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      *(_DWORD *)Data = v23;
      if ( (v23 & 1) != 0 )
        return -2147467259;
      v24 = (int)v23 / 2;
      pulOut = (int)v23 / 2;
      v44 = 0;
      v41 = v24;
      if ( !((int)v23 / 2) )
        goto LABEL_56;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v24) )
        ATL::BaseAtlThrow(-2147024362);
      if ( v24 > 0x100 )
      {
        ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v44, v24);
        v25 = v44;
      }
      else
      {
LABEL_56:
        v25 = v45;
        v44 = v45;
      }
      v26 = lpValueName;
      if ( !v25 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v44);
        return -2147467259;
      }
      memset_0(v25, 0, v24);
      v27 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_88:
        v16 = RegSetValueExW(*v5, v26, 0, 3u, v44, v24);
        if ( v44 != v45 )
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v44);
        goto LABEL_43;
      }
      v28 = 0;
      while ( 1 )
      {
        v29 = String1[v28];
        if ( v29 > 0x61 )
        {
          if ( v29 == 98 || v29 == 99 || v29 == 100 || v29 - 101 < 2 )
          {
LABEL_86:
            v30 = v29 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v30 = 0;
          goto LABEL_87;
        }
        if ( v29 == 97 )
          goto LABEL_86;
        if ( v29 <= 0x38 )
          break;
        if ( v29 == 57 )
          goto LABEL_73;
        if ( v29 != 65 && v29 != 66 && v29 != 67 && v29 != 68 && v29 - 69 > 1 )
          goto LABEL_85;
        v30 = v29 - 55;
LABEL_87:
        v44[v27 / 2] |= v30 << (4 - 4 * (v27 & 1));
        ++v27;
        if ( ++v28 >= (int)v23 )
          goto LABEL_88;
      }
      if ( v29 != 56 && v29 != 48 && v29 != 49 && v29 != 50 && v29 != 51 && v29 != 52 && v29 != 53 && v29 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v30 = v29 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007b54  push    rbx
0x180007b56  push    rsi
0x180007b57  push    rdi
0x180007b58  push    r12
0x180007b5a  push    r13
0x180007b5c  push    r14
0x180007b5e  push    r15
0x180007b60  mov     eax, 22B0h
0x180007b65  call    _alloca_probe
0x180007b6a  sub     rsp, rax
0x180007b6d  mov     rax, cs:__security_cookie
0x180007b74  xor     rax, rsp
0x180007b77  mov     [rsp+22E8h+var_48], rax
0x180007b7f  mov     r12, r8
0x180007b82  mov     [rsp+22E8h+lpValueName], r8
0x180007b87  mov     r13, rdx
0x180007b8a  mov     r15, rcx
0x180007b8d  mov     [rsp+22E8h+var_22B0], rcx
0x180007b92  mov     qword ptr [rsp+22E8h+Data], rdx
0x180007b97  mov     [rsp+22E8h+var_22A0], rcx
0x180007b9c  mov     [rsp+22E8h+var_2278], rdx
0x180007ba1  mov     [rsp+22E8h+var_2298], r8
0x180007ba6  mov     [rsp+22E8h+var_2270], r9
0x180007bab  lea     rdx, [rsp+22E8h+String1]; wchar_t *
0x180007bb3  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180007bb8  xor     ebx, ebx
0x180007bba  test    eax, eax
0x180007bbc  js      loc_180008119
0x180007bc2  lea     rdx, aS; "S"
0x180007bc9  lea     rcx, [rsp+22E8h+String1]; lpString1
0x180007bd1  call    cs:__imp_lstrcmpiW
0x180007bd7  test    eax, eax
0x180007bd9  jnz     short loc_180007BE0
0x180007bdb  lea     edi, [rbx+8]
0x180007bde  jmp     short loc_180007C3E
0x180007be0  lea     rdx, aM; "M"
0x180007be7  lea     rcx, [rsp+22E8h+String1]; lpString1
0x180007bef  call    cs:__imp_lstrcmpiW
0x180007bf5  test    eax, eax
0x180007bf7  jnz     short loc_180007C00
0x180007bf9  mov     edi, 4008h
0x180007bfe  jmp     short loc_180007C3E
0x180007c00  lea     rdx, aD_2; "D"
0x180007c07  lea     rcx, [rsp+22E8h+String1]; lpString1
0x180007c0f  call    cs:__imp_lstrcmpiW
0x180007c15  test    eax, eax
0x180007c17  jnz     short loc_180007C1E
0x180007c19  lea     edi, [rax+13h]
0x180007c1c  jmp     short loc_180007C3E
0x180007c1e  lea     rdx, aB; "B"
0x180007c25  lea     rcx, [rsp+22E8h+String1]; lpString1
0x180007c2d  call    cs:__imp_lstrcmpiW
0x180007c33  test    eax, eax
0x180007c35  jnz     loc_180008114
0x180007c3b  lea     edi, [rax+11h]
0x180007c3e  mov     rdx, [r15]
0x180007c41  movzx   ecx, word ptr [rdx]
0x180007c44  sub     ecx, 9
0x180007c47  jz      loc_180008103
0x180007c4d  sub     ecx, 1
0x180007c50  jz      loc_180008103
0x180007c56  sub     ecx, 3
0x180007c59  jz      loc_180008103
0x180007c5f  cmp     ecx, 13h
0x180007c62  jz      loc_180008103
0x180007c68  lea     rdx, [rsp+22E8h+String1]; wchar_t *
0x180007c70  mov     rcx, r15; this
0x180007c73  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180007c78  test    eax, eax
0x180007c7a  js      loc_180008119
0x180007c80  cmp     edi, 8
0x180007c83  jz      loc_1800080BA
0x180007c89  cmp     edi, 11h
0x180007c8c  jz      loc_180007E8B
0x180007c92  cmp     edi, 13h
0x180007c95  jz      loc_180007E33
0x180007c9b  cmp     edi, 4008h
0x180007ca1  jnz     loc_1800080ED
0x180007ca7  lea     rcx, [rsp+22E8h+String1]
0x180007caf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007cb3  mov     rax, rsi
0x180007cb6  inc     rax
0x180007cb9  cmp     [rcx+rax*2], bx
0x180007cbd  jnz     short loc_180007CB6
0x180007cbf  add     eax, 2
0x180007cc2  mov     [rsp+22E8h+var_2158], rbx
0x180007cca  test    eax, eax
0x180007ccc  jz      short loc_180007D07
0x180007cce  movsxd  rcx, eax
0x180007cd1  xor     edx, edx
0x180007cd3  mov     rax, rsi
0x180007cd6  div     rcx
0x180007cd9  cmp     rax, 2
0x180007cdd  jb      loc_18000813C
0x180007ce3  lea     rdx, [rcx+rcx]
0x180007ce7  cmp     rdx, 100h
0x180007cee  jbe     short loc_180007D07
0x180007cf0  lea     rcx, [rsp+22E8h+var_2158]
0x180007cf8  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007cfd  mov     rdi, [rsp+22E8h+var_2158]
0x180007d05  jmp     short loc_180007D17
0x180007d07  lea     rdi, [rsp+22E8h+var_2150]
0x180007d0f  mov     [rsp+22E8h+var_2158], rdi
0x180007d17  jmp     short loc_180007D3B
0x180007d19  xor     ebx, ebx
0x180007d1b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007d1f  mov     rdi, [rsp+22E8h+var_2158]
0x180007d27  mov     r13, qword ptr [rsp+22E8h+Data]
0x180007d2c  mov     rax, [rsp+22E8h+var_22A0]
0x180007d31  mov     [rsp+22E8h+var_22B0], rax
0x180007d36  mov     r12, [rsp+22E8h+var_2298]
0x180007d3b  test    rdi, rdi
0x180007d3e  jz      loc_180007DFB
0x180007d44  lea     r14, [rsp+22E8h+String1]
0x180007d4c  cmp     [rsp+22E8h+String1], bx
0x180007d54  jz      short loc_180007D97
0x180007d56  mov     r15d, 30h ; '0'
0x180007d5c  mov     rcx, r14; lpsz
0x180007d5f  call    cs:__imp_CharNextW
0x180007d65  movzx   ecx, word ptr [r14]
0x180007d69  cmp     cx, 5Ch ; '\'
0x180007d6d  jnz     short loc_180007D86
0x180007d6f  cmp     [rax], r15w
0x180007d73  jnz     short loc_180007D86
0x180007d75  mov     [rdi], bx
0x180007d78  mov     rcx, rax; lpsz
0x180007d7b  call    cs:__imp_CharNextW
0x180007d81  mov     r14, rax
0x180007d84  jmp     short loc_180007D8D
0x180007d86  mov     [rdi], cx
0x180007d89  add     r14, 2
0x180007d8d  add     rdi, 2
0x180007d91  cmp     [r14], bx
0x180007d95  jnz     short loc_180007D5C
0x180007d97  mov     dword ptr [rdi], 0
0x180007d9d  mov     rdi, [rsp+22E8h+var_2158]
0x180007da5  test    rdi, rdi
0x180007da8  jnz     short loc_180007DAF
0x180007daa  lea     esi, [rdi+0Dh]
0x180007dad  jmp     short loc_180007E00
0x180007daf  mov     r9d, ebx
0x180007db2  mov     r8, rdi
0x180007db5  mov     rcx, rsi
0x180007db8  inc     rcx
0x180007dbb  cmp     [r8+rcx*2], bx
0x180007dc0  jnz     short loc_180007DB8
0x180007dc2  inc     ecx
0x180007dc4  lea     r8, [r8+rcx*2]
0x180007dc8  lea     r9d, [r9+rcx*2]
0x180007dcc  cmp     ecx, 1
0x180007dcf  jnz     short loc_180007DB5
0x180007dd1  mov     [rsp+22E8h+cbData], r9d; cbData
0x180007dd6  mov     [rsp+22E8h+lpData], rdi; lpData
0x180007ddb  lea     r9d, [rcx+6]; dwType
0x180007ddf  xor     r8d, r8d; Reserved
0x180007de2  mov     rdx, r12; lpValueName
0x180007de5  mov     rcx, [r13+0]; hKey
0x180007de9  call    cs:__imp_RegSetValueExW
0x180007def  mov     esi, eax
0x180007df1  mov     rdi, [rsp+22E8h+var_2158]
0x180007df9  jmp     short loc_180007E00
0x180007dfb  mov     esi, 0Eh
0x180007e00  lea     rax, [rsp+22E8h+var_2150]
0x180007e08  cmp     rdi, rax
0x180007e0b  jz      short loc_180007E1A
0x180007e0d  lea     rcx, [rsp+22E8h+var_2158]
0x180007e15  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x180007e1a  mov     r15, [rsp+22E8h+var_22B0]
0x180007e1f  test    esi, esi
0x180007e21  jz      loc_1800080ED
0x180007e27  mov     ecx, esi; this
0x180007e29  call    ?hresult_from_win32@impl@winrt@@YAHI@Z; winrt::impl::hresult_from_win32(uint)
0x180007e2e  jmp     loc_180008119
0x180007e33  mov     [rsp+22E8h+pulOut], ebx
0x180007e37  lea     r9, [rsp+22E8h+pulOut]; pulOut
0x180007e3c  xor     r8d, r8d; dwFlags
0x180007e3f  xor     edx, edx; lcid
0x180007e41  lea     rcx, [rsp+22E8h+String1]; strIn
0x180007e49  call    cs:__imp_VarUI4FromStr
0x180007e4f  test    eax, eax
0x180007e51  js      loc_180008119
0x180007e57  mov     eax, [rsp+22E8h+pulOut]
0x180007e5b  mov     dword ptr [rsp+22E8h+Data], eax
0x180007e5f  mov     [rsp+22E8h+cbData], 4; cbData
0x180007e67  lea     rax, [rsp+22E8h+Data]
0x180007e6c  mov     r9d, 4; dwType
0x180007e72  mov     [rsp+22E8h+lpData], rax; lpData
0x180007e77  xor     r8d, r8d; Reserved
0x180007e7a  mov     rdx, r12; lpValueName
0x180007e7d  mov     rcx, [r13+0]; hKey
0x180007e81  call    cs:__imp_RegSetValueExW
0x180007e87  mov     esi, eax
0x180007e89  jmp     short loc_180007E1F
0x180007e8b  lea     rax, [rsp+22E8h+String1]
0x180007e93  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007e97  mov     rdi, rsi
0x180007e9a  inc     rdi
0x180007e9d  cmp     [rax+rdi*2], bx
0x180007ea1  jnz     short loc_180007E9A
0x180007ea3  mov     dword ptr [rsp+22E8h+Data], edi
0x180007ea7  test    dil, 1
0x180007eab  jnz     loc_180007F5E
0x180007eb1  mov     eax, edi
0x180007eb3  cdq
0x180007eb4  sub     eax, edx
0x180007eb6  sar     eax, 1
0x180007eb8  movsxd  r12, eax
0x180007ebb  mov     [rsp+22E8h+pulOut], r12d
0x180007ec0  mov     [rsp+22E8h+var_2268], rbx
0x180007ec8  mov     r14, r12
0x180007ecb  mov     [rsp+22E8h+var_2280], r12
0x180007ed0  test    eax, eax
0x180007ed2  jz      short loc_180007F09
0x180007ed4  xor     edx, edx
0x180007ed6  mov     rax, rsi
0x180007ed9  div     r14
0x180007edc  cmp     rax, 1
0x180007ee0  jb      loc_18000814B
0x180007ee6  cmp     r12, 100h
0x180007eed  jbe     short loc_180007F09
0x180007eef  mov     rdx, r12
0x180007ef2  lea     rcx, [rsp+22E8h+var_2268]
0x180007efa  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007eff  mov     rcx, [rsp+22E8h+var_2268]
0x180007f07  jmp     short loc_180007F19
0x180007f09  lea     rcx, [rsp+22E8h+var_2260]
0x180007f11  mov     [rsp+22E8h+var_2268], rcx
0x180007f19  mov     rsi, [rsp+22E8h+lpValueName]
0x180007f1e  jmp     short loc_180007F4C
0x180007f20  xor     ebx, ebx
0x180007f22  mov     edi, dword ptr [rsp+22E8h+Data]
0x180007f26  mov     r12d, [rsp+22E8h+pulOut]
0x180007f2b  mov     rcx, [rsp+22E8h+var_2268]; void *
0x180007f33  mov     r14, [rsp+22E8h+var_2280]
0x180007f38  mov     rax, [rsp+22E8h+var_22A0]
0x180007f3d  mov     [rsp+22E8h+var_22B0], rax
0x180007f42  mov     r13, [rsp+22E8h+var_2278]
0x180007f47  mov     rsi, [rsp+22E8h+var_2298]
0x180007f4c  test    rcx, rcx
0x180007f4f  jnz     short loc_180007F68
0x180007f51  lea     rcx, [rsp+22E8h+var_2268]
0x180007f59  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x180007f5e  mov     eax, 80004005h
0x180007f63  jmp     loc_180008119
0x180007f68  mov     r8, r14; Size
0x180007f6b  xor     edx, edx; Val
0x180007f6d  call    memset_0
0x180007f72  mov     r10d, ebx
0x180007f75  movsxd  rdi, edi
0x180007f78  test    rdi, rdi
0x180007f7b  jle     loc_180008068
0x180007f81  mov     r11, rbx
0x180007f84  mov     r15d, 30h ; '0'
0x180007f8a  movzx   edx, [rsp+r11*2+22E8h+String1]
0x180007f93  cmp     edx, 61h ; 'a'
0x180007f96  ja      short loc_180008005
0x180007f98  jz      loc_180008025
0x180007f9e  cmp     edx, 38h ; '8'
0x180007fa1  ja      short loc_180007FD7
0x180007fa3  jz      short loc_180007FCF
0x180007fa5  mov     ecx, edx
0x180007fa7  sub     ecx, r15d
0x180007faa  jz      short loc_180007FCF
0x180007fac  sub     ecx, 1
0x180007faf  jz      short loc_180007FCF
0x180007fb1  sub     ecx, 1
0x180007fb4  jz      short loc_180007FCF
0x180007fb6  sub     ecx, 1
0x180007fb9  jz      short loc_180007FCF
0x180007fbb  sub     ecx, 1
0x180007fbe  jz      short loc_180007FCF
0x180007fc0  sub     ecx, 1
0x180007fc3  jz      short loc_180007FCF
0x180007fc5  sub     ecx, 1
0x180007fc8  jz      short loc_180007FCF
0x180007fca  cmp     ecx, 1
0x180007fcd  jnz     short loc_180008020
0x180007fcf  mov     r9d, edx
0x180007fd2  sub     r9d, r15d
0x180007fd5  jmp     short loc_180008029
0x180007fd7  mov     r9d, edx
0x180007fda  mov     ecx, edx
0x180007fdc  sub     ecx, 39h ; '9'
0x180007fdf  jz      short loc_180007FCF
0x180007fe1  sub     ecx, 8
0x180007fe4  jz      short loc_180007FFF
0x180007fe6  sub     ecx, 1
0x180007fe9  jz      short loc_180007FFF
0x180007feb  sub     ecx, 1
0x180007fee  jz      short loc_180007FFF
0x180007ff0  sub     ecx, 1
0x180007ff3  jz      short loc_180007FFF
0x180007ff5  sub     ecx, 1
0x180007ff8  jz      short loc_180007FFF
0x180007ffa  cmp     ecx, 1
0x180007ffd  jnz     short loc_180008020
0x180007fff  add     r9d, 0FFFFFFC9h
0x180008003  jmp     short loc_180008029
0x180008005  mov     ecx, edx
0x180008007  sub     ecx, 62h ; 'b'
  ... truncated ...
```
