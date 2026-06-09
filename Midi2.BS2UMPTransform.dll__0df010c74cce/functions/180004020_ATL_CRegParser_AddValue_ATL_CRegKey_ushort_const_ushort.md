# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180004020`
- end: `0x1800045f4`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180006b7c`

## callees

- `0x180001e60`
- `0x1800028c8`
- `0x180004020`
- `0x1800045fc`
- `0x180004750`
- `0x180004768`
- `0x180004f58`
- `0x18000604c`
- `0x18000b390`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004309`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004309`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004341`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004542`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004341`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004542`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004220`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000423c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800045c4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004220`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000423c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800045c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800040b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800040b1`

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
0x180004020  push    rbx
0x180004022  push    rsi
0x180004023  push    rdi
0x180004024  push    r12
0x180004026  push    r13
0x180004028  push    r14
0x18000402a  push    r15
0x18000402c  mov     eax, 22C0h
0x180004031  call    _alloca_probe
0x180004036  sub     rsp, rax
0x180004039  mov     rax, cs:__security_cookie
0x180004040  xor     rax, rsp
0x180004043  mov     [rsp+22F8h+var_48], rax
0x18000404b  mov     r14, r8
0x18000404e  mov     [rsp+22F8h+lpValueName], r8
0x180004053  mov     r12, rdx
0x180004056  mov     [rsp+22F8h+var_2288], rdx
0x18000405b  mov     r15, rcx
0x18000405e  mov     [rsp+22F8h+var_22C0], rcx
0x180004063  mov     qword ptr [rsp+22F8h+Data], rdx
0x180004068  mov     [rsp+22F8h+var_22A8], rcx
0x18000406d  mov     [rsp+22F8h+var_2278], rdx
0x180004075  mov     [rsp+22F8h+var_2298], r8
0x18000407a  mov     [rsp+22F8h+var_2270], r9
0x180004082  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18000408a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000408f  xor     ebx, ebx
0x180004091  test    eax, eax
0x180004093  js      short loc_1800040C7
0x180004095  mov     edi, ebx
0x180004097  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000409e  movsxd  rsi, edi
0x1800040a1  add     rsi, rsi
0x1800040a4  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800040a9  lea     rcx, [rsp+22F8h+String1]; lpString1
0x1800040b1  call    cs:__imp_lstrcmpiW
0x1800040b7  test    eax, eax
0x1800040b9  jz      short loc_1800040EA
0x1800040bb  inc     edi
0x1800040bd  cmp     edi, 4
0x1800040c0  jb      short loc_18000409E
0x1800040c2  mov     eax, 80020009h
0x1800040c7  mov     rcx, [rsp+22F8h+var_48]
0x1800040cf  xor     rcx, rsp; StackCookie
0x1800040d2  call    __security_check_cookie
0x1800040d7  add     rsp, 22C0h
0x1800040de  pop     r15
0x1800040e0  pop     r14
0x1800040e2  pop     r13
0x1800040e4  pop     r12
0x1800040e6  pop     rdi
0x1800040e7  pop     rsi
0x1800040e8  pop     rbx
0x1800040e9  retn
0x1800040ea  movzx   edi, word ptr [r13+rsi*8+8]
0x1800040f0  mov     esi, 13h
0x1800040f5  mov     rdx, [r15]
0x1800040f8  movzx   ecx, word ptr [rdx]
0x1800040fb  sub     ecx, 9
0x1800040fe  jz      loc_1800045C1
0x180004104  sub     ecx, 1
0x180004107  jz      loc_1800045C1
0x18000410d  sub     ecx, 3
0x180004110  jz      loc_1800045C1
0x180004116  cmp     ecx, esi
0x180004118  jz      loc_1800045C1
0x18000411e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180004126  mov     rcx, r15; this
0x180004129  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000412e  test    eax, eax
0x180004130  js      short loc_1800040C7
0x180004132  mov     r13d, 8
0x180004138  cmp     di, r13w
0x18000413c  jz      loc_180004572
0x180004142  cmp     di, 11h
0x180004146  jz      loc_18000434B
0x18000414c  cmp     di, si
0x18000414f  jz      loc_1800042F3
0x180004155  mov     eax, 4008h
0x18000415a  cmp     di, ax
0x18000415d  jnz     loc_1800045A5
0x180004163  lea     rcx, [rsp+22F8h+String1]
0x18000416b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000416f  mov     rax, rsi
0x180004172  inc     rax
0x180004175  cmp     [rcx+rax*2], bx
0x180004179  jnz     short loc_180004172
0x18000417b  add     eax, 2
0x18000417e  mov     [rsp+22F8h+var_2158], rbx
0x180004186  test    eax, eax
0x180004188  jz      short loc_1800041C3
0x18000418a  movsxd  rcx, eax
0x18000418d  xor     edx, edx
0x18000418f  mov     rax, rsi
0x180004192  div     rcx
0x180004195  cmp     rax, 2
0x180004199  jb      loc_1800045D2
0x18000419f  lea     rdx, [rcx+rcx]
0x1800041a3  cmp     rdx, 100h
0x1800041aa  jbe     short loc_1800041C3
0x1800041ac  lea     rcx, [rsp+22F8h+var_2158]
0x1800041b4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800041b9  mov     rdi, [rsp+22F8h+var_2158]
0x1800041c1  jmp     short loc_1800041D3
0x1800041c3  lea     rdi, [rsp+22F8h+var_2150]
0x1800041cb  mov     [rsp+22F8h+var_2158], rdi
0x1800041d3  mov     r13, [rsp+22F8h+lpValueName]
0x1800041d8  jmp     short loc_1800041FC
0x1800041da  xor     ebx, ebx
0x1800041dc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800041e0  mov     rdi, [rsp+22F8h+var_2158]
0x1800041e8  mov     r12, qword ptr [rsp+22F8h+Data]
0x1800041ed  mov     rax, [rsp+22F8h+var_22A8]
0x1800041f2  mov     [rsp+22F8h+var_22C0], rax
0x1800041f7  mov     r13, [rsp+22F8h+var_2298]
0x1800041fc  test    rdi, rdi
0x1800041ff  jz      loc_1800042BB
0x180004205  lea     r14, [rsp+22F8h+String1]
0x18000420d  cmp     [rsp+22F8h+String1], bx
0x180004215  jz      short loc_180004258
0x180004217  mov     r15d, 30h ; '0'
0x18000421d  mov     rcx, r14; lpsz
0x180004220  call    cs:__imp_CharNextW
0x180004226  movzx   ecx, word ptr [r14]
0x18000422a  cmp     cx, 5Ch ; '\'
0x18000422e  jnz     short loc_180004247
0x180004230  cmp     [rax], r15w
0x180004234  jnz     short loc_180004247
0x180004236  mov     [rdi], bx
0x180004239  mov     rcx, rax; lpsz
0x18000423c  call    cs:__imp_CharNextW
0x180004242  mov     r14, rax
0x180004245  jmp     short loc_18000424E
0x180004247  mov     [rdi], cx
0x18000424a  add     r14, 2
0x18000424e  add     rdi, 2
0x180004252  cmp     [r14], bx
0x180004256  jnz     short loc_18000421D
0x180004258  mov     dword ptr [rdi], 0
0x18000425e  mov     r8, [rsp+22F8h+var_2158]
0x180004266  test    r8, r8
0x180004269  jz      loc_1800045DD
0x18000426f  mov     r10d, ebx
0x180004272  mov     r9, r8
0x180004275  mov     rcx, rsi
0x180004278  inc     rcx
0x18000427b  cmp     [r9+rcx*2], bx
0x180004280  jnz     short loc_180004278
0x180004282  inc     ecx
0x180004284  lea     r9, [r9+rcx*2]
0x180004288  lea     r10d, [r10+rcx*2]
0x18000428c  cmp     ecx, 1
0x18000428f  jnz     short loc_180004275
0x180004291  mov     [rsp+22F8h+cbData], r10d; cbData
0x180004296  mov     [rsp+22F8h+lpData], r8; lpData
0x18000429b  lea     r9d, [rcx+6]; dwType
0x18000429f  xor     r8d, r8d; Reserved
0x1800042a2  mov     rdx, r13; lpValueName
0x1800042a5  mov     rcx, [r12]; hKey
0x1800042a9  call    cs:__imp_RegSetValueExW
0x1800042af  mov     esi, eax
0x1800042b1  mov     rdi, [rsp+22F8h+var_2158]
0x1800042b9  jmp     short loc_1800042C0
0x1800042bb  mov     esi, 0Eh
0x1800042c0  lea     rax, [rsp+22F8h+var_2150]
0x1800042c8  cmp     rdi, rax
0x1800042cb  jz      short loc_1800042DA
0x1800042cd  lea     rcx, [rsp+22F8h+var_2158]
0x1800042d5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800042da  mov     r15, [rsp+22F8h+var_22C0]
0x1800042df  test    esi, esi
0x1800042e1  jz      loc_1800045A5
0x1800042e7  mov     ecx, esi; unsigned int
0x1800042e9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800042ee  jmp     loc_1800040C7
0x1800042f3  mov     [rsp+22F8h+pulOut], ebx
0x1800042f7  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x1800042fc  xor     r8d, r8d; dwFlags
0x1800042ff  xor     edx, edx; lcid
0x180004301  lea     rcx, [rsp+22F8h+String1]; strIn
0x180004309  call    cs:__imp_VarUI4FromStr
0x18000430f  test    eax, eax
0x180004311  js      loc_1800040C7
0x180004317  mov     eax, [rsp+22F8h+pulOut]
0x18000431b  mov     dword ptr [rsp+22F8h+Data], eax
0x18000431f  mov     [rsp+22F8h+cbData], 4; cbData
0x180004327  lea     rax, [rsp+22F8h+Data]
0x18000432c  mov     r9d, 4; dwType
0x180004332  mov     [rsp+22F8h+lpData], rax; lpData
0x180004337  xor     r8d, r8d; Reserved
0x18000433a  mov     rdx, r14; lpValueName
0x18000433d  mov     rcx, [r12]; hKey
0x180004341  call    cs:__imp_RegSetValueExW
0x180004347  mov     esi, eax
0x180004349  jmp     short loc_1800042DF
0x18000434b  lea     rax, [rsp+22F8h+String1]
0x180004353  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004357  mov     r14, rsi
0x18000435a  inc     r14
0x18000435d  cmp     [rax+r14*2], bx
0x180004362  jnz     short loc_18000435A
0x180004364  mov     dword ptr [rsp+22F8h+Data], r14d
0x180004369  test    r14b, 1
0x18000436d  jnz     loc_180004427
0x180004373  mov     eax, r14d
0x180004376  cdq
0x180004377  sub     eax, edx
0x180004379  sar     eax, 1
0x18000437b  movsxd  r12, eax
0x18000437e  mov     [rsp+22F8h+var_2268], rbx
0x180004386  mov     rdi, r12
0x180004389  mov     [rsp+22F8h+var_2280], r12
0x18000438e  test    eax, eax
0x180004390  jz      short loc_1800043C7
0x180004392  xor     edx, edx
0x180004394  mov     rax, rsi
0x180004397  div     rdi
0x18000439a  cmp     rax, 1
0x18000439e  jb      loc_1800045E8
0x1800043a4  cmp     rdi, 100h
0x1800043ab  jbe     short loc_1800043C7
0x1800043ad  mov     rdx, rdi
0x1800043b0  lea     rcx, [rsp+22F8h+var_2268]
0x1800043b8  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800043bd  mov     rcx, [rsp+22F8h+var_2268]
0x1800043c5  jmp     short loc_1800043D7
0x1800043c7  lea     rcx, [rsp+22F8h+var_2260]
0x1800043cf  mov     [rsp+22F8h+var_2268], rcx
0x1800043d7  mov     rsi, [rsp+22F8h+var_2288]
0x1800043dc  jmp     short loc_180004415
0x1800043de  xor     ebx, ebx
0x1800043e0  lea     r13d, [rbx+8]
0x1800043e4  mov     r14d, dword ptr [rsp+22F8h+Data]
0x1800043e9  mov     rcx, [rsp+22F8h+var_2268]; void *
0x1800043f1  mov     rdi, [rsp+22F8h+var_2280]
0x1800043f6  mov     rax, [rsp+22F8h+var_22A8]
0x1800043fb  mov     [rsp+22F8h+var_22C0], rax
0x180004400  mov     rsi, [rsp+22F8h+var_2278]
0x180004408  mov     rax, [rsp+22F8h+var_2298]
0x18000440d  mov     [rsp+22F8h+lpValueName], rax
0x180004412  mov     r12d, edi
0x180004415  test    rcx, rcx
0x180004418  jnz     short loc_180004431
0x18000441a  lea     rcx, [rsp+22F8h+var_2268]
0x180004422  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004427  mov     eax, 80004005h
0x18000442c  jmp     loc_1800040C7
0x180004431  mov     r8, rdi; Size
0x180004434  xor     edx, edx; Val
0x180004436  call    memset_0
0x18000443b  mov     r10d, ebx
0x18000443e  test    r14d, r14d
0x180004441  jle     loc_18000451F
0x180004447  mov     r15d, 30h ; '0'
0x18000444d  mov     eax, r10d
0x180004450  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180004458  cmp     edx, 61h ; 'a'
0x18000445b  ja      short loc_1800044CA
0x18000445d  jz      loc_1800044EA
0x180004463  cmp     edx, 38h ; '8'
0x180004466  ja      short loc_18000449C
0x180004468  jz      short loc_180004494
0x18000446a  mov     ecx, edx
0x18000446c  sub     ecx, r15d
0x18000446f  jz      short loc_180004494
0x180004471  sub     ecx, 1
0x180004474  jz      short loc_180004494
0x180004476  sub     ecx, 1
0x180004479  jz      short loc_180004494
0x18000447b  sub     ecx, 1
0x18000447e  jz      short loc_180004494
0x180004480  sub     ecx, 1
0x180004483  jz      short loc_180004494
0x180004485  sub     ecx, 1
0x180004488  jz      short loc_180004494
0x18000448a  sub     ecx, 1
0x18000448d  jz      short loc_180004494
0x18000448f  cmp     ecx, 1
0x180004492  jnz     short loc_1800044E5
0x180004494  mov     r9d, edx
0x180004497  sub     r9d, r15d
0x18000449a  jmp     short loc_1800044EE
0x18000449c  mov     r9d, edx
0x18000449f  mov     ecx, edx
0x1800044a1  sub     ecx, 39h ; '9'
0x1800044a4  jz      short loc_180004494
0x1800044a6  sub     ecx, r13d
0x1800044a9  jz      short loc_1800044C4
0x1800044ab  sub     ecx, 1
0x1800044ae  jz      short loc_1800044C4
0x1800044b0  sub     ecx, 1
0x1800044b3  jz      short loc_1800044C4
0x1800044b5  sub     ecx, 1
0x1800044b8  jz      short loc_1800044C4
0x1800044ba  sub     ecx, 1
0x1800044bd  jz      short loc_1800044C4
0x1800044bf  cmp     ecx, 1
0x1800044c2  jnz     short loc_1800044E5
0x1800044c4  add     r9d, 0FFFFFFC9h
0x1800044c8  jmp     short loc_1800044EE
  ... truncated ...
```
