# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180027658`
- end: `0x180027c38`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1504`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002ba78`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x18001047c`
- `0x180027658`
- `0x180027d5c`
- `0x180027f58`
- `0x180029b44`
- `0x18002b05c`
- `0x1801adab0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800276f5`
- `KERNEL32!lstrcmpiW` at `0x1800276f5`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002794d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002794d`
- `ADVAPI32!RegSetValueExW` at `0x1800278ed`
- `ADVAPI32!RegSetValueExW` at `0x180027985`
- `ADVAPI32!RegSetValueExW` at `0x180027b86`
- `ADVAPI32!RegSetValueExW` at `0x1800278ed`
- `ADVAPI32!RegSetValueExW` at `0x180027985`
- `ADVAPI32!RegSetValueExW` at `0x180027b86`
- `USER32!CharNextW` at `0x180027864`
- `USER32!CharNextW` at `0x180027880`
- `USER32!CharNextW` at `0x180027c08`
- `USER32!CharNextW` at `0x180027864`
- `USER32!CharNextW` at `0x180027880`
- `USER32!CharNextW` at `0x180027c08`

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
  DWORD cbData; // [rsp+28h] [rbp-22E0h]
  ULONG pulOut; // [rsp+30h] [rbp-22D8h] BYREF
  ATL::CRegParser *v36; // [rsp+38h] [rbp-22D0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22C8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22C0h]
  ATL::CRegParser *v39; // [rsp+50h] [rbp-22B8h]
  const WCHAR *v40; // [rsp+60h] [rbp-22A8h]
  struct ATL::CRegKey *v41; // [rsp+70h] [rbp-2298h]
  size_t v42; // [rsp+78h] [rbp-2290h]
  struct ATL::CRegKey *v43; // [rsp+80h] [rbp-2288h]
  unsigned __int16 *v44; // [rsp+88h] [rbp-2280h]
  __int64 v45; // [rsp+90h] [rbp-2278h]
  BYTE *v46; // [rsp+A0h] [rbp-2268h] BYREF
  _BYTE v47[264]; // [rsp+A8h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1B0h] [rbp-2158h] BYREF
  _BYTE v49[264]; // [rsp+1B8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2C0h] [rbp-2048h] BYREF

  v45 = -2;
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
              v13 = v49;
              lpData = v49;
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
          if ( v13 != v49 )
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
        v46 = 0;
        v26 = (int)v24 / 2;
        v42 = v26;
        if ( !((int)v24 / 2) )
          goto LABEL_56;
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v26) )
          ATL::AtlThrowImpl(-2147024809);
        if ( v26 > 0x100 )
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v46, v26);
          v27 = v46;
        }
        else
        {
LABEL_56:
          v27 = v47;
          v46 = v47;
        }
        v28 = (HKEY *)v41;
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v24) = *(_DWORD *)Data;
        v27 = v46;
        v26 = v42;
        v36 = v39;
        v28 = (HKEY *)v43;
        lpValueName = v40;
        v25 = v42;
      }
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v46);
        return -2147467259;
      }
      memset_0(v27, 0, v26);
      v29 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_88:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, v46, v25);
        if ( v46 != v47 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v46);
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
        v46[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
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
0x180027658  push    rbx
0x18002765a  push    rsi
0x18002765b  push    rdi
0x18002765c  push    r12
0x18002765e  push    r13
0x180027660  push    r14
0x180027662  push    r15
0x180027664  mov     eax, 22D0h
0x180027669  call    _alloca_probe
0x18002766e  sub     rsp, rax
0x180027671  mov     [rsp+2308h+var_2278], 0FFFFFFFFFFFFFFFEh
0x18002767d  mov     rax, cs:__security_cookie
0x180027684  xor     rax, rsp
0x180027687  mov     [rsp+2308h+var_48], rax
0x18002768f  mov     r14, r8
0x180027692  mov     [rsp+2308h+lpValueName], r8
0x180027697  mov     r12, rdx
0x18002769a  mov     [rsp+2308h+var_2298], rdx
0x18002769f  mov     r15, rcx
0x1800276a2  mov     [rsp+2308h+var_22D0], rcx
0x1800276a7  mov     qword ptr [rsp+2308h+Data], rdx
0x1800276ac  mov     [rsp+2308h+var_22B8], rcx
0x1800276b1  mov     [rsp+2308h+var_2288], rdx
0x1800276b9  mov     [rsp+2308h+var_22A8], r8
0x1800276be  mov     [rsp+2308h+var_2280], r9
0x1800276c6  lea     rdx, [rsp+2308h+String1]; unsigned __int16 *
0x1800276ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800276d3  xor     ebx, ebx
0x1800276d5  test    eax, eax
0x1800276d7  js      short loc_18002770B
0x1800276d9  mov     edi, ebx
0x1800276db  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800276e2  movsxd  rsi, edi
0x1800276e5  add     rsi, rsi
0x1800276e8  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800276ed  lea     rcx, [rsp+2308h+String1]; lpString1
0x1800276f5  call    cs:__imp_lstrcmpiW
0x1800276fb  test    eax, eax
0x1800276fd  jz      short loc_18002772E
0x1800276ff  inc     edi
0x180027701  cmp     edi, 4
0x180027704  jb      short loc_1800276E2
0x180027706  mov     eax, 80020009h
0x18002770b  mov     rcx, [rsp+2308h+var_48]
0x180027713  xor     rcx, rsp; StackCookie
0x180027716  call    __security_check_cookie
0x18002771b  add     rsp, 22D0h
0x180027722  pop     r15
0x180027724  pop     r14
0x180027726  pop     r13
0x180027728  pop     r12
0x18002772a  pop     rdi
0x18002772b  pop     rsi
0x18002772c  pop     rbx
0x18002772d  retn
0x18002772e  movzx   edi, word ptr [r13+rsi*8+8]
0x180027734  mov     esi, 13h
0x180027739  mov     rdx, [r15]
0x18002773c  movzx   ecx, word ptr [rdx]
0x18002773f  sub     ecx, 9
0x180027742  jz      loc_180027C05
0x180027748  sub     ecx, 1
0x18002774b  jz      loc_180027C05
0x180027751  sub     ecx, 3
0x180027754  jz      loc_180027C05
0x18002775a  cmp     ecx, esi
0x18002775c  jz      loc_180027C05
0x180027762  lea     rdx, [rsp+2308h+String1]; unsigned __int16 *
0x18002776a  mov     rcx, r15; this
0x18002776d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180027772  test    eax, eax
0x180027774  js      short loc_18002770B
0x180027776  mov     r13d, 8
0x18002777c  cmp     di, r13w
0x180027780  jz      loc_180027BB6
0x180027786  cmp     di, 11h
0x18002778a  jz      loc_18002798F
0x180027790  cmp     di, si
0x180027793  jz      loc_180027937
0x180027799  mov     eax, 4008h
0x18002779e  cmp     di, ax
0x1800277a1  jnz     loc_180027BE9
0x1800277a7  lea     rcx, [rsp+2308h+String1]
0x1800277af  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800277b3  mov     rax, rsi
0x1800277b6  inc     rax
0x1800277b9  cmp     [rcx+rax*2], bx
0x1800277bd  jnz     short loc_1800277B6
0x1800277bf  add     eax, 2
0x1800277c2  mov     [rsp+2308h+var_2158], rbx
0x1800277ca  test    eax, eax
0x1800277cc  jz      short loc_180027807
0x1800277ce  movsxd  rcx, eax
0x1800277d1  xor     edx, edx
0x1800277d3  mov     rax, rsi
0x1800277d6  div     rcx
0x1800277d9  cmp     rax, 2
0x1800277dd  jb      loc_180027C16
0x1800277e3  lea     rdx, [rcx+rcx]
0x1800277e7  cmp     rdx, 100h
0x1800277ee  jbe     short loc_180027807
0x1800277f0  lea     rcx, [rsp+2308h+var_2158]
0x1800277f8  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800277fd  mov     rdi, [rsp+2308h+var_2158]
0x180027805  jmp     short loc_180027817
0x180027807  lea     rdi, [rsp+2308h+var_2150]
0x18002780f  mov     [rsp+2308h+var_2158], rdi
0x180027817  mov     r13, [rsp+2308h+lpValueName]
0x18002781c  jmp     short loc_180027840
0x18002781e  xor     ebx, ebx
0x180027820  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027824  mov     rdi, [rsp+2308h+var_2158]
0x18002782c  mov     r12, qword ptr [rsp+2308h+Data]
0x180027831  mov     rax, [rsp+2308h+var_22B8]
0x180027836  mov     [rsp+2308h+var_22D0], rax
0x18002783b  mov     r13, [rsp+2308h+var_22A8]
0x180027840  test    rdi, rdi
0x180027843  jz      loc_1800278FF
0x180027849  lea     r14, [rsp+2308h+String1]
0x180027851  cmp     [rsp+2308h+String1], bx
0x180027859  jz      short loc_18002789C
0x18002785b  mov     r15d, 30h ; '0'
0x180027861  mov     rcx, r14; lpsz
0x180027864  call    cs:__imp_CharNextW
0x18002786a  movzx   ecx, word ptr [r14]
0x18002786e  cmp     cx, 5Ch ; '\'
0x180027872  jnz     short loc_18002788B
0x180027874  cmp     [rax], r15w
0x180027878  jnz     short loc_18002788B
0x18002787a  mov     [rdi], bx
0x18002787d  mov     rcx, rax; lpsz
0x180027880  call    cs:__imp_CharNextW
0x180027886  mov     r14, rax
0x180027889  jmp     short loc_180027892
0x18002788b  mov     [rdi], cx
0x18002788e  add     r14, 2
0x180027892  add     rdi, 2
0x180027896  cmp     [r14], bx
0x18002789a  jnz     short loc_180027861
0x18002789c  mov     dword ptr [rdi], 0
0x1800278a2  mov     r8, [rsp+2308h+var_2158]
0x1800278aa  test    r8, r8
0x1800278ad  jz      loc_180027C21
0x1800278b3  mov     r10d, ebx
0x1800278b6  mov     r9, r8
0x1800278b9  mov     rcx, rsi
0x1800278bc  inc     rcx
0x1800278bf  cmp     [r9+rcx*2], bx
0x1800278c4  jnz     short loc_1800278BC
0x1800278c6  inc     ecx
0x1800278c8  lea     r9, [r9+rcx*2]
0x1800278cc  lea     r10d, [r10+rcx*2]
0x1800278d0  cmp     ecx, 1
0x1800278d3  jnz     short loc_1800278B9
0x1800278d5  mov     [rsp+2308h+cbData], r10d; cbData
0x1800278da  mov     [rsp+2308h+lpData], r8; lpData
0x1800278df  lea     r9d, [rcx+6]; dwType
0x1800278e3  xor     r8d, r8d; Reserved
0x1800278e6  mov     rdx, r13; lpValueName
0x1800278e9  mov     rcx, [r12]; hKey
0x1800278ed  call    cs:__imp_RegSetValueExW
0x1800278f3  mov     esi, eax
0x1800278f5  mov     rdi, [rsp+2308h+var_2158]
0x1800278fd  jmp     short loc_180027904
0x1800278ff  mov     esi, 0Eh
0x180027904  lea     rax, [rsp+2308h+var_2150]
0x18002790c  cmp     rdi, rax
0x18002790f  jz      short loc_18002791E
0x180027911  lea     rcx, [rsp+2308h+var_2158]
0x180027919  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18002791e  mov     r15, [rsp+2308h+var_22D0]
0x180027923  test    esi, esi
0x180027925  jz      loc_180027BE9
0x18002792b  mov     ecx, esi; unsigned int
0x18002792d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180027932  jmp     loc_18002770B
0x180027937  mov     [rsp+2308h+pulOut], ebx
0x18002793b  lea     r9, [rsp+2308h+pulOut]; pulOut
0x180027940  xor     r8d, r8d; dwFlags
0x180027943  xor     edx, edx; lcid
0x180027945  lea     rcx, [rsp+2308h+String1]; strIn
0x18002794d  call    cs:__imp_VarUI4FromStr
0x180027953  test    eax, eax
0x180027955  js      loc_18002770B
0x18002795b  mov     eax, [rsp+2308h+pulOut]
0x18002795f  mov     dword ptr [rsp+2308h+Data], eax
0x180027963  mov     [rsp+2308h+cbData], 4; cbData
0x18002796b  lea     rax, [rsp+2308h+Data]
0x180027970  mov     r9d, 4; dwType
0x180027976  mov     [rsp+2308h+lpData], rax; lpData
0x18002797b  xor     r8d, r8d; Reserved
0x18002797e  mov     rdx, r14; lpValueName
0x180027981  mov     rcx, [r12]; hKey
0x180027985  call    cs:__imp_RegSetValueExW
0x18002798b  mov     esi, eax
0x18002798d  jmp     short loc_180027923
0x18002798f  lea     rax, [rsp+2308h+String1]
0x180027997  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002799b  mov     r14, rsi
0x18002799e  inc     r14
0x1800279a1  cmp     [rax+r14*2], bx
0x1800279a6  jnz     short loc_18002799E
0x1800279a8  mov     dword ptr [rsp+2308h+Data], r14d
0x1800279ad  test    r14b, 1
0x1800279b1  jnz     loc_180027A6B
0x1800279b7  mov     eax, r14d
0x1800279ba  cdq
0x1800279bb  sub     eax, edx
0x1800279bd  sar     eax, 1
0x1800279bf  movsxd  r12, eax
0x1800279c2  mov     [rsp+2308h+var_2268], rbx
0x1800279ca  mov     rdi, r12
0x1800279cd  mov     [rsp+2308h+var_2290], r12
0x1800279d2  test    eax, eax
0x1800279d4  jz      short loc_180027A0B
0x1800279d6  xor     edx, edx
0x1800279d8  mov     rax, rsi
0x1800279db  div     rdi
0x1800279de  cmp     rax, 1
0x1800279e2  jb      loc_180027C2C
0x1800279e8  cmp     rdi, 100h
0x1800279ef  jbe     short loc_180027A0B
0x1800279f1  mov     rdx, rdi
0x1800279f4  lea     rcx, [rsp+2308h+var_2268]
0x1800279fc  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180027a01  mov     rcx, [rsp+2308h+var_2268]
0x180027a09  jmp     short loc_180027A1B
0x180027a0b  lea     rcx, [rsp+2308h+var_2260]
0x180027a13  mov     [rsp+2308h+var_2268], rcx
0x180027a1b  mov     rsi, [rsp+2308h+var_2298]
0x180027a20  jmp     short loc_180027A59
0x180027a22  xor     ebx, ebx
0x180027a24  lea     r13d, [rbx+8]
0x180027a28  mov     r14d, dword ptr [rsp+2308h+Data]
0x180027a2d  mov     rcx, [rsp+2308h+var_2268]; void *
0x180027a35  mov     rdi, [rsp+2308h+var_2290]
0x180027a3a  mov     rax, [rsp+2308h+var_22B8]
0x180027a3f  mov     [rsp+2308h+var_22D0], rax
0x180027a44  mov     rsi, [rsp+2308h+var_2288]
0x180027a4c  mov     rax, [rsp+2308h+var_22A8]
0x180027a51  mov     [rsp+2308h+lpValueName], rax
0x180027a56  mov     r12d, edi
0x180027a59  test    rcx, rcx
0x180027a5c  jnz     short loc_180027A75
0x180027a5e  lea     rcx, [rsp+2308h+var_2268]
0x180027a66  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180027a6b  mov     eax, 80004005h
0x180027a70  jmp     loc_18002770B
0x180027a75  mov     r8, rdi; Size
0x180027a78  xor     edx, edx; Val
0x180027a7a  call    memset_0
0x180027a7f  mov     r10d, ebx
0x180027a82  test    r14d, r14d
0x180027a85  jle     loc_180027B63
0x180027a8b  mov     r15d, 30h ; '0'
0x180027a91  mov     eax, r10d
0x180027a94  movzx   edx, [rsp+rax*2+2308h+String1]
0x180027a9c  cmp     edx, 61h ; 'a'
0x180027a9f  ja      short loc_180027B0E
0x180027aa1  jz      loc_180027B2E
0x180027aa7  cmp     edx, 38h ; '8'
0x180027aaa  ja      short loc_180027AE0
0x180027aac  jz      short loc_180027AD8
0x180027aae  mov     ecx, edx
0x180027ab0  sub     ecx, r15d
0x180027ab3  jz      short loc_180027AD8
0x180027ab5  sub     ecx, 1
0x180027ab8  jz      short loc_180027AD8
0x180027aba  sub     ecx, 1
0x180027abd  jz      short loc_180027AD8
0x180027abf  sub     ecx, 1
0x180027ac2  jz      short loc_180027AD8
0x180027ac4  sub     ecx, 1
0x180027ac7  jz      short loc_180027AD8
0x180027ac9  sub     ecx, 1
0x180027acc  jz      short loc_180027AD8
0x180027ace  sub     ecx, 1
0x180027ad1  jz      short loc_180027AD8
0x180027ad3  cmp     ecx, 1
0x180027ad6  jnz     short loc_180027B29
0x180027ad8  mov     r9d, edx
0x180027adb  sub     r9d, r15d
0x180027ade  jmp     short loc_180027B32
0x180027ae0  mov     r9d, edx
0x180027ae3  mov     ecx, edx
0x180027ae5  sub     ecx, 39h ; '9'
0x180027ae8  jz      short loc_180027AD8
0x180027aea  sub     ecx, r13d
0x180027aed  jz      short loc_180027B08
0x180027aef  sub     ecx, 1
0x180027af2  jz      short loc_180027B08
0x180027af4  sub     ecx, 1
0x180027af7  jz      short loc_180027B08
0x180027af9  sub     ecx, 1
0x180027afc  jz      short loc_180027B08
0x180027afe  sub     ecx, 1
0x180027b01  jz      short loc_180027B08
0x180027b03  cmp     ecx, 1
0x180027b06  jnz     short loc_180027B29
0x180027b08  add     r9d, 0FFFFFFC9h
  ... truncated ...
```
