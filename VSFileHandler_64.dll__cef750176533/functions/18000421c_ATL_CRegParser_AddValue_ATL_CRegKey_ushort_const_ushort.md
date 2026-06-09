# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000421c`
- end: `0x180004839`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1565`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004bb4`

## callees

- `0x180002238`
- `0x180003b90`
- `0x180003bb0`
- `0x18000421c`
- `0x180004a00`
- `0x180004a10`
- `0x180007700`
- `0x18001aff0`
- `0x180024220`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800044d3`
- `ADVAPI32!RegSetValueExW` at `0x18000474c`
- `ADVAPI32!RegSetValueExW` at `0x1800047b1`
- `ADVAPI32!RegSetValueExW` at `0x1800044d3`
- `ADVAPI32!RegSetValueExW` at `0x18000474c`
- `ADVAPI32!RegSetValueExW` at `0x1800047b1`
- `KERNEL32!lstrcmpiW` at `0x180004297`
- `KERNEL32!lstrcmpiW` at `0x1800042b5`
- `KERNEL32!lstrcmpiW` at `0x1800042d5`
- `KERNEL32!lstrcmpiW` at `0x1800042f3`
- `KERNEL32!lstrcmpiW` at `0x180004297`
- `KERNEL32!lstrcmpiW` at `0x1800042b5`
- `KERNEL32!lstrcmpiW` at `0x1800042d5`
- `KERNEL32!lstrcmpiW` at `0x1800042f3`
- `USER32!CharNextW` at `0x18000444a`
- `USER32!CharNextW` at `0x180004466`
- `USER32!CharNextW` at `0x1800047e5`
- `USER32!CharNextW` at `0x18000444a`
- `USER32!CharNextW` at `0x180004466`
- `USER32!CharNextW` at `0x1800047e5`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000451f`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000451f`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  LPCWSTR *v6; // r13
  HRESULT result; // eax
  int v8; // edi
  __int64 v9; // rdi
  int v10; // edi
  BYTE **v11; // rdi
  HKEY *v12; // r12
  WCHAR *i; // r14
  const WCHAR *v14; // rax
  LSTATUS v15; // esi
  DWORD cbData; // r9d
  BYTE *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdi
  size_t v21; // r12
  BYTE **v22; // rcx
  int v23; // r9d
  __int64 v24; // r8
  unsigned int v25; // edx
  char v26; // dl
  __int64 v27; // rsi
  const WCHAR *lpValueName; // [rsp+30h] [rbp-22B8h]
  ULONG pulOut; // [rsp+70h] [rbp-2278h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-2270h] BYREF
  BYTE *v36[34]; // [rsp+80h] [rbp-2268h] BYREF
  BYTE *lpData[34]; // [rsp+190h] [rbp-2158h] BYREF
  WCHAR String1[4096]; // [rsp+2A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v6 = this;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  _mm_lfence();
  if ( result >= 0 )
  {
    if ( !lstrcmpiW(String1, L"S") )
    {
      v8 = 8;
      goto LABEL_10;
    }
    if ( !lstrcmpiW(String1, L"M") )
    {
      v8 = 16392;
      goto LABEL_10;
    }
    if ( !lstrcmpiW(String1, L"D") )
    {
      v8 = 19;
      goto LABEL_10;
    }
    if ( !lstrcmpiW(String1, L"B") )
    {
      v8 = 17;
LABEL_10:
      _mm_lfence();
      while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
        *v6 = CharNextW(*v6);
      result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
      if ( result < 0 )
        goto LABEL_16;
      if ( v8 == 8 )
      {
        v27 = -1;
        do
          ++v27;
        while ( String1[v27] );
        v15 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v27 + 2);
        goto LABEL_92;
      }
      if ( v8 != 17 )
      {
        if ( v8 == 19 )
        {
          result = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( result < 0 )
            goto LABEL_16;
          *(_DWORD *)Data = pulOut;
          v15 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        }
        else
        {
          v9 = -1;
          do
            ++v9;
          while ( String1[v9] );
          v10 = v9 + 2;
          memset(lpData, 0, 0x108u);
          try
          {
            lpData[0] = 0;
            if ( !v10 )
              goto LABEL_27;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v10 < 2 )
            {
              _mm_lfence();
              ATL::AtlThrowImpl(-2147024362);
            }
            if ( (unsigned __int64)(2LL * v10) > 0x100 )
            {
              _mm_lfence();
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(lpData, 2LL * v10);
              v11 = (BYTE **)lpData[0];
            }
            else
            {
LABEL_27:
              v11 = &lpData[1];
              lpData[0] = (BYTE *)&lpData[1];
            }
            v12 = a2;
          }
          catch ( ... )
          {
            v11 = (BYTE **)lpData[0];
            v6 = this;
            v12 = a2;
            lpValueName = a3;
          }
          if ( v11 )
          {
            for ( i = String1; *i; v11 = (BYTE **)((char *)v11 + 2) )
            {
              v14 = CharNextW(i);
              if ( *i == 92 && *v14 == 48 )
              {
                *(_WORD *)v11 = 0;
                i = CharNextW(v14);
              }
              else
              {
                *(_WORD *)v11 = *i++;
              }
            }
            *(_DWORD *)v11 = 0;
            v11 = (BYTE **)lpData[0];
            if ( lpData[0] )
            {
              cbData = 0;
              v17 = lpData[0];
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
              v15 = RegSetValueExW(*v12, lpValueName, 0, 7u, lpData[0], cbData);
              v11 = (BYTE **)lpData[0];
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
          if ( v11 != &lpData[1] )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(lpData);
        }
LABEL_92:
        if ( v15 )
          return ATL::AtlHresultFromWin32(v15);
        _mm_lfence();
        result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, a4);
        if ( result >= 0 )
          return 0;
LABEL_16:
        _mm_lfence();
        return result;
      }
      v20 = -1;
      do
        ++v20;
      while ( String1[v20] );
      *(_DWORD *)Data = v20;
      if ( (v20 & 1) != 0 )
        return -2147467259;
      v21 = (int)v20 / 2;
      pulOut = (int)v20 / 2;
      memset(v36, 0, 0x108u);
      v36[0] = 0;
      if ( !(_DWORD)v21 )
        goto LABEL_55;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v21) )
      {
        _mm_lfence();
        ATL::AtlThrowImpl(-2147024362);
      }
      if ( v21 > 0x100 )
      {
        _mm_lfence();
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(v36, v21);
        v22 = (BYTE **)v36[0];
      }
      else
      {
LABEL_55:
        v22 = &v36[1];
        v36[0] = (BYTE *)&v36[1];
      }
      if ( !v22 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(v36);
        return -2147467259;
      }
      memset(v22, 0, v21);
      v23 = 0;
      if ( (int)v20 <= 0 )
      {
LABEL_87:
        v15 = RegSetValueExW(*a2, lpValueName, 0, 3u, v36[0], v21);
        if ( (BYTE **)v36[0] != &v36[1] )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(v36);
        goto LABEL_92;
      }
      v24 = 0;
      while ( 1 )
      {
        v25 = String1[v24];
        if ( v25 > 0x61 )
        {
          if ( v25 == 98 || v25 == 99 || v25 == 100 || v25 - 101 < 2 )
          {
LABEL_85:
            v26 = v25 - 87;
            goto LABEL_86;
          }
LABEL_84:
          v26 = 0;
          goto LABEL_86;
        }
        if ( v25 == 97 )
          goto LABEL_85;
        if ( v25 <= 0x38 )
          break;
        if ( v25 == 57 )
          goto LABEL_72;
        if ( v25 != 65 && v25 != 66 && v25 != 67 && v25 != 68 && v25 - 69 > 1 )
          goto LABEL_84;
        v26 = v25 - 55;
LABEL_86:
        v36[0][v23 / 2] |= v26 << (4 - 4 * (v23 & 1));
        ++v23;
        if ( ++v24 >= (int)v20 )
          goto LABEL_87;
      }
      if ( v25 != 56 && v25 != 48 && v25 != 49 && v25 != 50 && v25 != 51 && v25 != 52 && v25 != 53 && v25 - 54 > 1 )
        goto LABEL_84;
LABEL_72:
      v26 = v25 - 48;
      goto LABEL_86;
    }
    return -2147352567;
  }
  return result;
}

```

## disassembly

```asm
0x18000421c  push    rbx
0x18000421e  push    rsi
0x18000421f  push    rdi
0x180004220  push    r12
0x180004222  push    r13
0x180004224  push    r14
0x180004226  push    r15
0x180004228  mov     eax, 22B0h
0x18000422d  call    _alloca_probe
0x180004232  sub     rsp, rax
0x180004235  mov     rax, cs:__security_cookie
0x18000423c  xor     rax, rsp
0x18000423f  mov     [rsp+22E8h+var_48], rax
0x180004247  mov     r14, r8
0x18000424a  mov     [rsp+22E8h+lpValueName], r8
0x18000424f  mov     r15, rdx
0x180004252  mov     [rsp+22E8h+var_22B0], rdx
0x180004257  mov     r13, rcx
0x18000425a  mov     [rsp+22E8h+var_22A8], rcx
0x18000425f  mov     [rsp+22E8h+var_22A0], rdx
0x180004264  mov     [rsp+22E8h+var_2298], r8
0x180004269  mov     [rsp+22E8h+var_2280], r9
0x18000426e  lea     rdx, [rsp+22E8h+String1]; unsigned __int16 *
0x180004276  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000427b  xor     ebx, ebx
0x18000427d  lfence
0x180004280  test    eax, eax
0x180004282  js      loc_1800047F9
0x180004288  lea     rdx, String2; "S"
0x18000428f  lea     rcx, [rsp+22E8h+String1]; lpString1
0x180004297  call    cs:__imp_lstrcmpiW
0x18000429d  test    eax, eax
0x18000429f  jnz     short loc_1800042A6
0x1800042a1  lea     edi, [rbx+8]
0x1800042a4  jmp     short loc_180004304
0x1800042a6  lea     rdx, aM; "M"
0x1800042ad  lea     rcx, [rsp+22E8h+String1]; lpString1
0x1800042b5  call    cs:__imp_lstrcmpiW
0x1800042bb  test    eax, eax
0x1800042bd  jnz     short loc_1800042C6
0x1800042bf  mov     edi, 4008h
0x1800042c4  jmp     short loc_180004304
0x1800042c6  lea     rdx, aD; "D"
0x1800042cd  lea     rcx, [rsp+22E8h+String1]; lpString1
0x1800042d5  call    cs:__imp_lstrcmpiW
0x1800042db  test    eax, eax
0x1800042dd  jnz     short loc_1800042E4
0x1800042df  lea     edi, [rax+13h]
0x1800042e2  jmp     short loc_180004304
0x1800042e4  lea     rdx, aB; "B"
0x1800042eb  lea     rcx, [rsp+22E8h+String1]; lpString1
0x1800042f3  call    cs:__imp_lstrcmpiW
0x1800042f9  test    eax, eax
0x1800042fb  jnz     loc_1800047F4
0x180004301  lea     edi, [rax+11h]
0x180004304  lfence
0x180004307  mov     rdx, [r13+0]
0x18000430b  movzx   ecx, word ptr [rdx]
0x18000430e  sub     ecx, 9
0x180004311  jz      loc_1800047E2
0x180004317  sub     ecx, 1
0x18000431a  jz      loc_1800047E2
0x180004320  sub     ecx, 3
0x180004323  jz      loc_1800047E2
0x180004329  cmp     ecx, 13h
0x18000432c  jz      loc_1800047E2
0x180004332  lea     rdx, [rsp+22E8h+String1]; unsigned __int16 *
0x18000433a  mov     rcx, r13; this
0x18000433d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004342  test    eax, eax
0x180004344  jns     short loc_18000434E
0x180004346  lfence
0x180004349  jmp     loc_1800047F9
0x18000434e  cmp     edi, 8
0x180004351  jz      loc_180004775
0x180004357  cmp     edi, 11h
0x18000435a  jz      loc_18000454D
0x180004360  cmp     edi, 13h
0x180004363  jz      loc_18000450D
0x180004369  cmp     edi, 4008h
0x18000436f  jnz     loc_1800047C6
0x180004375  lea     rax, [rsp+22E8h+String1]
0x18000437d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004381  mov     rdi, rsi
0x180004384  inc     rdi
0x180004387  cmp     [rax+rdi*2], bx
0x18000438b  jnz     short loc_180004384
0x18000438d  add     edi, 2
0x180004390  xor     edx, edx; Val
0x180004392  mov     r8d, 108h; Size
0x180004398  lea     rcx, [rsp+22E8h+var_2158]; void *
0x1800043a0  call    memset
0x1800043a5  mov     [rsp+22E8h+var_2158], rbx
0x1800043ad  movsxd  rcx, edi
0x1800043b0  test    edi, edi
0x1800043b2  jz      short loc_1800043ED
0x1800043b4  xor     edx, edx
0x1800043b6  mov     rax, rsi
0x1800043b9  div     rcx
0x1800043bc  cmp     rax, 2
0x1800043c0  jb      loc_18000481C
0x1800043c6  lea     rdx, [rcx+rcx]
0x1800043ca  cmp     rdx, 100h
0x1800043d1  jbe     short loc_1800043ED
0x1800043d3  lfence
0x1800043d6  lea     rcx, [rsp+22E8h+var_2158]
0x1800043de  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800043e3  mov     rdi, [rsp+22E8h+var_2158]
0x1800043eb  jmp     short loc_1800043FD
0x1800043ed  lea     rdi, [rsp+22E8h+var_2150]
0x1800043f5  mov     [rsp+22E8h+var_2158], rdi
0x1800043fd  mov     r12, [rsp+22E8h+var_22B0]
0x180004402  jmp     short loc_180004426
0x180004404  xor     ebx, ebx
0x180004406  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000440a  mov     rdi, [rsp+22E8h+var_2158]
0x180004412  mov     r13, [rsp+22E8h+var_22A8]
0x180004417  mov     r12, [rsp+22E8h+var_22A0]
0x18000441c  mov     rax, [rsp+22E8h+var_2298]
0x180004421  mov     [rsp+22E8h+lpValueName], rax
0x180004426  test    rdi, rdi
0x180004429  jz      loc_1800044E5
0x18000442f  lea     r14, [rsp+22E8h+String1]
0x180004437  cmp     [rsp+22E8h+String1], bx
0x18000443f  jz      short loc_180004482
0x180004441  mov     r15d, 30h ; '0'
0x180004447  mov     rcx, r14; lpsz
0x18000444a  call    cs:__imp_CharNextW
0x180004450  movzx   ecx, word ptr [r14]
0x180004454  cmp     cx, 5Ch ; '\'
0x180004458  jnz     short loc_180004471
0x18000445a  cmp     [rax], r15w
0x18000445e  jnz     short loc_180004471
0x180004460  mov     [rdi], bx
0x180004463  mov     rcx, rax; lpsz
0x180004466  call    cs:__imp_CharNextW
0x18000446c  mov     r14, rax
0x18000446f  jmp     short loc_180004478
0x180004471  mov     [rdi], cx
0x180004474  add     r14, 2
0x180004478  add     rdi, 2
0x18000447c  cmp     [r14], bx
0x180004480  jnz     short loc_180004447
0x180004482  and     dword ptr [rdi], 0
0x180004485  mov     rdi, [rsp+22E8h+var_2158]
0x18000448d  test    rdi, rdi
0x180004490  jnz     short loc_180004497
0x180004492  lea     esi, [rdi+0Dh]
0x180004495  jmp     short loc_1800044EA
0x180004497  mov     r9d, ebx
0x18000449a  mov     r8, rdi
0x18000449d  mov     rcx, rsi
0x1800044a0  inc     rcx
0x1800044a3  cmp     [r8+rcx*2], bx
0x1800044a8  jnz     short loc_1800044A0
0x1800044aa  inc     ecx
0x1800044ac  lea     r8, [r8+rcx*2]
0x1800044b0  lea     r9d, [r9+rcx*2]
0x1800044b4  cmp     ecx, 1
0x1800044b7  jnz     short loc_18000449D
0x1800044b9  mov     [rsp+22E8h+cbData], r9d; cbData
0x1800044be  mov     [rsp+22E8h+lpData], rdi; lpData
0x1800044c3  lea     r9d, [rcx+6]; dwType
0x1800044c7  xor     r8d, r8d; Reserved
0x1800044ca  mov     rdx, [rsp+22E8h+lpValueName]; lpValueName
0x1800044cf  mov     rcx, [r12]; hKey
0x1800044d3  call    cs:__imp_RegSetValueExW
0x1800044d9  mov     esi, eax
0x1800044db  mov     rdi, [rsp+22E8h+var_2158]
0x1800044e3  jmp     short loc_1800044EA
0x1800044e5  mov     esi, 0Eh
0x1800044ea  lea     rax, [rsp+22E8h+var_2150]
0x1800044f2  cmp     rdi, rax
0x1800044f5  jz      loc_1800047B9
0x1800044fb  lea     rcx, [rsp+22E8h+var_2158]
0x180004503  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004508  jmp     loc_1800047B9
0x18000450d  lea     r9, [rsp+22E8h+pulOut]; pulOut
0x180004512  xor     r8d, r8d; dwFlags
0x180004515  xor     edx, edx; lcid
0x180004517  lea     rcx, [rsp+22E8h+String1]; strIn
0x18000451f  call    cs:__imp_VarUI4FromStr
0x180004525  test    eax, eax
0x180004527  js      loc_180004346
0x18000452d  mov     eax, [rsp+22E8h+pulOut]
0x180004531  mov     dword ptr [rsp+22E8h+Data], eax
0x180004535  mov     [rsp+22E8h+cbData], 4
0x18000453d  lea     rax, [rsp+22E8h+Data]
0x180004542  mov     r9d, 4
0x180004548  jmp     loc_1800047A3
0x18000454d  lea     rax, [rsp+22E8h+String1]
0x180004555  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004559  mov     rdi, rsi
0x18000455c  inc     rdi
0x18000455f  cmp     [rax+rdi*2], bx
0x180004563  jnz     short loc_18000455C
0x180004565  mov     dword ptr [rsp+22E8h+Data], edi
0x180004569  test    dil, 1
0x18000456d  jnz     loc_180004639
0x180004573  mov     eax, edi
0x180004575  cdq
0x180004576  sub     eax, edx
0x180004578  sar     eax, 1
0x18000457a  movsxd  r12, eax
0x18000457d  mov     [rsp+22E8h+pulOut], r12d
0x180004582  xor     edx, edx; Val
0x180004584  mov     r8d, 108h; Size
0x18000458a  lea     rcx, [rsp+22E8h+var_2268]; void *
0x180004592  call    memset
0x180004597  mov     [rsp+22E8h+var_2268], rbx
0x18000459f  mov     r14, r12
0x1800045a2  mov     [rsp+22E8h+var_2288], r12
0x1800045a7  test    r12d, r12d
0x1800045aa  jz      short loc_1800045E4
0x1800045ac  xor     edx, edx
0x1800045ae  mov     rax, rsi
0x1800045b1  div     r14
0x1800045b4  cmp     rax, 1
0x1800045b8  jb      loc_18000482A
0x1800045be  cmp     r14, 100h
0x1800045c5  jbe     short loc_1800045E4
0x1800045c7  lfence
0x1800045ca  mov     rdx, r14
0x1800045cd  lea     rcx, [rsp+22E8h+var_2268]
0x1800045d5  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800045da  mov     rcx, [rsp+22E8h+var_2268]
0x1800045e2  jmp     short loc_1800045F4
0x1800045e4  lea     rcx, [rsp+22E8h+var_2260]; void *
0x1800045ec  mov     [rsp+22E8h+var_2268], rcx
0x1800045f4  mov     rsi, [rsp+22E8h+var_22B0]
0x1800045f9  jmp     short loc_180004627
0x1800045fb  xor     ebx, ebx
0x1800045fd  mov     edi, dword ptr [rsp+22E8h+Data]
0x180004601  mov     r12d, [rsp+22E8h+pulOut]
0x180004606  mov     rcx, [rsp+22E8h+var_2268]
0x18000460e  mov     r14, [rsp+22E8h+var_2288]
0x180004613  mov     r13, [rsp+22E8h+var_22A8]
0x180004618  mov     rsi, [rsp+22E8h+var_22A0]
0x18000461d  mov     rax, [rsp+22E8h+var_2298]
0x180004622  mov     [rsp+22E8h+lpValueName], rax
0x180004627  test    rcx, rcx
0x18000462a  jnz     short loc_180004643
0x18000462c  lea     rcx, [rsp+22E8h+var_2268]
0x180004634  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004639  mov     eax, 80004005h
0x18000463e  jmp     loc_1800047F9
0x180004643  mov     r8, r14; Size
0x180004646  xor     edx, edx; Val
0x180004648  call    memset
0x18000464d  mov     r9d, ebx
0x180004650  movsxd  r11, edi
0x180004653  test    edi, edi
0x180004655  jle     loc_180004729
0x18000465b  mov     r8, rbx
0x18000465e  mov     r15d, 30h ; '0'
0x180004664  mov     eax, r9d
0x180004667  cdq
0x180004668  sub     eax, edx
0x18000466a  sar     eax, 1
0x18000466c  movsxd  r10, eax
0x18000466f  add     r10, [rsp+22E8h+var_2268]
0x180004677  movzx   edx, [rsp+r8*2+22E8h+String1]
0x180004680  mov     ecx, edx
0x180004682  cmp     edx, 61h ; 'a'
0x180004685  ja      short loc_1800046E5
0x180004687  jz      short loc_180004702
0x180004689  cmp     edx, 38h ; '8'
0x18000468c  ja      short loc_1800046BD
0x18000468e  jz      short loc_1800046B8
0x180004690  sub     ecx, r15d
0x180004693  jz      short loc_1800046B8
0x180004695  sub     ecx, 1
0x180004698  jz      short loc_1800046B8
0x18000469a  sub     ecx, 1
0x18000469d  jz      short loc_1800046B8
0x18000469f  sub     ecx, 1
0x1800046a2  jz      short loc_1800046B8
0x1800046a4  sub     ecx, 1
0x1800046a7  jz      short loc_1800046B8
0x1800046a9  sub     ecx, 1
0x1800046ac  jz      short loc_1800046B8
0x1800046ae  sub     ecx, 1
0x1800046b1  jz      short loc_1800046B8
0x1800046b3  cmp     ecx, 1
0x1800046b6  jnz     short loc_1800046FE
0x1800046b8  sub     dl, r15b
0x1800046bb  jmp     short loc_180004705
0x1800046bd  sub     ecx, 39h ; '9'
0x1800046c0  jz      short loc_1800046B8
0x1800046c2  sub     ecx, 8
0x1800046c5  jz      short loc_1800046E0
0x1800046c7  sub     ecx, 1
0x1800046ca  jz      short loc_1800046E0
0x1800046cc  sub     ecx, 1
0x1800046cf  jz      short loc_1800046E0
0x1800046d1  sub     ecx, 1
0x1800046d4  jz      short loc_1800046E0
0x1800046d6  sub     ecx, 1
0x1800046d9  jz      short loc_1800046E0
0x1800046db  cmp     ecx, 1
  ... truncated ...
```
