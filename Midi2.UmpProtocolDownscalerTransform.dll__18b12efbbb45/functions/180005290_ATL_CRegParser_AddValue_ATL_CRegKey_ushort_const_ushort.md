# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180005290`
- end: `0x180005864`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007dec`

## callees

- `0x180002e70`
- `0x180003a20`
- `0x180005290`
- `0x18000586c`
- `0x1800059c0`
- `0x1800059d8`
- `0x1800061c8`
- `0x1800072bc`
- `0x180012080`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180005579`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180005579`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005519`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800055b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800057b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005519`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800055b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800057b2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005490`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800054ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005834`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005490`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800054ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005834`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005321`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005321`

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
0x180005290  push    rbx
0x180005292  push    rsi
0x180005293  push    rdi
0x180005294  push    r12
0x180005296  push    r13
0x180005298  push    r14
0x18000529a  push    r15
0x18000529c  mov     eax, 22C0h
0x1800052a1  call    _alloca_probe
0x1800052a6  sub     rsp, rax
0x1800052a9  mov     rax, cs:__security_cookie
0x1800052b0  xor     rax, rsp
0x1800052b3  mov     [rsp+22F8h+var_48], rax
0x1800052bb  mov     r14, r8
0x1800052be  mov     [rsp+22F8h+lpValueName], r8
0x1800052c3  mov     r12, rdx
0x1800052c6  mov     [rsp+22F8h+var_2288], rdx
0x1800052cb  mov     r15, rcx
0x1800052ce  mov     [rsp+22F8h+var_22C0], rcx
0x1800052d3  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800052d8  mov     [rsp+22F8h+var_22A8], rcx
0x1800052dd  mov     [rsp+22F8h+var_2278], rdx
0x1800052e5  mov     [rsp+22F8h+var_2298], r8
0x1800052ea  mov     [rsp+22F8h+var_2270], r9
0x1800052f2  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800052fa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800052ff  xor     ebx, ebx
0x180005301  test    eax, eax
0x180005303  js      short loc_180005337
0x180005305  mov     edi, ebx
0x180005307  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000530e  movsxd  rsi, edi
0x180005311  add     rsi, rsi
0x180005314  mov     rdx, [r13+rsi*8+0]; lpString2
0x180005319  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180005321  call    cs:__imp_lstrcmpiW
0x180005327  test    eax, eax
0x180005329  jz      short loc_18000535A
0x18000532b  inc     edi
0x18000532d  cmp     edi, 4
0x180005330  jb      short loc_18000530E
0x180005332  mov     eax, 80020009h
0x180005337  mov     rcx, [rsp+22F8h+var_48]
0x18000533f  xor     rcx, rsp; StackCookie
0x180005342  call    __security_check_cookie
0x180005347  add     rsp, 22C0h
0x18000534e  pop     r15
0x180005350  pop     r14
0x180005352  pop     r13
0x180005354  pop     r12
0x180005356  pop     rdi
0x180005357  pop     rsi
0x180005358  pop     rbx
0x180005359  retn
0x18000535a  movzx   edi, word ptr [r13+rsi*8+8]
0x180005360  mov     esi, 13h
0x180005365  mov     rdx, [r15]
0x180005368  movzx   ecx, word ptr [rdx]
0x18000536b  sub     ecx, 9
0x18000536e  jz      loc_180005831
0x180005374  sub     ecx, 1
0x180005377  jz      loc_180005831
0x18000537d  sub     ecx, 3
0x180005380  jz      loc_180005831
0x180005386  cmp     ecx, esi
0x180005388  jz      loc_180005831
0x18000538e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180005396  mov     rcx, r15; this
0x180005399  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000539e  test    eax, eax
0x1800053a0  js      short loc_180005337
0x1800053a2  mov     r13d, 8
0x1800053a8  cmp     di, r13w
0x1800053ac  jz      loc_1800057E2
0x1800053b2  cmp     di, 11h
0x1800053b6  jz      loc_1800055BB
0x1800053bc  cmp     di, si
0x1800053bf  jz      loc_180005563
0x1800053c5  mov     eax, 4008h
0x1800053ca  cmp     di, ax
0x1800053cd  jnz     loc_180005815
0x1800053d3  lea     rcx, [rsp+22F8h+String1]
0x1800053db  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800053df  mov     rax, rsi
0x1800053e2  inc     rax
0x1800053e5  cmp     [rcx+rax*2], bx
0x1800053e9  jnz     short loc_1800053E2
0x1800053eb  add     eax, 2
0x1800053ee  mov     [rsp+22F8h+var_2158], rbx
0x1800053f6  test    eax, eax
0x1800053f8  jz      short loc_180005433
0x1800053fa  movsxd  rcx, eax
0x1800053fd  xor     edx, edx
0x1800053ff  mov     rax, rsi
0x180005402  div     rcx
0x180005405  cmp     rax, 2
0x180005409  jb      loc_180005842
0x18000540f  lea     rdx, [rcx+rcx]
0x180005413  cmp     rdx, 100h
0x18000541a  jbe     short loc_180005433
0x18000541c  lea     rcx, [rsp+22F8h+var_2158]
0x180005424  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005429  mov     rdi, [rsp+22F8h+var_2158]
0x180005431  jmp     short loc_180005443
0x180005433  lea     rdi, [rsp+22F8h+var_2150]
0x18000543b  mov     [rsp+22F8h+var_2158], rdi
0x180005443  mov     r13, [rsp+22F8h+lpValueName]
0x180005448  jmp     short loc_18000546C
0x18000544a  xor     ebx, ebx
0x18000544c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005450  mov     rdi, [rsp+22F8h+var_2158]
0x180005458  mov     r12, qword ptr [rsp+22F8h+Data]
0x18000545d  mov     rax, [rsp+22F8h+var_22A8]
0x180005462  mov     [rsp+22F8h+var_22C0], rax
0x180005467  mov     r13, [rsp+22F8h+var_2298]
0x18000546c  test    rdi, rdi
0x18000546f  jz      loc_18000552B
0x180005475  lea     r14, [rsp+22F8h+String1]
0x18000547d  cmp     [rsp+22F8h+String1], bx
0x180005485  jz      short loc_1800054C8
0x180005487  mov     r15d, 30h ; '0'
0x18000548d  mov     rcx, r14; lpsz
0x180005490  call    cs:__imp_CharNextW
0x180005496  movzx   ecx, word ptr [r14]
0x18000549a  cmp     cx, 5Ch ; '\'
0x18000549e  jnz     short loc_1800054B7
0x1800054a0  cmp     [rax], r15w
0x1800054a4  jnz     short loc_1800054B7
0x1800054a6  mov     [rdi], bx
0x1800054a9  mov     rcx, rax; lpsz
0x1800054ac  call    cs:__imp_CharNextW
0x1800054b2  mov     r14, rax
0x1800054b5  jmp     short loc_1800054BE
0x1800054b7  mov     [rdi], cx
0x1800054ba  add     r14, 2
0x1800054be  add     rdi, 2
0x1800054c2  cmp     [r14], bx
0x1800054c6  jnz     short loc_18000548D
0x1800054c8  mov     dword ptr [rdi], 0
0x1800054ce  mov     r8, [rsp+22F8h+var_2158]
0x1800054d6  test    r8, r8
0x1800054d9  jz      loc_18000584D
0x1800054df  mov     r10d, ebx
0x1800054e2  mov     r9, r8
0x1800054e5  mov     rcx, rsi
0x1800054e8  inc     rcx
0x1800054eb  cmp     [r9+rcx*2], bx
0x1800054f0  jnz     short loc_1800054E8
0x1800054f2  inc     ecx
0x1800054f4  lea     r9, [r9+rcx*2]
0x1800054f8  lea     r10d, [r10+rcx*2]
0x1800054fc  cmp     ecx, 1
0x1800054ff  jnz     short loc_1800054E5
0x180005501  mov     [rsp+22F8h+cbData], r10d; cbData
0x180005506  mov     [rsp+22F8h+lpData], r8; lpData
0x18000550b  lea     r9d, [rcx+6]; dwType
0x18000550f  xor     r8d, r8d; Reserved
0x180005512  mov     rdx, r13; lpValueName
0x180005515  mov     rcx, [r12]; hKey
0x180005519  call    cs:__imp_RegSetValueExW
0x18000551f  mov     esi, eax
0x180005521  mov     rdi, [rsp+22F8h+var_2158]
0x180005529  jmp     short loc_180005530
0x18000552b  mov     esi, 0Eh
0x180005530  lea     rax, [rsp+22F8h+var_2150]
0x180005538  cmp     rdi, rax
0x18000553b  jz      short loc_18000554A
0x18000553d  lea     rcx, [rsp+22F8h+var_2158]
0x180005545  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000554a  mov     r15, [rsp+22F8h+var_22C0]
0x18000554f  test    esi, esi
0x180005551  jz      loc_180005815
0x180005557  mov     ecx, esi; this
0x180005559  call    ?hresult_from_win32@impl@winrt@@YAHI@Z; winrt::impl::hresult_from_win32(uint)
0x18000555e  jmp     loc_180005337
0x180005563  mov     [rsp+22F8h+pulOut], ebx
0x180005567  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x18000556c  xor     r8d, r8d; dwFlags
0x18000556f  xor     edx, edx; lcid
0x180005571  lea     rcx, [rsp+22F8h+String1]; strIn
0x180005579  call    cs:__imp_VarUI4FromStr
0x18000557f  test    eax, eax
0x180005581  js      loc_180005337
0x180005587  mov     eax, [rsp+22F8h+pulOut]
0x18000558b  mov     dword ptr [rsp+22F8h+Data], eax
0x18000558f  mov     [rsp+22F8h+cbData], 4; cbData
0x180005597  lea     rax, [rsp+22F8h+Data]
0x18000559c  mov     r9d, 4; dwType
0x1800055a2  mov     [rsp+22F8h+lpData], rax; lpData
0x1800055a7  xor     r8d, r8d; Reserved
0x1800055aa  mov     rdx, r14; lpValueName
0x1800055ad  mov     rcx, [r12]; hKey
0x1800055b1  call    cs:__imp_RegSetValueExW
0x1800055b7  mov     esi, eax
0x1800055b9  jmp     short loc_18000554F
0x1800055bb  lea     rax, [rsp+22F8h+String1]
0x1800055c3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800055c7  mov     r14, rsi
0x1800055ca  inc     r14
0x1800055cd  cmp     [rax+r14*2], bx
0x1800055d2  jnz     short loc_1800055CA
0x1800055d4  mov     dword ptr [rsp+22F8h+Data], r14d
0x1800055d9  test    r14b, 1
0x1800055dd  jnz     loc_180005697
0x1800055e3  mov     eax, r14d
0x1800055e6  cdq
0x1800055e7  sub     eax, edx
0x1800055e9  sar     eax, 1
0x1800055eb  movsxd  r12, eax
0x1800055ee  mov     [rsp+22F8h+var_2268], rbx
0x1800055f6  mov     rdi, r12
0x1800055f9  mov     [rsp+22F8h+var_2280], r12
0x1800055fe  test    eax, eax
0x180005600  jz      short loc_180005637
0x180005602  xor     edx, edx
0x180005604  mov     rax, rsi
0x180005607  div     rdi
0x18000560a  cmp     rax, 1
0x18000560e  jb      loc_180005858
0x180005614  cmp     rdi, 100h
0x18000561b  jbe     short loc_180005637
0x18000561d  mov     rdx, rdi
0x180005620  lea     rcx, [rsp+22F8h+var_2268]
0x180005628  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000562d  mov     rcx, [rsp+22F8h+var_2268]
0x180005635  jmp     short loc_180005647
0x180005637  lea     rcx, [rsp+22F8h+var_2260]
0x18000563f  mov     [rsp+22F8h+var_2268], rcx
0x180005647  mov     rsi, [rsp+22F8h+var_2288]
0x18000564c  jmp     short loc_180005685
0x18000564e  xor     ebx, ebx
0x180005650  lea     r13d, [rbx+8]
0x180005654  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180005659  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180005661  mov     rdi, [rsp+22F8h+var_2280]
0x180005666  mov     rax, [rsp+22F8h+var_22A8]
0x18000566b  mov     [rsp+22F8h+var_22C0], rax
0x180005670  mov     rsi, [rsp+22F8h+var_2278]
0x180005678  mov     rax, [rsp+22F8h+var_2298]
0x18000567d  mov     [rsp+22F8h+lpValueName], rax
0x180005682  mov     r12d, edi
0x180005685  test    rcx, rcx
0x180005688  jnz     short loc_1800056A1
0x18000568a  lea     rcx, [rsp+22F8h+var_2268]
0x180005692  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005697  mov     eax, 80004005h
0x18000569c  jmp     loc_180005337
0x1800056a1  mov     r8, rdi; Size
0x1800056a4  xor     edx, edx; Val
0x1800056a6  call    memset_0
0x1800056ab  mov     r10d, ebx
0x1800056ae  test    r14d, r14d
0x1800056b1  jle     loc_18000578F
0x1800056b7  mov     r15d, 30h ; '0'
0x1800056bd  mov     eax, r10d
0x1800056c0  movzx   edx, [rsp+rax*2+22F8h+String1]
0x1800056c8  cmp     edx, 61h ; 'a'
0x1800056cb  ja      short loc_18000573A
0x1800056cd  jz      loc_18000575A
0x1800056d3  cmp     edx, 38h ; '8'
0x1800056d6  ja      short loc_18000570C
0x1800056d8  jz      short loc_180005704
0x1800056da  mov     ecx, edx
0x1800056dc  sub     ecx, r15d
0x1800056df  jz      short loc_180005704
0x1800056e1  sub     ecx, 1
0x1800056e4  jz      short loc_180005704
0x1800056e6  sub     ecx, 1
0x1800056e9  jz      short loc_180005704
0x1800056eb  sub     ecx, 1
0x1800056ee  jz      short loc_180005704
0x1800056f0  sub     ecx, 1
0x1800056f3  jz      short loc_180005704
0x1800056f5  sub     ecx, 1
0x1800056f8  jz      short loc_180005704
0x1800056fa  sub     ecx, 1
0x1800056fd  jz      short loc_180005704
0x1800056ff  cmp     ecx, 1
0x180005702  jnz     short loc_180005755
0x180005704  mov     r9d, edx
0x180005707  sub     r9d, r15d
0x18000570a  jmp     short loc_18000575E
0x18000570c  mov     r9d, edx
0x18000570f  mov     ecx, edx
0x180005711  sub     ecx, 39h ; '9'
0x180005714  jz      short loc_180005704
0x180005716  sub     ecx, r13d
0x180005719  jz      short loc_180005734
0x18000571b  sub     ecx, 1
0x18000571e  jz      short loc_180005734
0x180005720  sub     ecx, 1
0x180005723  jz      short loc_180005734
0x180005725  sub     ecx, 1
0x180005728  jz      short loc_180005734
0x18000572a  sub     ecx, 1
0x18000572d  jz      short loc_180005734
0x18000572f  cmp     ecx, 1
0x180005732  jnz     short loc_180005755
0x180005734  add     r9d, 0FFFFFFC9h
0x180005738  jmp     short loc_18000575E
  ... truncated ...
```
