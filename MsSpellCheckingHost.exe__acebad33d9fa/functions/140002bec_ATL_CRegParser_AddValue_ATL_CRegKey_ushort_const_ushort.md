# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x140002bec`
- end: `0x1400031c0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140005098`

## callees

- `0x1400023f3`
- `0x140002bec`
- `0x1400031c8`
- `0x14000331c`
- `0x140003b88`
- `0x140003d60`
- `0x140004070`
- `0x140011e10`
- `0x140011ed0`

## import_xrefs

- `USER32!CharNextW` at `0x140002dec`
- `USER32!CharNextW` at `0x140002e08`
- `USER32!CharNextW` at `0x140003190`
- `USER32!CharNextW` at `0x140002dec`
- `USER32!CharNextW` at `0x140002e08`
- `USER32!CharNextW` at `0x140003190`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140002ed5`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140002ed5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140002e75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140002f0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000310e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140002e75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140002f0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000310e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140002c7d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140002c7d`

## pseudocode

```c
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
0x140002bec  push    rbx
0x140002bee  push    rsi
0x140002bef  push    rdi
0x140002bf0  push    r12
0x140002bf2  push    r13
0x140002bf4  push    r14
0x140002bf6  push    r15
0x140002bf8  mov     eax, 22C0h
0x140002bfd  call    _alloca_probe
0x140002c02  sub     rsp, rax
0x140002c05  mov     rax, cs:__security_cookie
0x140002c0c  xor     rax, rsp
0x140002c0f  mov     [rsp+22F8h+var_48], rax
0x140002c17  mov     r14, r8
0x140002c1a  mov     [rsp+22F8h+lpValueName], r8
0x140002c1f  mov     r12, rdx
0x140002c22  mov     [rsp+22F8h+var_2288], rdx
0x140002c27  mov     r15, rcx
0x140002c2a  mov     [rsp+22F8h+var_22C0], rcx
0x140002c2f  mov     qword ptr [rsp+22F8h+Data], rdx
0x140002c34  mov     [rsp+22F8h+var_22A8], rcx
0x140002c39  mov     [rsp+22F8h+var_2278], rdx
0x140002c41  mov     [rsp+22F8h+var_2298], r8
0x140002c46  mov     [rsp+22F8h+var_2270], r9
0x140002c4e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x140002c56  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140002c5b  xor     ebx, ebx
0x140002c5d  test    eax, eax
0x140002c5f  js      short loc_140002C93
0x140002c61  mov     edi, ebx
0x140002c63  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140002c6a  movsxd  rsi, edi
0x140002c6d  add     rsi, rsi
0x140002c70  mov     rdx, [r13+rsi*8+0]; lpString2
0x140002c75  lea     rcx, [rsp+22F8h+String1]; lpString1
0x140002c7d  call    cs:__imp_lstrcmpiW
0x140002c83  test    eax, eax
0x140002c85  jz      short loc_140002CB6
0x140002c87  inc     edi
0x140002c89  cmp     edi, 4
0x140002c8c  jb      short loc_140002C6A
0x140002c8e  mov     eax, 80020009h
0x140002c93  mov     rcx, [rsp+22F8h+var_48]
0x140002c9b  xor     rcx, rsp; StackCookie
0x140002c9e  call    __security_check_cookie
0x140002ca3  add     rsp, 22C0h
0x140002caa  pop     r15
0x140002cac  pop     r14
0x140002cae  pop     r13
0x140002cb0  pop     r12
0x140002cb2  pop     rdi
0x140002cb3  pop     rsi
0x140002cb4  pop     rbx
0x140002cb5  retn
0x140002cb6  movzx   edi, word ptr [r13+rsi*8+8]
0x140002cbc  mov     esi, 13h
0x140002cc1  mov     rdx, [r15]
0x140002cc4  movzx   ecx, word ptr [rdx]
0x140002cc7  sub     ecx, 9
0x140002cca  jz      loc_14000318D
0x140002cd0  sub     ecx, 1
0x140002cd3  jz      loc_14000318D
0x140002cd9  sub     ecx, 3
0x140002cdc  jz      loc_14000318D
0x140002ce2  cmp     ecx, esi
0x140002ce4  jz      loc_14000318D
0x140002cea  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x140002cf2  mov     rcx, r15; this
0x140002cf5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140002cfa  test    eax, eax
0x140002cfc  js      short loc_140002C93
0x140002cfe  mov     r13d, 8
0x140002d04  cmp     di, r13w
0x140002d08  jz      loc_14000313E
0x140002d0e  cmp     di, 11h
0x140002d12  jz      loc_140002F17
0x140002d18  cmp     di, si
0x140002d1b  jz      loc_140002EBF
0x140002d21  mov     eax, 4008h
0x140002d26  cmp     di, ax
0x140002d29  jnz     loc_140003171
0x140002d2f  lea     rcx, [rsp+22F8h+String1]
0x140002d37  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140002d3b  mov     rax, rsi
0x140002d3e  inc     rax
0x140002d41  cmp     [rcx+rax*2], bx
0x140002d45  jnz     short loc_140002D3E
0x140002d47  add     eax, 2
0x140002d4a  mov     [rsp+22F8h+var_2158], rbx
0x140002d52  test    eax, eax
0x140002d54  jz      short loc_140002D8F
0x140002d56  movsxd  rcx, eax
0x140002d59  xor     edx, edx
0x140002d5b  mov     rax, rsi
0x140002d5e  div     rcx
0x140002d61  cmp     rax, 2
0x140002d65  jb      loc_14000319E
0x140002d6b  lea     rdx, [rcx+rcx]
0x140002d6f  cmp     rdx, 100h
0x140002d76  jbe     short loc_140002D8F
0x140002d78  lea     rcx, [rsp+22F8h+var_2158]
0x140002d80  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140002d85  mov     rdi, [rsp+22F8h+var_2158]
0x140002d8d  jmp     short loc_140002D9F
0x140002d8f  lea     rdi, [rsp+22F8h+var_2150]
0x140002d97  mov     [rsp+22F8h+var_2158], rdi
0x140002d9f  mov     r13, [rsp+22F8h+lpValueName]
0x140002da4  jmp     short loc_140002DC8
0x140002da6  xor     ebx, ebx
0x140002da8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140002dac  mov     rdi, [rsp+22F8h+var_2158]
0x140002db4  mov     r12, qword ptr [rsp+22F8h+Data]
0x140002db9  mov     rax, [rsp+22F8h+var_22A8]
0x140002dbe  mov     [rsp+22F8h+var_22C0], rax
0x140002dc3  mov     r13, [rsp+22F8h+var_2298]
0x140002dc8  test    rdi, rdi
0x140002dcb  jz      loc_140002E87
0x140002dd1  lea     r14, [rsp+22F8h+String1]
0x140002dd9  cmp     [rsp+22F8h+String1], bx
0x140002de1  jz      short loc_140002E24
0x140002de3  mov     r15d, 30h ; '0'
0x140002de9  mov     rcx, r14; lpsz
0x140002dec  call    cs:__imp_CharNextW
0x140002df2  movzx   ecx, word ptr [r14]
0x140002df6  cmp     cx, 5Ch ; '\'
0x140002dfa  jnz     short loc_140002E13
0x140002dfc  cmp     [rax], r15w
0x140002e00  jnz     short loc_140002E13
0x140002e02  mov     [rdi], bx
0x140002e05  mov     rcx, rax; lpsz
0x140002e08  call    cs:__imp_CharNextW
0x140002e0e  mov     r14, rax
0x140002e11  jmp     short loc_140002E1A
0x140002e13  mov     [rdi], cx
0x140002e16  add     r14, 2
0x140002e1a  add     rdi, 2
0x140002e1e  cmp     [r14], bx
0x140002e22  jnz     short loc_140002DE9
0x140002e24  mov     dword ptr [rdi], 0
0x140002e2a  mov     r8, [rsp+22F8h+var_2158]
0x140002e32  test    r8, r8
0x140002e35  jz      loc_1400031A9
0x140002e3b  mov     r10d, ebx
0x140002e3e  mov     r9, r8
0x140002e41  mov     rcx, rsi
0x140002e44  inc     rcx
0x140002e47  cmp     [r9+rcx*2], bx
0x140002e4c  jnz     short loc_140002E44
0x140002e4e  inc     ecx
0x140002e50  lea     r9, [r9+rcx*2]
0x140002e54  lea     r10d, [r10+rcx*2]
0x140002e58  cmp     ecx, 1
0x140002e5b  jnz     short loc_140002E41
0x140002e5d  mov     [rsp+22F8h+cbData], r10d; cbData
0x140002e62  mov     [rsp+22F8h+lpData], r8; lpData
0x140002e67  lea     r9d, [rcx+6]; dwType
0x140002e6b  xor     r8d, r8d; Reserved
0x140002e6e  mov     rdx, r13; lpValueName
0x140002e71  mov     rcx, [r12]; hKey
0x140002e75  call    cs:__imp_RegSetValueExW
0x140002e7b  mov     esi, eax
0x140002e7d  mov     rdi, [rsp+22F8h+var_2158]
0x140002e85  jmp     short loc_140002E8C
0x140002e87  mov     esi, 0Eh
0x140002e8c  lea     rax, [rsp+22F8h+var_2150]
0x140002e94  cmp     rdi, rax
0x140002e97  jz      short loc_140002EA6
0x140002e99  lea     rcx, [rsp+22F8h+var_2158]
0x140002ea1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140002ea6  mov     r15, [rsp+22F8h+var_22C0]
0x140002eab  test    esi, esi
0x140002ead  jz      loc_140003171
0x140002eb3  mov     ecx, esi; unsigned int
0x140002eb5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140002eba  jmp     loc_140002C93
0x140002ebf  mov     [rsp+22F8h+pulOut], ebx
0x140002ec3  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x140002ec8  xor     r8d, r8d; dwFlags
0x140002ecb  xor     edx, edx; lcid
0x140002ecd  lea     rcx, [rsp+22F8h+String1]; strIn
0x140002ed5  call    cs:__imp_VarUI4FromStr
0x140002edb  test    eax, eax
0x140002edd  js      loc_140002C93
0x140002ee3  mov     eax, [rsp+22F8h+pulOut]
0x140002ee7  mov     dword ptr [rsp+22F8h+Data], eax
0x140002eeb  mov     [rsp+22F8h+cbData], 4; cbData
0x140002ef3  lea     rax, [rsp+22F8h+Data]
0x140002ef8  mov     r9d, 4; dwType
0x140002efe  mov     [rsp+22F8h+lpData], rax; lpData
0x140002f03  xor     r8d, r8d; Reserved
0x140002f06  mov     rdx, r14; lpValueName
0x140002f09  mov     rcx, [r12]; hKey
0x140002f0d  call    cs:__imp_RegSetValueExW
0x140002f13  mov     esi, eax
0x140002f15  jmp     short loc_140002EAB
0x140002f17  lea     rax, [rsp+22F8h+String1]
0x140002f1f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140002f23  mov     r14, rsi
0x140002f26  inc     r14
0x140002f29  cmp     [rax+r14*2], bx
0x140002f2e  jnz     short loc_140002F26
0x140002f30  mov     dword ptr [rsp+22F8h+Data], r14d
0x140002f35  test    r14b, 1
0x140002f39  jnz     loc_140002FF3
0x140002f3f  mov     eax, r14d
0x140002f42  cdq
0x140002f43  sub     eax, edx
0x140002f45  sar     eax, 1
0x140002f47  movsxd  r12, eax
0x140002f4a  mov     [rsp+22F8h+var_2268], rbx
0x140002f52  mov     rdi, r12
0x140002f55  mov     [rsp+22F8h+var_2280], r12
0x140002f5a  test    eax, eax
0x140002f5c  jz      short loc_140002F93
0x140002f5e  xor     edx, edx
0x140002f60  mov     rax, rsi
0x140002f63  div     rdi
0x140002f66  cmp     rax, 1
0x140002f6a  jb      loc_1400031B4
0x140002f70  cmp     rdi, 100h
0x140002f77  jbe     short loc_140002F93
0x140002f79  mov     rdx, rdi
0x140002f7c  lea     rcx, [rsp+22F8h+var_2268]
0x140002f84  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140002f89  mov     rcx, [rsp+22F8h+var_2268]
0x140002f91  jmp     short loc_140002FA3
0x140002f93  lea     rcx, [rsp+22F8h+var_2260]
0x140002f9b  mov     [rsp+22F8h+var_2268], rcx
0x140002fa3  mov     rsi, [rsp+22F8h+var_2288]
0x140002fa8  jmp     short loc_140002FE1
0x140002faa  xor     ebx, ebx
0x140002fac  lea     r13d, [rbx+8]
0x140002fb0  mov     r14d, dword ptr [rsp+22F8h+Data]
0x140002fb5  mov     rcx, [rsp+22F8h+var_2268]; void *
0x140002fbd  mov     rdi, [rsp+22F8h+var_2280]
0x140002fc2  mov     rax, [rsp+22F8h+var_22A8]
0x140002fc7  mov     [rsp+22F8h+var_22C0], rax
0x140002fcc  mov     rsi, [rsp+22F8h+var_2278]
0x140002fd4  mov     rax, [rsp+22F8h+var_2298]
0x140002fd9  mov     [rsp+22F8h+lpValueName], rax
0x140002fde  mov     r12d, edi
0x140002fe1  test    rcx, rcx
0x140002fe4  jnz     short loc_140002FFD
0x140002fe6  lea     rcx, [rsp+22F8h+var_2268]
0x140002fee  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140002ff3  mov     eax, 80004005h
0x140002ff8  jmp     loc_140002C93
0x140002ffd  mov     r8, rdi; Size
0x140003000  xor     edx, edx; Val
0x140003002  call    memset_0
0x140003007  mov     r10d, ebx
0x14000300a  test    r14d, r14d
0x14000300d  jle     loc_1400030EB
0x140003013  mov     r15d, 30h ; '0'
0x140003019  mov     eax, r10d
0x14000301c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x140003024  cmp     edx, 61h ; 'a'
0x140003027  ja      short loc_140003096
0x140003029  jz      loc_1400030B6
0x14000302f  cmp     edx, 38h ; '8'
0x140003032  ja      short loc_140003068
0x140003034  jz      short loc_140003060
0x140003036  mov     ecx, edx
0x140003038  sub     ecx, r15d
0x14000303b  jz      short loc_140003060
0x14000303d  sub     ecx, 1
0x140003040  jz      short loc_140003060
0x140003042  sub     ecx, 1
0x140003045  jz      short loc_140003060
0x140003047  sub     ecx, 1
0x14000304a  jz      short loc_140003060
0x14000304c  sub     ecx, 1
0x14000304f  jz      short loc_140003060
0x140003051  sub     ecx, 1
0x140003054  jz      short loc_140003060
0x140003056  sub     ecx, 1
0x140003059  jz      short loc_140003060
0x14000305b  cmp     ecx, 1
0x14000305e  jnz     short loc_1400030B1
0x140003060  mov     r9d, edx
0x140003063  sub     r9d, r15d
0x140003066  jmp     short loc_1400030BA
0x140003068  mov     r9d, edx
0x14000306b  mov     ecx, edx
0x14000306d  sub     ecx, 39h ; '9'
0x140003070  jz      short loc_140003060
0x140003072  sub     ecx, r13d
0x140003075  jz      short loc_140003090
0x140003077  sub     ecx, 1
0x14000307a  jz      short loc_140003090
0x14000307c  sub     ecx, 1
0x14000307f  jz      short loc_140003090
0x140003081  sub     ecx, 1
0x140003084  jz      short loc_140003090
0x140003086  sub     ecx, 1
0x140003089  jz      short loc_140003090
0x14000308b  cmp     ecx, 1
0x14000308e  jnz     short loc_1400030B1
0x140003090  add     r9d, 0FFFFFFC9h
0x140003094  jmp     short loc_1400030BA
  ... truncated ...
```
