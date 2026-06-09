# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180003ea0`
- end: `0x18000447b`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1499`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800049b8`

## callees

- `0x1800037a4`
- `0x1800037c8`
- `0x180003ea0`
- `0x180004484`
- `0x1800047ec`
- `0x1800047fc`
- `0x18000cdb0`
- `0x18000e0cc`
- `0x18000e430`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180004123`
- `ADVAPI32!RegSetValueExW` at `0x1800041aa`
- `ADVAPI32!RegSetValueExW` at `0x180004399`
- `ADVAPI32!RegSetValueExW` at `0x1800043ff`
- `ADVAPI32!RegSetValueExW` at `0x180004123`
- `ADVAPI32!RegSetValueExW` at `0x1800041aa`
- `ADVAPI32!RegSetValueExW` at `0x180004399`
- `ADVAPI32!RegSetValueExW` at `0x1800043ff`
- `KERNEL32!lstrcmpiW` at `0x180003f13`
- `KERNEL32!lstrcmpiW` at `0x180003f31`
- `KERNEL32!lstrcmpiW` at `0x180003f51`
- `KERNEL32!lstrcmpiW` at `0x180003f6f`
- `KERNEL32!lstrcmpiW` at `0x180003f13`
- `KERNEL32!lstrcmpiW` at `0x180003f31`
- `KERNEL32!lstrcmpiW` at `0x180003f51`
- `KERNEL32!lstrcmpiW` at `0x180003f6f`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004171`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004171`
- `USER32!CharNextW` at `0x18000409a`
- `USER32!CharNextW` at `0x1800040b6`
- `USER32!CharNextW` at `0x18000442d`
- `USER32!CharNextW` at `0x18000409a`
- `USER32!CharNextW` at `0x1800040b6`
- `USER32!CharNextW` at `0x18000442d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  HKEY *v5; // r13
  LPCWSTR *v6; // r12
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  __int64 v10; // rax
  int v11; // eax
  BYTE *v12; // rdi
  WCHAR *i; // r14
  const WCHAR *v14; // rax
  LSTATUS v15; // edi
  DWORD cbData; // r9d
  BYTE *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdi
  int v21; // eax
  unsigned __int64 v22; // r14
  unsigned __int64 v23; // rcx
  const WCHAR *v24; // rsi
  unsigned int v25; // r10d
  __int64 v26; // r9
  unsigned int v27; // edx
  char v28; // dl
  __int64 v29; // rsi
  int Token; // eax
  __int64 v31; // [rsp+0h] [rbp-21D8h] BYREF
  ULONG pulOut; // [rsp+30h] [rbp-21A8h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-21A0h] BYREF
  LPCWSTR lpValueName; // [rsp+40h] [rbp-2198h]
  const WCHAR *v35; // [rsp+50h] [rbp-2188h]
  ATL::CRegParser *v36; // [rsp+60h] [rbp-2178h]
  struct ATL::CRegKey *v37; // [rsp+68h] [rbp-2170h]
  unsigned __int16 *v38; // [rsp+70h] [rbp-2168h]
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v40[264]; // [rsp+88h] [rbp-2150h] BYREF
  WCHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v6 = this;
  v36 = (ATL::CRegParser *)this;
  v37 = (struct ATL::CRegKey *)a2;
  v35 = a3;
  v38 = a4;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  v8 = 0;
  if ( result >= 0 )
  {
    if ( lstrcmpiW(String1, L"S") )
    {
      if ( lstrcmpiW(String1, L"M") )
      {
        if ( lstrcmpiW(String1, L"D") )
        {
          if ( lstrcmpiW(String1, L"B") )
            return -2147352567;
          v9 = 17;
        }
        else
        {
          v9 = 19;
        }
      }
      else
      {
        v9 = 16392;
      }
    }
    else
    {
      v9 = 8;
    }
    while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
      *v6 = CharNextW(*v6);
    result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
    if ( result >= 0 )
    {
      if ( v9 == 8 )
      {
        v29 = -1;
        do
          ++v29;
        while ( String1[v29] );
        v15 = RegSetValueExW(*v5, a3, 0, 1u, (const BYTE *)String1, 2 * v29 + 2);
        goto LABEL_93;
      }
      if ( v9 != 17 )
      {
        if ( v9 == 19 )
        {
          v35 = 0;
          result = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( result < 0 )
            return result;
          *(_DWORD *)Data = pulOut;
          v15 = RegSetValueExW(*v5, a3, 0, 4u, Data, 4u);
          goto LABEL_93;
        }
        v10 = -1;
        do
          ++v10;
        while ( String1[v10] );
        v11 = v10 + 2;
        lpData = 0;
        try
        {
          if ( !v11 )
            goto LABEL_25;
          if ( 0xFFFFFFFFFFFFFFFFuLL / v11 < 2 )
            ATL::AtlThrowImpl(-2147024362);
          if ( (unsigned __int64)(2LL * v11) > 0x100 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v11);
          else
LABEL_25:
            lpData = v40;
        }
        catch ( ... )
        {
          v8 = 0;
          v6 = (LPCWSTR *)v36;
          v5 = (HKEY *)v37;
          lpValueName = v35;
        }
        v12 = lpData;
        if ( lpData )
        {
          for ( i = String1; *i; v12 += 2 )
          {
            v14 = CharNextW(i);
            if ( *i == 92 && *v14 == 48 )
            {
              *(_WORD *)v12 = 0;
              i = CharNextW(v14);
            }
            else
            {
              *(_WORD *)v12 = *i++;
            }
          }
          *(_DWORD *)v12 = 0;
          if ( lpData )
          {
            cbData = 0;
            v17 = lpData;
            do
            {
              v18 = -1;
              do
                ++v18;
              while ( *(_WORD *)&v17[2 * v18] );
              v19 = (unsigned int)(v18 + 1);
              v17 += 2 * v19;
              cbData += 2 * v19;
            }
            while ( (_DWORD)v19 != 1 );
            v15 = RegSetValueExW(*v5, lpValueName, 0, 7u, lpData, cbData);
          }
          else
          {
            v15 = 13;
          }
        }
        else
        {
          v15 = 14;
        }
        if ( lpData != v40 )
          goto LABEL_42;
        goto LABEL_93;
      }
      v20 = -1;
      do
        ++v20;
      while ( String1[v20] );
      *(_DWORD *)Data = v20;
      if ( (v20 & 1) != 0 )
        return -2147467259;
      v21 = (int)v20 / 2;
      v22 = (int)v20 / 2;
      pulOut = (int)v20 / 2;
      lpData = 0;
      try
      {
        v23 = v21;
        if ( v21 )
        {
          if ( !(0xFFFFFFFFFFFFFFFFuLL / v22) )
            ATL::AtlThrowImpl(-2147024362);
        }
        else
        {
          v23 = 0;
        }
        if ( v23 <= 0x100 )
          lpData = v40;
        else
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v23);
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v20) = *(_DWORD *)Data;
        LODWORD(v22) = pulOut;
        v6 = (LPCWSTR *)v36;
        v5 = (HKEY *)v37;
        v24 = v35;
        goto LABEL_56;
      }
      v24 = lpValueName;
LABEL_56:
      if ( !lpData )
      {
        if ( &v31 != (__int64 *)-136LL )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
        return -2147467259;
      }
      memset_0(lpData, 0, (int)v22);
      v25 = 0;
      if ( (int)v20 <= 0 )
      {
LABEL_88:
        v15 = RegSetValueExW(*v5, v24, 0, 3u, lpData, v22);
        if ( lpData != v40 )
LABEL_42:
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
LABEL_93:
        if ( v15 )
          return ATL::AtlHresultFromWin32(v15);
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v38);
        if ( Token < 0 )
          return Token;
        return v8;
      }
      v26 = 0;
      while ( 1 )
      {
        v27 = String1[v26];
        if ( v27 > 0x61 )
        {
          if ( v27 == 98 || v27 == 99 || v27 == 100 || v27 - 101 < 2 )
          {
LABEL_86:
            v28 = v27 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v28 = 0;
          goto LABEL_87;
        }
        if ( v27 == 97 )
          goto LABEL_86;
        if ( v27 <= 0x38 )
          break;
        if ( v27 == 57 )
          goto LABEL_73;
        if ( v27 != 65 && v27 != 66 && v27 != 67 && v27 != 68 && v27 - 69 > 1 )
          goto LABEL_85;
        v28 = v27 - 55;
LABEL_87:
        lpData[(unsigned __int64)v25 >> 1] |= v28 << (4 - 4 * (v25 & 1));
        ++v25;
        if ( ++v26 >= (int)v20 )
          goto LABEL_88;
      }
      if ( v27 != 56 && v27 != 48 && v27 != 49 && v27 != 50 && v27 != 51 && v27 != 52 && v27 != 53 && v27 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v28 = v27 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003ea0  push    rbx
0x180003ea2  push    rsi
0x180003ea3  push    rdi
0x180003ea4  push    r12
0x180003ea6  push    r13
0x180003ea8  push    r14
0x180003eaa  push    r15
0x180003eac  mov     eax, 21A0h
0x180003eb1  call    _alloca_probe
0x180003eb6  sub     rsp, rax
0x180003eb9  mov     rax, cs:__security_cookie
0x180003ec0  xor     rax, rsp
0x180003ec3  mov     [rsp+21D8h+var_48], rax
0x180003ecb  mov     r15, r8
0x180003ece  mov     [rsp+21D8h+lpValueName], r8
0x180003ed3  mov     r13, rdx
0x180003ed6  mov     r12, rcx
0x180003ed9  mov     [rsp+21D8h+var_2178], rcx
0x180003ede  mov     [rsp+21D8h+var_2170], rdx
0x180003ee3  mov     [rsp+21D8h+var_2188], r8
0x180003ee8  mov     [rsp+21D8h+var_2168], r9
0x180003eed  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180003ef5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003efa  xor     ebx, ebx
0x180003efc  test    eax, eax
0x180003efe  js      loc_180004441
0x180003f04  lea     rdx, String2; "S"
0x180003f0b  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180003f13  call    cs:__imp_lstrcmpiW
0x180003f19  test    eax, eax
0x180003f1b  jnz     short loc_180003F22
0x180003f1d  lea     edi, [rbx+8]
0x180003f20  jmp     short loc_180003F80
0x180003f22  lea     rdx, aM; "M"
0x180003f29  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180003f31  call    cs:__imp_lstrcmpiW
0x180003f37  test    eax, eax
0x180003f39  jnz     short loc_180003F42
0x180003f3b  mov     edi, 4008h
0x180003f40  jmp     short loc_180003F80
0x180003f42  lea     rdx, aD; "D"
0x180003f49  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180003f51  call    cs:__imp_lstrcmpiW
0x180003f57  test    eax, eax
0x180003f59  jnz     short loc_180003F60
0x180003f5b  lea     edi, [rax+13h]
0x180003f5e  jmp     short loc_180003F80
0x180003f60  lea     rdx, aB; "B"
0x180003f67  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180003f6f  call    cs:__imp_lstrcmpiW
0x180003f75  test    eax, eax
0x180003f77  jnz     loc_18000443C
0x180003f7d  lea     edi, [rax+11h]
0x180003f80  mov     rdx, [r12]
0x180003f84  movzx   ecx, word ptr [rdx]
0x180003f87  sub     ecx, 9
0x180003f8a  jz      loc_18000442A
0x180003f90  sub     ecx, 1
0x180003f93  jz      loc_18000442A
0x180003f99  sub     ecx, 3
0x180003f9c  jz      loc_18000442A
0x180003fa2  cmp     ecx, 13h
0x180003fa5  jz      loc_18000442A
0x180003fab  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180003fb3  mov     rcx, r12; this
0x180003fb6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003fbb  test    eax, eax
0x180003fbd  js      loc_180004441
0x180003fc3  cmp     edi, 8
0x180003fc6  jz      loc_1800043C2
0x180003fcc  cmp     edi, 11h
0x180003fcf  jz      loc_1800041B7
0x180003fd5  cmp     edi, 13h
0x180003fd8  jz      loc_18000415A
0x180003fde  cmp     edi, 4008h
0x180003fe4  jnz     loc_180004414
0x180003fea  lea     rcx, [rsp+21D8h+String1]
0x180003ff2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003ff6  mov     rax, rsi
0x180003ff9  inc     rax
0x180003ffc  cmp     [rcx+rax*2], bx
0x180004000  jnz     short loc_180003FF9
0x180004002  add     eax, 2
0x180004005  mov     [rsp+21D8h+var_2158], rbx
0x18000400d  movsxd  rcx, eax
0x180004010  test    eax, eax
0x180004012  jz      short loc_180004042
0x180004014  xor     edx, edx
0x180004016  mov     rax, rsi
0x180004019  div     rcx
0x18000401c  cmp     rax, 2
0x180004020  jb      loc_180004464
0x180004026  lea     rdx, [rcx+rcx]
0x18000402a  cmp     rdx, 100h
0x180004031  jbe     short loc_180004042
0x180004033  lea     rcx, [rsp+21D8h+var_2158]
0x18000403b  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004040  jmp     short loc_180004052
0x180004042  lea     rax, [rsp+21D8h+var_2150]
0x18000404a  mov     [rsp+21D8h+var_2158], rax
0x180004052  jmp     short loc_18000406E
0x180004054  xor     ebx, ebx
0x180004056  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000405a  mov     r12, [rsp+21D8h+var_2178]
0x18000405f  mov     r13, [rsp+21D8h+var_2170]
0x180004064  mov     rax, [rsp+21D8h+var_2188]
0x180004069  mov     [rsp+21D8h+lpValueName], rax
0x18000406e  mov     rdi, [rsp+21D8h+var_2158]
0x180004076  test    rdi, rdi
0x180004079  jz      loc_18000412D
0x18000407f  lea     r14, [rsp+21D8h+String1]
0x180004087  cmp     [rsp+21D8h+String1], bx
0x18000408f  jz      short loc_1800040D2
0x180004091  mov     r15d, 30h ; '0'
0x180004097  mov     rcx, r14; lpsz
0x18000409a  call    cs:__imp_CharNextW
0x1800040a0  movzx   ecx, word ptr [r14]
0x1800040a4  cmp     cx, 5Ch ; '\'
0x1800040a8  jnz     short loc_1800040C1
0x1800040aa  cmp     [rax], r15w
0x1800040ae  jnz     short loc_1800040C1
0x1800040b0  mov     [rdi], bx
0x1800040b3  mov     rcx, rax; lpsz
0x1800040b6  call    cs:__imp_CharNextW
0x1800040bc  mov     r14, rax
0x1800040bf  jmp     short loc_1800040C8
0x1800040c1  mov     [rdi], cx
0x1800040c4  add     r14, 2
0x1800040c8  add     rdi, 2
0x1800040cc  cmp     [r14], bx
0x1800040d0  jnz     short loc_180004097
0x1800040d2  and     dword ptr [rdi], 0
0x1800040d5  mov     rdx, [rsp+21D8h+var_2158]
0x1800040dd  test    rdx, rdx
0x1800040e0  jnz     short loc_1800040E7
0x1800040e2  lea     edi, [rdx+0Dh]
0x1800040e5  jmp     short loc_180004132
0x1800040e7  mov     r9d, ebx
0x1800040ea  mov     r8, rdx
0x1800040ed  mov     rcx, rsi
0x1800040f0  inc     rcx
0x1800040f3  cmp     [r8+rcx*2], bx
0x1800040f8  jnz     short loc_1800040F0
0x1800040fa  inc     ecx
0x1800040fc  lea     r8, [r8+rcx*2]
0x180004100  lea     r9d, [r9+rcx*2]
0x180004104  cmp     ecx, 1
0x180004107  jnz     short loc_1800040ED
0x180004109  mov     [rsp+21D8h+cbData], r9d; cbData
0x18000410e  mov     [rsp+21D8h+lpData], rdx; lpData
0x180004113  lea     r9d, [rcx+6]; dwType
0x180004117  xor     r8d, r8d; Reserved
0x18000411a  mov     rdx, [rsp+21D8h+lpValueName]; lpValueName
0x18000411f  mov     rcx, [r13+0]; hKey
0x180004123  call    cs:__imp_RegSetValueExW
0x180004129  mov     edi, eax
0x18000412b  jmp     short loc_180004132
0x18000412d  mov     edi, 0Eh
0x180004132  lea     rax, [rsp+21D8h+var_2150]
0x18000413a  cmp     [rsp+21D8h+var_2158], rax
0x180004142  jz      loc_180004407
0x180004148  lea     rcx, [rsp+21D8h+var_2158]
0x180004150  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004155  jmp     loc_180004407
0x18000415a  mov     [rsp+21D8h+var_2188], rbx
0x18000415f  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x180004164  xor     r8d, r8d; dwFlags
0x180004167  xor     edx, edx; lcid
0x180004169  lea     rcx, [rsp+21D8h+String1]; strIn
0x180004171  call    cs:__imp_VarUI4FromStr
0x180004177  test    eax, eax
0x180004179  jns     short loc_180004180
0x18000417b  jmp     loc_180004441
0x180004180  mov     eax, [rsp+21D8h+pulOut]
0x180004184  mov     dword ptr [rsp+21D8h+Data], eax
0x180004188  mov     [rsp+21D8h+cbData], 4; cbData
0x180004190  lea     rax, [rsp+21D8h+Data]
0x180004195  mov     [rsp+21D8h+lpData], rax; lpData
0x18000419a  mov     r9d, 4; dwType
0x1800041a0  xor     r8d, r8d; Reserved
0x1800041a3  mov     rdx, r15; lpValueName
0x1800041a6  mov     rcx, [r13+0]; hKey
0x1800041aa  call    cs:__imp_RegSetValueExW
0x1800041b0  mov     edi, eax
0x1800041b2  jmp     loc_180004407
0x1800041b7  lea     rax, [rsp+21D8h+String1]
0x1800041bf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800041c3  mov     rdi, rsi
0x1800041c6  inc     rdi
0x1800041c9  cmp     [rax+rdi*2], bx
0x1800041cd  jnz     short loc_1800041C6
0x1800041cf  mov     dword ptr [rsp+21D8h+Data], edi
0x1800041d3  test    dil, 1
0x1800041d7  jnz     loc_18000428A
0x1800041dd  mov     eax, edi
0x1800041df  cdq
0x1800041e0  sub     eax, edx
0x1800041e2  sar     eax, 1
0x1800041e4  movsxd  r14, eax
0x1800041e7  mov     [rsp+21D8h+pulOut], r14d
0x1800041ec  mov     [rsp+21D8h+var_2158], rbx
0x1800041f4  mov     rcx, r14
0x1800041f7  test    eax, eax
0x1800041f9  jnz     short loc_180004200
0x1800041fb  mov     rcx, rbx
0x1800041fe  jmp     short loc_180004212
0x180004200  xor     edx, edx
0x180004202  mov     rax, rsi
0x180004205  div     rcx
0x180004208  cmp     rax, 1
0x18000420c  jb      loc_18000446F
0x180004212  cmp     rcx, 100h
0x180004219  jbe     short loc_18000422D
0x18000421b  mov     rdx, rcx
0x18000421e  lea     rcx, [rsp+21D8h+var_2158]
0x180004226  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000422b  jmp     short loc_18000423D
0x18000422d  lea     rax, [rsp+21D8h+var_2150]
0x180004235  mov     [rsp+21D8h+var_2158], rax
0x18000423d  mov     rsi, [rsp+21D8h+lpValueName]
0x180004242  jmp     short loc_18000425E
0x180004244  xor     ebx, ebx
0x180004246  mov     edi, dword ptr [rsp+21D8h+Data]
0x18000424a  mov     r14d, [rsp+21D8h+pulOut]
0x18000424f  mov     r12, [rsp+21D8h+var_2178]
0x180004254  mov     r13, [rsp+21D8h+var_2170]
0x180004259  mov     rsi, [rsp+21D8h+var_2188]
0x18000425e  mov     rcx, [rsp+21D8h+var_2158]; void *
0x180004266  test    rcx, rcx
0x180004269  jnz     short loc_180004294
0x18000426b  lea     rax, [rsp+21D8h+var_2150]
0x180004273  cmp     [rsp+21D8h+var_2158], rax
0x18000427b  jz      short loc_18000428A
0x18000427d  lea     rcx, [rsp+21D8h+var_2158]
0x180004285  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000428a  mov     eax, 80004005h
0x18000428f  jmp     loc_180004441
0x180004294  movsxd  r8, r14d; Size
0x180004297  xor     edx, edx; Val
0x180004299  call    memset_0
0x18000429e  mov     r10d, ebx
0x1800042a1  movsxd  r11, edi
0x1800042a4  test    edi, edi
0x1800042a6  jle     loc_180004377
0x1800042ac  mov     r9, rbx
0x1800042af  mov     r15d, 30h ; '0'
0x1800042b5  mov     r8d, r10d
0x1800042b8  shr     r8, 1
0x1800042bb  add     r8, [rsp+21D8h+var_2158]
0x1800042c3  movzx   edx, [rsp+r9*2+21D8h+String1]
0x1800042cc  mov     ecx, edx
0x1800042ce  cmp     edx, 61h ; 'a'
0x1800042d1  ja      short loc_180004331
0x1800042d3  jz      short loc_18000434E
0x1800042d5  cmp     edx, 38h ; '8'
0x1800042d8  ja      short loc_180004309
0x1800042da  jz      short loc_180004304
0x1800042dc  sub     ecx, r15d
0x1800042df  jz      short loc_180004304
0x1800042e1  sub     ecx, 1
0x1800042e4  jz      short loc_180004304
0x1800042e6  sub     ecx, 1
0x1800042e9  jz      short loc_180004304
0x1800042eb  sub     ecx, 1
0x1800042ee  jz      short loc_180004304
0x1800042f0  sub     ecx, 1
0x1800042f3  jz      short loc_180004304
0x1800042f5  sub     ecx, 1
0x1800042f8  jz      short loc_180004304
0x1800042fa  sub     ecx, 1
0x1800042fd  jz      short loc_180004304
0x1800042ff  cmp     ecx, 1
0x180004302  jnz     short loc_18000434A
0x180004304  sub     dl, r15b
0x180004307  jmp     short loc_180004351
0x180004309  sub     ecx, 39h ; '9'
0x18000430c  jz      short loc_180004304
0x18000430e  sub     ecx, 8
0x180004311  jz      short loc_18000432C
0x180004313  sub     ecx, 1
0x180004316  jz      short loc_18000432C
0x180004318  sub     ecx, 1
0x18000431b  jz      short loc_18000432C
0x18000431d  sub     ecx, 1
0x180004320  jz      short loc_18000432C
0x180004322  sub     ecx, 1
0x180004325  jz      short loc_18000432C
0x180004327  cmp     ecx, 1
0x18000432a  jnz     short loc_18000434A
0x18000432c  sub     dl, 37h ; '7'
0x18000432f  jmp     short loc_180004351
0x180004331  sub     ecx, 62h ; 'b'
0x180004334  jz      short loc_18000434E
0x180004336  sub     ecx, 1
0x180004339  jz      short loc_18000434E
0x18000433b  sub     ecx, 1
0x18000433e  jz      short loc_18000434E
0x180004340  sub     ecx, 1
0x180004343  jz      short loc_18000434E
0x180004345  cmp     ecx, 1
  ... truncated ...
```
