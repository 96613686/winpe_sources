# GetContentId(ushort const *,_GUID *)

- ea: `0x180022348`
- end: `0x1800225bd`
- name: `?GetContentId@@YAJPEBGPEAU_GUID@@@Z`
- size: `629`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022720`

## callees

- `0x180001ac0`
- `0x180022348`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002252e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002259f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002252e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002259f`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800223c3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18002243d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800223c3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18002243d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800223f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800223f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022546`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002258d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022546`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002258d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800224cd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800224cd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800224b5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800224b5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180022518`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180022518`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800224ff`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800224ff`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180022524`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180022524`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002248b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002248b`

## pseudocode

```c
__int64 __fastcall GetContentId(LPCWSTR lpSrcStr, struct _GUID *a2)
{
  __int64 v2; // rsi
  struct _GUID *v3; // rdi
  __int64 v4; // rax
  BYTE *v6; // r14
  int v7; // eax
  unsigned __int64 cchDest; // r13
  SIZE_T v9; // rax
  BYTE *lpDestStr; // rdi
  signed int v11; // ebx
  signed int LastError; // eax
  signed int v14; // eax
  HCRYPTHASH phHash; // [rsp+50h] [rbp-19h] BYREF
  int cchSrc; // [rsp+58h] [rbp-11h] BYREF
  HCRYPTPROV phProv; // [rsp+60h] [rbp-9h] BYREF
  BYTE pbData[16]; // [rsp+68h] [rbp-1h] BYREF
  __int128 v19; // [rsp+78h] [rbp+Fh]

  phHash = (HCRYPTHASH)a2;
  v2 = -1;
  v3 = a2;
  v4 = -1;
  v6 = 0;
  do
    ++v4;
  while ( lpSrcStr[v4] );
  cchSrc = v4 + 1;
  v7 = LCMapStringEx(&LocaleName, 0x100u, lpSrcStr, v4 + 1, 0, 0, 0, 0, 0);
  cchDest = v7;
  if ( v7 )
  {
    phProv = 0;
    v9 = 2LL * v7;
    if ( !is_mul_ok(cchDest, 2u) )
      return (unsigned int)-2147024362;
    lpDestStr = (BYTE *)LocalAlloc(0x40u, v9);
    v11 = lpDestStr == 0 ? 0x8007000E : 0;
    if ( lpDestStr )
    {
      if ( LCMapStringEx(&LocaleName, 0x100u, lpSrcStr, cchSrc, (LPWSTR)lpDestStr, cchDest, 0, 0, 0) )
      {
        v6 = lpDestStr;
        *(_WORD *)&lpDestStr[2 * cchDest - 2] = 0;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        LocalFree(lpDestStr);
      }
    }
    v3 = (struct _GUID *)phHash;
  }
  else
  {
    v14 = GetLastError();
    v11 = v14;
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
  }
  if ( v11 >= 0 )
  {
    do
      ++v2;
    while ( *(_WORD *)&v6[2 * v2] );
    phProv = 0;
    if ( CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000) )
    {
      phHash = 0;
      if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, v6, 2 * v2, 0) )
        {
          cchSrc = 32;
          *(_OWORD *)pbData = 0;
          v19 = 0;
          if ( CryptGetHashParam(phHash, 2u, pbData, (DWORD *)&cchSrc, 0) )
          {
            v11 = 0;
            *v3 = *(struct _GUID *)pbData;
          }
        }
        CryptDestroyHash(phHash);
      }
      CryptReleaseContext(phProv, 0);
    }
    LocalFree(v6);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180022348  mov     [rsp-8+arg_10], rbx
0x18002234d  push    rbp
0x18002234e  push    rsi
0x18002234f  push    rdi
0x180022350  push    r12
0x180022352  push    r13
0x180022354  push    r14
0x180022356  push    r15
0x180022358  lea     rbp, [rsp-27h]
0x18002235d  sub     rsp, 90h
0x180022364  mov     rax, cs:__security_cookie
0x18002236b  xor     rax, rsp
0x18002236e  mov     [rbp+57h+var_38], rax
0x180022372  xor     r12d, r12d
0x180022375  mov     [rbp+57h+phHash], rdx
0x180022379  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002237d  mov     rdi, rdx
0x180022380  mov     rax, rsi
0x180022383  mov     r15, rcx
0x180022386  mov     r14d, r12d
0x180022389  inc     rax
0x18002238c  cmp     [rcx+rax*2], r12w
0x180022391  jnz     short loc_180022389
0x180022393  mov     [rsp+0C0h+sortHandle], r12; sortHandle
0x180022398  lea     rcx, LocaleName; lpLocaleName
0x18002239f  mov     [rsp+0C0h+lpReserved], r12; lpReserved
0x1800223a4  inc     eax
0x1800223a6  mov     [rsp+0C0h+lpVersionInformation], r12; lpVersionInformation
0x1800223ab  mov     r9d, eax; cchSrc
0x1800223ae  mov     [rsp+0C0h+cchDest], r12d; cchDest
0x1800223b3  mov     r8, r15; lpSrcStr
0x1800223b6  mov     edx, 100h; dwMapFlags
0x1800223bb  mov     [rsp+0C0h+lpDestStr], r12; lpDestStr
0x1800223c0  mov     [rbp+57h+cchSrc], eax
0x1800223c3  call    cs:__imp_LCMapStringEx
0x1800223c9  movsxd  r13, eax
0x1800223cc  test    eax, eax
0x1800223ce  jz      loc_18002259F
0x1800223d4  mov     eax, 2
0x1800223d9  mov     [rbp+57h+phProv], r12
0x1800223dd  mul     r13
0x1800223e0  test    rdx, rdx
0x1800223e3  jnz     loc_180022598
0x1800223e9  mov     rdx, rax; uBytes
0x1800223ec  mov     ecx, 40h ; '@'; uFlags
0x1800223f1  call    cs:__imp_LocalAlloc
0x1800223f7  mov     rcx, rax
0x1800223fa  mov     rdi, rax
0x1800223fd  neg     rcx
0x180022400  sbb     ebx, ebx
0x180022402  xor     eax, eax
0x180022404  not     ebx
0x180022406  and     ebx, 8007000Eh
0x18002240c  test    rdi, rdi
0x18002240f  jz      short loc_180022456
0x180022411  mov     r9d, [rbp+57h+cchSrc]; cchSrc
0x180022415  lea     rcx, LocaleName; lpLocaleName
0x18002241c  mov     [rsp+0C0h+sortHandle], rax; sortHandle
0x180022421  mov     r8, r15; lpSrcStr
0x180022424  mov     [rsp+0C0h+lpReserved], rax; lpReserved
0x180022429  mov     edx, 100h; dwMapFlags
0x18002242e  mov     [rsp+0C0h+lpVersionInformation], rax; lpVersionInformation
0x180022433  mov     [rsp+0C0h+cchDest], r13d; cchDest
0x180022438  mov     [rsp+0C0h+lpDestStr], rdi; lpDestStr
0x18002243d  call    cs:__imp_LCMapStringEx
0x180022443  test    eax, eax
0x180022445  jz      loc_180022575
0x18002244b  xor     eax, eax
0x18002244d  mov     r14, rdi
0x180022450  mov     [rdi+r13*2-2], ax
0x180022456  mov     rdi, [rbp+57h+phHash]
0x18002245a  test    ebx, ebx
0x18002245c  js      loc_18002254C
0x180022462  inc     rsi
0x180022465  cmp     [r14+rsi*2], r12w
0x18002246a  jnz     short loc_180022462
0x18002246c  mov     r9d, 18h; dwProvType
0x180022472  mov     [rbp+57h+phProv], r12
0x180022476  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18002247d  mov     dword ptr [rsp+0C0h+lpDestStr], 0F0000000h; dwFlags
0x180022485  xor     edx, edx; szContainer
0x180022487  lea     rcx, [rbp+57h+phProv]; phProv
0x18002248b  call    cs:__imp_CryptAcquireContextW
0x180022491  test    eax, eax
0x180022493  jz      loc_180022543
0x180022499  mov     rcx, [rbp+57h+phProv]; hProv
0x18002249d  lea     rax, [rbp+57h+phHash]
0x1800224a1  xor     r9d, r9d; dwFlags
0x1800224a4  mov     [rsp+0C0h+lpDestStr], rax; phHash
0x1800224a9  xor     r8d, r8d; hKey
0x1800224ac  mov     [rbp+57h+phHash], r12
0x1800224b0  mov     edx, 800Ch; Algid
0x1800224b5  call    cs:__imp_CryptCreateHash
0x1800224bb  test    eax, eax
0x1800224bd  jz      short loc_18002251E
0x1800224bf  mov     rcx, [rbp+57h+phHash]; hHash
0x1800224c3  lea     r8d, [rsi+rsi]; dwDataLen
0x1800224c7  xor     r9d, r9d; dwFlags
0x1800224ca  mov     rdx, r14; pbData
0x1800224cd  call    cs:__imp_CryptHashData
0x1800224d3  test    eax, eax
0x1800224d5  jz      short loc_180022514
0x1800224d7  mov     rcx, [rbp+57h+phHash]; hHash
0x1800224db  lea     r9, [rbp+57h+cchSrc]; pdwDataLen
0x1800224df  xorps   xmm0, xmm0
0x1800224e2  mov     [rbp+57h+cchSrc], 20h ; ' '
0x1800224e9  lea     r8, [rbp+57h+pbData]; pbData
0x1800224ed  mov     dword ptr [rsp+0C0h+lpDestStr], r12d; dwFlags
0x1800224f2  mov     edx, 2; dwParam
0x1800224f7  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x1800224fb  movups  [rbp+57h+var_48], xmm0
0x1800224ff  call    cs:__imp_CryptGetHashParam
0x180022505  test    eax, eax
0x180022507  jz      short loc_180022514
0x180022509  movups  xmm0, xmmword ptr [rbp+57h+pbData]
0x18002250d  mov     ebx, r12d
0x180022510  movdqu  xmmword ptr [rdi], xmm0
0x180022514  mov     rcx, [rbp+57h+phHash]; hHash
0x180022518  call    cs:__imp_CryptDestroyHash
0x18002251e  mov     rcx, [rbp+57h+phProv]; hProv
0x180022522  xor     edx, edx; dwFlags
0x180022524  call    cs:__imp_CryptReleaseContext
0x18002252a  test    ebx, ebx
0x18002252c  jns     short loc_180022543
0x18002252e  call    cs:__imp_GetLastError
0x180022534  mov     ebx, eax
0x180022536  test    eax, eax
0x180022538  jle     short loc_180022543
0x18002253a  movzx   ebx, ax
0x18002253d  or      ebx, 80070000h
0x180022543  mov     rcx, r14; hMem
0x180022546  call    cs:__imp_LocalFree
0x18002254c  mov     eax, ebx
0x18002254e  mov     rcx, [rbp+57h+var_38]
0x180022552  xor     rcx, rsp; StackCookie
0x180022555  call    __security_check_cookie
0x18002255a  mov     rbx, [rsp+0C0h+arg_10]
0x180022562  add     rsp, 90h
0x180022569  pop     r15
0x18002256b  pop     r14
0x18002256d  pop     r13
0x18002256f  pop     r12
0x180022571  pop     rdi
0x180022572  pop     rsi
0x180022573  pop     rbp
0x180022574  retn
0x180022575  call    cs:__imp_GetLastError
0x18002257b  mov     ebx, eax
0x18002257d  test    eax, eax
0x18002257f  jle     short loc_18002258A
0x180022581  movzx   ebx, ax
0x180022584  or      ebx, 80070000h
0x18002258a  mov     rcx, rdi; hMem
0x18002258d  call    cs:__imp_LocalFree
0x180022593  jmp     loc_180022456
0x180022598  mov     ebx, 80070216h
0x18002259d  jmp     short loc_18002254C
0x18002259f  call    cs:__imp_GetLastError
0x1800225a5  mov     ebx, eax
0x1800225a7  test    eax, eax
0x1800225a9  jle     loc_18002245A
0x1800225af  movzx   ebx, ax
0x1800225b2  or      ebx, 80070000h
0x1800225b8  jmp     loc_18002245A
```
