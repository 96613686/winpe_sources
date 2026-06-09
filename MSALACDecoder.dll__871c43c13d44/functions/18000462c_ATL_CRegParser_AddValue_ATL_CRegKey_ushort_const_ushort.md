# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000462c`
- end: `0x180004c00`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000607c`

## callees

- `0x180001550`
- `0x180001eac`
- `0x18000462c`
- `0x180004c08`
- `0x180004e28`
- `0x180004e40`
- `0x180005404`
- `0x180005630`
- `0x180009f10`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004915`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004915`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800048b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000494d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004b4e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800048b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000494d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004b4e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000482c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004848`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bd0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000482c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004848`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bd0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800046bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800046bd`

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
  WCHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

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
0x18000462c  push    rbx
0x18000462e  push    rsi
0x18000462f  push    rdi
0x180004630  push    r12
0x180004632  push    r13
0x180004634  push    r14
0x180004636  push    r15
0x180004638  mov     eax, 22C0h
0x18000463d  call    _alloca_probe
0x180004642  sub     rsp, rax
0x180004645  mov     rax, cs:__security_cookie
0x18000464c  xor     rax, rsp
0x18000464f  mov     [rsp+22F8h+var_48], rax
0x180004657  mov     r14, r8
0x18000465a  mov     [rsp+22F8h+lpValueName], r8
0x18000465f  mov     r12, rdx
0x180004662  mov     [rsp+22F8h+var_2288], rdx
0x180004667  mov     r15, rcx
0x18000466a  mov     [rsp+22F8h+var_22C0], rcx
0x18000466f  mov     qword ptr [rsp+22F8h+Data], rdx
0x180004674  mov     [rsp+22F8h+var_22A8], rcx
0x180004679  mov     [rsp+22F8h+var_2278], rdx
0x180004681  mov     [rsp+22F8h+var_2298], r8
0x180004686  mov     [rsp+22F8h+var_2270], r9
0x18000468e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180004696  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000469b  xor     ebx, ebx
0x18000469d  test    eax, eax
0x18000469f  js      short loc_1800046D3
0x1800046a1  mov     edi, ebx
0x1800046a3  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800046aa  movsxd  rsi, edi
0x1800046ad  add     rsi, rsi
0x1800046b0  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800046b5  lea     rcx, [rsp+22F8h+String1]; lpString1
0x1800046bd  call    cs:__imp_lstrcmpiW
0x1800046c3  test    eax, eax
0x1800046c5  jz      short loc_1800046F6
0x1800046c7  inc     edi
0x1800046c9  cmp     edi, 4
0x1800046cc  jb      short loc_1800046AA
0x1800046ce  mov     eax, 80020009h
0x1800046d3  mov     rcx, [rsp+22F8h+var_48]
0x1800046db  xor     rcx, rsp; StackCookie
0x1800046de  call    __security_check_cookie
0x1800046e3  add     rsp, 22C0h
0x1800046ea  pop     r15
0x1800046ec  pop     r14
0x1800046ee  pop     r13
0x1800046f0  pop     r12
0x1800046f2  pop     rdi
0x1800046f3  pop     rsi
0x1800046f4  pop     rbx
0x1800046f5  retn
0x1800046f6  movzx   edi, word ptr [r13+rsi*8+8]
0x1800046fc  mov     esi, 13h
0x180004701  mov     rdx, [r15]
0x180004704  movzx   ecx, word ptr [rdx]
0x180004707  sub     ecx, 9
0x18000470a  jz      loc_180004BCD
0x180004710  sub     ecx, 1
0x180004713  jz      loc_180004BCD
0x180004719  sub     ecx, 3
0x18000471c  jz      loc_180004BCD
0x180004722  cmp     ecx, esi
0x180004724  jz      loc_180004BCD
0x18000472a  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180004732  mov     rcx, r15; this
0x180004735  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000473a  test    eax, eax
0x18000473c  js      short loc_1800046D3
0x18000473e  mov     r13d, 8
0x180004744  cmp     di, r13w
0x180004748  jz      loc_180004B7E
0x18000474e  cmp     di, 11h
0x180004752  jz      loc_180004957
0x180004758  cmp     di, si
0x18000475b  jz      loc_1800048FF
0x180004761  mov     eax, 4008h
0x180004766  cmp     di, ax
0x180004769  jnz     loc_180004BB1
0x18000476f  lea     rcx, [rsp+22F8h+String1]
0x180004777  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000477b  mov     rax, rsi
0x18000477e  inc     rax
0x180004781  cmp     [rcx+rax*2], bx
0x180004785  jnz     short loc_18000477E
0x180004787  add     eax, 2
0x18000478a  mov     [rsp+22F8h+var_2158], rbx
0x180004792  test    eax, eax
0x180004794  jz      short loc_1800047CF
0x180004796  movsxd  rcx, eax
0x180004799  xor     edx, edx
0x18000479b  mov     rax, rsi
0x18000479e  div     rcx
0x1800047a1  cmp     rax, 2
0x1800047a5  jb      loc_180004BDE
0x1800047ab  lea     rdx, [rcx+rcx]
0x1800047af  cmp     rdx, 100h
0x1800047b6  jbe     short loc_1800047CF
0x1800047b8  lea     rcx, [rsp+22F8h+var_2158]
0x1800047c0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800047c5  mov     rdi, [rsp+22F8h+var_2158]
0x1800047cd  jmp     short loc_1800047DF
0x1800047cf  lea     rdi, [rsp+22F8h+var_2150]
0x1800047d7  mov     [rsp+22F8h+var_2158], rdi
0x1800047df  mov     r13, [rsp+22F8h+lpValueName]
0x1800047e4  jmp     short loc_180004808
0x1800047e6  xor     ebx, ebx
0x1800047e8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800047ec  mov     rdi, [rsp+22F8h+var_2158]
0x1800047f4  mov     r12, qword ptr [rsp+22F8h+Data]
0x1800047f9  mov     rax, [rsp+22F8h+var_22A8]
0x1800047fe  mov     [rsp+22F8h+var_22C0], rax
0x180004803  mov     r13, [rsp+22F8h+var_2298]
0x180004808  test    rdi, rdi
0x18000480b  jz      loc_1800048C7
0x180004811  lea     r14, [rsp+22F8h+String1]
0x180004819  cmp     [rsp+22F8h+String1], bx
0x180004821  jz      short loc_180004864
0x180004823  mov     r15d, 30h ; '0'
0x180004829  mov     rcx, r14; lpsz
0x18000482c  call    cs:__imp_CharNextW
0x180004832  movzx   ecx, word ptr [r14]
0x180004836  cmp     cx, 5Ch ; '\'
0x18000483a  jnz     short loc_180004853
0x18000483c  cmp     [rax], r15w
0x180004840  jnz     short loc_180004853
0x180004842  mov     [rdi], bx
0x180004845  mov     rcx, rax; lpsz
0x180004848  call    cs:__imp_CharNextW
0x18000484e  mov     r14, rax
0x180004851  jmp     short loc_18000485A
0x180004853  mov     [rdi], cx
0x180004856  add     r14, 2
0x18000485a  add     rdi, 2
0x18000485e  cmp     [r14], bx
0x180004862  jnz     short loc_180004829
0x180004864  mov     dword ptr [rdi], 0
0x18000486a  mov     r8, [rsp+22F8h+var_2158]
0x180004872  test    r8, r8
0x180004875  jz      loc_180004BE9
0x18000487b  mov     r10d, ebx
0x18000487e  mov     r9, r8
0x180004881  mov     rcx, rsi
0x180004884  inc     rcx
0x180004887  cmp     [r9+rcx*2], bx
0x18000488c  jnz     short loc_180004884
0x18000488e  inc     ecx
0x180004890  lea     r9, [r9+rcx*2]
0x180004894  lea     r10d, [r10+rcx*2]
0x180004898  cmp     ecx, 1
0x18000489b  jnz     short loc_180004881
0x18000489d  mov     [rsp+22F8h+cbData], r10d; cbData
0x1800048a2  mov     [rsp+22F8h+lpData], r8; lpData
0x1800048a7  lea     r9d, [rcx+6]; dwType
0x1800048ab  xor     r8d, r8d; Reserved
0x1800048ae  mov     rdx, r13; lpValueName
0x1800048b1  mov     rcx, [r12]; hKey
0x1800048b5  call    cs:__imp_RegSetValueExW
0x1800048bb  mov     esi, eax
0x1800048bd  mov     rdi, [rsp+22F8h+var_2158]
0x1800048c5  jmp     short loc_1800048CC
0x1800048c7  mov     esi, 0Eh
0x1800048cc  lea     rax, [rsp+22F8h+var_2150]
0x1800048d4  cmp     rdi, rax
0x1800048d7  jz      short loc_1800048E6
0x1800048d9  lea     rcx, [rsp+22F8h+var_2158]
0x1800048e1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800048e6  mov     r15, [rsp+22F8h+var_22C0]
0x1800048eb  test    esi, esi
0x1800048ed  jz      loc_180004BB1
0x1800048f3  mov     ecx, esi; unsigned int
0x1800048f5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800048fa  jmp     loc_1800046D3
0x1800048ff  mov     [rsp+22F8h+pulOut], ebx
0x180004903  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180004908  xor     r8d, r8d; dwFlags
0x18000490b  xor     edx, edx; lcid
0x18000490d  lea     rcx, [rsp+22F8h+String1]; strIn
0x180004915  call    cs:__imp_VarUI4FromStr
0x18000491b  test    eax, eax
0x18000491d  js      loc_1800046D3
0x180004923  mov     eax, [rsp+22F8h+pulOut]
0x180004927  mov     dword ptr [rsp+22F8h+Data], eax
0x18000492b  mov     [rsp+22F8h+cbData], 4; cbData
0x180004933  lea     rax, [rsp+22F8h+Data]
0x180004938  mov     r9d, 4; dwType
0x18000493e  mov     [rsp+22F8h+lpData], rax; lpData
0x180004943  xor     r8d, r8d; Reserved
0x180004946  mov     rdx, r14; lpValueName
0x180004949  mov     rcx, [r12]; hKey
0x18000494d  call    cs:__imp_RegSetValueExW
0x180004953  mov     esi, eax
0x180004955  jmp     short loc_1800048EB
0x180004957  lea     rax, [rsp+22F8h+String1]
0x18000495f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004963  mov     r14, rsi
0x180004966  inc     r14
0x180004969  cmp     [rax+r14*2], bx
0x18000496e  jnz     short loc_180004966
0x180004970  mov     dword ptr [rsp+22F8h+Data], r14d
0x180004975  test    r14b, 1
0x180004979  jnz     loc_180004A33
0x18000497f  mov     eax, r14d
0x180004982  cdq
0x180004983  sub     eax, edx
0x180004985  sar     eax, 1
0x180004987  movsxd  r12, eax
0x18000498a  mov     [rsp+22F8h+var_2268], rbx
0x180004992  mov     rdi, r12
0x180004995  mov     [rsp+22F8h+var_2280], r12
0x18000499a  test    eax, eax
0x18000499c  jz      short loc_1800049D3
0x18000499e  xor     edx, edx
0x1800049a0  mov     rax, rsi
0x1800049a3  div     rdi
0x1800049a6  cmp     rax, 1
0x1800049aa  jb      loc_180004BF4
0x1800049b0  cmp     rdi, 100h
0x1800049b7  jbe     short loc_1800049D3
0x1800049b9  mov     rdx, rdi
0x1800049bc  lea     rcx, [rsp+22F8h+var_2268]
0x1800049c4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800049c9  mov     rcx, [rsp+22F8h+var_2268]
0x1800049d1  jmp     short loc_1800049E3
0x1800049d3  lea     rcx, [rsp+22F8h+var_2260]
0x1800049db  mov     [rsp+22F8h+var_2268], rcx
0x1800049e3  mov     rsi, [rsp+22F8h+var_2288]
0x1800049e8  jmp     short loc_180004A21
0x1800049ea  xor     ebx, ebx
0x1800049ec  lea     r13d, [rbx+8]
0x1800049f0  mov     r14d, dword ptr [rsp+22F8h+Data]
0x1800049f5  mov     rcx, [rsp+22F8h+var_2268]; void *
0x1800049fd  mov     rdi, [rsp+22F8h+var_2280]
0x180004a02  mov     rax, [rsp+22F8h+var_22A8]
0x180004a07  mov     [rsp+22F8h+var_22C0], rax
0x180004a0c  mov     rsi, [rsp+22F8h+var_2278]
0x180004a14  mov     rax, [rsp+22F8h+var_2298]
0x180004a19  mov     [rsp+22F8h+lpValueName], rax
0x180004a1e  mov     r12d, edi
0x180004a21  test    rcx, rcx
0x180004a24  jnz     short loc_180004A3D
0x180004a26  lea     rcx, [rsp+22F8h+var_2268]
0x180004a2e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004a33  mov     eax, 80004005h
0x180004a38  jmp     loc_1800046D3
0x180004a3d  mov     r8, rdi; Size
0x180004a40  xor     edx, edx; Val
0x180004a42  call    memset_0
0x180004a47  mov     r10d, ebx
0x180004a4a  test    r14d, r14d
0x180004a4d  jle     loc_180004B2B
0x180004a53  mov     r15d, 30h ; '0'
0x180004a59  mov     eax, r10d
0x180004a5c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180004a64  cmp     edx, 61h ; 'a'
0x180004a67  ja      short loc_180004AD6
0x180004a69  jz      loc_180004AF6
0x180004a6f  cmp     edx, 38h ; '8'
0x180004a72  ja      short loc_180004AA8
0x180004a74  jz      short loc_180004AA0
0x180004a76  mov     ecx, edx
0x180004a78  sub     ecx, r15d
0x180004a7b  jz      short loc_180004AA0
0x180004a7d  sub     ecx, 1
0x180004a80  jz      short loc_180004AA0
0x180004a82  sub     ecx, 1
0x180004a85  jz      short loc_180004AA0
0x180004a87  sub     ecx, 1
0x180004a8a  jz      short loc_180004AA0
0x180004a8c  sub     ecx, 1
0x180004a8f  jz      short loc_180004AA0
0x180004a91  sub     ecx, 1
0x180004a94  jz      short loc_180004AA0
0x180004a96  sub     ecx, 1
0x180004a99  jz      short loc_180004AA0
0x180004a9b  cmp     ecx, 1
0x180004a9e  jnz     short loc_180004AF1
0x180004aa0  mov     r9d, edx
0x180004aa3  sub     r9d, r15d
0x180004aa6  jmp     short loc_180004AFA
0x180004aa8  mov     r9d, edx
0x180004aab  mov     ecx, edx
0x180004aad  sub     ecx, 39h ; '9'
0x180004ab0  jz      short loc_180004AA0
0x180004ab2  sub     ecx, r13d
0x180004ab5  jz      short loc_180004AD0
0x180004ab7  sub     ecx, 1
0x180004aba  jz      short loc_180004AD0
0x180004abc  sub     ecx, 1
0x180004abf  jz      short loc_180004AD0
0x180004ac1  sub     ecx, 1
0x180004ac4  jz      short loc_180004AD0
0x180004ac6  sub     ecx, 1
0x180004ac9  jz      short loc_180004AD0
0x180004acb  cmp     ecx, 1
0x180004ace  jnz     short loc_180004AF1
0x180004ad0  add     r9d, 0FFFFFFC9h
0x180004ad4  jmp     short loc_180004AFA
  ... truncated ...
```
