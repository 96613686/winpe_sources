# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180006df0`
- end: `0x1800073c4`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009cc4`

## callees

- `0x180004410`
- `0x18000526c`
- `0x180006df0`
- `0x1800073cc`
- `0x180007520`
- `0x180007538`
- `0x180007dec`
- `0x180008f08`
- `0x18003e3f0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800070d9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800070d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007079`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007111`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007312`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007079`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007111`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007312`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006ff0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000700c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007394`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006ff0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000700c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007394`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e81`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e81`

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
0x180006df0  push    rbx
0x180006df2  push    rsi
0x180006df3  push    rdi
0x180006df4  push    r12
0x180006df6  push    r13
0x180006df8  push    r14
0x180006dfa  push    r15
0x180006dfc  mov     eax, 22C0h
0x180006e01  call    _alloca_probe
0x180006e06  sub     rsp, rax
0x180006e09  mov     rax, cs:__security_cookie
0x180006e10  xor     rax, rsp
0x180006e13  mov     [rsp+22F8h+var_48], rax
0x180006e1b  mov     r14, r8
0x180006e1e  mov     [rsp+22F8h+lpValueName], r8
0x180006e23  mov     r12, rdx
0x180006e26  mov     [rsp+22F8h+var_2288], rdx
0x180006e2b  mov     r15, rcx
0x180006e2e  mov     [rsp+22F8h+var_22C0], rcx
0x180006e33  mov     qword ptr [rsp+22F8h+Data], rdx
0x180006e38  mov     [rsp+22F8h+var_22A8], rcx
0x180006e3d  mov     [rsp+22F8h+var_2278], rdx
0x180006e45  mov     [rsp+22F8h+var_2298], r8
0x180006e4a  mov     [rsp+22F8h+var_2270], r9
0x180006e52  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180006e5a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006e5f  xor     ebx, ebx
0x180006e61  test    eax, eax
0x180006e63  js      short loc_180006E97
0x180006e65  mov     edi, ebx
0x180006e67  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180006e6e  movsxd  rsi, edi
0x180006e71  add     rsi, rsi
0x180006e74  mov     rdx, [r13+rsi*8+0]; lpString2
0x180006e79  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180006e81  call    cs:__imp_lstrcmpiW
0x180006e87  test    eax, eax
0x180006e89  jz      short loc_180006EBA
0x180006e8b  inc     edi
0x180006e8d  cmp     edi, 4
0x180006e90  jb      short loc_180006E6E
0x180006e92  mov     eax, 80020009h
0x180006e97  mov     rcx, [rsp+22F8h+var_48]
0x180006e9f  xor     rcx, rsp; StackCookie
0x180006ea2  call    __security_check_cookie
0x180006ea7  add     rsp, 22C0h
0x180006eae  pop     r15
0x180006eb0  pop     r14
0x180006eb2  pop     r13
0x180006eb4  pop     r12
0x180006eb6  pop     rdi
0x180006eb7  pop     rsi
0x180006eb8  pop     rbx
0x180006eb9  retn
0x180006eba  movzx   edi, word ptr [r13+rsi*8+8]
0x180006ec0  mov     esi, 13h
0x180006ec5  mov     rdx, [r15]
0x180006ec8  movzx   ecx, word ptr [rdx]
0x180006ecb  sub     ecx, 9
0x180006ece  jz      loc_180007391
0x180006ed4  sub     ecx, 1
0x180006ed7  jz      loc_180007391
0x180006edd  sub     ecx, 3
0x180006ee0  jz      loc_180007391
0x180006ee6  cmp     ecx, esi
0x180006ee8  jz      loc_180007391
0x180006eee  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180006ef6  mov     rcx, r15; this
0x180006ef9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006efe  test    eax, eax
0x180006f00  js      short loc_180006E97
0x180006f02  mov     r13d, 8
0x180006f08  cmp     di, r13w
0x180006f0c  jz      loc_180007342
0x180006f12  cmp     di, 11h
0x180006f16  jz      loc_18000711B
0x180006f1c  cmp     di, si
0x180006f1f  jz      loc_1800070C3
0x180006f25  mov     eax, 4008h
0x180006f2a  cmp     di, ax
0x180006f2d  jnz     loc_180007375
0x180006f33  lea     rcx, [rsp+22F8h+String1]
0x180006f3b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006f3f  mov     rax, rsi
0x180006f42  inc     rax
0x180006f45  cmp     [rcx+rax*2], bx
0x180006f49  jnz     short loc_180006F42
0x180006f4b  add     eax, 2
0x180006f4e  mov     [rsp+22F8h+var_2158], rbx
0x180006f56  test    eax, eax
0x180006f58  jz      short loc_180006F93
0x180006f5a  movsxd  rcx, eax
0x180006f5d  xor     edx, edx
0x180006f5f  mov     rax, rsi
0x180006f62  div     rcx
0x180006f65  cmp     rax, 2
0x180006f69  jb      loc_1800073A2
0x180006f6f  lea     rdx, [rcx+rcx]
0x180006f73  cmp     rdx, 100h
0x180006f7a  jbe     short loc_180006F93
0x180006f7c  lea     rcx, [rsp+22F8h+var_2158]
0x180006f84  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006f89  mov     rdi, [rsp+22F8h+var_2158]
0x180006f91  jmp     short loc_180006FA3
0x180006f93  lea     rdi, [rsp+22F8h+var_2150]
0x180006f9b  mov     [rsp+22F8h+var_2158], rdi
0x180006fa3  mov     r13, [rsp+22F8h+lpValueName]
0x180006fa8  jmp     short loc_180006FCC
0x180006faa  xor     ebx, ebx
0x180006fac  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006fb0  mov     rdi, [rsp+22F8h+var_2158]
0x180006fb8  mov     r12, qword ptr [rsp+22F8h+Data]
0x180006fbd  mov     rax, [rsp+22F8h+var_22A8]
0x180006fc2  mov     [rsp+22F8h+var_22C0], rax
0x180006fc7  mov     r13, [rsp+22F8h+var_2298]
0x180006fcc  test    rdi, rdi
0x180006fcf  jz      loc_18000708B
0x180006fd5  lea     r14, [rsp+22F8h+String1]
0x180006fdd  cmp     [rsp+22F8h+String1], bx
0x180006fe5  jz      short loc_180007028
0x180006fe7  mov     r15d, 30h ; '0'
0x180006fed  mov     rcx, r14; lpsz
0x180006ff0  call    cs:__imp_CharNextW
0x180006ff6  movzx   ecx, word ptr [r14]
0x180006ffa  cmp     cx, 5Ch ; '\'
0x180006ffe  jnz     short loc_180007017
0x180007000  cmp     [rax], r15w
0x180007004  jnz     short loc_180007017
0x180007006  mov     [rdi], bx
0x180007009  mov     rcx, rax; lpsz
0x18000700c  call    cs:__imp_CharNextW
0x180007012  mov     r14, rax
0x180007015  jmp     short loc_18000701E
0x180007017  mov     [rdi], cx
0x18000701a  add     r14, 2
0x18000701e  add     rdi, 2
0x180007022  cmp     [r14], bx
0x180007026  jnz     short loc_180006FED
0x180007028  mov     dword ptr [rdi], 0
0x18000702e  mov     r8, [rsp+22F8h+var_2158]
0x180007036  test    r8, r8
0x180007039  jz      loc_1800073AD
0x18000703f  mov     r10d, ebx
0x180007042  mov     r9, r8
0x180007045  mov     rcx, rsi
0x180007048  inc     rcx
0x18000704b  cmp     [r9+rcx*2], bx
0x180007050  jnz     short loc_180007048
0x180007052  inc     ecx
0x180007054  lea     r9, [r9+rcx*2]
0x180007058  lea     r10d, [r10+rcx*2]
0x18000705c  cmp     ecx, 1
0x18000705f  jnz     short loc_180007045
0x180007061  mov     [rsp+22F8h+cbData], r10d; cbData
0x180007066  mov     [rsp+22F8h+lpData], r8; lpData
0x18000706b  lea     r9d, [rcx+6]; dwType
0x18000706f  xor     r8d, r8d; Reserved
0x180007072  mov     rdx, r13; lpValueName
0x180007075  mov     rcx, [r12]; hKey
0x180007079  call    cs:__imp_RegSetValueExW
0x18000707f  mov     esi, eax
0x180007081  mov     rdi, [rsp+22F8h+var_2158]
0x180007089  jmp     short loc_180007090
0x18000708b  mov     esi, 0Eh
0x180007090  lea     rax, [rsp+22F8h+var_2150]
0x180007098  cmp     rdi, rax
0x18000709b  jz      short loc_1800070AA
0x18000709d  lea     rcx, [rsp+22F8h+var_2158]
0x1800070a5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800070aa  mov     r15, [rsp+22F8h+var_22C0]
0x1800070af  test    esi, esi
0x1800070b1  jz      loc_180007375
0x1800070b7  mov     ecx, esi; this
0x1800070b9  call    ?hresult_from_win32@impl@winrt@@YAHI@Z; winrt::impl::hresult_from_win32(uint)
0x1800070be  jmp     loc_180006E97
0x1800070c3  mov     [rsp+22F8h+pulOut], ebx
0x1800070c7  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x1800070cc  xor     r8d, r8d; dwFlags
0x1800070cf  xor     edx, edx; lcid
0x1800070d1  lea     rcx, [rsp+22F8h+String1]; strIn
0x1800070d9  call    cs:__imp_VarUI4FromStr
0x1800070df  test    eax, eax
0x1800070e1  js      loc_180006E97
0x1800070e7  mov     eax, [rsp+22F8h+pulOut]
0x1800070eb  mov     dword ptr [rsp+22F8h+Data], eax
0x1800070ef  mov     [rsp+22F8h+cbData], 4; cbData
0x1800070f7  lea     rax, [rsp+22F8h+Data]
0x1800070fc  mov     r9d, 4; dwType
0x180007102  mov     [rsp+22F8h+lpData], rax; lpData
0x180007107  xor     r8d, r8d; Reserved
0x18000710a  mov     rdx, r14; lpValueName
0x18000710d  mov     rcx, [r12]; hKey
0x180007111  call    cs:__imp_RegSetValueExW
0x180007117  mov     esi, eax
0x180007119  jmp     short loc_1800070AF
0x18000711b  lea     rax, [rsp+22F8h+String1]
0x180007123  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007127  mov     r14, rsi
0x18000712a  inc     r14
0x18000712d  cmp     [rax+r14*2], bx
0x180007132  jnz     short loc_18000712A
0x180007134  mov     dword ptr [rsp+22F8h+Data], r14d
0x180007139  test    r14b, 1
0x18000713d  jnz     loc_1800071F7
0x180007143  mov     eax, r14d
0x180007146  cdq
0x180007147  sub     eax, edx
0x180007149  sar     eax, 1
0x18000714b  movsxd  r12, eax
0x18000714e  mov     [rsp+22F8h+var_2268], rbx
0x180007156  mov     rdi, r12
0x180007159  mov     [rsp+22F8h+var_2280], r12
0x18000715e  test    eax, eax
0x180007160  jz      short loc_180007197
0x180007162  xor     edx, edx
0x180007164  mov     rax, rsi
0x180007167  div     rdi
0x18000716a  cmp     rax, 1
0x18000716e  jb      loc_1800073B8
0x180007174  cmp     rdi, 100h
0x18000717b  jbe     short loc_180007197
0x18000717d  mov     rdx, rdi
0x180007180  lea     rcx, [rsp+22F8h+var_2268]
0x180007188  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000718d  mov     rcx, [rsp+22F8h+var_2268]
0x180007195  jmp     short loc_1800071A7
0x180007197  lea     rcx, [rsp+22F8h+var_2260]
0x18000719f  mov     [rsp+22F8h+var_2268], rcx
0x1800071a7  mov     rsi, [rsp+22F8h+var_2288]
0x1800071ac  jmp     short loc_1800071E5
0x1800071ae  xor     ebx, ebx
0x1800071b0  lea     r13d, [rbx+8]
0x1800071b4  mov     r14d, dword ptr [rsp+22F8h+Data]
0x1800071b9  mov     rcx, [rsp+22F8h+var_2268]; void *
0x1800071c1  mov     rdi, [rsp+22F8h+var_2280]
0x1800071c6  mov     rax, [rsp+22F8h+var_22A8]
0x1800071cb  mov     [rsp+22F8h+var_22C0], rax
0x1800071d0  mov     rsi, [rsp+22F8h+var_2278]
0x1800071d8  mov     rax, [rsp+22F8h+var_2298]
0x1800071dd  mov     [rsp+22F8h+lpValueName], rax
0x1800071e2  mov     r12d, edi
0x1800071e5  test    rcx, rcx
0x1800071e8  jnz     short loc_180007201
0x1800071ea  lea     rcx, [rsp+22F8h+var_2268]
0x1800071f2  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800071f7  mov     eax, 80004005h
0x1800071fc  jmp     loc_180006E97
0x180007201  mov     r8, rdi; Size
0x180007204  xor     edx, edx; Val
0x180007206  call    memset_0
0x18000720b  mov     r10d, ebx
0x18000720e  test    r14d, r14d
0x180007211  jle     loc_1800072EF
0x180007217  mov     r15d, 30h ; '0'
0x18000721d  mov     eax, r10d
0x180007220  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180007228  cmp     edx, 61h ; 'a'
0x18000722b  ja      short loc_18000729A
0x18000722d  jz      loc_1800072BA
0x180007233  cmp     edx, 38h ; '8'
0x180007236  ja      short loc_18000726C
0x180007238  jz      short loc_180007264
0x18000723a  mov     ecx, edx
0x18000723c  sub     ecx, r15d
0x18000723f  jz      short loc_180007264
0x180007241  sub     ecx, 1
0x180007244  jz      short loc_180007264
0x180007246  sub     ecx, 1
0x180007249  jz      short loc_180007264
0x18000724b  sub     ecx, 1
0x18000724e  jz      short loc_180007264
0x180007250  sub     ecx, 1
0x180007253  jz      short loc_180007264
0x180007255  sub     ecx, 1
0x180007258  jz      short loc_180007264
0x18000725a  sub     ecx, 1
0x18000725d  jz      short loc_180007264
0x18000725f  cmp     ecx, 1
0x180007262  jnz     short loc_1800072B5
0x180007264  mov     r9d, edx
0x180007267  sub     r9d, r15d
0x18000726a  jmp     short loc_1800072BE
0x18000726c  mov     r9d, edx
0x18000726f  mov     ecx, edx
0x180007271  sub     ecx, 39h ; '9'
0x180007274  jz      short loc_180007264
0x180007276  sub     ecx, r13d
0x180007279  jz      short loc_180007294
0x18000727b  sub     ecx, 1
0x18000727e  jz      short loc_180007294
0x180007280  sub     ecx, 1
0x180007283  jz      short loc_180007294
0x180007285  sub     ecx, 1
0x180007288  jz      short loc_180007294
0x18000728a  sub     ecx, 1
0x18000728d  jz      short loc_180007294
0x18000728f  cmp     ecx, 1
0x180007292  jnz     short loc_1800072B5
0x180007294  add     r9d, 0FFFFFFC9h
0x180007298  jmp     short loc_1800072BE
  ... truncated ...
```
