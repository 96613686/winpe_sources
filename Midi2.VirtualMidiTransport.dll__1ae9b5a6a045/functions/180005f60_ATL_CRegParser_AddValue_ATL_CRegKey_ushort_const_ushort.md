# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180005f60`
- end: `0x180006534`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180008afc`

## callees

- `0x1800038f0`
- `0x1800046a0`
- `0x180005f60`
- `0x18000653c`
- `0x180006690`
- `0x1800066a8`
- `0x180006e9c`
- `0x180007f8c`
- `0x18001f830`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180006249`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180006249`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800061e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006281`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006482`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800061e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006281`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006482`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006160`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000617c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006504`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006160`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000617c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006504`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005ff1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005ff1`

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
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  BYTE *v14; // rdi
  const WCHAR *v15; // r13
  WCHAR *i; // r14
  const WCHAR *v17; // rax
  DWORD v18; // r10d
  BYTE *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // esi
  const BYTE *v23; // rax
  DWORD v24; // r9d
  __int64 v25; // r14
  DWORD v26; // r12d
  size_t v27; // rdi
  BYTE *v28; // rcx
  HKEY *v29; // rsi
  unsigned int v30; // r10d
  unsigned int v31; // edx
  char v32; // r9
  __int64 v33; // rsi
  int Token; // eax
  __int64 v35; // [rsp+0h] [rbp-22F8h] BYREF
  DWORD cbData; // [rsp+28h] [rbp-22D0h]
  ULONG pulOut; // [rsp+30h] [rbp-22C8h] BYREF
  ATL::CRegParser *v38; // [rsp+38h] [rbp-22C0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22B8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22B0h]
  ATL::CRegParser *v41; // [rsp+50h] [rbp-22A8h]
  const WCHAR *v42; // [rsp+60h] [rbp-2298h]
  struct ATL::CRegKey *v43; // [rsp+70h] [rbp-2288h]
  size_t v44; // [rsp+78h] [rbp-2280h]
  struct ATL::CRegKey *v45; // [rsp+80h] [rbp-2278h]
  unsigned __int16 *v46; // [rsp+88h] [rbp-2270h]
  BYTE *v47; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v48[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v50[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v43 = (struct ATL::CRegKey *)a2;
  v6 = this;
  v38 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v41 = (ATL::CRegParser *)this;
  v45 = (struct ATL::CRegKey *)a2;
  v42 = a3;
  v46 = a4;
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
        v33 = -1;
        do
          ++v33;
        while ( String1[v33] );
        cbData = 2 * v33 + 2;
        v23 = (const BYTE *)String1;
        v24 = 1;
        goto LABEL_47;
      }
      if ( v10 != 17 )
      {
        if ( v10 != 19 )
        {
          if ( v10 != 16392 )
          {
LABEL_93:
            Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v46);
            if ( Token < 0 )
              return Token;
            return v8;
          }
          v12 = -1;
          do
            ++v12;
          while ( String1[v12] );
          v13 = v12 + 2;
          lpData = 0;
          try
          {
            if ( !v13 )
              goto LABEL_24;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v13 < 2 )
              ATL::AtlThrowImpl(-2147024809);
            v11 = (__int64 *)(2LL * v13);
            if ( (unsigned __int64)v11 > 0x100 )
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v11);
              v14 = lpData;
            }
            else
            {
LABEL_24:
              v14 = v50;
              lpData = v50;
            }
          }
          catch ( ... )
          {
            v11 = &v35;
            v8 = 0;
            v14 = lpData;
            v5 = *(HKEY **)Data;
            v38 = v41;
            v15 = v42;
            goto LABEL_26;
          }
          v15 = lpValueName;
LABEL_26:
          if ( v14 )
          {
            for ( i = String1; *i; v14 += 2 )
            {
              v17 = CharNextW(i);
              if ( *i == 92 && *v17 == 48 )
              {
                *(_WORD *)v14 = 0;
                i = CharNextW(v17);
              }
              else
              {
                *(_WORD *)v14 = *i++;
              }
            }
            *(_DWORD *)v14 = 0;
            if ( !lpData )
              ATL::AtlThrowImpl(-2147467259);
            v18 = 0;
            v19 = lpData;
            do
            {
              v20 = -1;
              do
                ++v20;
              while ( *(_WORD *)&v19[2 * v20] );
              v21 = (unsigned int)(v20 + 1);
              v19 += 2 * v21;
              v18 += 2 * v21;
            }
            while ( (_DWORD)v21 != 1 );
            v22 = RegSetValueExW(*v5, v15, 0, 7u, lpData, v18);
            v14 = lpData;
          }
          else
          {
            v22 = 14;
          }
          if ( v14 != v50 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
          goto LABEL_42;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v23 = Data;
        v24 = 4;
LABEL_47:
        v22 = RegSetValueExW(*v5, a3, 0, v24, v23, cbData);
LABEL_43:
        if ( v22 )
          return winrt::impl::hresult_from_win32((winrt::impl *)v22, (unsigned int)v11);
        goto LABEL_93;
      }
      v25 = -1;
      do
        ++v25;
      while ( String1[v25] );
      *(_DWORD *)Data = v25;
      if ( (v25 & 1) != 0 )
        return -2147467259;
      try
      {
        v26 = (int)v25 / 2;
        v47 = 0;
        v27 = (int)v25 / 2;
        v44 = v27;
        if ( !((int)v25 / 2) )
          goto LABEL_56;
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v27) )
          ATL::AtlThrowImpl(-2147024809);
        if ( v27 > 0x100 )
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v47, v27);
          v28 = v47;
        }
        else
        {
LABEL_56:
          v28 = v48;
          v47 = v48;
        }
        v29 = (HKEY *)v43;
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v25) = *(_DWORD *)Data;
        v28 = v47;
        v27 = v44;
        v38 = v41;
        v29 = (HKEY *)v45;
        lpValueName = v42;
        v26 = v44;
      }
      if ( !v28 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v47);
        return -2147467259;
      }
      memset_0(v28, 0, v27);
      v30 = 0;
      if ( (int)v25 <= 0 )
      {
LABEL_88:
        v22 = RegSetValueExW(*v29, lpValueName, 0, 3u, v47, v26);
        if ( v47 != v48 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v47);
LABEL_42:
        v6 = (LPCWSTR *)v38;
        goto LABEL_43;
      }
      while ( 1 )
      {
        v31 = String1[v30];
        if ( v31 > 0x61 )
        {
          if ( v31 == 98 || v31 == 99 || v31 == 100 || v31 - 101 < 2 )
          {
LABEL_86:
            v32 = v31 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v32 = 0;
          goto LABEL_87;
        }
        if ( v31 == 97 )
          goto LABEL_86;
        if ( v31 <= 0x38 )
          break;
        if ( v31 == 57 )
          goto LABEL_73;
        if ( v31 != 65 && v31 != 66 && v31 != 67 && v31 != 68 && v31 - 69 > 1 )
          goto LABEL_85;
        v32 = v31 - 55;
LABEL_87:
        v47[(unsigned __int64)v30 >> 1] |= v32 << (4 - 4 * (v30 & 1));
        if ( (int)++v30 >= (int)v25 )
          goto LABEL_88;
      }
      if ( v31 != 56 && v31 != 48 && v31 != 49 && v31 != 50 && v31 != 51 && v31 != 52 && v31 != 53 && v31 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v32 = v31 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005f60  push    rbx
0x180005f62  push    rsi
0x180005f63  push    rdi
0x180005f64  push    r12
0x180005f66  push    r13
0x180005f68  push    r14
0x180005f6a  push    r15
0x180005f6c  mov     eax, 22C0h
0x180005f71  call    _alloca_probe
0x180005f76  sub     rsp, rax
0x180005f79  mov     rax, cs:__security_cookie
0x180005f80  xor     rax, rsp
0x180005f83  mov     [rsp+22F8h+var_48], rax
0x180005f8b  mov     r14, r8
0x180005f8e  mov     [rsp+22F8h+lpValueName], r8
0x180005f93  mov     r12, rdx
0x180005f96  mov     [rsp+22F8h+var_2288], rdx
0x180005f9b  mov     r15, rcx
0x180005f9e  mov     [rsp+22F8h+var_22C0], rcx
0x180005fa3  mov     qword ptr [rsp+22F8h+Data], rdx
0x180005fa8  mov     [rsp+22F8h+var_22A8], rcx
0x180005fad  mov     [rsp+22F8h+var_2278], rdx
0x180005fb5  mov     [rsp+22F8h+var_2298], r8
0x180005fba  mov     [rsp+22F8h+var_2270], r9
0x180005fc2  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180005fca  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005fcf  xor     ebx, ebx
0x180005fd1  test    eax, eax
0x180005fd3  js      short loc_180006007
0x180005fd5  mov     edi, ebx
0x180005fd7  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180005fde  movsxd  rsi, edi
0x180005fe1  add     rsi, rsi
0x180005fe4  mov     rdx, [r13+rsi*8+0]; lpString2
0x180005fe9  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180005ff1  call    cs:__imp_lstrcmpiW
0x180005ff7  test    eax, eax
0x180005ff9  jz      short loc_18000602A
0x180005ffb  inc     edi
0x180005ffd  cmp     edi, 4
0x180006000  jb      short loc_180005FDE
0x180006002  mov     eax, 80020009h
0x180006007  mov     rcx, [rsp+22F8h+var_48]
0x18000600f  xor     rcx, rsp; StackCookie
0x180006012  call    __security_check_cookie
0x180006017  add     rsp, 22C0h
0x18000601e  pop     r15
0x180006020  pop     r14
0x180006022  pop     r13
0x180006024  pop     r12
0x180006026  pop     rdi
0x180006027  pop     rsi
0x180006028  pop     rbx
0x180006029  retn
0x18000602a  movzx   edi, word ptr [r13+rsi*8+8]
0x180006030  mov     esi, 13h
0x180006035  mov     rdx, [r15]
0x180006038  movzx   ecx, word ptr [rdx]
0x18000603b  sub     ecx, 9
0x18000603e  jz      loc_180006501
0x180006044  sub     ecx, 1
0x180006047  jz      loc_180006501
0x18000604d  sub     ecx, 3
0x180006050  jz      loc_180006501
0x180006056  cmp     ecx, esi
0x180006058  jz      loc_180006501
0x18000605e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180006066  mov     rcx, r15; this
0x180006069  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000606e  test    eax, eax
0x180006070  js      short loc_180006007
0x180006072  mov     r13d, 8
0x180006078  cmp     di, r13w
0x18000607c  jz      loc_1800064B2
0x180006082  cmp     di, 11h
0x180006086  jz      loc_18000628B
0x18000608c  cmp     di, si
0x18000608f  jz      loc_180006233
0x180006095  mov     eax, 4008h
0x18000609a  cmp     di, ax
0x18000609d  jnz     loc_1800064E5
0x1800060a3  lea     rcx, [rsp+22F8h+String1]
0x1800060ab  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800060af  mov     rax, rsi
0x1800060b2  inc     rax
0x1800060b5  cmp     [rcx+rax*2], bx
0x1800060b9  jnz     short loc_1800060B2
0x1800060bb  add     eax, 2
0x1800060be  mov     [rsp+22F8h+var_2158], rbx
0x1800060c6  test    eax, eax
0x1800060c8  jz      short loc_180006103
0x1800060ca  movsxd  rcx, eax
0x1800060cd  xor     edx, edx
0x1800060cf  mov     rax, rsi
0x1800060d2  div     rcx
0x1800060d5  cmp     rax, 2
0x1800060d9  jb      loc_180006512
0x1800060df  lea     rdx, [rcx+rcx]
0x1800060e3  cmp     rdx, 100h
0x1800060ea  jbe     short loc_180006103
0x1800060ec  lea     rcx, [rsp+22F8h+var_2158]
0x1800060f4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800060f9  mov     rdi, [rsp+22F8h+var_2158]
0x180006101  jmp     short loc_180006113
0x180006103  lea     rdi, [rsp+22F8h+var_2150]
0x18000610b  mov     [rsp+22F8h+var_2158], rdi
0x180006113  mov     r13, [rsp+22F8h+lpValueName]
0x180006118  jmp     short loc_18000613C
0x18000611a  xor     ebx, ebx
0x18000611c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006120  mov     rdi, [rsp+22F8h+var_2158]
0x180006128  mov     r12, qword ptr [rsp+22F8h+Data]
0x18000612d  mov     rax, [rsp+22F8h+var_22A8]
0x180006132  mov     [rsp+22F8h+var_22C0], rax
0x180006137  mov     r13, [rsp+22F8h+var_2298]
0x18000613c  test    rdi, rdi
0x18000613f  jz      loc_1800061FB
0x180006145  lea     r14, [rsp+22F8h+String1]
0x18000614d  cmp     [rsp+22F8h+String1], bx
0x180006155  jz      short loc_180006198
0x180006157  mov     r15d, 30h ; '0'
0x18000615d  mov     rcx, r14; lpsz
0x180006160  call    cs:__imp_CharNextW
0x180006166  movzx   ecx, word ptr [r14]
0x18000616a  cmp     cx, 5Ch ; '\'
0x18000616e  jnz     short loc_180006187
0x180006170  cmp     [rax], r15w
0x180006174  jnz     short loc_180006187
0x180006176  mov     [rdi], bx
0x180006179  mov     rcx, rax; lpsz
0x18000617c  call    cs:__imp_CharNextW
0x180006182  mov     r14, rax
0x180006185  jmp     short loc_18000618E
0x180006187  mov     [rdi], cx
0x18000618a  add     r14, 2
0x18000618e  add     rdi, 2
0x180006192  cmp     [r14], bx
0x180006196  jnz     short loc_18000615D
0x180006198  mov     dword ptr [rdi], 0
0x18000619e  mov     r8, [rsp+22F8h+var_2158]
0x1800061a6  test    r8, r8
0x1800061a9  jz      loc_18000651D
0x1800061af  mov     r10d, ebx
0x1800061b2  mov     r9, r8
0x1800061b5  mov     rcx, rsi
0x1800061b8  inc     rcx
0x1800061bb  cmp     [r9+rcx*2], bx
0x1800061c0  jnz     short loc_1800061B8
0x1800061c2  inc     ecx
0x1800061c4  lea     r9, [r9+rcx*2]
0x1800061c8  lea     r10d, [r10+rcx*2]
0x1800061cc  cmp     ecx, 1
0x1800061cf  jnz     short loc_1800061B5
0x1800061d1  mov     [rsp+22F8h+cbData], r10d; cbData
0x1800061d6  mov     [rsp+22F8h+lpData], r8; lpData
0x1800061db  lea     r9d, [rcx+6]; dwType
0x1800061df  xor     r8d, r8d; Reserved
0x1800061e2  mov     rdx, r13; lpValueName
0x1800061e5  mov     rcx, [r12]; hKey
0x1800061e9  call    cs:__imp_RegSetValueExW
0x1800061ef  mov     esi, eax
0x1800061f1  mov     rdi, [rsp+22F8h+var_2158]
0x1800061f9  jmp     short loc_180006200
0x1800061fb  mov     esi, 0Eh
0x180006200  lea     rax, [rsp+22F8h+var_2150]
0x180006208  cmp     rdi, rax
0x18000620b  jz      short loc_18000621A
0x18000620d  lea     rcx, [rsp+22F8h+var_2158]
0x180006215  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000621a  mov     r15, [rsp+22F8h+var_22C0]
0x18000621f  test    esi, esi
0x180006221  jz      loc_1800064E5
0x180006227  mov     ecx, esi; this
0x180006229  call    ?hresult_from_win32@impl@winrt@@YAHI@Z; winrt::impl::hresult_from_win32(uint)
0x18000622e  jmp     loc_180006007
0x180006233  mov     [rsp+22F8h+pulOut], ebx
0x180006237  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x18000623c  xor     r8d, r8d; dwFlags
0x18000623f  xor     edx, edx; lcid
0x180006241  lea     rcx, [rsp+22F8h+String1]; strIn
0x180006249  call    cs:__imp_VarUI4FromStr
0x18000624f  test    eax, eax
0x180006251  js      loc_180006007
0x180006257  mov     eax, [rsp+22F8h+pulOut]
0x18000625b  mov     dword ptr [rsp+22F8h+Data], eax
0x18000625f  mov     [rsp+22F8h+cbData], 4; cbData
0x180006267  lea     rax, [rsp+22F8h+Data]
0x18000626c  mov     r9d, 4; dwType
0x180006272  mov     [rsp+22F8h+lpData], rax; lpData
0x180006277  xor     r8d, r8d; Reserved
0x18000627a  mov     rdx, r14; lpValueName
0x18000627d  mov     rcx, [r12]; hKey
0x180006281  call    cs:__imp_RegSetValueExW
0x180006287  mov     esi, eax
0x180006289  jmp     short loc_18000621F
0x18000628b  lea     rax, [rsp+22F8h+String1]
0x180006293  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006297  mov     r14, rsi
0x18000629a  inc     r14
0x18000629d  cmp     [rax+r14*2], bx
0x1800062a2  jnz     short loc_18000629A
0x1800062a4  mov     dword ptr [rsp+22F8h+Data], r14d
0x1800062a9  test    r14b, 1
0x1800062ad  jnz     loc_180006367
0x1800062b3  mov     eax, r14d
0x1800062b6  cdq
0x1800062b7  sub     eax, edx
0x1800062b9  sar     eax, 1
0x1800062bb  movsxd  r12, eax
0x1800062be  mov     [rsp+22F8h+var_2268], rbx
0x1800062c6  mov     rdi, r12
0x1800062c9  mov     [rsp+22F8h+var_2280], r12
0x1800062ce  test    eax, eax
0x1800062d0  jz      short loc_180006307
0x1800062d2  xor     edx, edx
0x1800062d4  mov     rax, rsi
0x1800062d7  div     rdi
0x1800062da  cmp     rax, 1
0x1800062de  jb      loc_180006528
0x1800062e4  cmp     rdi, 100h
0x1800062eb  jbe     short loc_180006307
0x1800062ed  mov     rdx, rdi
0x1800062f0  lea     rcx, [rsp+22F8h+var_2268]
0x1800062f8  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800062fd  mov     rcx, [rsp+22F8h+var_2268]
0x180006305  jmp     short loc_180006317
0x180006307  lea     rcx, [rsp+22F8h+var_2260]
0x18000630f  mov     [rsp+22F8h+var_2268], rcx
0x180006317  mov     rsi, [rsp+22F8h+var_2288]
0x18000631c  jmp     short loc_180006355
0x18000631e  xor     ebx, ebx
0x180006320  lea     r13d, [rbx+8]
0x180006324  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180006329  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180006331  mov     rdi, [rsp+22F8h+var_2280]
0x180006336  mov     rax, [rsp+22F8h+var_22A8]
0x18000633b  mov     [rsp+22F8h+var_22C0], rax
0x180006340  mov     rsi, [rsp+22F8h+var_2278]
0x180006348  mov     rax, [rsp+22F8h+var_2298]
0x18000634d  mov     [rsp+22F8h+lpValueName], rax
0x180006352  mov     r12d, edi
0x180006355  test    rcx, rcx
0x180006358  jnz     short loc_180006371
0x18000635a  lea     rcx, [rsp+22F8h+var_2268]
0x180006362  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006367  mov     eax, 80004005h
0x18000636c  jmp     loc_180006007
0x180006371  mov     r8, rdi; Size
0x180006374  xor     edx, edx; Val
0x180006376  call    memset_0
0x18000637b  mov     r10d, ebx
0x18000637e  test    r14d, r14d
0x180006381  jle     loc_18000645F
0x180006387  mov     r15d, 30h ; '0'
0x18000638d  mov     eax, r10d
0x180006390  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180006398  cmp     edx, 61h ; 'a'
0x18000639b  ja      short loc_18000640A
0x18000639d  jz      loc_18000642A
0x1800063a3  cmp     edx, 38h ; '8'
0x1800063a6  ja      short loc_1800063DC
0x1800063a8  jz      short loc_1800063D4
0x1800063aa  mov     ecx, edx
0x1800063ac  sub     ecx, r15d
0x1800063af  jz      short loc_1800063D4
0x1800063b1  sub     ecx, 1
0x1800063b4  jz      short loc_1800063D4
0x1800063b6  sub     ecx, 1
0x1800063b9  jz      short loc_1800063D4
0x1800063bb  sub     ecx, 1
0x1800063be  jz      short loc_1800063D4
0x1800063c0  sub     ecx, 1
0x1800063c3  jz      short loc_1800063D4
0x1800063c5  sub     ecx, 1
0x1800063c8  jz      short loc_1800063D4
0x1800063ca  sub     ecx, 1
0x1800063cd  jz      short loc_1800063D4
0x1800063cf  cmp     ecx, 1
0x1800063d2  jnz     short loc_180006425
0x1800063d4  mov     r9d, edx
0x1800063d7  sub     r9d, r15d
0x1800063da  jmp     short loc_18000642E
0x1800063dc  mov     r9d, edx
0x1800063df  mov     ecx, edx
0x1800063e1  sub     ecx, 39h ; '9'
0x1800063e4  jz      short loc_1800063D4
0x1800063e6  sub     ecx, r13d
0x1800063e9  jz      short loc_180006404
0x1800063eb  sub     ecx, 1
0x1800063ee  jz      short loc_180006404
0x1800063f0  sub     ecx, 1
0x1800063f3  jz      short loc_180006404
0x1800063f5  sub     ecx, 1
0x1800063f8  jz      short loc_180006404
0x1800063fa  sub     ecx, 1
0x1800063fd  jz      short loc_180006404
0x1800063ff  cmp     ecx, 1
0x180006402  jnz     short loc_180006425
0x180006404  add     r9d, 0FFFFFFC9h
0x180006408  jmp     short loc_18000642E
  ... truncated ...
```
