# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800041c0`
- end: `0x180004794`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180006d1c`

## callees

- `0x180002000`
- `0x180002a68`
- `0x1800041c0`
- `0x18000479c`
- `0x1800048f0`
- `0x180004908`
- `0x1800050f8`
- `0x1800061ec`
- `0x18000cc00`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800044a9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800044a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004449`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800044e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800046e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004449`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800044e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800046e2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800043c0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800043dc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004764`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800043c0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800043dc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004764`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004251`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004251`

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
0x1800041c0  push    rbx
0x1800041c2  push    rsi
0x1800041c3  push    rdi
0x1800041c4  push    r12
0x1800041c6  push    r13
0x1800041c8  push    r14
0x1800041ca  push    r15
0x1800041cc  mov     eax, 22C0h
0x1800041d1  call    _alloca_probe
0x1800041d6  sub     rsp, rax
0x1800041d9  mov     rax, cs:__security_cookie
0x1800041e0  xor     rax, rsp
0x1800041e3  mov     [rsp+22F8h+var_48], rax
0x1800041eb  mov     r14, r8
0x1800041ee  mov     [rsp+22F8h+lpValueName], r8
0x1800041f3  mov     r12, rdx
0x1800041f6  mov     [rsp+22F8h+var_2288], rdx
0x1800041fb  mov     r15, rcx
0x1800041fe  mov     [rsp+22F8h+var_22C0], rcx
0x180004203  mov     qword ptr [rsp+22F8h+Data], rdx
0x180004208  mov     [rsp+22F8h+var_22A8], rcx
0x18000420d  mov     [rsp+22F8h+var_2278], rdx
0x180004215  mov     [rsp+22F8h+var_2298], r8
0x18000421a  mov     [rsp+22F8h+var_2270], r9
0x180004222  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18000422a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000422f  xor     ebx, ebx
0x180004231  test    eax, eax
0x180004233  js      short loc_180004267
0x180004235  mov     edi, ebx
0x180004237  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000423e  movsxd  rsi, edi
0x180004241  add     rsi, rsi
0x180004244  mov     rdx, [r13+rsi*8+0]; lpString2
0x180004249  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180004251  call    cs:__imp_lstrcmpiW
0x180004257  test    eax, eax
0x180004259  jz      short loc_18000428A
0x18000425b  inc     edi
0x18000425d  cmp     edi, 4
0x180004260  jb      short loc_18000423E
0x180004262  mov     eax, 80020009h
0x180004267  mov     rcx, [rsp+22F8h+var_48]
0x18000426f  xor     rcx, rsp; StackCookie
0x180004272  call    __security_check_cookie
0x180004277  add     rsp, 22C0h
0x18000427e  pop     r15
0x180004280  pop     r14
0x180004282  pop     r13
0x180004284  pop     r12
0x180004286  pop     rdi
0x180004287  pop     rsi
0x180004288  pop     rbx
0x180004289  retn
0x18000428a  movzx   edi, word ptr [r13+rsi*8+8]
0x180004290  mov     esi, 13h
0x180004295  mov     rdx, [r15]
0x180004298  movzx   ecx, word ptr [rdx]
0x18000429b  sub     ecx, 9
0x18000429e  jz      loc_180004761
0x1800042a4  sub     ecx, 1
0x1800042a7  jz      loc_180004761
0x1800042ad  sub     ecx, 3
0x1800042b0  jz      loc_180004761
0x1800042b6  cmp     ecx, esi
0x1800042b8  jz      loc_180004761
0x1800042be  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800042c6  mov     rcx, r15; this
0x1800042c9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800042ce  test    eax, eax
0x1800042d0  js      short loc_180004267
0x1800042d2  mov     r13d, 8
0x1800042d8  cmp     di, r13w
0x1800042dc  jz      loc_180004712
0x1800042e2  cmp     di, 11h
0x1800042e6  jz      loc_1800044EB
0x1800042ec  cmp     di, si
0x1800042ef  jz      loc_180004493
0x1800042f5  mov     eax, 4008h
0x1800042fa  cmp     di, ax
0x1800042fd  jnz     loc_180004745
0x180004303  lea     rcx, [rsp+22F8h+String1]
0x18000430b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000430f  mov     rax, rsi
0x180004312  inc     rax
0x180004315  cmp     [rcx+rax*2], bx
0x180004319  jnz     short loc_180004312
0x18000431b  add     eax, 2
0x18000431e  mov     [rsp+22F8h+var_2158], rbx
0x180004326  test    eax, eax
0x180004328  jz      short loc_180004363
0x18000432a  movsxd  rcx, eax
0x18000432d  xor     edx, edx
0x18000432f  mov     rax, rsi
0x180004332  div     rcx
0x180004335  cmp     rax, 2
0x180004339  jb      loc_180004772
0x18000433f  lea     rdx, [rcx+rcx]
0x180004343  cmp     rdx, 100h
0x18000434a  jbe     short loc_180004363
0x18000434c  lea     rcx, [rsp+22F8h+var_2158]
0x180004354  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004359  mov     rdi, [rsp+22F8h+var_2158]
0x180004361  jmp     short loc_180004373
0x180004363  lea     rdi, [rsp+22F8h+var_2150]
0x18000436b  mov     [rsp+22F8h+var_2158], rdi
0x180004373  mov     r13, [rsp+22F8h+lpValueName]
0x180004378  jmp     short loc_18000439C
0x18000437a  xor     ebx, ebx
0x18000437c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004380  mov     rdi, [rsp+22F8h+var_2158]
0x180004388  mov     r12, qword ptr [rsp+22F8h+Data]
0x18000438d  mov     rax, [rsp+22F8h+var_22A8]
0x180004392  mov     [rsp+22F8h+var_22C0], rax
0x180004397  mov     r13, [rsp+22F8h+var_2298]
0x18000439c  test    rdi, rdi
0x18000439f  jz      loc_18000445B
0x1800043a5  lea     r14, [rsp+22F8h+String1]
0x1800043ad  cmp     [rsp+22F8h+String1], bx
0x1800043b5  jz      short loc_1800043F8
0x1800043b7  mov     r15d, 30h ; '0'
0x1800043bd  mov     rcx, r14; lpsz
0x1800043c0  call    cs:__imp_CharNextW
0x1800043c6  movzx   ecx, word ptr [r14]
0x1800043ca  cmp     cx, 5Ch ; '\'
0x1800043ce  jnz     short loc_1800043E7
0x1800043d0  cmp     [rax], r15w
0x1800043d4  jnz     short loc_1800043E7
0x1800043d6  mov     [rdi], bx
0x1800043d9  mov     rcx, rax; lpsz
0x1800043dc  call    cs:__imp_CharNextW
0x1800043e2  mov     r14, rax
0x1800043e5  jmp     short loc_1800043EE
0x1800043e7  mov     [rdi], cx
0x1800043ea  add     r14, 2
0x1800043ee  add     rdi, 2
0x1800043f2  cmp     [r14], bx
0x1800043f6  jnz     short loc_1800043BD
0x1800043f8  mov     dword ptr [rdi], 0
0x1800043fe  mov     r8, [rsp+22F8h+var_2158]
0x180004406  test    r8, r8
0x180004409  jz      loc_18000477D
0x18000440f  mov     r10d, ebx
0x180004412  mov     r9, r8
0x180004415  mov     rcx, rsi
0x180004418  inc     rcx
0x18000441b  cmp     [r9+rcx*2], bx
0x180004420  jnz     short loc_180004418
0x180004422  inc     ecx
0x180004424  lea     r9, [r9+rcx*2]
0x180004428  lea     r10d, [r10+rcx*2]
0x18000442c  cmp     ecx, 1
0x18000442f  jnz     short loc_180004415
0x180004431  mov     [rsp+22F8h+cbData], r10d; cbData
0x180004436  mov     [rsp+22F8h+lpData], r8; lpData
0x18000443b  lea     r9d, [rcx+6]; dwType
0x18000443f  xor     r8d, r8d; Reserved
0x180004442  mov     rdx, r13; lpValueName
0x180004445  mov     rcx, [r12]; hKey
0x180004449  call    cs:__imp_RegSetValueExW
0x18000444f  mov     esi, eax
0x180004451  mov     rdi, [rsp+22F8h+var_2158]
0x180004459  jmp     short loc_180004460
0x18000445b  mov     esi, 0Eh
0x180004460  lea     rax, [rsp+22F8h+var_2150]
0x180004468  cmp     rdi, rax
0x18000446b  jz      short loc_18000447A
0x18000446d  lea     rcx, [rsp+22F8h+var_2158]
0x180004475  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000447a  mov     r15, [rsp+22F8h+var_22C0]
0x18000447f  test    esi, esi
0x180004481  jz      loc_180004745
0x180004487  mov     ecx, esi; unsigned int
0x180004489  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000448e  jmp     loc_180004267
0x180004493  mov     [rsp+22F8h+pulOut], ebx
0x180004497  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x18000449c  xor     r8d, r8d; dwFlags
0x18000449f  xor     edx, edx; lcid
0x1800044a1  lea     rcx, [rsp+22F8h+String1]; strIn
0x1800044a9  call    cs:__imp_VarUI4FromStr
0x1800044af  test    eax, eax
0x1800044b1  js      loc_180004267
0x1800044b7  mov     eax, [rsp+22F8h+pulOut]
0x1800044bb  mov     dword ptr [rsp+22F8h+Data], eax
0x1800044bf  mov     [rsp+22F8h+cbData], 4; cbData
0x1800044c7  lea     rax, [rsp+22F8h+Data]
0x1800044cc  mov     r9d, 4; dwType
0x1800044d2  mov     [rsp+22F8h+lpData], rax; lpData
0x1800044d7  xor     r8d, r8d; Reserved
0x1800044da  mov     rdx, r14; lpValueName
0x1800044dd  mov     rcx, [r12]; hKey
0x1800044e1  call    cs:__imp_RegSetValueExW
0x1800044e7  mov     esi, eax
0x1800044e9  jmp     short loc_18000447F
0x1800044eb  lea     rax, [rsp+22F8h+String1]
0x1800044f3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800044f7  mov     r14, rsi
0x1800044fa  inc     r14
0x1800044fd  cmp     [rax+r14*2], bx
0x180004502  jnz     short loc_1800044FA
0x180004504  mov     dword ptr [rsp+22F8h+Data], r14d
0x180004509  test    r14b, 1
0x18000450d  jnz     loc_1800045C7
0x180004513  mov     eax, r14d
0x180004516  cdq
0x180004517  sub     eax, edx
0x180004519  sar     eax, 1
0x18000451b  movsxd  r12, eax
0x18000451e  mov     [rsp+22F8h+var_2268], rbx
0x180004526  mov     rdi, r12
0x180004529  mov     [rsp+22F8h+var_2280], r12
0x18000452e  test    eax, eax
0x180004530  jz      short loc_180004567
0x180004532  xor     edx, edx
0x180004534  mov     rax, rsi
0x180004537  div     rdi
0x18000453a  cmp     rax, 1
0x18000453e  jb      loc_180004788
0x180004544  cmp     rdi, 100h
0x18000454b  jbe     short loc_180004567
0x18000454d  mov     rdx, rdi
0x180004550  lea     rcx, [rsp+22F8h+var_2268]
0x180004558  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000455d  mov     rcx, [rsp+22F8h+var_2268]
0x180004565  jmp     short loc_180004577
0x180004567  lea     rcx, [rsp+22F8h+var_2260]
0x18000456f  mov     [rsp+22F8h+var_2268], rcx
0x180004577  mov     rsi, [rsp+22F8h+var_2288]
0x18000457c  jmp     short loc_1800045B5
0x18000457e  xor     ebx, ebx
0x180004580  lea     r13d, [rbx+8]
0x180004584  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180004589  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180004591  mov     rdi, [rsp+22F8h+var_2280]
0x180004596  mov     rax, [rsp+22F8h+var_22A8]
0x18000459b  mov     [rsp+22F8h+var_22C0], rax
0x1800045a0  mov     rsi, [rsp+22F8h+var_2278]
0x1800045a8  mov     rax, [rsp+22F8h+var_2298]
0x1800045ad  mov     [rsp+22F8h+lpValueName], rax
0x1800045b2  mov     r12d, edi
0x1800045b5  test    rcx, rcx
0x1800045b8  jnz     short loc_1800045D1
0x1800045ba  lea     rcx, [rsp+22F8h+var_2268]
0x1800045c2  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800045c7  mov     eax, 80004005h
0x1800045cc  jmp     loc_180004267
0x1800045d1  mov     r8, rdi; Size
0x1800045d4  xor     edx, edx; Val
0x1800045d6  call    memset_0
0x1800045db  mov     r10d, ebx
0x1800045de  test    r14d, r14d
0x1800045e1  jle     loc_1800046BF
0x1800045e7  mov     r15d, 30h ; '0'
0x1800045ed  mov     eax, r10d
0x1800045f0  movzx   edx, [rsp+rax*2+22F8h+String1]
0x1800045f8  cmp     edx, 61h ; 'a'
0x1800045fb  ja      short loc_18000466A
0x1800045fd  jz      loc_18000468A
0x180004603  cmp     edx, 38h ; '8'
0x180004606  ja      short loc_18000463C
0x180004608  jz      short loc_180004634
0x18000460a  mov     ecx, edx
0x18000460c  sub     ecx, r15d
0x18000460f  jz      short loc_180004634
0x180004611  sub     ecx, 1
0x180004614  jz      short loc_180004634
0x180004616  sub     ecx, 1
0x180004619  jz      short loc_180004634
0x18000461b  sub     ecx, 1
0x18000461e  jz      short loc_180004634
0x180004620  sub     ecx, 1
0x180004623  jz      short loc_180004634
0x180004625  sub     ecx, 1
0x180004628  jz      short loc_180004634
0x18000462a  sub     ecx, 1
0x18000462d  jz      short loc_180004634
0x18000462f  cmp     ecx, 1
0x180004632  jnz     short loc_180004685
0x180004634  mov     r9d, edx
0x180004637  sub     r9d, r15d
0x18000463a  jmp     short loc_18000468E
0x18000463c  mov     r9d, edx
0x18000463f  mov     ecx, edx
0x180004641  sub     ecx, 39h ; '9'
0x180004644  jz      short loc_180004634
0x180004646  sub     ecx, r13d
0x180004649  jz      short loc_180004664
0x18000464b  sub     ecx, 1
0x18000464e  jz      short loc_180004664
0x180004650  sub     ecx, 1
0x180004653  jz      short loc_180004664
0x180004655  sub     ecx, 1
0x180004658  jz      short loc_180004664
0x18000465a  sub     ecx, 1
0x18000465d  jz      short loc_180004664
0x18000465f  cmp     ecx, 1
0x180004662  jnz     short loc_180004685
0x180004664  add     r9d, 0FFFFFFC9h
0x180004668  jmp     short loc_18000468E
  ... truncated ...
```
