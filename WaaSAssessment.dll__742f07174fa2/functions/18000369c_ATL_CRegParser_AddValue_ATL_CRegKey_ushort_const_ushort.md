# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000369c`
- end: `0x180003c70`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000589c`

## callees

- `0x18000369c`
- `0x180003c78`
- `0x180003ed8`
- `0x180004740`
- `0x180004ca4`
- `0x180004ef0`
- `0x18001972e`
- `0x180019760`
- `0x180019820`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003985`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003985`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003925`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800039bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003bbe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003925`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800039bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003bbe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000389c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800038b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003c40`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000389c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800038b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003c40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000372d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000372d`

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
0x18000369c  push    rbx
0x18000369e  push    rsi
0x18000369f  push    rdi
0x1800036a0  push    r12
0x1800036a2  push    r13
0x1800036a4  push    r14
0x1800036a6  push    r15
0x1800036a8  mov     eax, 22C0h
0x1800036ad  call    _alloca_probe
0x1800036b2  sub     rsp, rax
0x1800036b5  mov     rax, cs:__security_cookie
0x1800036bc  xor     rax, rsp
0x1800036bf  mov     [rsp+22F8h+var_48], rax
0x1800036c7  mov     r14, r8
0x1800036ca  mov     [rsp+22F8h+lpValueName], r8
0x1800036cf  mov     r12, rdx
0x1800036d2  mov     [rsp+22F8h+var_2288], rdx
0x1800036d7  mov     r15, rcx
0x1800036da  mov     [rsp+22F8h+var_22C0], rcx
0x1800036df  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800036e4  mov     [rsp+22F8h+var_22A8], rcx
0x1800036e9  mov     [rsp+22F8h+var_2278], rdx
0x1800036f1  mov     [rsp+22F8h+var_2298], r8
0x1800036f6  mov     [rsp+22F8h+var_2270], r9
0x1800036fe  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180003706  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000370b  xor     ebx, ebx
0x18000370d  test    eax, eax
0x18000370f  js      short loc_180003743
0x180003711  mov     edi, ebx
0x180003713  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000371a  movsxd  rsi, edi
0x18000371d  add     rsi, rsi
0x180003720  mov     rdx, [r13+rsi*8+0]; lpString2
0x180003725  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18000372d  call    cs:__imp_lstrcmpiW
0x180003733  test    eax, eax
0x180003735  jz      short loc_180003766
0x180003737  inc     edi
0x180003739  cmp     edi, 4
0x18000373c  jb      short loc_18000371A
0x18000373e  mov     eax, 80020009h
0x180003743  mov     rcx, [rsp+22F8h+var_48]
0x18000374b  xor     rcx, rsp; StackCookie
0x18000374e  call    __security_check_cookie
0x180003753  add     rsp, 22C0h
0x18000375a  pop     r15
0x18000375c  pop     r14
0x18000375e  pop     r13
0x180003760  pop     r12
0x180003762  pop     rdi
0x180003763  pop     rsi
0x180003764  pop     rbx
0x180003765  retn
0x180003766  movzx   edi, word ptr [r13+rsi*8+8]
0x18000376c  mov     esi, 13h
0x180003771  mov     rdx, [r15]
0x180003774  movzx   ecx, word ptr [rdx]
0x180003777  sub     ecx, 9
0x18000377a  jz      loc_180003C3D
0x180003780  sub     ecx, 1
0x180003783  jz      loc_180003C3D
0x180003789  sub     ecx, 3
0x18000378c  jz      loc_180003C3D
0x180003792  cmp     ecx, esi
0x180003794  jz      loc_180003C3D
0x18000379a  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800037a2  mov     rcx, r15; this
0x1800037a5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800037aa  test    eax, eax
0x1800037ac  js      short loc_180003743
0x1800037ae  mov     r13d, 8
0x1800037b4  cmp     di, r13w
0x1800037b8  jz      loc_180003BEE
0x1800037be  cmp     di, 11h
0x1800037c2  jz      loc_1800039C7
0x1800037c8  cmp     di, si
0x1800037cb  jz      loc_18000396F
0x1800037d1  mov     eax, 4008h
0x1800037d6  cmp     di, ax
0x1800037d9  jnz     loc_180003C21
0x1800037df  lea     rcx, [rsp+22F8h+String1]
0x1800037e7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800037eb  mov     rax, rsi
0x1800037ee  inc     rax
0x1800037f1  cmp     [rcx+rax*2], bx
0x1800037f5  jnz     short loc_1800037EE
0x1800037f7  add     eax, 2
0x1800037fa  mov     [rsp+22F8h+var_2158], rbx
0x180003802  test    eax, eax
0x180003804  jz      short loc_18000383F
0x180003806  movsxd  rcx, eax
0x180003809  xor     edx, edx
0x18000380b  mov     rax, rsi
0x18000380e  div     rcx
0x180003811  cmp     rax, 2
0x180003815  jb      loc_180003C4E
0x18000381b  lea     rdx, [rcx+rcx]
0x18000381f  cmp     rdx, 100h
0x180003826  jbe     short loc_18000383F
0x180003828  lea     rcx, [rsp+22F8h+var_2158]
0x180003830  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003835  mov     rdi, [rsp+22F8h+var_2158]
0x18000383d  jmp     short loc_18000384F
0x18000383f  lea     rdi, [rsp+22F8h+var_2150]
0x180003847  mov     [rsp+22F8h+var_2158], rdi
0x18000384f  mov     r13, [rsp+22F8h+lpValueName]
0x180003854  jmp     short loc_180003878
0x180003856  xor     ebx, ebx
0x180003858  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000385c  mov     rdi, [rsp+22F8h+var_2158]
0x180003864  mov     r12, qword ptr [rsp+22F8h+Data]
0x180003869  mov     rax, [rsp+22F8h+var_22A8]
0x18000386e  mov     [rsp+22F8h+var_22C0], rax
0x180003873  mov     r13, [rsp+22F8h+var_2298]
0x180003878  test    rdi, rdi
0x18000387b  jz      loc_180003937
0x180003881  lea     r14, [rsp+22F8h+String1]
0x180003889  cmp     [rsp+22F8h+String1], bx
0x180003891  jz      short loc_1800038D4
0x180003893  mov     r15d, 30h ; '0'
0x180003899  mov     rcx, r14; lpsz
0x18000389c  call    cs:__imp_CharNextW
0x1800038a2  movzx   ecx, word ptr [r14]
0x1800038a6  cmp     cx, 5Ch ; '\'
0x1800038aa  jnz     short loc_1800038C3
0x1800038ac  cmp     [rax], r15w
0x1800038b0  jnz     short loc_1800038C3
0x1800038b2  mov     [rdi], bx
0x1800038b5  mov     rcx, rax; lpsz
0x1800038b8  call    cs:__imp_CharNextW
0x1800038be  mov     r14, rax
0x1800038c1  jmp     short loc_1800038CA
0x1800038c3  mov     [rdi], cx
0x1800038c6  add     r14, 2
0x1800038ca  add     rdi, 2
0x1800038ce  cmp     [r14], bx
0x1800038d2  jnz     short loc_180003899
0x1800038d4  mov     dword ptr [rdi], 0
0x1800038da  mov     r8, [rsp+22F8h+var_2158]
0x1800038e2  test    r8, r8
0x1800038e5  jz      loc_180003C59
0x1800038eb  mov     r10d, ebx
0x1800038ee  mov     r9, r8
0x1800038f1  mov     rcx, rsi
0x1800038f4  inc     rcx
0x1800038f7  cmp     [r9+rcx*2], bx
0x1800038fc  jnz     short loc_1800038F4
0x1800038fe  inc     ecx
0x180003900  lea     r9, [r9+rcx*2]
0x180003904  lea     r10d, [r10+rcx*2]
0x180003908  cmp     ecx, 1
0x18000390b  jnz     short loc_1800038F1
0x18000390d  mov     [rsp+22F8h+cbData], r10d; cbData
0x180003912  mov     [rsp+22F8h+lpData], r8; lpData
0x180003917  lea     r9d, [rcx+6]; dwType
0x18000391b  xor     r8d, r8d; Reserved
0x18000391e  mov     rdx, r13; lpValueName
0x180003921  mov     rcx, [r12]; hKey
0x180003925  call    cs:__imp_RegSetValueExW
0x18000392b  mov     esi, eax
0x18000392d  mov     rdi, [rsp+22F8h+var_2158]
0x180003935  jmp     short loc_18000393C
0x180003937  mov     esi, 0Eh
0x18000393c  lea     rax, [rsp+22F8h+var_2150]
0x180003944  cmp     rdi, rax
0x180003947  jz      short loc_180003956
0x180003949  lea     rcx, [rsp+22F8h+var_2158]
0x180003951  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003956  mov     r15, [rsp+22F8h+var_22C0]
0x18000395b  test    esi, esi
0x18000395d  jz      loc_180003C21
0x180003963  mov     ecx, esi; unsigned int
0x180003965  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000396a  jmp     loc_180003743
0x18000396f  mov     [rsp+22F8h+pulOut], ebx
0x180003973  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180003978  xor     r8d, r8d; dwFlags
0x18000397b  xor     edx, edx; lcid
0x18000397d  lea     rcx, [rsp+22F8h+String1]; strIn
0x180003985  call    cs:__imp_VarUI4FromStr
0x18000398b  test    eax, eax
0x18000398d  js      loc_180003743
0x180003993  mov     eax, [rsp+22F8h+pulOut]
0x180003997  mov     dword ptr [rsp+22F8h+Data], eax
0x18000399b  mov     [rsp+22F8h+cbData], 4; cbData
0x1800039a3  lea     rax, [rsp+22F8h+Data]
0x1800039a8  mov     r9d, 4; dwType
0x1800039ae  mov     [rsp+22F8h+lpData], rax; lpData
0x1800039b3  xor     r8d, r8d; Reserved
0x1800039b6  mov     rdx, r14; lpValueName
0x1800039b9  mov     rcx, [r12]; hKey
0x1800039bd  call    cs:__imp_RegSetValueExW
0x1800039c3  mov     esi, eax
0x1800039c5  jmp     short loc_18000395B
0x1800039c7  lea     rax, [rsp+22F8h+String1]
0x1800039cf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800039d3  mov     r14, rsi
0x1800039d6  inc     r14
0x1800039d9  cmp     [rax+r14*2], bx
0x1800039de  jnz     short loc_1800039D6
0x1800039e0  mov     dword ptr [rsp+22F8h+Data], r14d
0x1800039e5  test    r14b, 1
0x1800039e9  jnz     loc_180003AA3
0x1800039ef  mov     eax, r14d
0x1800039f2  cdq
0x1800039f3  sub     eax, edx
0x1800039f5  sar     eax, 1
0x1800039f7  movsxd  r12, eax
0x1800039fa  mov     [rsp+22F8h+var_2268], rbx
0x180003a02  mov     rdi, r12
0x180003a05  mov     [rsp+22F8h+var_2280], r12
0x180003a0a  test    eax, eax
0x180003a0c  jz      short loc_180003A43
0x180003a0e  xor     edx, edx
0x180003a10  mov     rax, rsi
0x180003a13  div     rdi
0x180003a16  cmp     rax, 1
0x180003a1a  jb      loc_180003C64
0x180003a20  cmp     rdi, 100h
0x180003a27  jbe     short loc_180003A43
0x180003a29  mov     rdx, rdi
0x180003a2c  lea     rcx, [rsp+22F8h+var_2268]
0x180003a34  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003a39  mov     rcx, [rsp+22F8h+var_2268]
0x180003a41  jmp     short loc_180003A53
0x180003a43  lea     rcx, [rsp+22F8h+var_2260]
0x180003a4b  mov     [rsp+22F8h+var_2268], rcx
0x180003a53  mov     rsi, [rsp+22F8h+var_2288]
0x180003a58  jmp     short loc_180003A91
0x180003a5a  xor     ebx, ebx
0x180003a5c  lea     r13d, [rbx+8]
0x180003a60  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180003a65  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180003a6d  mov     rdi, [rsp+22F8h+var_2280]
0x180003a72  mov     rax, [rsp+22F8h+var_22A8]
0x180003a77  mov     [rsp+22F8h+var_22C0], rax
0x180003a7c  mov     rsi, [rsp+22F8h+var_2278]
0x180003a84  mov     rax, [rsp+22F8h+var_2298]
0x180003a89  mov     [rsp+22F8h+lpValueName], rax
0x180003a8e  mov     r12d, edi
0x180003a91  test    rcx, rcx
0x180003a94  jnz     short loc_180003AAD
0x180003a96  lea     rcx, [rsp+22F8h+var_2268]
0x180003a9e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003aa3  mov     eax, 80004005h
0x180003aa8  jmp     loc_180003743
0x180003aad  mov     r8, rdi; Size
0x180003ab0  xor     edx, edx; Val
0x180003ab2  call    memset_0
0x180003ab7  mov     r10d, ebx
0x180003aba  test    r14d, r14d
0x180003abd  jle     loc_180003B9B
0x180003ac3  mov     r15d, 30h ; '0'
0x180003ac9  mov     eax, r10d
0x180003acc  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180003ad4  cmp     edx, 61h ; 'a'
0x180003ad7  ja      short loc_180003B46
0x180003ad9  jz      loc_180003B66
0x180003adf  cmp     edx, 38h ; '8'
0x180003ae2  ja      short loc_180003B18
0x180003ae4  jz      short loc_180003B10
0x180003ae6  mov     ecx, edx
0x180003ae8  sub     ecx, r15d
0x180003aeb  jz      short loc_180003B10
0x180003aed  sub     ecx, 1
0x180003af0  jz      short loc_180003B10
0x180003af2  sub     ecx, 1
0x180003af5  jz      short loc_180003B10
0x180003af7  sub     ecx, 1
0x180003afa  jz      short loc_180003B10
0x180003afc  sub     ecx, 1
0x180003aff  jz      short loc_180003B10
0x180003b01  sub     ecx, 1
0x180003b04  jz      short loc_180003B10
0x180003b06  sub     ecx, 1
0x180003b09  jz      short loc_180003B10
0x180003b0b  cmp     ecx, 1
0x180003b0e  jnz     short loc_180003B61
0x180003b10  mov     r9d, edx
0x180003b13  sub     r9d, r15d
0x180003b16  jmp     short loc_180003B6A
0x180003b18  mov     r9d, edx
0x180003b1b  mov     ecx, edx
0x180003b1d  sub     ecx, 39h ; '9'
0x180003b20  jz      short loc_180003B10
0x180003b22  sub     ecx, r13d
0x180003b25  jz      short loc_180003B40
0x180003b27  sub     ecx, 1
0x180003b2a  jz      short loc_180003B40
0x180003b2c  sub     ecx, 1
0x180003b2f  jz      short loc_180003B40
0x180003b31  sub     ecx, 1
0x180003b34  jz      short loc_180003B40
0x180003b36  sub     ecx, 1
0x180003b39  jz      short loc_180003B40
0x180003b3b  cmp     ecx, 1
0x180003b3e  jnz     short loc_180003B61
0x180003b40  add     r9d, 0FFFFFFC9h
0x180003b44  jmp     short loc_180003B6A
  ... truncated ...
```
