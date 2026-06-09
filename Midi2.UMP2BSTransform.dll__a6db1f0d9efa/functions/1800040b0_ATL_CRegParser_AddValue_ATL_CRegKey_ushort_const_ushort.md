# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800040b0`
- end: `0x180004684`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180006c0c`

## callees

- `0x180001ef0`
- `0x180002958`
- `0x1800040b0`
- `0x18000468c`
- `0x1800047e0`
- `0x1800047f8`
- `0x180004fe8`
- `0x1800060dc`
- `0x18000e890`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004399`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004399`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004339`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800045d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004339`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800045d2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800042b0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800042cc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004654`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800042b0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800042cc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004654`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004141`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004141`

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
0x1800040b0  push    rbx
0x1800040b2  push    rsi
0x1800040b3  push    rdi
0x1800040b4  push    r12
0x1800040b6  push    r13
0x1800040b8  push    r14
0x1800040ba  push    r15
0x1800040bc  mov     eax, 22C0h
0x1800040c1  call    _alloca_probe
0x1800040c6  sub     rsp, rax
0x1800040c9  mov     rax, cs:__security_cookie
0x1800040d0  xor     rax, rsp
0x1800040d3  mov     [rsp+22F8h+var_48], rax
0x1800040db  mov     r14, r8
0x1800040de  mov     [rsp+22F8h+lpValueName], r8
0x1800040e3  mov     r12, rdx
0x1800040e6  mov     [rsp+22F8h+var_2288], rdx
0x1800040eb  mov     r15, rcx
0x1800040ee  mov     [rsp+22F8h+var_22C0], rcx
0x1800040f3  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800040f8  mov     [rsp+22F8h+var_22A8], rcx
0x1800040fd  mov     [rsp+22F8h+var_2278], rdx
0x180004105  mov     [rsp+22F8h+var_2298], r8
0x18000410a  mov     [rsp+22F8h+var_2270], r9
0x180004112  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18000411a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000411f  xor     ebx, ebx
0x180004121  test    eax, eax
0x180004123  js      short loc_180004157
0x180004125  mov     edi, ebx
0x180004127  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000412e  movsxd  rsi, edi
0x180004131  add     rsi, rsi
0x180004134  mov     rdx, [r13+rsi*8+0]; lpString2
0x180004139  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180004141  call    cs:__imp_lstrcmpiW
0x180004147  test    eax, eax
0x180004149  jz      short loc_18000417A
0x18000414b  inc     edi
0x18000414d  cmp     edi, 4
0x180004150  jb      short loc_18000412E
0x180004152  mov     eax, 80020009h
0x180004157  mov     rcx, [rsp+22F8h+var_48]
0x18000415f  xor     rcx, rsp; StackCookie
0x180004162  call    __security_check_cookie
0x180004167  add     rsp, 22C0h
0x18000416e  pop     r15
0x180004170  pop     r14
0x180004172  pop     r13
0x180004174  pop     r12
0x180004176  pop     rdi
0x180004177  pop     rsi
0x180004178  pop     rbx
0x180004179  retn
0x18000417a  movzx   edi, word ptr [r13+rsi*8+8]
0x180004180  mov     esi, 13h
0x180004185  mov     rdx, [r15]
0x180004188  movzx   ecx, word ptr [rdx]
0x18000418b  sub     ecx, 9
0x18000418e  jz      loc_180004651
0x180004194  sub     ecx, 1
0x180004197  jz      loc_180004651
0x18000419d  sub     ecx, 3
0x1800041a0  jz      loc_180004651
0x1800041a6  cmp     ecx, esi
0x1800041a8  jz      loc_180004651
0x1800041ae  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800041b6  mov     rcx, r15; this
0x1800041b9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800041be  test    eax, eax
0x1800041c0  js      short loc_180004157
0x1800041c2  mov     r13d, 8
0x1800041c8  cmp     di, r13w
0x1800041cc  jz      loc_180004602
0x1800041d2  cmp     di, 11h
0x1800041d6  jz      loc_1800043DB
0x1800041dc  cmp     di, si
0x1800041df  jz      loc_180004383
0x1800041e5  mov     eax, 4008h
0x1800041ea  cmp     di, ax
0x1800041ed  jnz     loc_180004635
0x1800041f3  lea     rcx, [rsp+22F8h+String1]
0x1800041fb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800041ff  mov     rax, rsi
0x180004202  inc     rax
0x180004205  cmp     [rcx+rax*2], bx
0x180004209  jnz     short loc_180004202
0x18000420b  add     eax, 2
0x18000420e  mov     [rsp+22F8h+var_2158], rbx
0x180004216  test    eax, eax
0x180004218  jz      short loc_180004253
0x18000421a  movsxd  rcx, eax
0x18000421d  xor     edx, edx
0x18000421f  mov     rax, rsi
0x180004222  div     rcx
0x180004225  cmp     rax, 2
0x180004229  jb      loc_180004662
0x18000422f  lea     rdx, [rcx+rcx]
0x180004233  cmp     rdx, 100h
0x18000423a  jbe     short loc_180004253
0x18000423c  lea     rcx, [rsp+22F8h+var_2158]
0x180004244  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004249  mov     rdi, [rsp+22F8h+var_2158]
0x180004251  jmp     short loc_180004263
0x180004253  lea     rdi, [rsp+22F8h+var_2150]
0x18000425b  mov     [rsp+22F8h+var_2158], rdi
0x180004263  mov     r13, [rsp+22F8h+lpValueName]
0x180004268  jmp     short loc_18000428C
0x18000426a  xor     ebx, ebx
0x18000426c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004270  mov     rdi, [rsp+22F8h+var_2158]
0x180004278  mov     r12, qword ptr [rsp+22F8h+Data]
0x18000427d  mov     rax, [rsp+22F8h+var_22A8]
0x180004282  mov     [rsp+22F8h+var_22C0], rax
0x180004287  mov     r13, [rsp+22F8h+var_2298]
0x18000428c  test    rdi, rdi
0x18000428f  jz      loc_18000434B
0x180004295  lea     r14, [rsp+22F8h+String1]
0x18000429d  cmp     [rsp+22F8h+String1], bx
0x1800042a5  jz      short loc_1800042E8
0x1800042a7  mov     r15d, 30h ; '0'
0x1800042ad  mov     rcx, r14; lpsz
0x1800042b0  call    cs:__imp_CharNextW
0x1800042b6  movzx   ecx, word ptr [r14]
0x1800042ba  cmp     cx, 5Ch ; '\'
0x1800042be  jnz     short loc_1800042D7
0x1800042c0  cmp     [rax], r15w
0x1800042c4  jnz     short loc_1800042D7
0x1800042c6  mov     [rdi], bx
0x1800042c9  mov     rcx, rax; lpsz
0x1800042cc  call    cs:__imp_CharNextW
0x1800042d2  mov     r14, rax
0x1800042d5  jmp     short loc_1800042DE
0x1800042d7  mov     [rdi], cx
0x1800042da  add     r14, 2
0x1800042de  add     rdi, 2
0x1800042e2  cmp     [r14], bx
0x1800042e6  jnz     short loc_1800042AD
0x1800042e8  mov     dword ptr [rdi], 0
0x1800042ee  mov     r8, [rsp+22F8h+var_2158]
0x1800042f6  test    r8, r8
0x1800042f9  jz      loc_18000466D
0x1800042ff  mov     r10d, ebx
0x180004302  mov     r9, r8
0x180004305  mov     rcx, rsi
0x180004308  inc     rcx
0x18000430b  cmp     [r9+rcx*2], bx
0x180004310  jnz     short loc_180004308
0x180004312  inc     ecx
0x180004314  lea     r9, [r9+rcx*2]
0x180004318  lea     r10d, [r10+rcx*2]
0x18000431c  cmp     ecx, 1
0x18000431f  jnz     short loc_180004305
0x180004321  mov     [rsp+22F8h+cbData], r10d; cbData
0x180004326  mov     [rsp+22F8h+lpData], r8; lpData
0x18000432b  lea     r9d, [rcx+6]; dwType
0x18000432f  xor     r8d, r8d; Reserved
0x180004332  mov     rdx, r13; lpValueName
0x180004335  mov     rcx, [r12]; hKey
0x180004339  call    cs:__imp_RegSetValueExW
0x18000433f  mov     esi, eax
0x180004341  mov     rdi, [rsp+22F8h+var_2158]
0x180004349  jmp     short loc_180004350
0x18000434b  mov     esi, 0Eh
0x180004350  lea     rax, [rsp+22F8h+var_2150]
0x180004358  cmp     rdi, rax
0x18000435b  jz      short loc_18000436A
0x18000435d  lea     rcx, [rsp+22F8h+var_2158]
0x180004365  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000436a  mov     r15, [rsp+22F8h+var_22C0]
0x18000436f  test    esi, esi
0x180004371  jz      loc_180004635
0x180004377  mov     ecx, esi; unsigned int
0x180004379  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000437e  jmp     loc_180004157
0x180004383  mov     [rsp+22F8h+pulOut], ebx
0x180004387  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x18000438c  xor     r8d, r8d; dwFlags
0x18000438f  xor     edx, edx; lcid
0x180004391  lea     rcx, [rsp+22F8h+String1]; strIn
0x180004399  call    cs:__imp_VarUI4FromStr
0x18000439f  test    eax, eax
0x1800043a1  js      loc_180004157
0x1800043a7  mov     eax, [rsp+22F8h+pulOut]
0x1800043ab  mov     dword ptr [rsp+22F8h+Data], eax
0x1800043af  mov     [rsp+22F8h+cbData], 4; cbData
0x1800043b7  lea     rax, [rsp+22F8h+Data]
0x1800043bc  mov     r9d, 4; dwType
0x1800043c2  mov     [rsp+22F8h+lpData], rax; lpData
0x1800043c7  xor     r8d, r8d; Reserved
0x1800043ca  mov     rdx, r14; lpValueName
0x1800043cd  mov     rcx, [r12]; hKey
0x1800043d1  call    cs:__imp_RegSetValueExW
0x1800043d7  mov     esi, eax
0x1800043d9  jmp     short loc_18000436F
0x1800043db  lea     rax, [rsp+22F8h+String1]
0x1800043e3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800043e7  mov     r14, rsi
0x1800043ea  inc     r14
0x1800043ed  cmp     [rax+r14*2], bx
0x1800043f2  jnz     short loc_1800043EA
0x1800043f4  mov     dword ptr [rsp+22F8h+Data], r14d
0x1800043f9  test    r14b, 1
0x1800043fd  jnz     loc_1800044B7
0x180004403  mov     eax, r14d
0x180004406  cdq
0x180004407  sub     eax, edx
0x180004409  sar     eax, 1
0x18000440b  movsxd  r12, eax
0x18000440e  mov     [rsp+22F8h+var_2268], rbx
0x180004416  mov     rdi, r12
0x180004419  mov     [rsp+22F8h+var_2280], r12
0x18000441e  test    eax, eax
0x180004420  jz      short loc_180004457
0x180004422  xor     edx, edx
0x180004424  mov     rax, rsi
0x180004427  div     rdi
0x18000442a  cmp     rax, 1
0x18000442e  jb      loc_180004678
0x180004434  cmp     rdi, 100h
0x18000443b  jbe     short loc_180004457
0x18000443d  mov     rdx, rdi
0x180004440  lea     rcx, [rsp+22F8h+var_2268]
0x180004448  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000444d  mov     rcx, [rsp+22F8h+var_2268]
0x180004455  jmp     short loc_180004467
0x180004457  lea     rcx, [rsp+22F8h+var_2260]
0x18000445f  mov     [rsp+22F8h+var_2268], rcx
0x180004467  mov     rsi, [rsp+22F8h+var_2288]
0x18000446c  jmp     short loc_1800044A5
0x18000446e  xor     ebx, ebx
0x180004470  lea     r13d, [rbx+8]
0x180004474  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180004479  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180004481  mov     rdi, [rsp+22F8h+var_2280]
0x180004486  mov     rax, [rsp+22F8h+var_22A8]
0x18000448b  mov     [rsp+22F8h+var_22C0], rax
0x180004490  mov     rsi, [rsp+22F8h+var_2278]
0x180004498  mov     rax, [rsp+22F8h+var_2298]
0x18000449d  mov     [rsp+22F8h+lpValueName], rax
0x1800044a2  mov     r12d, edi
0x1800044a5  test    rcx, rcx
0x1800044a8  jnz     short loc_1800044C1
0x1800044aa  lea     rcx, [rsp+22F8h+var_2268]
0x1800044b2  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800044b7  mov     eax, 80004005h
0x1800044bc  jmp     loc_180004157
0x1800044c1  mov     r8, rdi; Size
0x1800044c4  xor     edx, edx; Val
0x1800044c6  call    memset_0
0x1800044cb  mov     r10d, ebx
0x1800044ce  test    r14d, r14d
0x1800044d1  jle     loc_1800045AF
0x1800044d7  mov     r15d, 30h ; '0'
0x1800044dd  mov     eax, r10d
0x1800044e0  movzx   edx, [rsp+rax*2+22F8h+String1]
0x1800044e8  cmp     edx, 61h ; 'a'
0x1800044eb  ja      short loc_18000455A
0x1800044ed  jz      loc_18000457A
0x1800044f3  cmp     edx, 38h ; '8'
0x1800044f6  ja      short loc_18000452C
0x1800044f8  jz      short loc_180004524
0x1800044fa  mov     ecx, edx
0x1800044fc  sub     ecx, r15d
0x1800044ff  jz      short loc_180004524
0x180004501  sub     ecx, 1
0x180004504  jz      short loc_180004524
0x180004506  sub     ecx, 1
0x180004509  jz      short loc_180004524
0x18000450b  sub     ecx, 1
0x18000450e  jz      short loc_180004524
0x180004510  sub     ecx, 1
0x180004513  jz      short loc_180004524
0x180004515  sub     ecx, 1
0x180004518  jz      short loc_180004524
0x18000451a  sub     ecx, 1
0x18000451d  jz      short loc_180004524
0x18000451f  cmp     ecx, 1
0x180004522  jnz     short loc_180004575
0x180004524  mov     r9d, edx
0x180004527  sub     r9d, r15d
0x18000452a  jmp     short loc_18000457E
0x18000452c  mov     r9d, edx
0x18000452f  mov     ecx, edx
0x180004531  sub     ecx, 39h ; '9'
0x180004534  jz      short loc_180004524
0x180004536  sub     ecx, r13d
0x180004539  jz      short loc_180004554
0x18000453b  sub     ecx, 1
0x18000453e  jz      short loc_180004554
0x180004540  sub     ecx, 1
0x180004543  jz      short loc_180004554
0x180004545  sub     ecx, 1
0x180004548  jz      short loc_180004554
0x18000454a  sub     ecx, 1
0x18000454d  jz      short loc_180004554
0x18000454f  cmp     ecx, 1
0x180004552  jnz     short loc_180004575
0x180004554  add     r9d, 0FFFFFFC9h
0x180004558  jmp     short loc_18000457E
  ... truncated ...
```
