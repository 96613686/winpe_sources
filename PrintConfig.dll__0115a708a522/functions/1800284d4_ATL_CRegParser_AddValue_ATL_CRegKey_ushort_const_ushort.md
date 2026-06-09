# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800284d4`
- end: `0x180028ae5`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1553`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002cc74`

## callees

- `0x180003400`
- `0x180004558`
- `0x1800109e8`
- `0x1800284d4`
- `0x180028c18`
- `0x180028e6c`
- `0x18002aba4`
- `0x18002c188`
- `0x1801b5620`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180028571`
- `KERNEL32!lstrcmpiW` at `0x180028571`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800287e2`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800287e2`
- `ADVAPI32!RegSetValueExW` at `0x18002877c`
- `ADVAPI32!RegSetValueExW` at `0x180028820`
- `ADVAPI32!RegSetValueExW` at `0x180028a27`
- `ADVAPI32!RegSetValueExW` at `0x18002877c`
- `ADVAPI32!RegSetValueExW` at `0x180028820`
- `ADVAPI32!RegSetValueExW` at `0x180028a27`
- `USER32!CharNextW` at `0x1800286e7`
- `USER32!CharNextW` at `0x180028709`
- `USER32!CharNextW` at `0x180028aaf`
- `USER32!CharNextW` at `0x1800286e7`
- `USER32!CharNextW` at `0x180028709`
- `USER32!CharNextW` at `0x180028aaf`

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
  OLECHAR *i; // r14
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
  LPCWSTR *v36; // [rsp+38h] [rbp-22D0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22C8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22C0h]
  LPCWSTR *v39; // [rsp+50h] [rbp-22B8h]
  const WCHAR *v40; // [rsp+60h] [rbp-22A8h]
  HKEY *v41; // [rsp+70h] [rbp-2298h]
  size_t v42; // [rsp+78h] [rbp-2290h]
  HKEY *v43; // [rsp+80h] [rbp-2288h]
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
  v41 = a2;
  v6 = this;
  v36 = this;
  *(_QWORD *)Data = a2;
  v39 = this;
  v43 = a2;
  v40 = a3;
  v44 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
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
    result = ATL::CRegParser::NextToken(v6, String1);
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
            Token = ATL::CRegParser::NextToken(v6, v44);
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
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&lpData);
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
        v28 = v41;
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v24) = *(_DWORD *)Data;
        v27 = v46;
        v26 = v42;
        v36 = v39;
        v28 = v43;
        lpValueName = v40;
        v25 = v42;
      }
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v46);
        return -2147467259;
      }
      memset_0(v27, 0, v26);
      v29 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_88:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, v46, v25);
        if ( v46 != v47 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v46);
LABEL_42:
        v6 = v36;
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
0x1800284d4  push    rbx
0x1800284d6  push    rsi
0x1800284d7  push    rdi
0x1800284d8  push    r12
0x1800284da  push    r13
0x1800284dc  push    r14
0x1800284de  push    r15
0x1800284e0  mov     eax, 22D0h
0x1800284e5  call    _alloca_probe
0x1800284ea  sub     rsp, rax
0x1800284ed  mov     [rsp+2308h+var_2278], 0FFFFFFFFFFFFFFFEh
0x1800284f9  mov     rax, cs:__security_cookie
0x180028500  xor     rax, rsp
0x180028503  mov     [rsp+2308h+var_48], rax
0x18002850b  mov     r14, r8
0x18002850e  mov     [rsp+2308h+lpValueName], r8
0x180028513  mov     r12, rdx
0x180028516  mov     [rsp+2308h+var_2298], rdx
0x18002851b  mov     r15, rcx
0x18002851e  mov     [rsp+2308h+var_22D0], rcx
0x180028523  mov     qword ptr [rsp+2308h+Data], rdx
0x180028528  mov     [rsp+2308h+var_22B8], rcx
0x18002852d  mov     [rsp+2308h+var_2288], rdx
0x180028535  mov     [rsp+2308h+var_22A8], r8
0x18002853a  mov     [rsp+2308h+var_2280], r9
0x180028542  lea     rdx, [rsp+2308h+String1]; unsigned __int16 *
0x18002854a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002854f  xor     ebx, ebx
0x180028551  test    eax, eax
0x180028553  js      short loc_18002858D
0x180028555  mov     edi, ebx
0x180028557  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18002855e  movsxd  rsi, edi
0x180028561  add     rsi, rsi
0x180028564  mov     rdx, [r13+rsi*8+0]; lpString2
0x180028569  lea     rcx, [rsp+2308h+String1]; lpString1
0x180028571  call    cs:__imp_lstrcmpiW
0x180028578  nop     dword ptr [rax+rax+00h]
0x18002857d  test    eax, eax
0x18002857f  jz      short loc_1800285B1
0x180028581  inc     edi
0x180028583  cmp     edi, 4
0x180028586  jb      short loc_18002855E
0x180028588  mov     eax, 80020009h
0x18002858d  mov     rcx, [rsp+2308h+var_48]
0x180028595  xor     rcx, rsp; StackCookie
0x180028598  call    __security_check_cookie
0x18002859d  add     rsp, 22D0h
0x1800285a4  pop     r15
0x1800285a6  pop     r14
0x1800285a8  pop     r13
0x1800285aa  pop     r12
0x1800285ac  pop     rdi
0x1800285ad  pop     rsi
0x1800285ae  pop     rbx
0x1800285af  retn
0x1800285b1  movzx   edi, word ptr [r13+rsi*8+8]
0x1800285b7  mov     esi, 13h
0x1800285bc  mov     rdx, [r15]
0x1800285bf  movzx   ecx, word ptr [rdx]
0x1800285c2  sub     ecx, 9
0x1800285c5  jz      loc_180028AAC
0x1800285cb  sub     ecx, 1
0x1800285ce  jz      loc_180028AAC
0x1800285d4  sub     ecx, 3
0x1800285d7  jz      loc_180028AAC
0x1800285dd  cmp     ecx, esi
0x1800285df  jz      loc_180028AAC
0x1800285e5  lea     rdx, [rsp+2308h+String1]; unsigned __int16 *
0x1800285ed  mov     rcx, r15; this
0x1800285f0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800285f5  test    eax, eax
0x1800285f7  js      short loc_18002858D
0x1800285f9  mov     r13d, 8
0x1800285ff  cmp     di, r13w
0x180028603  jz      loc_180028A5D
0x180028609  cmp     di, 11h
0x18002860d  jz      loc_180028830
0x180028613  cmp     di, si
0x180028616  jz      loc_1800287CC
0x18002861c  mov     eax, 4008h
0x180028621  cmp     di, ax
0x180028624  jnz     loc_180028A90
0x18002862a  lea     rcx, [rsp+2308h+String1]
0x180028632  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028636  mov     rax, rsi
0x180028639  inc     rax
0x18002863c  cmp     [rcx+rax*2], bx
0x180028640  jnz     short loc_180028639
0x180028642  add     eax, 2
0x180028645  mov     [rsp+2308h+var_2158], rbx
0x18002864d  test    eax, eax
0x18002864f  jz      short loc_18002868A
0x180028651  movsxd  rcx, eax
0x180028654  xor     edx, edx
0x180028656  mov     rax, rsi
0x180028659  div     rcx
0x18002865c  cmp     rax, 2
0x180028660  jb      loc_180028AC3
0x180028666  lea     rdx, [rcx+rcx]
0x18002866a  cmp     rdx, 100h
0x180028671  jbe     short loc_18002868A
0x180028673  lea     rcx, [rsp+2308h+var_2158]
0x18002867b  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180028680  mov     rdi, [rsp+2308h+var_2158]
0x180028688  jmp     short loc_18002869A
0x18002868a  lea     rdi, [rsp+2308h+var_2150]
0x180028692  mov     [rsp+2308h+var_2158], rdi
0x18002869a  mov     r13, [rsp+2308h+lpValueName]
0x18002869f  jmp     short loc_1800286C3
0x1800286a1  xor     ebx, ebx
0x1800286a3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800286a7  mov     rdi, [rsp+2308h+var_2158]
0x1800286af  mov     r12, qword ptr [rsp+2308h+Data]
0x1800286b4  mov     rax, [rsp+2308h+var_22B8]
0x1800286b9  mov     [rsp+2308h+var_22D0], rax
0x1800286be  mov     r13, [rsp+2308h+var_22A8]
0x1800286c3  test    rdi, rdi
0x1800286c6  jz      loc_180028794
0x1800286cc  lea     r14, [rsp+2308h+String1]
0x1800286d4  cmp     [rsp+2308h+String1], bx
0x1800286dc  jz      short loc_18002872B
0x1800286de  mov     r15d, 30h ; '0'
0x1800286e4  mov     rcx, r14; lpsz
0x1800286e7  call    cs:__imp_CharNextW
0x1800286ee  nop     dword ptr [rax+rax+00h]
0x1800286f3  movzx   ecx, word ptr [r14]
0x1800286f7  cmp     cx, 5Ch ; '\'
0x1800286fb  jnz     short loc_18002871A
0x1800286fd  cmp     [rax], r15w
0x180028701  jnz     short loc_18002871A
0x180028703  mov     [rdi], bx
0x180028706  mov     rcx, rax; lpsz
0x180028709  call    cs:__imp_CharNextW
0x180028710  nop     dword ptr [rax+rax+00h]
0x180028715  mov     r14, rax
0x180028718  jmp     short loc_180028721
0x18002871a  mov     [rdi], cx
0x18002871d  add     r14, 2
0x180028721  add     rdi, 2
0x180028725  cmp     [r14], bx
0x180028729  jnz     short loc_1800286E4
0x18002872b  mov     dword ptr [rdi], 0
0x180028731  mov     r8, [rsp+2308h+var_2158]
0x180028739  test    r8, r8
0x18002873c  jz      loc_180028ACE
0x180028742  mov     r10d, ebx
0x180028745  mov     r9, r8
0x180028748  mov     rcx, rsi
0x18002874b  inc     rcx
0x18002874e  cmp     [r9+rcx*2], bx
0x180028753  jnz     short loc_18002874B
0x180028755  inc     ecx
0x180028757  lea     r9, [r9+rcx*2]
0x18002875b  lea     r10d, [r10+rcx*2]
0x18002875f  cmp     ecx, 1
0x180028762  jnz     short loc_180028748
0x180028764  mov     [rsp+2308h+cbData], r10d; cbData
0x180028769  mov     [rsp+2308h+lpData], r8; lpData
0x18002876e  lea     r9d, [rcx+6]; dwType
0x180028772  xor     r8d, r8d; Reserved
0x180028775  mov     rdx, r13; lpValueName
0x180028778  mov     rcx, [r12]; hKey
0x18002877c  call    cs:__imp_RegSetValueExW
0x180028783  nop     dword ptr [rax+rax+00h]
0x180028788  mov     esi, eax
0x18002878a  mov     rdi, [rsp+2308h+var_2158]
0x180028792  jmp     short loc_180028799
0x180028794  mov     esi, 0Eh
0x180028799  lea     rax, [rsp+2308h+var_2150]
0x1800287a1  cmp     rdi, rax
0x1800287a4  jz      short loc_1800287B3
0x1800287a6  lea     rcx, [rsp+2308h+var_2158]
0x1800287ae  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800287b3  mov     r15, [rsp+2308h+var_22D0]
0x1800287b8  test    esi, esi
0x1800287ba  jz      loc_180028A90
0x1800287c0  mov     ecx, esi; unsigned int
0x1800287c2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800287c7  jmp     loc_18002858D
0x1800287cc  mov     [rsp+2308h+pulOut], ebx
0x1800287d0  lea     r9, [rsp+2308h+pulOut]; pulOut
0x1800287d5  xor     r8d, r8d; dwFlags
0x1800287d8  xor     edx, edx; lcid
0x1800287da  lea     rcx, [rsp+2308h+String1]; strIn
0x1800287e2  call    cs:__imp_VarUI4FromStr
0x1800287e9  nop     dword ptr [rax+rax+00h]
0x1800287ee  test    eax, eax
0x1800287f0  js      loc_18002858D
0x1800287f6  mov     eax, [rsp+2308h+pulOut]
0x1800287fa  mov     dword ptr [rsp+2308h+Data], eax
0x1800287fe  mov     [rsp+2308h+cbData], 4; cbData
0x180028806  lea     rax, [rsp+2308h+Data]
0x18002880b  mov     r9d, 4; dwType
0x180028811  mov     [rsp+2308h+lpData], rax; lpData
0x180028816  xor     r8d, r8d; Reserved
0x180028819  mov     rdx, r14; lpValueName
0x18002881c  mov     rcx, [r12]; hKey
0x180028820  call    cs:__imp_RegSetValueExW
0x180028827  nop     dword ptr [rax+rax+00h]
0x18002882c  mov     esi, eax
0x18002882e  jmp     short loc_1800287B8
0x180028830  lea     rax, [rsp+2308h+String1]
0x180028838  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002883c  mov     r14, rsi
0x18002883f  inc     r14
0x180028842  cmp     [rax+r14*2], bx
0x180028847  jnz     short loc_18002883F
0x180028849  mov     dword ptr [rsp+2308h+Data], r14d
0x18002884e  test    r14b, 1
0x180028852  jnz     loc_18002890C
0x180028858  mov     eax, r14d
0x18002885b  cdq
0x18002885c  sub     eax, edx
0x18002885e  sar     eax, 1
0x180028860  movsxd  r12, eax
0x180028863  mov     [rsp+2308h+var_2268], rbx
0x18002886b  mov     rdi, r12
0x18002886e  mov     [rsp+2308h+var_2290], r12
0x180028873  test    eax, eax
0x180028875  jz      short loc_1800288AC
0x180028877  xor     edx, edx
0x180028879  mov     rax, rsi
0x18002887c  div     rdi
0x18002887f  cmp     rax, 1
0x180028883  jb      loc_180028AD9
0x180028889  cmp     rdi, 100h
0x180028890  jbe     short loc_1800288AC
0x180028892  mov     rdx, rdi
0x180028895  lea     rcx, [rsp+2308h+var_2268]
0x18002889d  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800288a2  mov     rcx, [rsp+2308h+var_2268]
0x1800288aa  jmp     short loc_1800288BC
0x1800288ac  lea     rcx, [rsp+2308h+var_2260]
0x1800288b4  mov     [rsp+2308h+var_2268], rcx
0x1800288bc  mov     rsi, [rsp+2308h+var_2298]
0x1800288c1  jmp     short loc_1800288FA
0x1800288c3  xor     ebx, ebx
0x1800288c5  lea     r13d, [rbx+8]
0x1800288c9  mov     r14d, dword ptr [rsp+2308h+Data]
0x1800288ce  mov     rcx, [rsp+2308h+var_2268]; void *
0x1800288d6  mov     rdi, [rsp+2308h+var_2290]
0x1800288db  mov     rax, [rsp+2308h+var_22B8]
0x1800288e0  mov     [rsp+2308h+var_22D0], rax
0x1800288e5  mov     rsi, [rsp+2308h+var_2288]
0x1800288ed  mov     rax, [rsp+2308h+var_22A8]
0x1800288f2  mov     [rsp+2308h+lpValueName], rax
0x1800288f7  mov     r12d, edi
0x1800288fa  test    rcx, rcx
0x1800288fd  jnz     short loc_180028916
0x1800288ff  lea     rcx, [rsp+2308h+var_2268]
0x180028907  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18002890c  mov     eax, 80004005h
0x180028911  jmp     loc_18002858D
0x180028916  mov     r8, rdi; Size
0x180028919  xor     edx, edx; Val
0x18002891b  call    memset_0
0x180028920  mov     r10d, ebx
0x180028923  test    r14d, r14d
0x180028926  jle     loc_180028A04
0x18002892c  mov     r15d, 30h ; '0'
0x180028932  mov     eax, r10d
0x180028935  movzx   edx, [rsp+rax*2+2308h+String1]
0x18002893d  cmp     edx, 61h ; 'a'
0x180028940  ja      short loc_1800289AF
0x180028942  jz      loc_1800289CF
0x180028948  cmp     edx, 38h ; '8'
0x18002894b  ja      short loc_180028981
0x18002894d  jz      short loc_180028979
0x18002894f  mov     ecx, edx
0x180028951  sub     ecx, r15d
0x180028954  jz      short loc_180028979
0x180028956  sub     ecx, 1
0x180028959  jz      short loc_180028979
0x18002895b  sub     ecx, 1
0x18002895e  jz      short loc_180028979
0x180028960  sub     ecx, 1
0x180028963  jz      short loc_180028979
0x180028965  sub     ecx, 1
0x180028968  jz      short loc_180028979
0x18002896a  sub     ecx, 1
0x18002896d  jz      short loc_180028979
0x18002896f  sub     ecx, 1
0x180028972  jz      short loc_180028979
0x180028974  cmp     ecx, 1
0x180028977  jnz     short loc_1800289CA
0x180028979  mov     r9d, edx
0x18002897c  sub     r9d, r15d
0x18002897f  jmp     short loc_1800289D3
0x180028981  mov     r9d, edx
0x180028984  mov     ecx, edx
0x180028986  sub     ecx, 39h ; '9'
0x180028989  jz      short loc_180028979
0x18002898b  sub     ecx, r13d
0x18002898e  jz      short loc_1800289A9
0x180028990  sub     ecx, 1
0x180028993  jz      short loc_1800289A9
0x180028995  sub     ecx, 1
0x180028998  jz      short loc_1800289A9
0x18002899a  sub     ecx, 1
  ... truncated ...
```
