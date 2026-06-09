# GetContentId(ushort const *,_GUID *)

- ea: `0x180030320`
- end: `0x1800305bb`
- name: `?GetContentId@@YAJPEBGPEAU_GUID@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002fec0`

## callees

- `0x180030320`
- `0x180075e60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030590`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800303a2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180030416`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800303a2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180030416`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003043c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030528`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003043c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030528`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800303d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800303d1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800304fb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800304fb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18003050e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18003050e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18003051b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18003051b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18003047d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18003047d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800304aa`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800304aa`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800304c3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800304c3`

## pseudocode

```c
__int64 __fastcall GetContentId(LPCWSTR lpSrcStr, struct _GUID *a2)
{
  __int64 v2; // rbx
  BYTE *v3; // rsi
  __int64 v4; // rax
  struct _GUID *v5; // r14
  bool v7; // zf
  int v8; // r12d
  int v9; // eax
  unsigned __int64 cchDest; // r15
  SIZE_T v11; // rax
  BYTE *lpDestStr; // r14
  signed int v13; // ebp
  signed int LastError; // eax
  signed int v16; // eax
  HCRYPTHASH phHash; // [rsp+50h] [rbp-78h] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp-70h] BYREF
  DWORD pdwDataLen; // [rsp+60h] [rbp-68h] BYREF
  BYTE pbData[16]; // [rsp+68h] [rbp-60h] BYREF
  __int128 v21; // [rsp+78h] [rbp-50h]

  phHash = (HCRYPTHASH)a2;
  v2 = -1;
  v3 = 0;
  v4 = -1;
  v5 = a2;
  do
    v7 = lpSrcStr[++v4] == 0;
  while ( !v7 );
  v8 = v4 + 1;
  v9 = LCMapStringEx(&LocaleName, 0x100u, lpSrcStr, v4 + 1, 0, 0, 0, 0, 0);
  cchDest = v9;
  if ( v9 )
  {
    phProv = 0;
    v11 = 2LL * v9;
    if ( !is_mul_ok(cchDest, 2u) )
      return 2147942934LL;
    lpDestStr = (BYTE *)LocalAlloc(0x40u, v11);
    v13 = 0;
    if ( lpDestStr )
    {
      if ( LCMapStringEx(&LocaleName, 0x100u, lpSrcStr, v8, (LPWSTR)lpDestStr, cchDest, 0, 0, 0) )
      {
        v3 = lpDestStr;
        *(_WORD *)&lpDestStr[2 * cchDest - 2] = 0;
      }
      else
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        LocalFree(lpDestStr);
      }
    }
    else
    {
      v13 = -2147024882;
    }
    v5 = (struct _GUID *)phHash;
  }
  else
  {
    v16 = GetLastError();
    v13 = v16;
    if ( v16 > 0 )
      v13 = (unsigned __int16)v16 | 0x80070000;
  }
  if ( v13 >= 0 )
  {
    do
      v7 = *(_WORD *)&v3[2 * v2++ + 2] == 0;
    while ( !v7 );
    phProv = 0;
    if ( CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000) )
    {
      phHash = 0;
      if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, v3, 2 * v2, 0) )
        {
          pdwDataLen = 32;
          *(_OWORD *)pbData = 0;
          v21 = 0;
          if ( CryptGetHashParam(phHash, 2u, pbData, &pdwDataLen, 0) )
          {
            v13 = 0;
            *v5 = *(struct _GUID *)pbData;
          }
        }
        CryptDestroyHash(phHash);
      }
      CryptReleaseContext(phProv, 0);
    }
    LocalFree(v3);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180030320  push    rbx
0x180030322  push    rsi
0x180030323  push    rdi
0x180030324  push    r12
0x180030326  push    r13
0x180030328  push    r14
0x18003032a  push    r15
0x18003032c  sub     rsp, 90h
0x180030333  mov     rax, cs:__security_cookie
0x18003033a  xor     rax, rsp
0x18003033d  mov     [rsp+0C8h+var_40], rax
0x180030345  xor     r13d, r13d
0x180030348  mov     [rsp+0C8h+phHash], rdx
0x18003034d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180030354  mov     esi, r13d
0x180030357  mov     rax, rbx
0x18003035a  mov     r14, rdx
0x18003035d  mov     rdi, rcx
0x180030360  cmp     [rcx+rax*2+2], si
0x180030365  lea     rax, [rax+1]
0x180030369  jnz     short loc_180030360
0x18003036b  mov     [rsp+0C8h+sortHandle], r13; sortHandle
0x180030370  lea     r12d, [rax+1]
0x180030374  mov     [rsp+0C8h+lpReserved], r13; lpReserved
0x180030379  lea     rcx, LocaleName; lpLocaleName
0x180030380  mov     [rsp+0C8h+lpVersionInformation], r13; lpVersionInformation
0x180030385  mov     r9d, r12d; cchSrc
0x180030388  mov     [rsp+0C8h+cchDest], r13d; cchDest
0x18003038d  mov     r8, rdi; lpSrcStr
0x180030390  mov     edx, 100h; dwMapFlags
0x180030395  mov     [rsp+0C8h+lpDestStr], r13; lpDestStr
0x18003039a  mov     [rsp+0C8h+arg_10], rbp
0x1800303a2  call    cs:__imp_LCMapStringEx
0x1800303a8  movsxd  r15, eax
0x1800303ab  test    eax, eax
0x1800303ad  jz      loc_180030572
0x1800303b3  mov     eax, 2
0x1800303b8  mov     [rsp+0C8h+phProv], r13
0x1800303bd  mul     r15
0x1800303c0  test    rdx, rdx
0x1800303c3  jnz     loc_18003056B
0x1800303c9  mov     rdx, rax; uBytes
0x1800303cc  mov     ecx, 40h ; '@'; uFlags
0x1800303d1  call    cs:__imp_LocalAlloc
0x1800303d7  mov     r14, rax
0x1800303da  xor     ecx, ecx
0x1800303dc  test    r14, r14
0x1800303df  mov     ebp, ecx
0x1800303e1  mov     eax, 8007000Eh
0x1800303e6  cmovz   ebp, eax
0x1800303e9  jz      short loc_180030442
0x1800303eb  mov     [rsp+0C8h+sortHandle], rcx; sortHandle
0x1800303f0  mov     r9d, r12d; cchSrc
0x1800303f3  mov     [rsp+0C8h+lpReserved], rcx; lpReserved
0x1800303f8  mov     r8, rdi; lpSrcStr
0x1800303fb  mov     [rsp+0C8h+lpVersionInformation], rcx; lpVersionInformation
0x180030400  mov     edx, 100h; dwMapFlags
0x180030405  mov     [rsp+0C8h+cchDest], r15d; cchDest
0x18003040a  lea     rcx, LocaleName; lpLocaleName
0x180030411  mov     [rsp+0C8h+lpDestStr], r14; lpDestStr
0x180030416  call    cs:__imp_LCMapStringEx
0x18003041c  test    eax, eax
0x18003041e  jnz     loc_18003055B
0x180030424  call    cs:__imp_GetLastError
0x18003042a  mov     ebp, eax
0x18003042c  test    eax, eax
0x18003042e  jle     short loc_180030439
0x180030430  movzx   ebp, ax
0x180030433  or      ebp, 80070000h
0x180030439  mov     rcx, r14; hMem
0x18003043c  call    cs:__imp_LocalFree
0x180030442  mov     r14, [rsp+0C8h+phHash]
0x180030447  test    ebp, ebp
0x180030449  js      loc_18003052E
0x18003044f  nop
0x180030450  cmp     word ptr [rsi+rbx*2+2], 0
0x180030456  lea     rbx, [rbx+1]
0x18003045a  jnz     short loc_180030450
0x18003045c  mov     r9d, 18h; dwProvType
0x180030462  mov     [rsp+0C8h+phProv], r13
0x180030467  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18003046e  mov     dword ptr [rsp+0C8h+lpDestStr], 0F0000000h; dwFlags
0x180030476  xor     edx, edx; szContainer
0x180030478  lea     rcx, [rsp+0C8h+phProv]; phProv
0x18003047d  call    cs:__imp_CryptAcquireContextW
0x180030483  test    eax, eax
0x180030485  jz      loc_180030525
0x18003048b  mov     rcx, [rsp+0C8h+phProv]; hProv
0x180030490  lea     rax, [rsp+0C8h+phHash]
0x180030495  xor     r9d, r9d; dwFlags
0x180030498  mov     [rsp+0C8h+lpDestStr], rax; phHash
0x18003049d  xor     r8d, r8d; hKey
0x1800304a0  mov     [rsp+0C8h+phHash], r13
0x1800304a5  mov     edx, 800Ch; Algid
0x1800304aa  call    cs:__imp_CryptCreateHash
0x1800304b0  test    eax, eax
0x1800304b2  jz      short loc_180030514
0x1800304b4  mov     rcx, [rsp+0C8h+phHash]; hHash
0x1800304b9  lea     r8d, [rbx+rbx]; dwDataLen
0x1800304bd  xor     r9d, r9d; dwFlags
0x1800304c0  mov     rdx, rsi; pbData
0x1800304c3  call    cs:__imp_CryptHashData
0x1800304c9  test    eax, eax
0x1800304cb  jz      short loc_180030509
0x1800304cd  mov     rcx, [rsp+0C8h+phHash]; hHash
0x1800304d2  lea     r9, [rsp+0C8h+pdwDataLen]; pdwDataLen
0x1800304d7  xorps   xmm0, xmm0
0x1800304da  mov     [rsp+0C8h+pdwDataLen], 20h ; ' '
0x1800304e2  lea     r8, [rsp+0C8h+pbData]; pbData
0x1800304e7  mov     dword ptr [rsp+0C8h+lpDestStr], r13d; dwFlags
0x1800304ec  mov     edx, 2; dwParam
0x1800304f1  movups  xmmword ptr [rsp+0C8h+pbData], xmm0
0x1800304f6  movups  [rsp+0C8h+var_50], xmm0
0x1800304fb  call    cs:__imp_CryptGetHashParam
0x180030501  test    eax, eax
0x180030503  jnz     loc_1800305AA
0x180030509  mov     rcx, [rsp+0C8h+phHash]; hHash
0x18003050e  call    cs:__imp_CryptDestroyHash
0x180030514  mov     rcx, [rsp+0C8h+phProv]; hProv
0x180030519  xor     edx, edx; dwFlags
0x18003051b  call    cs:__imp_CryptReleaseContext
0x180030521  test    ebp, ebp
0x180030523  js      short loc_180030590
0x180030525  mov     rcx, rsi; hMem
0x180030528  call    cs:__imp_LocalFree
0x18003052e  mov     eax, ebp
0x180030530  mov     rbp, [rsp+0C8h+arg_10]
0x180030538  mov     rcx, [rsp+0C8h+var_40]
0x180030540  xor     rcx, rsp; StackCookie
0x180030543  call    __security_check_cookie
0x180030548  add     rsp, 90h
0x18003054f  pop     r15
0x180030551  pop     r14
0x180030553  pop     r13
0x180030555  pop     r12
0x180030557  pop     rdi
0x180030558  pop     rsi
0x180030559  pop     rbx
0x18003055a  retn
0x18003055b  xor     eax, eax
0x18003055d  mov     rsi, r14
0x180030560  mov     [r14+r15*2-2], ax
0x180030566  jmp     loc_180030442
0x18003056b  mov     eax, 80070216h
0x180030570  jmp     short loc_180030530
0x180030572  call    cs:__imp_GetLastError
0x180030578  mov     ebp, eax
0x18003057a  test    eax, eax
0x18003057c  jle     loc_180030447
0x180030582  movzx   ebp, ax
0x180030585  or      ebp, 80070000h
0x18003058b  jmp     loc_180030447
0x180030590  call    cs:__imp_GetLastError
0x180030596  mov     ebp, eax
0x180030598  test    eax, eax
0x18003059a  jle     short loc_180030525
0x18003059c  movzx   ebp, ax
0x18003059f  or      ebp, 80070000h
0x1800305a5  jmp     loc_180030525
0x1800305aa  movups  xmm0, xmmword ptr [rsp+0C8h+pbData]
0x1800305af  mov     ebp, r13d
0x1800305b2  movups  xmmword ptr [r14], xmm0
0x1800305b6  jmp     loc_180030509
```
