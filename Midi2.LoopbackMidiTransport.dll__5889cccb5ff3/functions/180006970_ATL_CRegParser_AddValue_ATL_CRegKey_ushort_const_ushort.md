# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180006970`
- end: `0x180006f44`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800094ec`

## callees

- `0x180004180`
- `0x18000500c`
- `0x180006970`
- `0x180006f4c`
- `0x1800070a0`
- `0x1800070b8`
- `0x1800078cc`
- `0x1800089bc`
- `0x1800300d0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180006c59`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180006c59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006bf9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006c91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006e92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006bf9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006c91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006e92`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b70`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b8c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006f14`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b70`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b8c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006f14`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006a01`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006a01`

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
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  BYTE *v14; // rdi
  const WCHAR *v15; // r13
  WCHAR *i; // r14
  const WCHAR *v17; // rax
  DWORD v18; // r10d
  BYTE *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // esi
  const BYTE *v23; // rax
  DWORD v24; // r9d
  __int64 v25; // r14
  DWORD v26; // r12d
  size_t v27; // rdi
  BYTE *v28; // rcx
  HKEY *v29; // rsi
  unsigned int v30; // r10d
  unsigned int v31; // edx
  char v32; // r9
  __int64 v33; // rsi
  int Token; // eax
  __int64 v35; // [rsp+0h] [rbp-22F8h] BYREF
  DWORD cbData; // [rsp+28h] [rbp-22D0h]
  ULONG pulOut; // [rsp+30h] [rbp-22C8h] BYREF
  ATL::CRegParser *v38; // [rsp+38h] [rbp-22C0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22B8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22B0h]
  ATL::CRegParser *v41; // [rsp+50h] [rbp-22A8h]
  const WCHAR *v42; // [rsp+60h] [rbp-2298h]
  struct ATL::CRegKey *v43; // [rsp+70h] [rbp-2288h]
  size_t v44; // [rsp+78h] [rbp-2280h]
  struct ATL::CRegKey *v45; // [rsp+80h] [rbp-2278h]
  unsigned __int16 *v46; // [rsp+88h] [rbp-2270h]
  BYTE *v47; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v48[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v50[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v43 = (struct ATL::CRegKey *)a2;
  v6 = this;
  v38 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v41 = (ATL::CRegParser *)this;
  v45 = (struct ATL::CRegKey *)a2;
  v42 = a3;
  v46 = a4;
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
        v33 = -1;
        do
          ++v33;
        while ( String1[v33] );
        cbData = 2 * v33 + 2;
        v23 = (const BYTE *)String1;
        v24 = 1;
        goto LABEL_47;
      }
      if ( v10 != 17 )
      {
        if ( v10 != 19 )
        {
          if ( v10 != 16392 )
          {
LABEL_93:
            Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v46);
            if ( Token < 0 )
              return Token;
            return v8;
          }
          v12 = -1;
          do
            ++v12;
          while ( String1[v12] );
          v13 = v12 + 2;
          lpData = 0;
          try
          {
            if ( !v13 )
              goto LABEL_24;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v13 < 2 )
              ATL::AtlThrowImpl(-2147024809);
            v11 = (__int64 *)(2LL * v13);
            if ( (unsigned __int64)v11 > 0x100 )
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v11);
              v14 = lpData;
            }
            else
            {
LABEL_24:
              v14 = v50;
              lpData = v50;
            }
          }
          catch ( ... )
          {
            v11 = &v35;
            v8 = 0;
            v14 = lpData;
            v5 = *(HKEY **)Data;
            v38 = v41;
            v15 = v42;
            goto LABEL_26;
          }
          v15 = lpValueName;
LABEL_26:
          if ( v14 )
          {
            for ( i = String1; *i; v14 += 2 )
            {
              v17 = CharNextW(i);
              if ( *i == 92 && *v17 == 48 )
              {
                *(_WORD *)v14 = 0;
                i = CharNextW(v17);
              }
              else
              {
                *(_WORD *)v14 = *i++;
              }
            }
            *(_DWORD *)v14 = 0;
            if ( !lpData )
              ATL::AtlThrowImpl(-2147467259);
            v18 = 0;
            v19 = lpData;
            do
            {
              v20 = -1;
              do
                ++v20;
              while ( *(_WORD *)&v19[2 * v20] );
              v21 = (unsigned int)(v20 + 1);
              v19 += 2 * v21;
              v18 += 2 * v21;
            }
            while ( (_DWORD)v21 != 1 );
            v22 = RegSetValueExW(*v5, v15, 0, 7u, lpData, v18);
            v14 = lpData;
          }
          else
          {
            v22 = 14;
          }
          if ( v14 != v50 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
          goto LABEL_42;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v23 = Data;
        v24 = 4;
LABEL_47:
        v22 = RegSetValueExW(*v5, a3, 0, v24, v23, cbData);
LABEL_43:
        if ( v22 )
          return winrt::impl::hresult_from_win32((winrt::impl *)v22, (unsigned int)v11);
        goto LABEL_93;
      }
      v25 = -1;
      do
        ++v25;
      while ( String1[v25] );
      *(_DWORD *)Data = v25;
      if ( (v25 & 1) != 0 )
        return -2147467259;
      try
      {
        v26 = (int)v25 / 2;
        v47 = 0;
        v27 = (int)v25 / 2;
        v44 = v27;
        if ( !((int)v25 / 2) )
          goto LABEL_56;
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v27) )
          ATL::AtlThrowImpl(-2147024809);
        if ( v27 > 0x100 )
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v47, v27);
          v28 = v47;
        }
        else
        {
LABEL_56:
          v28 = v48;
          v47 = v48;
        }
        v29 = (HKEY *)v43;
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v25) = *(_DWORD *)Data;
        v28 = v47;
        v27 = v44;
        v38 = v41;
        v29 = (HKEY *)v45;
        lpValueName = v42;
        v26 = v44;
      }
      if ( !v28 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v47);
        return -2147467259;
      }
      memset_0(v28, 0, v27);
      v30 = 0;
      if ( (int)v25 <= 0 )
      {
LABEL_88:
        v22 = RegSetValueExW(*v29, lpValueName, 0, 3u, v47, v26);
        if ( v47 != v48 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v47);
LABEL_42:
        v6 = (LPCWSTR *)v38;
        goto LABEL_43;
      }
      while ( 1 )
      {
        v31 = String1[v30];
        if ( v31 > 0x61 )
        {
          if ( v31 == 98 || v31 == 99 || v31 == 100 || v31 - 101 < 2 )
          {
LABEL_86:
            v32 = v31 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v32 = 0;
          goto LABEL_87;
        }
        if ( v31 == 97 )
          goto LABEL_86;
        if ( v31 <= 0x38 )
          break;
        if ( v31 == 57 )
          goto LABEL_73;
        if ( v31 != 65 && v31 != 66 && v31 != 67 && v31 != 68 && v31 - 69 > 1 )
          goto LABEL_85;
        v32 = v31 - 55;
LABEL_87:
        v47[(unsigned __int64)v30 >> 1] |= v32 << (4 - 4 * (v30 & 1));
        if ( (int)++v30 >= (int)v25 )
          goto LABEL_88;
      }
      if ( v31 != 56 && v31 != 48 && v31 != 49 && v31 != 50 && v31 != 51 && v31 != 52 && v31 != 53 && v31 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v32 = v31 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006970  push    rbx
0x180006972  push    rsi
0x180006973  push    rdi
0x180006974  push    r12
0x180006976  push    r13
0x180006978  push    r14
0x18000697a  push    r15
0x18000697c  mov     eax, 22C0h
0x180006981  call    _alloca_probe
0x180006986  sub     rsp, rax
0x180006989  mov     rax, cs:__security_cookie
0x180006990  xor     rax, rsp
0x180006993  mov     [rsp+22F8h+var_48], rax
0x18000699b  mov     r14, r8
0x18000699e  mov     [rsp+22F8h+lpValueName], r8
0x1800069a3  mov     r12, rdx
0x1800069a6  mov     [rsp+22F8h+var_2288], rdx
0x1800069ab  mov     r15, rcx
0x1800069ae  mov     [rsp+22F8h+var_22C0], rcx
0x1800069b3  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800069b8  mov     [rsp+22F8h+var_22A8], rcx
0x1800069bd  mov     [rsp+22F8h+var_2278], rdx
0x1800069c5  mov     [rsp+22F8h+var_2298], r8
0x1800069ca  mov     [rsp+22F8h+var_2270], r9
0x1800069d2  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800069da  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800069df  xor     ebx, ebx
0x1800069e1  test    eax, eax
0x1800069e3  js      short loc_180006A17
0x1800069e5  mov     edi, ebx
0x1800069e7  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800069ee  movsxd  rsi, edi
0x1800069f1  add     rsi, rsi
0x1800069f4  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800069f9  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180006a01  call    cs:__imp_lstrcmpiW
0x180006a07  test    eax, eax
0x180006a09  jz      short loc_180006A3A
0x180006a0b  inc     edi
0x180006a0d  cmp     edi, 4
0x180006a10  jb      short loc_1800069EE
0x180006a12  mov     eax, 80020009h
0x180006a17  mov     rcx, [rsp+22F8h+var_48]
0x180006a1f  xor     rcx, rsp; StackCookie
0x180006a22  call    __security_check_cookie
0x180006a27  add     rsp, 22C0h
0x180006a2e  pop     r15
0x180006a30  pop     r14
0x180006a32  pop     r13
0x180006a34  pop     r12
0x180006a36  pop     rdi
0x180006a37  pop     rsi
0x180006a38  pop     rbx
0x180006a39  retn
0x180006a3a  movzx   edi, word ptr [r13+rsi*8+8]
0x180006a40  mov     esi, 13h
0x180006a45  mov     rdx, [r15]
0x180006a48  movzx   ecx, word ptr [rdx]
0x180006a4b  sub     ecx, 9
0x180006a4e  jz      loc_180006F11
0x180006a54  sub     ecx, 1
0x180006a57  jz      loc_180006F11
0x180006a5d  sub     ecx, 3
0x180006a60  jz      loc_180006F11
0x180006a66  cmp     ecx, esi
0x180006a68  jz      loc_180006F11
0x180006a6e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180006a76  mov     rcx, r15; this
0x180006a79  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006a7e  test    eax, eax
0x180006a80  js      short loc_180006A17
0x180006a82  mov     r13d, 8
0x180006a88  cmp     di, r13w
0x180006a8c  jz      loc_180006EC2
0x180006a92  cmp     di, 11h
0x180006a96  jz      loc_180006C9B
0x180006a9c  cmp     di, si
0x180006a9f  jz      loc_180006C43
0x180006aa5  mov     eax, 4008h
0x180006aaa  cmp     di, ax
0x180006aad  jnz     loc_180006EF5
0x180006ab3  lea     rcx, [rsp+22F8h+String1]
0x180006abb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006abf  mov     rax, rsi
0x180006ac2  inc     rax
0x180006ac5  cmp     [rcx+rax*2], bx
0x180006ac9  jnz     short loc_180006AC2
0x180006acb  add     eax, 2
0x180006ace  mov     [rsp+22F8h+var_2158], rbx
0x180006ad6  test    eax, eax
0x180006ad8  jz      short loc_180006B13
0x180006ada  movsxd  rcx, eax
0x180006add  xor     edx, edx
0x180006adf  mov     rax, rsi
0x180006ae2  div     rcx
0x180006ae5  cmp     rax, 2
0x180006ae9  jb      loc_180006F22
0x180006aef  lea     rdx, [rcx+rcx]
0x180006af3  cmp     rdx, 100h
0x180006afa  jbe     short loc_180006B13
0x180006afc  lea     rcx, [rsp+22F8h+var_2158]
0x180006b04  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006b09  mov     rdi, [rsp+22F8h+var_2158]
0x180006b11  jmp     short loc_180006B23
0x180006b13  lea     rdi, [rsp+22F8h+var_2150]
0x180006b1b  mov     [rsp+22F8h+var_2158], rdi
0x180006b23  mov     r13, [rsp+22F8h+lpValueName]
0x180006b28  jmp     short loc_180006B4C
0x180006b2a  xor     ebx, ebx
0x180006b2c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006b30  mov     rdi, [rsp+22F8h+var_2158]
0x180006b38  mov     r12, qword ptr [rsp+22F8h+Data]
0x180006b3d  mov     rax, [rsp+22F8h+var_22A8]
0x180006b42  mov     [rsp+22F8h+var_22C0], rax
0x180006b47  mov     r13, [rsp+22F8h+var_2298]
0x180006b4c  test    rdi, rdi
0x180006b4f  jz      loc_180006C0B
0x180006b55  lea     r14, [rsp+22F8h+String1]
0x180006b5d  cmp     [rsp+22F8h+String1], bx
0x180006b65  jz      short loc_180006BA8
0x180006b67  mov     r15d, 30h ; '0'
0x180006b6d  mov     rcx, r14; lpsz
0x180006b70  call    cs:__imp_CharNextW
0x180006b76  movzx   ecx, word ptr [r14]
0x180006b7a  cmp     cx, 5Ch ; '\'
0x180006b7e  jnz     short loc_180006B97
0x180006b80  cmp     [rax], r15w
0x180006b84  jnz     short loc_180006B97
0x180006b86  mov     [rdi], bx
0x180006b89  mov     rcx, rax; lpsz
0x180006b8c  call    cs:__imp_CharNextW
0x180006b92  mov     r14, rax
0x180006b95  jmp     short loc_180006B9E
0x180006b97  mov     [rdi], cx
0x180006b9a  add     r14, 2
0x180006b9e  add     rdi, 2
0x180006ba2  cmp     [r14], bx
0x180006ba6  jnz     short loc_180006B6D
0x180006ba8  mov     dword ptr [rdi], 0
0x180006bae  mov     r8, [rsp+22F8h+var_2158]
0x180006bb6  test    r8, r8
0x180006bb9  jz      loc_180006F2D
0x180006bbf  mov     r10d, ebx
0x180006bc2  mov     r9, r8
0x180006bc5  mov     rcx, rsi
0x180006bc8  inc     rcx
0x180006bcb  cmp     [r9+rcx*2], bx
0x180006bd0  jnz     short loc_180006BC8
0x180006bd2  inc     ecx
0x180006bd4  lea     r9, [r9+rcx*2]
0x180006bd8  lea     r10d, [r10+rcx*2]
0x180006bdc  cmp     ecx, 1
0x180006bdf  jnz     short loc_180006BC5
0x180006be1  mov     [rsp+22F8h+cbData], r10d; cbData
0x180006be6  mov     [rsp+22F8h+lpData], r8; lpData
0x180006beb  lea     r9d, [rcx+6]; dwType
0x180006bef  xor     r8d, r8d; Reserved
0x180006bf2  mov     rdx, r13; lpValueName
0x180006bf5  mov     rcx, [r12]; hKey
0x180006bf9  call    cs:__imp_RegSetValueExW
0x180006bff  mov     esi, eax
0x180006c01  mov     rdi, [rsp+22F8h+var_2158]
0x180006c09  jmp     short loc_180006C10
0x180006c0b  mov     esi, 0Eh
0x180006c10  lea     rax, [rsp+22F8h+var_2150]
0x180006c18  cmp     rdi, rax
0x180006c1b  jz      short loc_180006C2A
0x180006c1d  lea     rcx, [rsp+22F8h+var_2158]
0x180006c25  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006c2a  mov     r15, [rsp+22F8h+var_22C0]
0x180006c2f  test    esi, esi
0x180006c31  jz      loc_180006EF5
0x180006c37  mov     ecx, esi; this
0x180006c39  call    ?hresult_from_win32@impl@winrt@@YAHI@Z; winrt::impl::hresult_from_win32(uint)
0x180006c3e  jmp     loc_180006A17
0x180006c43  mov     [rsp+22F8h+pulOut], ebx
0x180006c47  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180006c4c  xor     r8d, r8d; dwFlags
0x180006c4f  xor     edx, edx; lcid
0x180006c51  lea     rcx, [rsp+22F8h+String1]; strIn
0x180006c59  call    cs:__imp_VarUI4FromStr
0x180006c5f  test    eax, eax
0x180006c61  js      loc_180006A17
0x180006c67  mov     eax, [rsp+22F8h+pulOut]
0x180006c6b  mov     dword ptr [rsp+22F8h+Data], eax
0x180006c6f  mov     [rsp+22F8h+cbData], 4; cbData
0x180006c77  lea     rax, [rsp+22F8h+Data]
0x180006c7c  mov     r9d, 4; dwType
0x180006c82  mov     [rsp+22F8h+lpData], rax; lpData
0x180006c87  xor     r8d, r8d; Reserved
0x180006c8a  mov     rdx, r14; lpValueName
0x180006c8d  mov     rcx, [r12]; hKey
0x180006c91  call    cs:__imp_RegSetValueExW
0x180006c97  mov     esi, eax
0x180006c99  jmp     short loc_180006C2F
0x180006c9b  lea     rax, [rsp+22F8h+String1]
0x180006ca3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006ca7  mov     r14, rsi
0x180006caa  inc     r14
0x180006cad  cmp     [rax+r14*2], bx
0x180006cb2  jnz     short loc_180006CAA
0x180006cb4  mov     dword ptr [rsp+22F8h+Data], r14d
0x180006cb9  test    r14b, 1
0x180006cbd  jnz     loc_180006D77
0x180006cc3  mov     eax, r14d
0x180006cc6  cdq
0x180006cc7  sub     eax, edx
0x180006cc9  sar     eax, 1
0x180006ccb  movsxd  r12, eax
0x180006cce  mov     [rsp+22F8h+var_2268], rbx
0x180006cd6  mov     rdi, r12
0x180006cd9  mov     [rsp+22F8h+var_2280], r12
0x180006cde  test    eax, eax
0x180006ce0  jz      short loc_180006D17
0x180006ce2  xor     edx, edx
0x180006ce4  mov     rax, rsi
0x180006ce7  div     rdi
0x180006cea  cmp     rax, 1
0x180006cee  jb      loc_180006F38
0x180006cf4  cmp     rdi, 100h
0x180006cfb  jbe     short loc_180006D17
0x180006cfd  mov     rdx, rdi
0x180006d00  lea     rcx, [rsp+22F8h+var_2268]
0x180006d08  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006d0d  mov     rcx, [rsp+22F8h+var_2268]
0x180006d15  jmp     short loc_180006D27
0x180006d17  lea     rcx, [rsp+22F8h+var_2260]
0x180006d1f  mov     [rsp+22F8h+var_2268], rcx
0x180006d27  mov     rsi, [rsp+22F8h+var_2288]
0x180006d2c  jmp     short loc_180006D65
0x180006d2e  xor     ebx, ebx
0x180006d30  lea     r13d, [rbx+8]
0x180006d34  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180006d39  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180006d41  mov     rdi, [rsp+22F8h+var_2280]
0x180006d46  mov     rax, [rsp+22F8h+var_22A8]
0x180006d4b  mov     [rsp+22F8h+var_22C0], rax
0x180006d50  mov     rsi, [rsp+22F8h+var_2278]
0x180006d58  mov     rax, [rsp+22F8h+var_2298]
0x180006d5d  mov     [rsp+22F8h+lpValueName], rax
0x180006d62  mov     r12d, edi
0x180006d65  test    rcx, rcx
0x180006d68  jnz     short loc_180006D81
0x180006d6a  lea     rcx, [rsp+22F8h+var_2268]
0x180006d72  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006d77  mov     eax, 80004005h
0x180006d7c  jmp     loc_180006A17
0x180006d81  mov     r8, rdi; Size
0x180006d84  xor     edx, edx; Val
0x180006d86  call    memset_0
0x180006d8b  mov     r10d, ebx
0x180006d8e  test    r14d, r14d
0x180006d91  jle     loc_180006E6F
0x180006d97  mov     r15d, 30h ; '0'
0x180006d9d  mov     eax, r10d
0x180006da0  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180006da8  cmp     edx, 61h ; 'a'
0x180006dab  ja      short loc_180006E1A
0x180006dad  jz      loc_180006E3A
0x180006db3  cmp     edx, 38h ; '8'
0x180006db6  ja      short loc_180006DEC
0x180006db8  jz      short loc_180006DE4
0x180006dba  mov     ecx, edx
0x180006dbc  sub     ecx, r15d
0x180006dbf  jz      short loc_180006DE4
0x180006dc1  sub     ecx, 1
0x180006dc4  jz      short loc_180006DE4
0x180006dc6  sub     ecx, 1
0x180006dc9  jz      short loc_180006DE4
0x180006dcb  sub     ecx, 1
0x180006dce  jz      short loc_180006DE4
0x180006dd0  sub     ecx, 1
0x180006dd3  jz      short loc_180006DE4
0x180006dd5  sub     ecx, 1
0x180006dd8  jz      short loc_180006DE4
0x180006dda  sub     ecx, 1
0x180006ddd  jz      short loc_180006DE4
0x180006ddf  cmp     ecx, 1
0x180006de2  jnz     short loc_180006E35
0x180006de4  mov     r9d, edx
0x180006de7  sub     r9d, r15d
0x180006dea  jmp     short loc_180006E3E
0x180006dec  mov     r9d, edx
0x180006def  mov     ecx, edx
0x180006df1  sub     ecx, 39h ; '9'
0x180006df4  jz      short loc_180006DE4
0x180006df6  sub     ecx, r13d
0x180006df9  jz      short loc_180006E14
0x180006dfb  sub     ecx, 1
0x180006dfe  jz      short loc_180006E14
0x180006e00  sub     ecx, 1
0x180006e03  jz      short loc_180006E14
0x180006e05  sub     ecx, 1
0x180006e08  jz      short loc_180006E14
0x180006e0a  sub     ecx, 1
0x180006e0d  jz      short loc_180006E14
0x180006e0f  cmp     ecx, 1
0x180006e12  jnz     short loc_180006E35
0x180006e14  add     r9d, 0FFFFFFC9h
0x180006e18  jmp     short loc_180006E3E
  ... truncated ...
```
