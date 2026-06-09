# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180004770`
- end: `0x180004d44`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800072dc`

## callees

- `0x180002470`
- `0x180002ff8`
- `0x180004770`
- `0x180004d4c`
- `0x180004ea0`
- `0x180004eb8`
- `0x1800056a8`
- `0x1800067ac`
- `0x180014020`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004a59`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180004a59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004c92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004c92`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004970`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000498c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004d14`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004970`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000498c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004d14`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004801`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004801`

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
0x180004770  push    rbx
0x180004772  push    rsi
0x180004773  push    rdi
0x180004774  push    r12
0x180004776  push    r13
0x180004778  push    r14
0x18000477a  push    r15
0x18000477c  mov     eax, 22C0h
0x180004781  call    _alloca_probe
0x180004786  sub     rsp, rax
0x180004789  mov     rax, cs:__security_cookie
0x180004790  xor     rax, rsp
0x180004793  mov     [rsp+22F8h+var_48], rax
0x18000479b  mov     r14, r8
0x18000479e  mov     [rsp+22F8h+lpValueName], r8
0x1800047a3  mov     r12, rdx
0x1800047a6  mov     [rsp+22F8h+var_2288], rdx
0x1800047ab  mov     r15, rcx
0x1800047ae  mov     [rsp+22F8h+var_22C0], rcx
0x1800047b3  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800047b8  mov     [rsp+22F8h+var_22A8], rcx
0x1800047bd  mov     [rsp+22F8h+var_2278], rdx
0x1800047c5  mov     [rsp+22F8h+var_2298], r8
0x1800047ca  mov     [rsp+22F8h+var_2270], r9
0x1800047d2  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800047da  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800047df  xor     ebx, ebx
0x1800047e1  test    eax, eax
0x1800047e3  js      short loc_180004817
0x1800047e5  mov     edi, ebx
0x1800047e7  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800047ee  movsxd  rsi, edi
0x1800047f1  add     rsi, rsi
0x1800047f4  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800047f9  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180004801  call    cs:__imp_lstrcmpiW
0x180004807  test    eax, eax
0x180004809  jz      short loc_18000483A
0x18000480b  inc     edi
0x18000480d  cmp     edi, 4
0x180004810  jb      short loc_1800047EE
0x180004812  mov     eax, 80020009h
0x180004817  mov     rcx, [rsp+22F8h+var_48]
0x18000481f  xor     rcx, rsp; StackCookie
0x180004822  call    __security_check_cookie
0x180004827  add     rsp, 22C0h
0x18000482e  pop     r15
0x180004830  pop     r14
0x180004832  pop     r13
0x180004834  pop     r12
0x180004836  pop     rdi
0x180004837  pop     rsi
0x180004838  pop     rbx
0x180004839  retn
0x18000483a  movzx   edi, word ptr [r13+rsi*8+8]
0x180004840  mov     esi, 13h
0x180004845  mov     rdx, [r15]
0x180004848  movzx   ecx, word ptr [rdx]
0x18000484b  sub     ecx, 9
0x18000484e  jz      loc_180004D11
0x180004854  sub     ecx, 1
0x180004857  jz      loc_180004D11
0x18000485d  sub     ecx, 3
0x180004860  jz      loc_180004D11
0x180004866  cmp     ecx, esi
0x180004868  jz      loc_180004D11
0x18000486e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180004876  mov     rcx, r15; this
0x180004879  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000487e  test    eax, eax
0x180004880  js      short loc_180004817
0x180004882  mov     r13d, 8
0x180004888  cmp     di, r13w
0x18000488c  jz      loc_180004CC2
0x180004892  cmp     di, 11h
0x180004896  jz      loc_180004A9B
0x18000489c  cmp     di, si
0x18000489f  jz      loc_180004A43
0x1800048a5  mov     eax, 4008h
0x1800048aa  cmp     di, ax
0x1800048ad  jnz     loc_180004CF5
0x1800048b3  lea     rcx, [rsp+22F8h+String1]
0x1800048bb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800048bf  mov     rax, rsi
0x1800048c2  inc     rax
0x1800048c5  cmp     [rcx+rax*2], bx
0x1800048c9  jnz     short loc_1800048C2
0x1800048cb  add     eax, 2
0x1800048ce  mov     [rsp+22F8h+var_2158], rbx
0x1800048d6  test    eax, eax
0x1800048d8  jz      short loc_180004913
0x1800048da  movsxd  rcx, eax
0x1800048dd  xor     edx, edx
0x1800048df  mov     rax, rsi
0x1800048e2  div     rcx
0x1800048e5  cmp     rax, 2
0x1800048e9  jb      loc_180004D22
0x1800048ef  lea     rdx, [rcx+rcx]
0x1800048f3  cmp     rdx, 100h
0x1800048fa  jbe     short loc_180004913
0x1800048fc  lea     rcx, [rsp+22F8h+var_2158]
0x180004904  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004909  mov     rdi, [rsp+22F8h+var_2158]
0x180004911  jmp     short loc_180004923
0x180004913  lea     rdi, [rsp+22F8h+var_2150]
0x18000491b  mov     [rsp+22F8h+var_2158], rdi
0x180004923  mov     r13, [rsp+22F8h+lpValueName]
0x180004928  jmp     short loc_18000494C
0x18000492a  xor     ebx, ebx
0x18000492c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004930  mov     rdi, [rsp+22F8h+var_2158]
0x180004938  mov     r12, qword ptr [rsp+22F8h+Data]
0x18000493d  mov     rax, [rsp+22F8h+var_22A8]
0x180004942  mov     [rsp+22F8h+var_22C0], rax
0x180004947  mov     r13, [rsp+22F8h+var_2298]
0x18000494c  test    rdi, rdi
0x18000494f  jz      loc_180004A0B
0x180004955  lea     r14, [rsp+22F8h+String1]
0x18000495d  cmp     [rsp+22F8h+String1], bx
0x180004965  jz      short loc_1800049A8
0x180004967  mov     r15d, 30h ; '0'
0x18000496d  mov     rcx, r14; lpsz
0x180004970  call    cs:__imp_CharNextW
0x180004976  movzx   ecx, word ptr [r14]
0x18000497a  cmp     cx, 5Ch ; '\'
0x18000497e  jnz     short loc_180004997
0x180004980  cmp     [rax], r15w
0x180004984  jnz     short loc_180004997
0x180004986  mov     [rdi], bx
0x180004989  mov     rcx, rax; lpsz
0x18000498c  call    cs:__imp_CharNextW
0x180004992  mov     r14, rax
0x180004995  jmp     short loc_18000499E
0x180004997  mov     [rdi], cx
0x18000499a  add     r14, 2
0x18000499e  add     rdi, 2
0x1800049a2  cmp     [r14], bx
0x1800049a6  jnz     short loc_18000496D
0x1800049a8  mov     dword ptr [rdi], 0
0x1800049ae  mov     r8, [rsp+22F8h+var_2158]
0x1800049b6  test    r8, r8
0x1800049b9  jz      loc_180004D2D
0x1800049bf  mov     r10d, ebx
0x1800049c2  mov     r9, r8
0x1800049c5  mov     rcx, rsi
0x1800049c8  inc     rcx
0x1800049cb  cmp     [r9+rcx*2], bx
0x1800049d0  jnz     short loc_1800049C8
0x1800049d2  inc     ecx
0x1800049d4  lea     r9, [r9+rcx*2]
0x1800049d8  lea     r10d, [r10+rcx*2]
0x1800049dc  cmp     ecx, 1
0x1800049df  jnz     short loc_1800049C5
0x1800049e1  mov     [rsp+22F8h+cbData], r10d; cbData
0x1800049e6  mov     [rsp+22F8h+lpData], r8; lpData
0x1800049eb  lea     r9d, [rcx+6]; dwType
0x1800049ef  xor     r8d, r8d; Reserved
0x1800049f2  mov     rdx, r13; lpValueName
0x1800049f5  mov     rcx, [r12]; hKey
0x1800049f9  call    cs:__imp_RegSetValueExW
0x1800049ff  mov     esi, eax
0x180004a01  mov     rdi, [rsp+22F8h+var_2158]
0x180004a09  jmp     short loc_180004A10
0x180004a0b  mov     esi, 0Eh
0x180004a10  lea     rax, [rsp+22F8h+var_2150]
0x180004a18  cmp     rdi, rax
0x180004a1b  jz      short loc_180004A2A
0x180004a1d  lea     rcx, [rsp+22F8h+var_2158]
0x180004a25  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004a2a  mov     r15, [rsp+22F8h+var_22C0]
0x180004a2f  test    esi, esi
0x180004a31  jz      loc_180004CF5
0x180004a37  mov     ecx, esi; unsigned int
0x180004a39  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180004a3e  jmp     loc_180004817
0x180004a43  mov     [rsp+22F8h+pulOut], ebx
0x180004a47  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180004a4c  xor     r8d, r8d; dwFlags
0x180004a4f  xor     edx, edx; lcid
0x180004a51  lea     rcx, [rsp+22F8h+String1]; strIn
0x180004a59  call    cs:__imp_VarUI4FromStr
0x180004a5f  test    eax, eax
0x180004a61  js      loc_180004817
0x180004a67  mov     eax, [rsp+22F8h+pulOut]
0x180004a6b  mov     dword ptr [rsp+22F8h+Data], eax
0x180004a6f  mov     [rsp+22F8h+cbData], 4; cbData
0x180004a77  lea     rax, [rsp+22F8h+Data]
0x180004a7c  mov     r9d, 4; dwType
0x180004a82  mov     [rsp+22F8h+lpData], rax; lpData
0x180004a87  xor     r8d, r8d; Reserved
0x180004a8a  mov     rdx, r14; lpValueName
0x180004a8d  mov     rcx, [r12]; hKey
0x180004a91  call    cs:__imp_RegSetValueExW
0x180004a97  mov     esi, eax
0x180004a99  jmp     short loc_180004A2F
0x180004a9b  lea     rax, [rsp+22F8h+String1]
0x180004aa3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004aa7  mov     r14, rsi
0x180004aaa  inc     r14
0x180004aad  cmp     [rax+r14*2], bx
0x180004ab2  jnz     short loc_180004AAA
0x180004ab4  mov     dword ptr [rsp+22F8h+Data], r14d
0x180004ab9  test    r14b, 1
0x180004abd  jnz     loc_180004B77
0x180004ac3  mov     eax, r14d
0x180004ac6  cdq
0x180004ac7  sub     eax, edx
0x180004ac9  sar     eax, 1
0x180004acb  movsxd  r12, eax
0x180004ace  mov     [rsp+22F8h+var_2268], rbx
0x180004ad6  mov     rdi, r12
0x180004ad9  mov     [rsp+22F8h+var_2280], r12
0x180004ade  test    eax, eax
0x180004ae0  jz      short loc_180004B17
0x180004ae2  xor     edx, edx
0x180004ae4  mov     rax, rsi
0x180004ae7  div     rdi
0x180004aea  cmp     rax, 1
0x180004aee  jb      loc_180004D38
0x180004af4  cmp     rdi, 100h
0x180004afb  jbe     short loc_180004B17
0x180004afd  mov     rdx, rdi
0x180004b00  lea     rcx, [rsp+22F8h+var_2268]
0x180004b08  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004b0d  mov     rcx, [rsp+22F8h+var_2268]
0x180004b15  jmp     short loc_180004B27
0x180004b17  lea     rcx, [rsp+22F8h+var_2260]
0x180004b1f  mov     [rsp+22F8h+var_2268], rcx
0x180004b27  mov     rsi, [rsp+22F8h+var_2288]
0x180004b2c  jmp     short loc_180004B65
0x180004b2e  xor     ebx, ebx
0x180004b30  lea     r13d, [rbx+8]
0x180004b34  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180004b39  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180004b41  mov     rdi, [rsp+22F8h+var_2280]
0x180004b46  mov     rax, [rsp+22F8h+var_22A8]
0x180004b4b  mov     [rsp+22F8h+var_22C0], rax
0x180004b50  mov     rsi, [rsp+22F8h+var_2278]
0x180004b58  mov     rax, [rsp+22F8h+var_2298]
0x180004b5d  mov     [rsp+22F8h+lpValueName], rax
0x180004b62  mov     r12d, edi
0x180004b65  test    rcx, rcx
0x180004b68  jnz     short loc_180004B81
0x180004b6a  lea     rcx, [rsp+22F8h+var_2268]
0x180004b72  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004b77  mov     eax, 80004005h
0x180004b7c  jmp     loc_180004817
0x180004b81  mov     r8, rdi; Size
0x180004b84  xor     edx, edx; Val
0x180004b86  call    memset_0
0x180004b8b  mov     r10d, ebx
0x180004b8e  test    r14d, r14d
0x180004b91  jle     loc_180004C6F
0x180004b97  mov     r15d, 30h ; '0'
0x180004b9d  mov     eax, r10d
0x180004ba0  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180004ba8  cmp     edx, 61h ; 'a'
0x180004bab  ja      short loc_180004C1A
0x180004bad  jz      loc_180004C3A
0x180004bb3  cmp     edx, 38h ; '8'
0x180004bb6  ja      short loc_180004BEC
0x180004bb8  jz      short loc_180004BE4
0x180004bba  mov     ecx, edx
0x180004bbc  sub     ecx, r15d
0x180004bbf  jz      short loc_180004BE4
0x180004bc1  sub     ecx, 1
0x180004bc4  jz      short loc_180004BE4
0x180004bc6  sub     ecx, 1
0x180004bc9  jz      short loc_180004BE4
0x180004bcb  sub     ecx, 1
0x180004bce  jz      short loc_180004BE4
0x180004bd0  sub     ecx, 1
0x180004bd3  jz      short loc_180004BE4
0x180004bd5  sub     ecx, 1
0x180004bd8  jz      short loc_180004BE4
0x180004bda  sub     ecx, 1
0x180004bdd  jz      short loc_180004BE4
0x180004bdf  cmp     ecx, 1
0x180004be2  jnz     short loc_180004C35
0x180004be4  mov     r9d, edx
0x180004be7  sub     r9d, r15d
0x180004bea  jmp     short loc_180004C3E
0x180004bec  mov     r9d, edx
0x180004bef  mov     ecx, edx
0x180004bf1  sub     ecx, 39h ; '9'
0x180004bf4  jz      short loc_180004BE4
0x180004bf6  sub     ecx, r13d
0x180004bf9  jz      short loc_180004C14
0x180004bfb  sub     ecx, 1
0x180004bfe  jz      short loc_180004C14
0x180004c00  sub     ecx, 1
0x180004c03  jz      short loc_180004C14
0x180004c05  sub     ecx, 1
0x180004c08  jz      short loc_180004C14
0x180004c0a  sub     ecx, 1
0x180004c0d  jz      short loc_180004C14
0x180004c0f  cmp     ecx, 1
0x180004c12  jnz     short loc_180004C35
0x180004c14  add     r9d, 0FFFFFFC9h
0x180004c18  jmp     short loc_180004C3E
  ... truncated ...
```
