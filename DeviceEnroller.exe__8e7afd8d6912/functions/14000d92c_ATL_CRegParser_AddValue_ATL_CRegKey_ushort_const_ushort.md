# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x14000d92c`
- end: `0x14000df00`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140016794`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x14000d92c`
- `0x14000e3dc`
- `0x14000e530`
- `0x14000e548`
- `0x14000f50c`
- `0x140013988`
- `0x140059180`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000dc15`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000dc15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000dbb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000dc4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000de4e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000dbb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000dc4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000de4e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000db2c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000db48`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000ded0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000db2c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000db48`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000ded0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000d9bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000d9bd`

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
0x14000d92c  push    rbx
0x14000d92e  push    rsi
0x14000d92f  push    rdi
0x14000d930  push    r12
0x14000d932  push    r13
0x14000d934  push    r14
0x14000d936  push    r15
0x14000d938  mov     eax, 22C0h
0x14000d93d  call    _alloca_probe
0x14000d942  sub     rsp, rax
0x14000d945  mov     rax, cs:__security_cookie
0x14000d94c  xor     rax, rsp
0x14000d94f  mov     [rsp+22F8h+var_48], rax
0x14000d957  mov     r14, r8
0x14000d95a  mov     [rsp+22F8h+lpValueName], r8
0x14000d95f  mov     r12, rdx
0x14000d962  mov     [rsp+22F8h+var_2288], rdx
0x14000d967  mov     r15, rcx
0x14000d96a  mov     [rsp+22F8h+var_22C0], rcx
0x14000d96f  mov     qword ptr [rsp+22F8h+Data], rdx
0x14000d974  mov     [rsp+22F8h+var_22A8], rcx
0x14000d979  mov     [rsp+22F8h+var_2278], rdx
0x14000d981  mov     [rsp+22F8h+var_2298], r8
0x14000d986  mov     [rsp+22F8h+var_2270], r9
0x14000d98e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x14000d996  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000d99b  xor     ebx, ebx
0x14000d99d  test    eax, eax
0x14000d99f  js      short loc_14000D9D3
0x14000d9a1  mov     edi, ebx
0x14000d9a3  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000d9aa  movsxd  rsi, edi
0x14000d9ad  add     rsi, rsi
0x14000d9b0  mov     rdx, [r13+rsi*8+0]; lpString2
0x14000d9b5  lea     rcx, [rsp+22F8h+String1]; lpString1
0x14000d9bd  call    cs:__imp_lstrcmpiW
0x14000d9c3  test    eax, eax
0x14000d9c5  jz      short loc_14000D9F6
0x14000d9c7  inc     edi
0x14000d9c9  cmp     edi, 4
0x14000d9cc  jb      short loc_14000D9AA
0x14000d9ce  mov     eax, 80020009h
0x14000d9d3  mov     rcx, [rsp+22F8h+var_48]
0x14000d9db  xor     rcx, rsp; StackCookie
0x14000d9de  call    __security_check_cookie
0x14000d9e3  add     rsp, 22C0h
0x14000d9ea  pop     r15
0x14000d9ec  pop     r14
0x14000d9ee  pop     r13
0x14000d9f0  pop     r12
0x14000d9f2  pop     rdi
0x14000d9f3  pop     rsi
0x14000d9f4  pop     rbx
0x14000d9f5  retn
0x14000d9f6  movzx   edi, word ptr [r13+rsi*8+8]
0x14000d9fc  mov     esi, 13h
0x14000da01  mov     rdx, [r15]
0x14000da04  movzx   ecx, word ptr [rdx]
0x14000da07  sub     ecx, 9
0x14000da0a  jz      loc_14000DECD
0x14000da10  sub     ecx, 1
0x14000da13  jz      loc_14000DECD
0x14000da19  sub     ecx, 3
0x14000da1c  jz      loc_14000DECD
0x14000da22  cmp     ecx, esi
0x14000da24  jz      loc_14000DECD
0x14000da2a  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x14000da32  mov     rcx, r15; this
0x14000da35  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000da3a  test    eax, eax
0x14000da3c  js      short loc_14000D9D3
0x14000da3e  mov     r13d, 8
0x14000da44  cmp     di, r13w
0x14000da48  jz      loc_14000DE7E
0x14000da4e  cmp     di, 11h
0x14000da52  jz      loc_14000DC57
0x14000da58  cmp     di, si
0x14000da5b  jz      loc_14000DBFF
0x14000da61  mov     eax, 4008h
0x14000da66  cmp     di, ax
0x14000da69  jnz     loc_14000DEB1
0x14000da6f  lea     rcx, [rsp+22F8h+String1]
0x14000da77  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000da7b  mov     rax, rsi
0x14000da7e  inc     rax
0x14000da81  cmp     [rcx+rax*2], bx
0x14000da85  jnz     short loc_14000DA7E
0x14000da87  add     eax, 2
0x14000da8a  mov     [rsp+22F8h+var_2158], rbx
0x14000da92  test    eax, eax
0x14000da94  jz      short loc_14000DACF
0x14000da96  movsxd  rcx, eax
0x14000da99  xor     edx, edx
0x14000da9b  mov     rax, rsi
0x14000da9e  div     rcx
0x14000daa1  cmp     rax, 2
0x14000daa5  jb      loc_14000DEDE
0x14000daab  lea     rdx, [rcx+rcx]
0x14000daaf  cmp     rdx, 100h
0x14000dab6  jbe     short loc_14000DACF
0x14000dab8  lea     rcx, [rsp+22F8h+var_2158]
0x14000dac0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000dac5  mov     rdi, [rsp+22F8h+var_2158]
0x14000dacd  jmp     short loc_14000DADF
0x14000dacf  lea     rdi, [rsp+22F8h+var_2150]
0x14000dad7  mov     [rsp+22F8h+var_2158], rdi
0x14000dadf  mov     r13, [rsp+22F8h+lpValueName]
0x14000dae4  jmp     short loc_14000DB08
0x14000dae6  xor     ebx, ebx
0x14000dae8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000daec  mov     rdi, [rsp+22F8h+var_2158]
0x14000daf4  mov     r12, qword ptr [rsp+22F8h+Data]
0x14000daf9  mov     rax, [rsp+22F8h+var_22A8]
0x14000dafe  mov     [rsp+22F8h+var_22C0], rax
0x14000db03  mov     r13, [rsp+22F8h+var_2298]
0x14000db08  test    rdi, rdi
0x14000db0b  jz      loc_14000DBC7
0x14000db11  lea     r14, [rsp+22F8h+String1]
0x14000db19  cmp     [rsp+22F8h+String1], bx
0x14000db21  jz      short loc_14000DB64
0x14000db23  mov     r15d, 30h ; '0'
0x14000db29  mov     rcx, r14; lpsz
0x14000db2c  call    cs:__imp_CharNextW
0x14000db32  movzx   ecx, word ptr [r14]
0x14000db36  cmp     cx, 5Ch ; '\'
0x14000db3a  jnz     short loc_14000DB53
0x14000db3c  cmp     [rax], r15w
0x14000db40  jnz     short loc_14000DB53
0x14000db42  mov     [rdi], bx
0x14000db45  mov     rcx, rax; lpsz
0x14000db48  call    cs:__imp_CharNextW
0x14000db4e  mov     r14, rax
0x14000db51  jmp     short loc_14000DB5A
0x14000db53  mov     [rdi], cx
0x14000db56  add     r14, 2
0x14000db5a  add     rdi, 2
0x14000db5e  cmp     [r14], bx
0x14000db62  jnz     short loc_14000DB29
0x14000db64  mov     dword ptr [rdi], 0
0x14000db6a  mov     r8, [rsp+22F8h+var_2158]
0x14000db72  test    r8, r8
0x14000db75  jz      loc_14000DEE9
0x14000db7b  mov     r10d, ebx
0x14000db7e  mov     r9, r8
0x14000db81  mov     rcx, rsi
0x14000db84  inc     rcx
0x14000db87  cmp     [r9+rcx*2], bx
0x14000db8c  jnz     short loc_14000DB84
0x14000db8e  inc     ecx
0x14000db90  lea     r9, [r9+rcx*2]
0x14000db94  lea     r10d, [r10+rcx*2]
0x14000db98  cmp     ecx, 1
0x14000db9b  jnz     short loc_14000DB81
0x14000db9d  mov     [rsp+22F8h+cbData], r10d; cbData
0x14000dba2  mov     [rsp+22F8h+lpData], r8; lpData
0x14000dba7  lea     r9d, [rcx+6]; dwType
0x14000dbab  xor     r8d, r8d; Reserved
0x14000dbae  mov     rdx, r13; lpValueName
0x14000dbb1  mov     rcx, [r12]; hKey
0x14000dbb5  call    cs:__imp_RegSetValueExW
0x14000dbbb  mov     esi, eax
0x14000dbbd  mov     rdi, [rsp+22F8h+var_2158]
0x14000dbc5  jmp     short loc_14000DBCC
0x14000dbc7  mov     esi, 0Eh
0x14000dbcc  lea     rax, [rsp+22F8h+var_2150]
0x14000dbd4  cmp     rdi, rax
0x14000dbd7  jz      short loc_14000DBE6
0x14000dbd9  lea     rcx, [rsp+22F8h+var_2158]
0x14000dbe1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000dbe6  mov     r15, [rsp+22F8h+var_22C0]
0x14000dbeb  test    esi, esi
0x14000dbed  jz      loc_14000DEB1
0x14000dbf3  mov     ecx, esi; unsigned int
0x14000dbf5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000dbfa  jmp     loc_14000D9D3
0x14000dbff  mov     [rsp+22F8h+pulOut], ebx
0x14000dc03  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x14000dc08  xor     r8d, r8d; dwFlags
0x14000dc0b  xor     edx, edx; lcid
0x14000dc0d  lea     rcx, [rsp+22F8h+String1]; strIn
0x14000dc15  call    cs:__imp_VarUI4FromStr
0x14000dc1b  test    eax, eax
0x14000dc1d  js      loc_14000D9D3
0x14000dc23  mov     eax, [rsp+22F8h+pulOut]
0x14000dc27  mov     dword ptr [rsp+22F8h+Data], eax
0x14000dc2b  mov     [rsp+22F8h+cbData], 4; cbData
0x14000dc33  lea     rax, [rsp+22F8h+Data]
0x14000dc38  mov     r9d, 4; dwType
0x14000dc3e  mov     [rsp+22F8h+lpData], rax; lpData
0x14000dc43  xor     r8d, r8d; Reserved
0x14000dc46  mov     rdx, r14; lpValueName
0x14000dc49  mov     rcx, [r12]; hKey
0x14000dc4d  call    cs:__imp_RegSetValueExW
0x14000dc53  mov     esi, eax
0x14000dc55  jmp     short loc_14000DBEB
0x14000dc57  lea     rax, [rsp+22F8h+String1]
0x14000dc5f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000dc63  mov     r14, rsi
0x14000dc66  inc     r14
0x14000dc69  cmp     [rax+r14*2], bx
0x14000dc6e  jnz     short loc_14000DC66
0x14000dc70  mov     dword ptr [rsp+22F8h+Data], r14d
0x14000dc75  test    r14b, 1
0x14000dc79  jnz     loc_14000DD33
0x14000dc7f  mov     eax, r14d
0x14000dc82  cdq
0x14000dc83  sub     eax, edx
0x14000dc85  sar     eax, 1
0x14000dc87  movsxd  r12, eax
0x14000dc8a  mov     [rsp+22F8h+var_2268], rbx
0x14000dc92  mov     rdi, r12
0x14000dc95  mov     [rsp+22F8h+var_2280], r12
0x14000dc9a  test    eax, eax
0x14000dc9c  jz      short loc_14000DCD3
0x14000dc9e  xor     edx, edx
0x14000dca0  mov     rax, rsi
0x14000dca3  div     rdi
0x14000dca6  cmp     rax, 1
0x14000dcaa  jb      loc_14000DEF4
0x14000dcb0  cmp     rdi, 100h
0x14000dcb7  jbe     short loc_14000DCD3
0x14000dcb9  mov     rdx, rdi
0x14000dcbc  lea     rcx, [rsp+22F8h+var_2268]
0x14000dcc4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000dcc9  mov     rcx, [rsp+22F8h+var_2268]
0x14000dcd1  jmp     short loc_14000DCE3
0x14000dcd3  lea     rcx, [rsp+22F8h+var_2260]
0x14000dcdb  mov     [rsp+22F8h+var_2268], rcx
0x14000dce3  mov     rsi, [rsp+22F8h+var_2288]
0x14000dce8  jmp     short loc_14000DD21
0x14000dcea  xor     ebx, ebx
0x14000dcec  lea     r13d, [rbx+8]
0x14000dcf0  mov     r14d, dword ptr [rsp+22F8h+Data]
0x14000dcf5  mov     rcx, [rsp+22F8h+var_2268]; void *
0x14000dcfd  mov     rdi, [rsp+22F8h+var_2280]
0x14000dd02  mov     rax, [rsp+22F8h+var_22A8]
0x14000dd07  mov     [rsp+22F8h+var_22C0], rax
0x14000dd0c  mov     rsi, [rsp+22F8h+var_2278]
0x14000dd14  mov     rax, [rsp+22F8h+var_2298]
0x14000dd19  mov     [rsp+22F8h+lpValueName], rax
0x14000dd1e  mov     r12d, edi
0x14000dd21  test    rcx, rcx
0x14000dd24  jnz     short loc_14000DD3D
0x14000dd26  lea     rcx, [rsp+22F8h+var_2268]
0x14000dd2e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000dd33  mov     eax, 80004005h
0x14000dd38  jmp     loc_14000D9D3
0x14000dd3d  mov     r8, rdi; Size
0x14000dd40  xor     edx, edx; Val
0x14000dd42  call    memset_0
0x14000dd47  mov     r10d, ebx
0x14000dd4a  test    r14d, r14d
0x14000dd4d  jle     loc_14000DE2B
0x14000dd53  mov     r15d, 30h ; '0'
0x14000dd59  mov     eax, r10d
0x14000dd5c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x14000dd64  cmp     edx, 61h ; 'a'
0x14000dd67  ja      short loc_14000DDD6
0x14000dd69  jz      loc_14000DDF6
0x14000dd6f  cmp     edx, 38h ; '8'
0x14000dd72  ja      short loc_14000DDA8
0x14000dd74  jz      short loc_14000DDA0
0x14000dd76  mov     ecx, edx
0x14000dd78  sub     ecx, r15d
0x14000dd7b  jz      short loc_14000DDA0
0x14000dd7d  sub     ecx, 1
0x14000dd80  jz      short loc_14000DDA0
0x14000dd82  sub     ecx, 1
0x14000dd85  jz      short loc_14000DDA0
0x14000dd87  sub     ecx, 1
0x14000dd8a  jz      short loc_14000DDA0
0x14000dd8c  sub     ecx, 1
0x14000dd8f  jz      short loc_14000DDA0
0x14000dd91  sub     ecx, 1
0x14000dd94  jz      short loc_14000DDA0
0x14000dd96  sub     ecx, 1
0x14000dd99  jz      short loc_14000DDA0
0x14000dd9b  cmp     ecx, 1
0x14000dd9e  jnz     short loc_14000DDF1
0x14000dda0  mov     r9d, edx
0x14000dda3  sub     r9d, r15d
0x14000dda6  jmp     short loc_14000DDFA
0x14000dda8  mov     r9d, edx
0x14000ddab  mov     ecx, edx
0x14000ddad  sub     ecx, 39h ; '9'
0x14000ddb0  jz      short loc_14000DDA0
0x14000ddb2  sub     ecx, r13d
0x14000ddb5  jz      short loc_14000DDD0
0x14000ddb7  sub     ecx, 1
0x14000ddba  jz      short loc_14000DDD0
0x14000ddbc  sub     ecx, 1
0x14000ddbf  jz      short loc_14000DDD0
0x14000ddc1  sub     ecx, 1
0x14000ddc4  jz      short loc_14000DDD0
0x14000ddc6  sub     ecx, 1
0x14000ddc9  jz      short loc_14000DDD0
0x14000ddcb  cmp     ecx, 1
0x14000ddce  jnz     short loc_14000DDF1
0x14000ddd0  add     r9d, 0FFFFFFC9h
0x14000ddd4  jmp     short loc_14000DDFA
  ... truncated ...
```
