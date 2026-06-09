# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180003f3c`
- end: `0x180004510`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000784c`

## callees

- `0x180003f3c`
- `0x180004518`
- `0x18000466c`
- `0x180004684`
- `0x1800050fc`
- `0x180006dbc`
- `0x18000fbf2`
- `0x18000fc30`
- `0x18000fcf0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180003fcd`
- `KERNEL32!lstrcmpiW` at `0x180003fcd`
- `USER32!CharNextW` at `0x18000413c`
- `USER32!CharNextW` at `0x180004158`
- `USER32!CharNextW` at `0x1800044e0`
- `USER32!CharNextW` at `0x18000413c`
- `USER32!CharNextW` at `0x180004158`
- `USER32!CharNextW` at `0x1800044e0`
- `ADVAPI32!RegSetValueExW` at `0x1800041c5`
- `ADVAPI32!RegSetValueExW` at `0x18000425d`
- `ADVAPI32!RegSetValueExW` at `0x18000445e`
- `ADVAPI32!RegSetValueExW` at `0x1800041c5`
- `ADVAPI32!RegSetValueExW` at `0x18000425d`
- `ADVAPI32!RegSetValueExW` at `0x18000445e`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004225`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004225`

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
0x180003f3c  push    rbx
0x180003f3e  push    rsi
0x180003f3f  push    rdi
0x180003f40  push    r12
0x180003f42  push    r13
0x180003f44  push    r14
0x180003f46  push    r15
0x180003f48  mov     eax, 22C0h
0x180003f4d  call    _alloca_probe
0x180003f52  sub     rsp, rax
0x180003f55  mov     rax, cs:__security_cookie
0x180003f5c  xor     rax, rsp
0x180003f5f  mov     [rsp+22F8h+var_48], rax
0x180003f67  mov     r14, r8
0x180003f6a  mov     [rsp+22F8h+lpValueName], r8
0x180003f6f  mov     r12, rdx
0x180003f72  mov     [rsp+22F8h+var_2288], rdx
0x180003f77  mov     r15, rcx
0x180003f7a  mov     [rsp+22F8h+var_22C0], rcx
0x180003f7f  mov     qword ptr [rsp+22F8h+Data], rdx
0x180003f84  mov     [rsp+22F8h+var_22A8], rcx
0x180003f89  mov     [rsp+22F8h+var_2278], rdx
0x180003f91  mov     [rsp+22F8h+var_2298], r8
0x180003f96  mov     [rsp+22F8h+var_2270], r9
0x180003f9e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180003fa6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003fab  xor     ebx, ebx
0x180003fad  test    eax, eax
0x180003faf  js      short loc_180003FE3
0x180003fb1  mov     edi, ebx
0x180003fb3  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003fba  movsxd  rsi, edi
0x180003fbd  add     rsi, rsi
0x180003fc0  mov     rdx, [r13+rsi*8+0]; lpString2
0x180003fc5  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180003fcd  call    cs:__imp_lstrcmpiW
0x180003fd3  test    eax, eax
0x180003fd5  jz      short loc_180004006
0x180003fd7  inc     edi
0x180003fd9  cmp     edi, 4
0x180003fdc  jb      short loc_180003FBA
0x180003fde  mov     eax, 80020009h
0x180003fe3  mov     rcx, [rsp+22F8h+var_48]
0x180003feb  xor     rcx, rsp; StackCookie
0x180003fee  call    __security_check_cookie
0x180003ff3  add     rsp, 22C0h
0x180003ffa  pop     r15
0x180003ffc  pop     r14
0x180003ffe  pop     r13
0x180004000  pop     r12
0x180004002  pop     rdi
0x180004003  pop     rsi
0x180004004  pop     rbx
0x180004005  retn
0x180004006  movzx   edi, word ptr [r13+rsi*8+8]
0x18000400c  mov     esi, 13h
0x180004011  mov     rdx, [r15]
0x180004014  movzx   ecx, word ptr [rdx]
0x180004017  sub     ecx, 9
0x18000401a  jz      loc_1800044DD
0x180004020  sub     ecx, 1
0x180004023  jz      loc_1800044DD
0x180004029  sub     ecx, 3
0x18000402c  jz      loc_1800044DD
0x180004032  cmp     ecx, esi
0x180004034  jz      loc_1800044DD
0x18000403a  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180004042  mov     rcx, r15; this
0x180004045  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000404a  test    eax, eax
0x18000404c  js      short loc_180003FE3
0x18000404e  mov     r13d, 8
0x180004054  cmp     di, r13w
0x180004058  jz      loc_18000448E
0x18000405e  cmp     di, 11h
0x180004062  jz      loc_180004267
0x180004068  cmp     di, si
0x18000406b  jz      loc_18000420F
0x180004071  mov     eax, 4008h
0x180004076  cmp     di, ax
0x180004079  jnz     loc_1800044C1
0x18000407f  lea     rcx, [rsp+22F8h+String1]
0x180004087  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000408b  mov     rax, rsi
0x18000408e  inc     rax
0x180004091  cmp     [rcx+rax*2], bx
0x180004095  jnz     short loc_18000408E
0x180004097  add     eax, 2
0x18000409a  mov     [rsp+22F8h+var_2158], rbx
0x1800040a2  test    eax, eax
0x1800040a4  jz      short loc_1800040DF
0x1800040a6  movsxd  rcx, eax
0x1800040a9  xor     edx, edx
0x1800040ab  mov     rax, rsi
0x1800040ae  div     rcx
0x1800040b1  cmp     rax, 2
0x1800040b5  jb      loc_1800044EE
0x1800040bb  lea     rdx, [rcx+rcx]
0x1800040bf  cmp     rdx, 100h
0x1800040c6  jbe     short loc_1800040DF
0x1800040c8  lea     rcx, [rsp+22F8h+var_2158]
0x1800040d0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800040d5  mov     rdi, [rsp+22F8h+var_2158]
0x1800040dd  jmp     short loc_1800040EF
0x1800040df  lea     rdi, [rsp+22F8h+var_2150]
0x1800040e7  mov     [rsp+22F8h+var_2158], rdi
0x1800040ef  mov     r13, [rsp+22F8h+lpValueName]
0x1800040f4  jmp     short loc_180004118
0x1800040f6  xor     ebx, ebx
0x1800040f8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800040fc  mov     rdi, [rsp+22F8h+var_2158]
0x180004104  mov     r12, qword ptr [rsp+22F8h+Data]
0x180004109  mov     rax, [rsp+22F8h+var_22A8]
0x18000410e  mov     [rsp+22F8h+var_22C0], rax
0x180004113  mov     r13, [rsp+22F8h+var_2298]
0x180004118  test    rdi, rdi
0x18000411b  jz      loc_1800041D7
0x180004121  lea     r14, [rsp+22F8h+String1]
0x180004129  cmp     [rsp+22F8h+String1], bx
0x180004131  jz      short loc_180004174
0x180004133  mov     r15d, 30h ; '0'
0x180004139  mov     rcx, r14; lpsz
0x18000413c  call    cs:__imp_CharNextW
0x180004142  movzx   ecx, word ptr [r14]
0x180004146  cmp     cx, 5Ch ; '\'
0x18000414a  jnz     short loc_180004163
0x18000414c  cmp     [rax], r15w
0x180004150  jnz     short loc_180004163
0x180004152  mov     [rdi], bx
0x180004155  mov     rcx, rax; lpsz
0x180004158  call    cs:__imp_CharNextW
0x18000415e  mov     r14, rax
0x180004161  jmp     short loc_18000416A
0x180004163  mov     [rdi], cx
0x180004166  add     r14, 2
0x18000416a  add     rdi, 2
0x18000416e  cmp     [r14], bx
0x180004172  jnz     short loc_180004139
0x180004174  mov     dword ptr [rdi], 0
0x18000417a  mov     r8, [rsp+22F8h+var_2158]
0x180004182  test    r8, r8
0x180004185  jz      loc_1800044F9
0x18000418b  mov     r10d, ebx
0x18000418e  mov     r9, r8
0x180004191  mov     rcx, rsi
0x180004194  inc     rcx
0x180004197  cmp     [r9+rcx*2], bx
0x18000419c  jnz     short loc_180004194
0x18000419e  inc     ecx
0x1800041a0  lea     r9, [r9+rcx*2]
0x1800041a4  lea     r10d, [r10+rcx*2]
0x1800041a8  cmp     ecx, 1
0x1800041ab  jnz     short loc_180004191
0x1800041ad  mov     [rsp+22F8h+cbData], r10d; cbData
0x1800041b2  mov     [rsp+22F8h+lpData], r8; lpData
0x1800041b7  lea     r9d, [rcx+6]; dwType
0x1800041bb  xor     r8d, r8d; Reserved
0x1800041be  mov     rdx, r13; lpValueName
0x1800041c1  mov     rcx, [r12]; hKey
0x1800041c5  call    cs:__imp_RegSetValueExW
0x1800041cb  mov     esi, eax
0x1800041cd  mov     rdi, [rsp+22F8h+var_2158]
0x1800041d5  jmp     short loc_1800041DC
0x1800041d7  mov     esi, 0Eh
0x1800041dc  lea     rax, [rsp+22F8h+var_2150]
0x1800041e4  cmp     rdi, rax
0x1800041e7  jz      short loc_1800041F6
0x1800041e9  lea     rcx, [rsp+22F8h+var_2158]
0x1800041f1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800041f6  mov     r15, [rsp+22F8h+var_22C0]
0x1800041fb  test    esi, esi
0x1800041fd  jz      loc_1800044C1
0x180004203  mov     ecx, esi; unsigned int
0x180004205  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000420a  jmp     loc_180003FE3
0x18000420f  mov     [rsp+22F8h+pulOut], ebx
0x180004213  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180004218  xor     r8d, r8d; dwFlags
0x18000421b  xor     edx, edx; lcid
0x18000421d  lea     rcx, [rsp+22F8h+String1]; strIn
0x180004225  call    cs:__imp_VarUI4FromStr
0x18000422b  test    eax, eax
0x18000422d  js      loc_180003FE3
0x180004233  mov     eax, [rsp+22F8h+pulOut]
0x180004237  mov     dword ptr [rsp+22F8h+Data], eax
0x18000423b  mov     [rsp+22F8h+cbData], 4; cbData
0x180004243  lea     rax, [rsp+22F8h+Data]
0x180004248  mov     r9d, 4; dwType
0x18000424e  mov     [rsp+22F8h+lpData], rax; lpData
0x180004253  xor     r8d, r8d; Reserved
0x180004256  mov     rdx, r14; lpValueName
0x180004259  mov     rcx, [r12]; hKey
0x18000425d  call    cs:__imp_RegSetValueExW
0x180004263  mov     esi, eax
0x180004265  jmp     short loc_1800041FB
0x180004267  lea     rax, [rsp+22F8h+String1]
0x18000426f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004273  mov     r14, rsi
0x180004276  inc     r14
0x180004279  cmp     [rax+r14*2], bx
0x18000427e  jnz     short loc_180004276
0x180004280  mov     dword ptr [rsp+22F8h+Data], r14d
0x180004285  test    r14b, 1
0x180004289  jnz     loc_180004343
0x18000428f  mov     eax, r14d
0x180004292  cdq
0x180004293  sub     eax, edx
0x180004295  sar     eax, 1
0x180004297  movsxd  r12, eax
0x18000429a  mov     [rsp+22F8h+var_2268], rbx
0x1800042a2  mov     rdi, r12
0x1800042a5  mov     [rsp+22F8h+var_2280], r12
0x1800042aa  test    eax, eax
0x1800042ac  jz      short loc_1800042E3
0x1800042ae  xor     edx, edx
0x1800042b0  mov     rax, rsi
0x1800042b3  div     rdi
0x1800042b6  cmp     rax, 1
0x1800042ba  jb      loc_180004504
0x1800042c0  cmp     rdi, 100h
0x1800042c7  jbe     short loc_1800042E3
0x1800042c9  mov     rdx, rdi
0x1800042cc  lea     rcx, [rsp+22F8h+var_2268]
0x1800042d4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800042d9  mov     rcx, [rsp+22F8h+var_2268]
0x1800042e1  jmp     short loc_1800042F3
0x1800042e3  lea     rcx, [rsp+22F8h+var_2260]
0x1800042eb  mov     [rsp+22F8h+var_2268], rcx
0x1800042f3  mov     rsi, [rsp+22F8h+var_2288]
0x1800042f8  jmp     short loc_180004331
0x1800042fa  xor     ebx, ebx
0x1800042fc  lea     r13d, [rbx+8]
0x180004300  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180004305  mov     rcx, [rsp+22F8h+var_2268]; void *
0x18000430d  mov     rdi, [rsp+22F8h+var_2280]
0x180004312  mov     rax, [rsp+22F8h+var_22A8]
0x180004317  mov     [rsp+22F8h+var_22C0], rax
0x18000431c  mov     rsi, [rsp+22F8h+var_2278]
0x180004324  mov     rax, [rsp+22F8h+var_2298]
0x180004329  mov     [rsp+22F8h+lpValueName], rax
0x18000432e  mov     r12d, edi
0x180004331  test    rcx, rcx
0x180004334  jnz     short loc_18000434D
0x180004336  lea     rcx, [rsp+22F8h+var_2268]
0x18000433e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004343  mov     eax, 80004005h
0x180004348  jmp     loc_180003FE3
0x18000434d  mov     r8, rdi; Size
0x180004350  xor     edx, edx; Val
0x180004352  call    memset_0
0x180004357  mov     r10d, ebx
0x18000435a  test    r14d, r14d
0x18000435d  jle     loc_18000443B
0x180004363  mov     r15d, 30h ; '0'
0x180004369  mov     eax, r10d
0x18000436c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180004374  cmp     edx, 61h ; 'a'
0x180004377  ja      short loc_1800043E6
0x180004379  jz      loc_180004406
0x18000437f  cmp     edx, 38h ; '8'
0x180004382  ja      short loc_1800043B8
0x180004384  jz      short loc_1800043B0
0x180004386  mov     ecx, edx
0x180004388  sub     ecx, r15d
0x18000438b  jz      short loc_1800043B0
0x18000438d  sub     ecx, 1
0x180004390  jz      short loc_1800043B0
0x180004392  sub     ecx, 1
0x180004395  jz      short loc_1800043B0
0x180004397  sub     ecx, 1
0x18000439a  jz      short loc_1800043B0
0x18000439c  sub     ecx, 1
0x18000439f  jz      short loc_1800043B0
0x1800043a1  sub     ecx, 1
0x1800043a4  jz      short loc_1800043B0
0x1800043a6  sub     ecx, 1
0x1800043a9  jz      short loc_1800043B0
0x1800043ab  cmp     ecx, 1
0x1800043ae  jnz     short loc_180004401
0x1800043b0  mov     r9d, edx
0x1800043b3  sub     r9d, r15d
0x1800043b6  jmp     short loc_18000440A
0x1800043b8  mov     r9d, edx
0x1800043bb  mov     ecx, edx
0x1800043bd  sub     ecx, 39h ; '9'
0x1800043c0  jz      short loc_1800043B0
0x1800043c2  sub     ecx, r13d
0x1800043c5  jz      short loc_1800043E0
0x1800043c7  sub     ecx, 1
0x1800043ca  jz      short loc_1800043E0
0x1800043cc  sub     ecx, 1
0x1800043cf  jz      short loc_1800043E0
0x1800043d1  sub     ecx, 1
0x1800043d4  jz      short loc_1800043E0
0x1800043d6  sub     ecx, 1
0x1800043d9  jz      short loc_1800043E0
0x1800043db  cmp     ecx, 1
0x1800043de  jnz     short loc_180004401
0x1800043e0  add     r9d, 0FFFFFFC9h
0x1800043e4  jmp     short loc_18000440A
  ... truncated ...
```
