# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18001f49c`
- end: `0x18001fa70`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002140c`

## callees

- `0x1800018f0`
- `0x18000227c`
- `0x18001afd0`
- `0x18001f49c`
- `0x18001fa78`
- `0x18001fc98`
- `0x180020178`
- `0x180020754`
- `0x180020980`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001f785`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001f785`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f725`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f7bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f9be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f725`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f7bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f9be`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001f69c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001f6b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001fa40`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001f69c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001f6b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001fa40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001f52d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001f52d`

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
0x18001f49c  push    rbx
0x18001f49e  push    rsi
0x18001f49f  push    rdi
0x18001f4a0  push    r12
0x18001f4a2  push    r13
0x18001f4a4  push    r14
0x18001f4a6  push    r15
0x18001f4a8  mov     eax, 22C0h
0x18001f4ad  call    _alloca_probe
0x18001f4b2  sub     rsp, rax
0x18001f4b5  mov     rax, cs:__security_cookie
0x18001f4bc  xor     rax, rsp
0x18001f4bf  mov     [rsp+22F8h+var_48], rax
0x18001f4c7  mov     r14, r8
0x18001f4ca  mov     [rsp+22F8h+lpValueName], r8
0x18001f4cf  mov     r12, rdx
0x18001f4d2  mov     [rsp+22F8h+var_2288], rdx
0x18001f4d7  mov     r15, rcx
0x18001f4da  mov     [rsp+22F8h+var_22C0], rcx
0x18001f4df  mov     qword ptr [rsp+22F8h+Data], rdx
0x18001f4e4  mov     [rsp+22F8h+var_22A8], rcx
0x18001f4e9  mov     [rsp+22F8h+var_2278], rdx
0x18001f4f1  mov     [rsp+22F8h+var_2298], r8
0x18001f4f6  mov     [rsp+22F8h+var_2270], r9
0x18001f4fe  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18001f506  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f50b  xor     ebx, ebx
0x18001f50d  test    eax, eax
0x18001f50f  js      short loc_18001F543
0x18001f511  mov     edi, ebx
0x18001f513  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001f51a  movsxd  rsi, edi
0x18001f51d  add     rsi, rsi
0x18001f520  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001f525  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18001f52d  call    cs:__imp_lstrcmpiW
0x18001f533  test    eax, eax
0x18001f535  jz      short loc_18001F566
0x18001f537  inc     edi
0x18001f539  cmp     edi, 4
0x18001f53c  jb      short loc_18001F51A
0x18001f53e  mov     eax, 80020009h
0x18001f543  mov     rcx, [rsp+22F8h+var_48]
0x18001f54b  xor     rcx, rsp; StackCookie
0x18001f54e  call    __security_check_cookie
0x18001f553  add     rsp, 22C0h
0x18001f55a  pop     r15
0x18001f55c  pop     r14
0x18001f55e  pop     r13
0x18001f560  pop     r12
0x18001f562  pop     rdi
0x18001f563  pop     rsi
0x18001f564  pop     rbx
0x18001f565  retn
0x18001f566  movzx   edi, word ptr [r13+rsi*8+8]
0x18001f56c  mov     esi, 13h
0x18001f571  mov     rdx, [r15]
0x18001f574  movzx   ecx, word ptr [rdx]
0x18001f577  sub     ecx, 9
0x18001f57a  jz      loc_18001FA3D
0x18001f580  sub     ecx, 1
0x18001f583  jz      loc_18001FA3D
0x18001f589  sub     ecx, 3
0x18001f58c  jz      loc_18001FA3D
0x18001f592  cmp     ecx, esi
0x18001f594  jz      loc_18001FA3D
0x18001f59a  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18001f5a2  mov     rcx, r15; this
0x18001f5a5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f5aa  test    eax, eax
0x18001f5ac  js      short loc_18001F543
0x18001f5ae  mov     r13d, 8
0x18001f5b4  cmp     di, r13w
0x18001f5b8  jz      loc_18001F9EE
0x18001f5be  cmp     di, 11h
0x18001f5c2  jz      loc_18001F7C7
0x18001f5c8  cmp     di, si
0x18001f5cb  jz      loc_18001F76F
0x18001f5d1  mov     eax, 4008h
0x18001f5d6  cmp     di, ax
0x18001f5d9  jnz     loc_18001FA21
0x18001f5df  lea     rcx, [rsp+22F8h+String1]
0x18001f5e7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f5eb  mov     rax, rsi
0x18001f5ee  inc     rax
0x18001f5f1  cmp     [rcx+rax*2], bx
0x18001f5f5  jnz     short loc_18001F5EE
0x18001f5f7  add     eax, 2
0x18001f5fa  mov     [rsp+22F8h+var_2158], rbx
0x18001f602  test    eax, eax
0x18001f604  jz      short loc_18001F63F
0x18001f606  movsxd  rcx, eax
0x18001f609  xor     edx, edx
0x18001f60b  mov     rax, rsi
0x18001f60e  div     rcx
0x18001f611  cmp     rax, 2
0x18001f615  jb      loc_18001FA4E
0x18001f61b  lea     rdx, [rcx+rcx]
0x18001f61f  cmp     rdx, 100h
0x18001f626  jbe     short loc_18001F63F
0x18001f628  lea     rcx, [rsp+22F8h+var_2158]
0x18001f630  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001f635  mov     rdi, [rsp+22F8h+var_2158]
0x18001f63d  jmp     short loc_18001F64F
0x18001f63f  lea     rdi, [rsp+22F8h+var_2150]
0x18001f647  mov     [rsp+22F8h+var_2158], rdi
0x18001f64f  mov     r13, [rsp+22F8h+lpValueName]
0x18001f654  jmp     short loc_18001F678
0x18001f656  xor     ebx, ebx
0x18001f658  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f65c  mov     rdi, [rsp+22F8h+var_2158]
0x18001f664  mov     r12, qword ptr [rsp+22F8h+Data]
0x18001f669  mov     rax, [rsp+22F8h+var_22A8]
0x18001f66e  mov     [rsp+22F8h+var_22C0], rax
0x18001f673  mov     r13, [rsp+22F8h+var_2298]
0x18001f678  test    rdi, rdi
0x18001f67b  jz      loc_18001F737
0x18001f681  lea     r14, [rsp+22F8h+String1]
0x18001f689  cmp     [rsp+22F8h+String1], bx
0x18001f691  jz      short loc_18001F6D4
0x18001f693  mov     r15d, 30h ; '0'
0x18001f699  mov     rcx, r14; lpsz
0x18001f69c  call    cs:__imp_CharNextW
0x18001f6a2  movzx   ecx, word ptr [r14]
0x18001f6a6  cmp     cx, 5Ch ; '\'
0x18001f6aa  jnz     short loc_18001F6C3
0x18001f6ac  cmp     [rax], r15w
0x18001f6b0  jnz     short loc_18001F6C3
0x18001f6b2  mov     [rdi], bx
0x18001f6b5  mov     rcx, rax; lpsz
0x18001f6b8  call    cs:__imp_CharNextW
0x18001f6be  mov     r14, rax
0x18001f6c1  jmp     short loc_18001F6CA
0x18001f6c3  mov     [rdi], cx
0x18001f6c6  add     r14, 2
0x18001f6ca  add     rdi, 2
0x18001f6ce  cmp     [r14], bx
0x18001f6d2  jnz     short loc_18001F699
0x18001f6d4  mov     dword ptr [rdi], 0
0x18001f6da  mov     r8, [rsp+22F8h+var_2158]
0x18001f6e2  test    r8, r8
0x18001f6e5  jz      loc_18001FA59
0x18001f6eb  mov     r10d, ebx
0x18001f6ee  mov     r9, r8
0x18001f6f1  mov     rcx, rsi
0x18001f6f4  inc     rcx
0x18001f6f7  cmp     [r9+rcx*2], bx
0x18001f6fc  jnz     short loc_18001F6F4
0x18001f6fe  inc     ecx
0x18001f700  lea     r9, [r9+rcx*2]
0x18001f704  lea     r10d, [r10+rcx*2]
0x18001f708  cmp     ecx, 1
0x18001f70b  jnz     short loc_18001F6F1
0x18001f70d  mov     [rsp+22F8h+cbData], r10d; cbData
0x18001f712  mov     [rsp+22F8h+lpData], r8; lpData
0x18001f717  lea     r9d, [rcx+6]; dwType
0x18001f71b  xor     r8d, r8d; Reserved
0x18001f71e  mov     rdx, r13; lpValueName
0x18001f721  mov     rcx, [r12]; hKey
0x18001f725  call    cs:__imp_RegSetValueExW
0x18001f72b  mov     esi, eax
0x18001f72d  mov     rdi, [rsp+22F8h+var_2158]
0x18001f735  jmp     short loc_18001F73C
0x18001f737  mov     esi, 0Eh
0x18001f73c  lea     rax, [rsp+22F8h+var_2150]
0x18001f744  cmp     rdi, rax
0x18001f747  jz      short loc_18001F756
0x18001f749  lea     rcx, [rsp+22F8h+var_2158]
0x18001f751  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18001f756  mov     r15, [rsp+22F8h+var_22C0]
0x18001f75b  test    esi, esi
0x18001f75d  jz      loc_18001FA21
0x18001f763  mov     ecx, esi; unsigned int
0x18001f765  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001f76a  jmp     loc_18001F543
0x18001f76f  mov     [rsp+22F8h+pulOut], ebx
0x18001f773  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x18001f778  xor     r8d, r8d; dwFlags
0x18001f77b  xor     edx, edx; lcid
0x18001f77d  lea     rcx, [rsp+22F8h+String1]; strIn
0x18001f785  call    cs:__imp_VarUI4FromStr
0x18001f78b  test    eax, eax
0x18001f78d  js      loc_18001F543
0x18001f793  mov     eax, [rsp+22F8h+pulOut]
0x18001f797  mov     dword ptr [rsp+22F8h+Data], eax
0x18001f79b  mov     [rsp+22F8h+cbData], 4; cbData
0x18001f7a3  lea     rax, [rsp+22F8h+Data]
0x18001f7a8  mov     r9d, 4; dwType
0x18001f7ae  mov     [rsp+22F8h+lpData], rax; lpData
0x18001f7b3  xor     r8d, r8d; Reserved
0x18001f7b6  mov     rdx, r14; lpValueName
0x18001f7b9  mov     rcx, [r12]; hKey
0x18001f7bd  call    cs:__imp_RegSetValueExW
0x18001f7c3  mov     esi, eax
0x18001f7c5  jmp     short loc_18001F75B
0x18001f7c7  lea     rax, [rsp+22F8h+String1]
0x18001f7cf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f7d3  mov     r14, rsi
0x18001f7d6  inc     r14
0x18001f7d9  cmp     [rax+r14*2], bx
0x18001f7de  jnz     short loc_18001F7D6
0x18001f7e0  mov     dword ptr [rsp+22F8h+Data], r14d
0x18001f7e5  test    r14b, 1
0x18001f7e9  jnz     loc_18001F8A3
0x18001f7ef  mov     eax, r14d
0x18001f7f2  cdq
0x18001f7f3  sub     eax, edx
0x18001f7f5  sar     eax, 1
0x18001f7f7  movsxd  r12, eax
0x18001f7fa  mov     [rsp+22F8h+var_2268], rbx
0x18001f802  mov     rdi, r12
0x18001f805  mov     [rsp+22F8h+var_2280], r12
0x18001f80a  test    eax, eax
0x18001f80c  jz      short loc_18001F843
0x18001f80e  xor     edx, edx
0x18001f810  mov     rax, rsi
0x18001f813  div     rdi
0x18001f816  cmp     rax, 1
0x18001f81a  jb      loc_18001FA64
0x18001f820  cmp     rdi, 100h
0x18001f827  jbe     short loc_18001F843
0x18001f829  mov     rdx, rdi
0x18001f82c  lea     rcx, [rsp+22F8h+var_2268]
0x18001f834  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001f839  mov     rcx, [rsp+22F8h+var_2268]
0x18001f841  jmp     short loc_18001F853
0x18001f843  lea     rcx, [rsp+22F8h+var_2260]
0x18001f84b  mov     [rsp+22F8h+var_2268], rcx
0x18001f853  mov     rsi, [rsp+22F8h+var_2288]
0x18001f858  jmp     short loc_18001F891
0x18001f85a  xor     ebx, ebx
0x18001f85c  lea     r13d, [rbx+8]
0x18001f860  mov     r14d, dword ptr [rsp+22F8h+Data]
0x18001f865  mov     rcx, [rsp+22F8h+var_2268]; void *
0x18001f86d  mov     rdi, [rsp+22F8h+var_2280]
0x18001f872  mov     rax, [rsp+22F8h+var_22A8]
0x18001f877  mov     [rsp+22F8h+var_22C0], rax
0x18001f87c  mov     rsi, [rsp+22F8h+var_2278]
0x18001f884  mov     rax, [rsp+22F8h+var_2298]
0x18001f889  mov     [rsp+22F8h+lpValueName], rax
0x18001f88e  mov     r12d, edi
0x18001f891  test    rcx, rcx
0x18001f894  jnz     short loc_18001F8AD
0x18001f896  lea     rcx, [rsp+22F8h+var_2268]
0x18001f89e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18001f8a3  mov     eax, 80004005h
0x18001f8a8  jmp     loc_18001F543
0x18001f8ad  mov     r8, rdi; Size
0x18001f8b0  xor     edx, edx; Val
0x18001f8b2  call    memset_0
0x18001f8b7  mov     r10d, ebx
0x18001f8ba  test    r14d, r14d
0x18001f8bd  jle     loc_18001F99B
0x18001f8c3  mov     r15d, 30h ; '0'
0x18001f8c9  mov     eax, r10d
0x18001f8cc  movzx   edx, [rsp+rax*2+22F8h+String1]
0x18001f8d4  cmp     edx, 61h ; 'a'
0x18001f8d7  ja      short loc_18001F946
0x18001f8d9  jz      loc_18001F966
0x18001f8df  cmp     edx, 38h ; '8'
0x18001f8e2  ja      short loc_18001F918
0x18001f8e4  jz      short loc_18001F910
0x18001f8e6  mov     ecx, edx
0x18001f8e8  sub     ecx, r15d
0x18001f8eb  jz      short loc_18001F910
0x18001f8ed  sub     ecx, 1
0x18001f8f0  jz      short loc_18001F910
0x18001f8f2  sub     ecx, 1
0x18001f8f5  jz      short loc_18001F910
0x18001f8f7  sub     ecx, 1
0x18001f8fa  jz      short loc_18001F910
0x18001f8fc  sub     ecx, 1
0x18001f8ff  jz      short loc_18001F910
0x18001f901  sub     ecx, 1
0x18001f904  jz      short loc_18001F910
0x18001f906  sub     ecx, 1
0x18001f909  jz      short loc_18001F910
0x18001f90b  cmp     ecx, 1
0x18001f90e  jnz     short loc_18001F961
0x18001f910  mov     r9d, edx
0x18001f913  sub     r9d, r15d
0x18001f916  jmp     short loc_18001F96A
0x18001f918  mov     r9d, edx
0x18001f91b  mov     ecx, edx
0x18001f91d  sub     ecx, 39h ; '9'
0x18001f920  jz      short loc_18001F910
0x18001f922  sub     ecx, r13d
0x18001f925  jz      short loc_18001F940
0x18001f927  sub     ecx, 1
0x18001f92a  jz      short loc_18001F940
0x18001f92c  sub     ecx, 1
0x18001f92f  jz      short loc_18001F940
0x18001f931  sub     ecx, 1
0x18001f934  jz      short loc_18001F940
0x18001f936  sub     ecx, 1
0x18001f939  jz      short loc_18001F940
0x18001f93b  cmp     ecx, 1
0x18001f93e  jnz     short loc_18001F961
0x18001f940  add     r9d, 0FFFFFFC9h
0x18001f944  jmp     short loc_18001F96A
  ... truncated ...
```
