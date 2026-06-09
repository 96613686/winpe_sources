# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180012a40`
- end: `0x180013014`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180015e40`

## callees

- `0x180001800`
- `0x180002678`
- `0x180003858`
- `0x180012a40`
- `0x18001301c`
- `0x180013218`
- `0x1800144ac`
- `0x180015400`
- `0x180032a50`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180012cc9`
- `ADVAPI32!RegSetValueExW` at `0x180012d61`
- `ADVAPI32!RegSetValueExW` at `0x180012f62`
- `ADVAPI32!RegSetValueExW` at `0x180012cc9`
- `ADVAPI32!RegSetValueExW` at `0x180012d61`
- `ADVAPI32!RegSetValueExW` at `0x180012f62`
- `KERNEL32!lstrcmpiW` at `0x180012ad1`
- `KERNEL32!lstrcmpiW` at `0x180012ad1`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180012d29`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180012d29`
- `USER32!CharNextW` at `0x180012c40`
- `USER32!CharNextW` at `0x180012c5c`
- `USER32!CharNextW` at `0x180012fe4`
- `USER32!CharNextW` at `0x180012c40`
- `USER32!CharNextW` at `0x180012c5c`
- `USER32!CharNextW` at `0x180012fe4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180012a40  push    rbx
0x180012a42  push    rsi
0x180012a43  push    rdi
0x180012a44  push    r12
0x180012a46  push    r13
0x180012a48  push    r14
0x180012a4a  push    r15
0x180012a4c  mov     eax, 22C0h
0x180012a51  call    _alloca_probe
0x180012a56  sub     rsp, rax
0x180012a59  mov     rax, cs:__security_cookie
0x180012a60  xor     rax, rsp
0x180012a63  mov     [rsp+22F8h+var_48], rax
0x180012a6b  mov     r14, r8
0x180012a6e  mov     [rsp+22F8h+lpValueName], r8
0x180012a73  mov     r12, rdx
0x180012a76  mov     [rsp+22F8h+var_2288], rdx
0x180012a7b  mov     r15, rcx
0x180012a7e  mov     [rsp+22F8h+var_22C0], rcx
0x180012a83  mov     qword ptr [rsp+22F8h+Data], rdx
0x180012a88  mov     [rsp+22F8h+var_22A8], rcx
0x180012a8d  mov     [rsp+22F8h+var_2278], rdx
0x180012a95  mov     [rsp+22F8h+var_2298], r8
0x180012a9a  mov     [rsp+22F8h+var_2270], r9
0x180012aa2  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180012aaa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012aaf  xor     ebx, ebx
0x180012ab1  test    eax, eax
0x180012ab3  js      short loc_180012AE7
0x180012ab5  mov     edi, ebx
0x180012ab7  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180012abe  movsxd  rsi, edi
0x180012ac1  add     rsi, rsi
0x180012ac4  mov     rdx, [r13+rsi*8+0]; lpString2
0x180012ac9  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180012ad1  call    cs:__imp_lstrcmpiW
0x180012ad7  test    eax, eax
0x180012ad9  jz      short loc_180012B0A
0x180012adb  inc     edi
0x180012add  cmp     edi, 4
0x180012ae0  jb      short loc_180012ABE
0x180012ae2  mov     eax, 80020009h
0x180012ae7  mov     rcx, [rsp+22F8h+var_48]
0x180012aef  xor     rcx, rsp; StackCookie
0x180012af2  call    __security_check_cookie
0x180012af7  add     rsp, 22C0h
0x180012afe  pop     r15
0x180012b00  pop     r14
0x180012b02  pop     r13
0x180012b04  pop     r12
0x180012b06  pop     rdi
0x180012b07  pop     rsi
0x180012b08  pop     rbx
0x180012b09  retn
0x180012b0a  movzx   edi, word ptr [r13+rsi*8+8]
0x180012b10  mov     esi, 13h
0x180012b15  mov     rdx, [r15]
0x180012b18  movzx   ecx, word ptr [rdx]
0x180012b1b  sub     ecx, 9
0x180012b1e  jz      loc_180012FE1
0x180012b24  sub     ecx, 1
0x180012b27  jz      loc_180012FE1
0x180012b2d  sub     ecx, 3
0x180012b30  jz      loc_180012FE1
0x180012b36  cmp     ecx, esi
0x180012b38  jz      loc_180012FE1
0x180012b3e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180012b46  mov     rcx, r15; this
0x180012b49  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012b4e  test    eax, eax
0x180012b50  js      short loc_180012AE7
0x180012b52  mov     r13d, 8
0x180012b58  cmp     di, r13w
0x180012b5c  jz      loc_180012F92
0x180012b62  cmp     di, 11h
0x180012b66  jz      loc_180012D6B
0x180012b6c  cmp     di, si
0x180012b6f  jz      loc_180012D13
0x180012b75  mov     eax, 4008h
0x180012b7a  cmp     di, ax
0x180012b7d  jnz     loc_180012FC5
0x180012b83  lea     rcx, [rsp+22F8h+String1]
0x180012b8b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012b8f  mov     rax, rsi
0x180012b92  inc     rax
0x180012b95  cmp     [rcx+rax*2], bx
0x180012b99  jnz     short loc_180012B92
0x180012b9b  add     eax, 2
0x180012b9e  mov     [rsp+22F8h+var_2158], rbx
0x180012ba6  test    eax, eax
0x180012ba8  jz      short loc_180012BE3
0x180012baa  movsxd  rcx, eax
0x180012bad  xor     edx, edx
0x180012baf  mov     rax, rsi
0x180012bb2  div     rcx
0x180012bb5  cmp     rax, 2
0x180012bb9  jb      loc_180012FF2
0x180012bbf  lea     rdx, [rcx+rcx]
0x180012bc3  cmp     rdx, 100h
0x180012bca  jbe     short loc_180012BE3
0x180012bcc  lea     rcx, [rsp+22F8h+var_2158]
0x180012bd4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180012bd9  mov     rdi, [rsp+22F8h+var_2158]
0x180012be1  jmp     short loc_180012BF3
0x180012be3  lea     rdi, [rsp+22F8h+var_2150]
0x180012beb  mov     [rsp+22F8h+var_2158], rdi
0x180012bf3  mov     r13, [rsp+22F8h+lpValueName]
0x180012bf8  jmp     short loc_180012C1C
0x180012bfa  xor     ebx, ebx
0x180012bfc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012c00  mov     rdi, [rsp+22F8h+var_2158]
0x180012c08  mov     r12, qword ptr [rsp+22F8h+Data]
0x180012c0d  mov     rax, [rsp+22F8h+var_22A8]
0x180012c12  mov     [rsp+22F8h+var_22C0], rax
0x180012c17  mov     r13, [rsp+22F8h+var_2298]
0x180012c1c  test    rdi, rdi
0x180012c1f  jz      loc_180012CDB
0x180012c25  lea     r14, [rsp+22F8h+String1]
0x180012c2d  cmp     [rsp+22F8h+String1], bx
0x180012c35  jz      short loc_180012C78
0x180012c37  mov     r15d, 30h ; '0'
0x180012c3d  mov     rcx, r14; lpsz
0x180012c40  call    cs:__imp_CharNextW
0x180012c46  movzx   ecx, word ptr [r14]
0x180012c4a  cmp     cx, 5Ch ; '\'
0x180012c4e  jnz     short loc_180012C67
0x180012c50  cmp     [rax], r15w
0x180012c54  jnz     short loc_180012C67
0x180012c56  mov     [rdi], bx
0x180012c59  mov     rcx, rax; lpsz
0x180012c5c  call    cs:__imp_CharNextW
0x180012c62  mov     r14, rax
0x180012c65  jmp     short loc_180012C6E
0x180012c67  mov     [rdi], cx
0x180012c6a  add     r14, 2
0x180012c6e  add     rdi, 2
0x180012c72  cmp     [r14], bx
0x180012c76  jnz     short loc_180012C3D
0x180012c78  mov     dword ptr [rdi], 0
0x180012c7e  mov     r8, [rsp+22F8h+var_2158]
0x180012c86  test    r8, r8
0x180012c89  jz      loc_180012FFD
0x180012c8f  mov     r10d, ebx
0x180012c92  mov     r9, r8
0x180012c95  mov     rcx, rsi
0x180012c98  inc     rcx
0x180012c9b  cmp     [r9+rcx*2], bx
0x180012ca0  jnz     short loc_180012C98
0x180012ca2  inc     ecx
0x180012ca4  lea     r9, [r9+rcx*2]
0x180012ca8  lea     r10d, [r10+rcx*2]
0x180012cac  cmp     ecx, 1
0x180012caf  jnz     short loc_180012C95
0x180012cb1  mov     [rsp+22F8h+cbData], r10d; cbData
0x180012cb6  mov     [rsp+22F8h+lpData], r8; lpData
0x180012cbb  lea     r9d, [rcx+6]; dwType
0x180012cbf  xor     r8d, r8d; Reserved
0x180012cc2  mov     rdx, r13; lpValueName
0x180012cc5  mov     rcx, [r12]; hKey
0x180012cc9  call    cs:__imp_RegSetValueExW
0x180012ccf  mov     esi, eax
0x180012cd1  mov     rdi, [rsp+22F8h+var_2158]
0x180012cd9  jmp     short loc_180012CE0
0x180012cdb  mov     esi, 0Eh
0x180012ce0  lea     rax, [rsp+22F8h+var_2150]
0x180012ce8  cmp     rdi, rax
0x180012ceb  jz      short loc_180012CFA
0x180012ced  lea     rcx, [rsp+22F8h+var_2158]
0x180012cf5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180012cfa  mov     r15, [rsp+22F8h+var_22C0]
0x180012cff  test    esi, esi
0x180012d01  jz      loc_180012FC5
0x180012d07  mov     ecx, esi; unsigned int
0x180012d09  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180012d0e  jmp     loc_180012AE7
0x180012d13  mov     [rsp+22F8h+pulOut], ebx
0x180012d17  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180012d1c  xor     r8d, r8d; dwFlags
0x180012d1f  xor     edx, edx; lcid
0x180012d21  lea     rcx, [rsp+22F8h+String1]; strIn
0x180012d29  call    cs:__imp_VarUI4FromStr
0x180012d2f  test    eax, eax
0x180012d31  js      loc_180012AE7
0x180012d37  mov     eax, [rsp+22F8h+pulOut]
0x180012d3b  mov     dword ptr [rsp+22F8h+Data], eax
0x180012d3f  mov     [rsp+22F8h+cbData], 4; cbData
0x180012d47  lea     rax, [rsp+22F8h+Data]
0x180012d4c  mov     r9d, 4; dwType
0x180012d52  mov     [rsp+22F8h+lpData], rax; lpData
0x180012d57  xor     r8d, r8d; Reserved
0x180012d5a  mov     rdx, r14; lpValueName
0x180012d5d  mov     rcx, [r12]; hKey
0x180012d61  call    cs:__imp_RegSetValueExW
0x180012d67  mov     esi, eax
0x180012d69  jmp     short loc_180012CFF
0x180012d6b  lea     rax, [rsp+22F8h+String1]
0x180012d73  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012d77  mov     r14, rsi
0x180012d7a  inc     r14
0x180012d7d  cmp     [rax+r14*2], bx
0x180012d82  jnz     short loc_180012D7A
0x180012d84  mov     dword ptr [rsp+22F8h+Data], r14d
0x180012d89  test    r14b, 1
0x180012d8d  jnz     loc_180012E47
0x180012d93  mov     eax, r14d
0x180012d96  cdq
0x180012d97  sub     eax, edx
0x180012d99  sar     eax, 1
0x180012d9b  movsxd  r12, eax
0x180012d9e  mov     [rsp+22F8h+var_2268], rbx
0x180012da6  mov     rdi, r12
0x180012da9  mov     [rsp+22F8h+var_2280], r12
0x180012dae  test    eax, eax
0x180012db0  jz      short loc_180012DE7
0x180012db2  xor     edx, edx
0x180012db4  mov     rax, rsi
0x180012db7  div     rdi
0x180012dba  cmp     rax, 1
0x180012dbe  jb      loc_180013008
0x180012dc4  cmp     rdi, 100h
0x180012dcb  jbe     short loc_180012DE7
0x180012dcd  mov     rdx, rdi
0x180012dd0  lea     rcx, [rsp+22F8h+var_2268]
0x180012dd8  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180012ddd  mov     rcx, [rsp+22F8h+var_2268]
0x180012de5  jmp     short loc_180012DF7
0x180012de7  lea     rcx, [rsp+22F8h+var_2260]
0x180012def  mov     [rsp+22F8h+var_2268], rcx
0x180012df7  mov     rsi, [rsp+22F8h+var_2288]
0x180012dfc  jmp     short loc_180012E35
0x180012dfe  xor     ebx, ebx
0x180012e00  lea     r13d, [rbx+8]
0x180012e04  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180012e09  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180012e11  mov     rdi, [rsp+22F8h+var_2280]
0x180012e16  mov     rax, [rsp+22F8h+var_22A8]
0x180012e1b  mov     [rsp+22F8h+var_22C0], rax
0x180012e20  mov     rsi, [rsp+22F8h+var_2278]
0x180012e28  mov     rax, [rsp+22F8h+var_2298]
0x180012e2d  mov     [rsp+22F8h+lpValueName], rax
0x180012e32  mov     r12d, edi
0x180012e35  test    rcx, rcx
0x180012e38  jnz     short loc_180012E51
0x180012e3a  lea     rcx, [rsp+22F8h+var_2268]
0x180012e42  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180012e47  mov     eax, 80004005h
0x180012e4c  jmp     loc_180012AE7
0x180012e51  mov     r8, rdi; Size
0x180012e54  xor     edx, edx; Val
0x180012e56  call    memset_0
0x180012e5b  mov     r10d, ebx
0x180012e5e  test    r14d, r14d
0x180012e61  jle     loc_180012F3F
0x180012e67  mov     r15d, 30h ; '0'
0x180012e6d  mov     eax, r10d
0x180012e70  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180012e78  cmp     edx, 61h ; 'a'
0x180012e7b  ja      short loc_180012EEA
0x180012e7d  jz      loc_180012F0A
0x180012e83  cmp     edx, 38h ; '8'
0x180012e86  ja      short loc_180012EBC
0x180012e88  jz      short loc_180012EB4
0x180012e8a  mov     ecx, edx
0x180012e8c  sub     ecx, r15d
0x180012e8f  jz      short loc_180012EB4
0x180012e91  sub     ecx, 1
0x180012e94  jz      short loc_180012EB4
0x180012e96  sub     ecx, 1
0x180012e99  jz      short loc_180012EB4
0x180012e9b  sub     ecx, 1
0x180012e9e  jz      short loc_180012EB4
0x180012ea0  sub     ecx, 1
0x180012ea3  jz      short loc_180012EB4
0x180012ea5  sub     ecx, 1
0x180012ea8  jz      short loc_180012EB4
0x180012eaa  sub     ecx, 1
0x180012ead  jz      short loc_180012EB4
0x180012eaf  cmp     ecx, 1
0x180012eb2  jnz     short loc_180012F05
0x180012eb4  mov     r9d, edx
0x180012eb7  sub     r9d, r15d
0x180012eba  jmp     short loc_180012F0E
0x180012ebc  mov     r9d, edx
0x180012ebf  mov     ecx, edx
0x180012ec1  sub     ecx, 39h ; '9'
0x180012ec4  jz      short loc_180012EB4
0x180012ec6  sub     ecx, r13d
0x180012ec9  jz      short loc_180012EE4
0x180012ecb  sub     ecx, 1
0x180012ece  jz      short loc_180012EE4
0x180012ed0  sub     ecx, 1
0x180012ed3  jz      short loc_180012EE4
0x180012ed5  sub     ecx, 1
0x180012ed8  jz      short loc_180012EE4
0x180012eda  sub     ecx, 1
0x180012edd  jz      short loc_180012EE4
0x180012edf  cmp     ecx, 1
0x180012ee2  jnz     short loc_180012F05
0x180012ee4  add     r9d, 0FFFFFFC9h
0x180012ee8  jmp     short loc_180012F0E
  ... truncated ...
```
