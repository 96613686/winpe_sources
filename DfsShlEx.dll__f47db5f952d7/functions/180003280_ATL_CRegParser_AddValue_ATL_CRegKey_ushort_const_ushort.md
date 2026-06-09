# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180003280`
- end: `0x180003854`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180005764`

## callees

- `0x180003280`
- `0x18000385c`
- `0x180003abc`
- `0x180004328`
- `0x180004a50`
- `0x180004c80`
- `0x18000a9a6`
- `0x18000a9d0`
- `0x18000aa90`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180003311`
- `KERNEL32!lstrcmpiW` at `0x180003311`
- `USER32!CharNextW` at `0x180003480`
- `USER32!CharNextW` at `0x18000349c`
- `USER32!CharNextW` at `0x180003824`
- `USER32!CharNextW` at `0x180003480`
- `USER32!CharNextW` at `0x18000349c`
- `USER32!CharNextW` at `0x180003824`
- `ADVAPI32!RegSetValueExW` at `0x180003509`
- `ADVAPI32!RegSetValueExW` at `0x1800035a1`
- `ADVAPI32!RegSetValueExW` at `0x1800037a2`
- `ADVAPI32!RegSetValueExW` at `0x180003509`
- `ADVAPI32!RegSetValueExW` at `0x1800035a1`
- `ADVAPI32!RegSetValueExW` at `0x1800037a2`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003569`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003569`

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
0x180003280  push    rbx
0x180003282  push    rsi
0x180003283  push    rdi
0x180003284  push    r12
0x180003286  push    r13
0x180003288  push    r14
0x18000328a  push    r15
0x18000328c  mov     eax, 22C0h
0x180003291  call    _alloca_probe
0x180003296  sub     rsp, rax
0x180003299  mov     rax, cs:__security_cookie
0x1800032a0  xor     rax, rsp
0x1800032a3  mov     [rsp+22F8h+var_48], rax
0x1800032ab  mov     r14, r8
0x1800032ae  mov     [rsp+22F8h+lpValueName], r8
0x1800032b3  mov     r12, rdx
0x1800032b6  mov     [rsp+22F8h+var_2288], rdx
0x1800032bb  mov     r15, rcx
0x1800032be  mov     [rsp+22F8h+var_22C0], rcx
0x1800032c3  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800032c8  mov     [rsp+22F8h+var_22A8], rcx
0x1800032cd  mov     [rsp+22F8h+var_2278], rdx
0x1800032d5  mov     [rsp+22F8h+var_2298], r8
0x1800032da  mov     [rsp+22F8h+var_2270], r9
0x1800032e2  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800032ea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800032ef  xor     ebx, ebx
0x1800032f1  test    eax, eax
0x1800032f3  js      short loc_180003327
0x1800032f5  mov     edi, ebx
0x1800032f7  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800032fe  movsxd  rsi, edi
0x180003301  add     rsi, rsi
0x180003304  mov     rdx, [r13+rsi*8+0]; lpString2
0x180003309  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180003311  call    cs:__imp_lstrcmpiW
0x180003317  test    eax, eax
0x180003319  jz      short loc_18000334A
0x18000331b  inc     edi
0x18000331d  cmp     edi, 4
0x180003320  jb      short loc_1800032FE
0x180003322  mov     eax, 80020009h
0x180003327  mov     rcx, [rsp+22F8h+var_48]
0x18000332f  xor     rcx, rsp; StackCookie
0x180003332  call    __security_check_cookie
0x180003337  add     rsp, 22C0h
0x18000333e  pop     r15
0x180003340  pop     r14
0x180003342  pop     r13
0x180003344  pop     r12
0x180003346  pop     rdi
0x180003347  pop     rsi
0x180003348  pop     rbx
0x180003349  retn
0x18000334a  movzx   edi, word ptr [r13+rsi*8+8]
0x180003350  mov     esi, 13h
0x180003355  mov     rdx, [r15]
0x180003358  movzx   ecx, word ptr [rdx]
0x18000335b  sub     ecx, 9
0x18000335e  jz      loc_180003821
0x180003364  sub     ecx, 1
0x180003367  jz      loc_180003821
0x18000336d  sub     ecx, 3
0x180003370  jz      loc_180003821
0x180003376  cmp     ecx, esi
0x180003378  jz      loc_180003821
0x18000337e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180003386  mov     rcx, r15; this
0x180003389  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000338e  test    eax, eax
0x180003390  js      short loc_180003327
0x180003392  mov     r13d, 8
0x180003398  cmp     di, r13w
0x18000339c  jz      loc_1800037D2
0x1800033a2  cmp     di, 11h
0x1800033a6  jz      loc_1800035AB
0x1800033ac  cmp     di, si
0x1800033af  jz      loc_180003553
0x1800033b5  mov     eax, 4008h
0x1800033ba  cmp     di, ax
0x1800033bd  jnz     loc_180003805
0x1800033c3  lea     rcx, [rsp+22F8h+String1]
0x1800033cb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800033cf  mov     rax, rsi
0x1800033d2  inc     rax
0x1800033d5  cmp     [rcx+rax*2], bx
0x1800033d9  jnz     short loc_1800033D2
0x1800033db  add     eax, 2
0x1800033de  mov     [rsp+22F8h+var_2158], rbx
0x1800033e6  test    eax, eax
0x1800033e8  jz      short loc_180003423
0x1800033ea  movsxd  rcx, eax
0x1800033ed  xor     edx, edx
0x1800033ef  mov     rax, rsi
0x1800033f2  div     rcx
0x1800033f5  cmp     rax, 2
0x1800033f9  jb      loc_180003832
0x1800033ff  lea     rdx, [rcx+rcx]
0x180003403  cmp     rdx, 100h
0x18000340a  jbe     short loc_180003423
0x18000340c  lea     rcx, [rsp+22F8h+var_2158]
0x180003414  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003419  mov     rdi, [rsp+22F8h+var_2158]
0x180003421  jmp     short loc_180003433
0x180003423  lea     rdi, [rsp+22F8h+var_2150]
0x18000342b  mov     [rsp+22F8h+var_2158], rdi
0x180003433  mov     r13, [rsp+22F8h+lpValueName]
0x180003438  jmp     short loc_18000345C
0x18000343a  xor     ebx, ebx
0x18000343c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003440  mov     rdi, [rsp+22F8h+var_2158]
0x180003448  mov     r12, qword ptr [rsp+22F8h+Data]
0x18000344d  mov     rax, [rsp+22F8h+var_22A8]
0x180003452  mov     [rsp+22F8h+var_22C0], rax
0x180003457  mov     r13, [rsp+22F8h+var_2298]
0x18000345c  test    rdi, rdi
0x18000345f  jz      loc_18000351B
0x180003465  lea     r14, [rsp+22F8h+String1]
0x18000346d  cmp     [rsp+22F8h+String1], bx
0x180003475  jz      short loc_1800034B8
0x180003477  mov     r15d, 30h ; '0'
0x18000347d  mov     rcx, r14; lpsz
0x180003480  call    cs:__imp_CharNextW
0x180003486  movzx   ecx, word ptr [r14]
0x18000348a  cmp     cx, 5Ch ; '\'
0x18000348e  jnz     short loc_1800034A7
0x180003490  cmp     [rax], r15w
0x180003494  jnz     short loc_1800034A7
0x180003496  mov     [rdi], bx
0x180003499  mov     rcx, rax; lpsz
0x18000349c  call    cs:__imp_CharNextW
0x1800034a2  mov     r14, rax
0x1800034a5  jmp     short loc_1800034AE
0x1800034a7  mov     [rdi], cx
0x1800034aa  add     r14, 2
0x1800034ae  add     rdi, 2
0x1800034b2  cmp     [r14], bx
0x1800034b6  jnz     short loc_18000347D
0x1800034b8  mov     dword ptr [rdi], 0
0x1800034be  mov     r8, [rsp+22F8h+var_2158]
0x1800034c6  test    r8, r8
0x1800034c9  jz      loc_18000383D
0x1800034cf  mov     r10d, ebx
0x1800034d2  mov     r9, r8
0x1800034d5  mov     rcx, rsi
0x1800034d8  inc     rcx
0x1800034db  cmp     [r9+rcx*2], bx
0x1800034e0  jnz     short loc_1800034D8
0x1800034e2  inc     ecx
0x1800034e4  lea     r9, [r9+rcx*2]
0x1800034e8  lea     r10d, [r10+rcx*2]
0x1800034ec  cmp     ecx, 1
0x1800034ef  jnz     short loc_1800034D5
0x1800034f1  mov     [rsp+22F8h+cbData], r10d; cbData
0x1800034f6  mov     [rsp+22F8h+lpData], r8; lpData
0x1800034fb  lea     r9d, [rcx+6]; dwType
0x1800034ff  xor     r8d, r8d; Reserved
0x180003502  mov     rdx, r13; lpValueName
0x180003505  mov     rcx, [r12]; hKey
0x180003509  call    cs:__imp_RegSetValueExW
0x18000350f  mov     esi, eax
0x180003511  mov     rdi, [rsp+22F8h+var_2158]
0x180003519  jmp     short loc_180003520
0x18000351b  mov     esi, 0Eh
0x180003520  lea     rax, [rsp+22F8h+var_2150]
0x180003528  cmp     rdi, rax
0x18000352b  jz      short loc_18000353A
0x18000352d  lea     rcx, [rsp+22F8h+var_2158]
0x180003535  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000353a  mov     r15, [rsp+22F8h+var_22C0]
0x18000353f  test    esi, esi
0x180003541  jz      loc_180003805
0x180003547  mov     ecx, esi; unsigned int
0x180003549  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000354e  jmp     loc_180003327
0x180003553  mov     [rsp+22F8h+pulOut], ebx
0x180003557  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x18000355c  xor     r8d, r8d; dwFlags
0x18000355f  xor     edx, edx; lcid
0x180003561  lea     rcx, [rsp+22F8h+String1]; strIn
0x180003569  call    cs:__imp_VarUI4FromStr
0x18000356f  test    eax, eax
0x180003571  js      loc_180003327
0x180003577  mov     eax, [rsp+22F8h+pulOut]
0x18000357b  mov     dword ptr [rsp+22F8h+Data], eax
0x18000357f  mov     [rsp+22F8h+cbData], 4; cbData
0x180003587  lea     rax, [rsp+22F8h+Data]
0x18000358c  mov     r9d, 4; dwType
0x180003592  mov     [rsp+22F8h+lpData], rax; lpData
0x180003597  xor     r8d, r8d; Reserved
0x18000359a  mov     rdx, r14; lpValueName
0x18000359d  mov     rcx, [r12]; hKey
0x1800035a1  call    cs:__imp_RegSetValueExW
0x1800035a7  mov     esi, eax
0x1800035a9  jmp     short loc_18000353F
0x1800035ab  lea     rax, [rsp+22F8h+String1]
0x1800035b3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800035b7  mov     r14, rsi
0x1800035ba  inc     r14
0x1800035bd  cmp     [rax+r14*2], bx
0x1800035c2  jnz     short loc_1800035BA
0x1800035c4  mov     dword ptr [rsp+22F8h+Data], r14d
0x1800035c9  test    r14b, 1
0x1800035cd  jnz     loc_180003687
0x1800035d3  mov     eax, r14d
0x1800035d6  cdq
0x1800035d7  sub     eax, edx
0x1800035d9  sar     eax, 1
0x1800035db  movsxd  r12, eax
0x1800035de  mov     [rsp+22F8h+var_2268], rbx
0x1800035e6  mov     rdi, r12
0x1800035e9  mov     [rsp+22F8h+var_2280], r12
0x1800035ee  test    eax, eax
0x1800035f0  jz      short loc_180003627
0x1800035f2  xor     edx, edx
0x1800035f4  mov     rax, rsi
0x1800035f7  div     rdi
0x1800035fa  cmp     rax, 1
0x1800035fe  jb      loc_180003848
0x180003604  cmp     rdi, 100h
0x18000360b  jbe     short loc_180003627
0x18000360d  mov     rdx, rdi
0x180003610  lea     rcx, [rsp+22F8h+var_2268]
0x180003618  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000361d  mov     rcx, [rsp+22F8h+var_2268]
0x180003625  jmp     short loc_180003637
0x180003627  lea     rcx, [rsp+22F8h+var_2260]
0x18000362f  mov     [rsp+22F8h+var_2268], rcx
0x180003637  mov     rsi, [rsp+22F8h+var_2288]
0x18000363c  jmp     short loc_180003675
0x18000363e  xor     ebx, ebx
0x180003640  lea     r13d, [rbx+8]
0x180003644  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180003649  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180003651  mov     rdi, [rsp+22F8h+var_2280]
0x180003656  mov     rax, [rsp+22F8h+var_22A8]
0x18000365b  mov     [rsp+22F8h+var_22C0], rax
0x180003660  mov     rsi, [rsp+22F8h+var_2278]
0x180003668  mov     rax, [rsp+22F8h+var_2298]
0x18000366d  mov     [rsp+22F8h+lpValueName], rax
0x180003672  mov     r12d, edi
0x180003675  test    rcx, rcx
0x180003678  jnz     short loc_180003691
0x18000367a  lea     rcx, [rsp+22F8h+var_2268]
0x180003682  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003687  mov     eax, 80004005h
0x18000368c  jmp     loc_180003327
0x180003691  mov     r8, rdi; Size
0x180003694  xor     edx, edx; Val
0x180003696  call    memset_0
0x18000369b  mov     r10d, ebx
0x18000369e  test    r14d, r14d
0x1800036a1  jle     loc_18000377F
0x1800036a7  mov     r15d, 30h ; '0'
0x1800036ad  mov     eax, r10d
0x1800036b0  movzx   edx, [rsp+rax*2+22F8h+String1]
0x1800036b8  cmp     edx, 61h ; 'a'
0x1800036bb  ja      short loc_18000372A
0x1800036bd  jz      loc_18000374A
0x1800036c3  cmp     edx, 38h ; '8'
0x1800036c6  ja      short loc_1800036FC
0x1800036c8  jz      short loc_1800036F4
0x1800036ca  mov     ecx, edx
0x1800036cc  sub     ecx, r15d
0x1800036cf  jz      short loc_1800036F4
0x1800036d1  sub     ecx, 1
0x1800036d4  jz      short loc_1800036F4
0x1800036d6  sub     ecx, 1
0x1800036d9  jz      short loc_1800036F4
0x1800036db  sub     ecx, 1
0x1800036de  jz      short loc_1800036F4
0x1800036e0  sub     ecx, 1
0x1800036e3  jz      short loc_1800036F4
0x1800036e5  sub     ecx, 1
0x1800036e8  jz      short loc_1800036F4
0x1800036ea  sub     ecx, 1
0x1800036ed  jz      short loc_1800036F4
0x1800036ef  cmp     ecx, 1
0x1800036f2  jnz     short loc_180003745
0x1800036f4  mov     r9d, edx
0x1800036f7  sub     r9d, r15d
0x1800036fa  jmp     short loc_18000374E
0x1800036fc  mov     r9d, edx
0x1800036ff  mov     ecx, edx
0x180003701  sub     ecx, 39h ; '9'
0x180003704  jz      short loc_1800036F4
0x180003706  sub     ecx, r13d
0x180003709  jz      short loc_180003724
0x18000370b  sub     ecx, 1
0x18000370e  jz      short loc_180003724
0x180003710  sub     ecx, 1
0x180003713  jz      short loc_180003724
0x180003715  sub     ecx, 1
0x180003718  jz      short loc_180003724
0x18000371a  sub     ecx, 1
0x18000371d  jz      short loc_180003724
0x18000371f  cmp     ecx, 1
0x180003722  jnz     short loc_180003745
0x180003724  add     r9d, 0FFFFFFC9h
0x180003728  jmp     short loc_18000374E
  ... truncated ...
```
