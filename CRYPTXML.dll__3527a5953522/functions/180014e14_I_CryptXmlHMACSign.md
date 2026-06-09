# I_CryptXmlHMACSign

- ea: `0x180014e14`
- end: `0x180015153`
- name: `I_CryptXmlHMACSign`
- size: `831`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, int, PUCHAR pbOutput)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800094a0`
- `0x18000b3b0`

## callees

- `0x1800070d0`
- `0x180008078`
- `0x180014ce0`
- `0x180014e14`
- `0x1800185f5`
- `0x180018640`
- `0x180019010`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001510c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001510c`
- `bcrypt!BCryptGetProperty` at `0x180014edd`
- `bcrypt!BCryptGetProperty` at `0x180014f68`
- `bcrypt!BCryptGetProperty` at `0x180014edd`
- `bcrypt!BCryptGetProperty` at `0x180014f68`
- `bcrypt!BCryptFinishHash` at `0x1800150d8`
- `bcrypt!BCryptFinishHash` at `0x1800150d8`
- `bcrypt!BCryptDestroyHash` at `0x1800150f5`
- `bcrypt!BCryptDestroyHash` at `0x1800150f5`
- `bcrypt!BCryptHashData` at `0x1800150af`
- `bcrypt!BCryptHashData` at `0x1800150af`
- `bcrypt!BCryptCreateHash` at `0x180015072`
- `bcrypt!BCryptCreateHash` at `0x180015072`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180014e5f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180014e5f`

## string_xrefs

- `0x180014e7c`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180014ef3`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180014f27`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180014f7e`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18001502d`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180015088`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlHMACSign(
        LPCWSTR pszAlgId,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR a6,
        unsigned int a7,
        PUCHAR pbOutput)
{
  UCHAR *p_phAlgorithm; // rdi
  NTSTATUS v12; // ebx
  unsigned int v13; // ebx
  const char *v14; // r8
  const char *v15; // rax
  bool v16; // zf
  int v17; // r9d
  NTSTATUS Property; // eax
  ULONG v19; // esi
  NTSTATUS v20; // eax
  unsigned __int64 v21; // rbx
  __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  UCHAR *v26; // rax
  NTSTATUS v27; // eax
  NTSTATUS v28; // ebx
  __int64 v30; // [rsp+0h] [rbp-40h] BYREF
  UCHAR v31[4]; // [rsp+40h] [rbp+0h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp+4h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp+8h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp+10h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)v31 = 0;
  pcbResult = 0;
  p_phAlgorithm = 0;
  v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 8u);
  if ( v12 < 0 )
  {
    v13 = v12 | 0x10000000;
    v14 = "";
    while ( 1 )
    {
      v15 = v14--;
      v16 = *v14 == 92;
      if ( *v14 == 92 )
        break;
      if ( v14 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
      {
        v16 = *v14 == 92;
        break;
      }
    }
    if ( v16 )
      v14 = v15;
    v17 = 710;
    goto LABEL_9;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v13 = Property | 0x10000000;
    v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
    v17 = 725;
LABEL_9:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v14, v17);
    goto LABEL_37;
  }
  if ( a6 )
  {
    v19 = *(_DWORD *)pbOutput;
    if ( *(_DWORD *)pbOutput > a7 )
    {
      v13 = -805306333;
      v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v17 = 738;
      goto LABEL_9;
    }
    v20 = BCryptGetProperty(phAlgorithm, L"ObjectLength", v31, 4u, &pcbResult, 0);
    if ( v20 < 0 )
    {
      v13 = v20 | 0x10000000;
      v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v17 = 755;
      goto LABEL_9;
    }
    v21 = *(unsigned int *)v31;
    if ( !*(_DWORD *)v31
      || *(unsigned int *)v31 > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)*(unsigned int *)v31 + g_ulAdditionalProbeSize + 8 < *(unsigned int *)v31
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_47;
    }
    v22 = v21 + 23;
    if ( v21 + 23 <= v21 + 8 )
      v22 = 0xFFFFFFFFFFFFFF0LL;
    v23 = v22 & 0xFFFFFFFFFFFFFFF0uLL;
    v24 = alloca(v23);
    v25 = alloca(v23);
    p_phAlgorithm = v31;
    if ( &v30 == (__int64 *)-64LL || (*(_DWORD *)v31 = 1801679955, (p_phAlgorithm = (UCHAR *)&phAlgorithm) == 0) )
    {
LABEL_47:
      if ( v21 + 8 >= v21 )
      {
        v26 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_phAlgorithm = v26;
        if ( v26 )
        {
          *(_DWORD *)v26 = 1885431112;
          p_phAlgorithm = v26 + 8;
        }
      }
    }
    if ( !p_phAlgorithm )
    {
      v13 = -2147024888;
      v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v17 = 764;
      goto LABEL_9;
    }
    v27 = BCryptCreateHash(phAlgorithm, &phHash, p_phAlgorithm, *(ULONG *)v31, pbSecret, cbSecret, 0);
    if ( v27 < 0 )
    {
      v13 = v27 | 0x10000000;
      v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v17 = 780;
      goto LABEL_9;
    }
    v28 = BCryptHashData(phHash, pbInput, cbInput, 0);
    if ( v28 < 0 || (v28 = BCryptFinishHash(phHash, a6, v19, 0), v28 < 0) )
      v13 = v28 | 0x10000000;
    else
      v13 = 0;
  }
  else
  {
    v13 = 1;
  }
LABEL_37:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( p_phAlgorithm && *((_DWORD *)p_phAlgorithm - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v13;
}

```

## disassembly

```asm
0x180014e14  push    rbp
0x180014e16  push    rbx
0x180014e17  push    rsi
0x180014e18  push    rdi
0x180014e19  push    r12
0x180014e1b  push    r13
0x180014e1d  push    r15
0x180014e1f  sub     rsp, 70h
0x180014e23  lea     rbp, [rsp+40h]
0x180014e28  mov     rax, cs:__security_cookie
0x180014e2f  xor     rax, rbp
0x180014e32  mov     [rbp+60h+var_40], rax
0x180014e36  xor     eax, eax
0x180014e38  mov     r12, rdx
0x180014e3b  mov     r13, r9
0x180014e3e  mov     [rbp+60h+phAlgorithm], rax
0x180014e42  mov     r15d, r8d
0x180014e45  mov     [rbp+60h+phHash], rax
0x180014e49  mov     rdx, rcx; pszAlgId
0x180014e4c  mov     dword ptr [rbp+60h+var_60], eax
0x180014e4f  lea     r9d, [rax+8]; dwFlags
0x180014e53  mov     [rbp+60h+var_5C], eax
0x180014e56  xor     r8d, r8d; pszImplementation
0x180014e59  lea     rcx, [rbp+60h+phAlgorithm]; phAlgorithm
0x180014e5d  mov     edi, eax
0x180014e5f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180014e66  nop     dword ptr [rax+rax+00h]
0x180014e6b  mov     ebx, eax
0x180014e6d  test    eax, eax
0x180014e6f  jns     short loc_180014EB5
0x180014e71  bts     ebx, 1Ch
0x180014e75  lea     r8, aOnecoreDsSecur_11+33h; ""
0x180014e7c  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014e83  mov     rax, r8
0x180014e86  dec     r8
0x180014e89  cmp     byte ptr [r8], 5Ch ; '\'
0x180014e8d  jz      short loc_180014E98
0x180014e8f  cmp     r8, rcx
0x180014e92  ja      short loc_180014E83
0x180014e94  cmp     byte ptr [r8], 5Ch ; '\'
0x180014e98  cmovz   r8, rax
0x180014e9c  mov     r9d, 2C6h
0x180014ea2  mov     edx, ebx
0x180014ea4  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180014eab  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180014eb0  jmp     loc_1800150EC
0x180014eb5  mov     rsi, [rbp+60h+pbOutput]
0x180014ebc  lea     rax, [rbp+60h+var_5C]
0x180014ec0  mov     rcx, [rbp+60h+phAlgorithm]; hObject
0x180014ec4  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180014ecb  mov     r8, rsi; pbOutput
0x180014ece  mov     [rsp+0A0h+dwFlags], edi; dwFlags
0x180014ed2  mov     r9d, 4; cbOutput
0x180014ed8  mov     [rsp+0A0h+pcbResult], rax; pcbResult
0x180014edd  call    cs:__imp_BCryptGetProperty
0x180014ee4  nop     dword ptr [rax+rax+00h]
0x180014ee9  mov     ebx, eax
0x180014eeb  test    eax, eax
0x180014eed  jns     short loc_180014F0A
0x180014eef  bts     ebx, 1Ch
0x180014ef3  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014efa  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014eff  mov     r8, rax
0x180014f02  mov     r9d, 2D5h
0x180014f08  jmp     short loc_180014EA2
0x180014f0a  cmp     [rbp+60h+arg_28], rdi
0x180014f11  jnz     short loc_180014F1D
0x180014f13  mov     ebx, 1
0x180014f18  jmp     loc_1800150EC
0x180014f1d  mov     esi, [rsi]
0x180014f1f  cmp     esi, [rbp+60h+arg_30]
0x180014f25  jbe     short loc_180014F46
0x180014f27  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014f2e  mov     ebx, 0D0000023h
0x180014f33  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014f38  mov     r8, rax
0x180014f3b  mov     r9d, 2E2h
0x180014f41  jmp     loc_180014EA2
0x180014f46  mov     rcx, [rbp+60h+phAlgorithm]; hObject
0x180014f4a  lea     rax, [rbp+60h+var_5C]
0x180014f4e  mov     [rsp+0A0h+dwFlags], edi; dwFlags
0x180014f52  lea     r8, [rbp+60h+var_60]; pbOutput
0x180014f56  mov     r9d, 4; cbOutput
0x180014f5c  mov     [rsp+0A0h+pcbResult], rax; pcbResult
0x180014f61  lea     rdx, pszProperty; "ObjectLength"
0x180014f68  call    cs:__imp_BCryptGetProperty
0x180014f6f  nop     dword ptr [rax+rax+00h]
0x180014f74  mov     ebx, eax
0x180014f76  test    eax, eax
0x180014f78  jns     short loc_180014F98
0x180014f7a  bts     ebx, 1Ch
0x180014f7e  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014f85  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014f8a  mov     r8, rax
0x180014f8d  mov     r9d, 2F3h
0x180014f93  jmp     loc_180014EA2
0x180014f98  mov     ebx, dword ptr [rbp+60h+var_60]
0x180014f9b  test    rbx, rbx
0x180014f9e  jz      short loc_180015001
0x180014fa0  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180014fa7  ja      short loc_180015001
0x180014fa9  mov     rcx, cs:g_ulAdditionalProbeSize
0x180014fb0  add     rcx, 8
0x180014fb4  add     rcx, rbx
0x180014fb7  cmp     rcx, rbx
0x180014fba  jb      short loc_180015001
0x180014fbc  call    VerifyStackAvailable
0x180014fc1  test    eax, eax
0x180014fc3  jz      short loc_180015001
0x180014fc5  lea     rax, [rbx+8]
0x180014fc9  lea     rcx, [rax+0Fh]
0x180014fcd  cmp     rcx, rax
0x180014fd0  ja      short loc_180014FDC
0x180014fd2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180014fdc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180014fe0  mov     rax, rcx
0x180014fe3  call    __chkstk_0
0x180014fe8  sub     rsp, rcx
0x180014feb  lea     rdi, [rsp+0A0h+var_60]
0x180014ff0  test    rdi, rdi
0x180014ff3  jz      short loc_180015001
0x180014ff5  mov     dword ptr [rdi], 6B637453h
0x180014ffb  add     rdi, 8
0x180014fff  jnz     short loc_180015028
0x180015001  lea     rcx, [rbx+8]
0x180015005  cmp     rcx, rbx
0x180015008  jb      short loc_180015028
0x18001500a  mov     rax, cs:g_pfnAllocate
0x180015011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015016  mov     rdi, rax
0x180015019  test    rax, rax
0x18001501c  jz      short loc_180015028
0x18001501e  mov     dword ptr [rax], 70616548h
0x180015024  add     rdi, 8
0x180015028  test    rdi, rdi
0x18001502b  jnz     short loc_18001504C
0x18001502d  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180015034  mov     ebx, 80070008h
0x180015039  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001503e  mov     r8, rax
0x180015041  mov     r9d, 2FCh
0x180015047  jmp     loc_180014EA2
0x18001504c  mov     eax, [rbp+60h+cbSecret]
0x180015052  lea     rdx, [rbp+60h+phHash]; phHash
0x180015056  mov     r9d, dword ptr [rbp+60h+var_60]; cbHashObject
0x18001505a  mov     r8, rdi; pbHashObject
0x18001505d  mov     rcx, [rbp+60h+phAlgorithm]; hAlgorithm
0x180015061  mov     [rsp+0A0h+var_70], 0; dwFlags
0x180015069  mov     [rsp+0A0h+dwFlags], eax; cbSecret
0x18001506d  mov     [rsp+0A0h+pcbResult], r13; pbSecret
0x180015072  call    cs:__imp_BCryptCreateHash
0x180015079  nop     dword ptr [rax+rax+00h]
0x18001507e  mov     ebx, eax
0x180015080  test    eax, eax
0x180015082  jns     short loc_1800150A2
0x180015084  bts     ebx, 1Ch
0x180015088  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001508f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180015094  mov     r8, rax
0x180015097  mov     r9d, 30Ch
0x18001509d  jmp     loc_180014EA2
0x1800150a2  mov     rcx, [rbp+60h+phHash]; hHash
0x1800150a6  xor     r9d, r9d; dwFlags
0x1800150a9  mov     r8d, r15d; cbInput
0x1800150ac  mov     rdx, r12; pbInput
0x1800150af  call    cs:__imp_BCryptHashData
0x1800150b6  nop     dword ptr [rax+rax+00h]
0x1800150bb  mov     ebx, eax
0x1800150bd  test    eax, eax
0x1800150bf  jns     short loc_1800150C7
0x1800150c1  bts     ebx, 1Ch
0x1800150c5  jmp     short loc_1800150EC
0x1800150c7  mov     rdx, [rbp+60h+arg_28]; pbOutput
0x1800150ce  xor     r9d, r9d; dwFlags
0x1800150d1  mov     rcx, [rbp+60h+phHash]; hHash
0x1800150d5  mov     r8d, esi; cbOutput
0x1800150d8  call    cs:__imp_BCryptFinishHash
0x1800150df  nop     dword ptr [rax+rax+00h]
0x1800150e4  mov     ebx, eax
0x1800150e6  test    eax, eax
0x1800150e8  js      short loc_1800150C1
0x1800150ea  xor     ebx, ebx
0x1800150ec  mov     rcx, [rbp+60h+phHash]; hHash
0x1800150f0  test    rcx, rcx
0x1800150f3  jz      short loc_180015101
0x1800150f5  call    cs:__imp_BCryptDestroyHash
0x1800150fc  nop     dword ptr [rax+rax+00h]
0x180015101  mov     rcx, [rbp+60h+phAlgorithm]; hAlgorithm
0x180015105  test    rcx, rcx
0x180015108  jz      short loc_180015118
0x18001510a  xor     edx, edx; dwFlags
0x18001510c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180015113  nop     dword ptr [rax+rax+00h]
0x180015118  test    rdi, rdi
0x18001511b  jz      short loc_180015135
0x18001511d  lea     rcx, [rdi-8]
0x180015121  cmp     dword ptr [rcx], 70616548h
0x180015127  jnz     short loc_180015135
0x180015129  mov     rax, cs:g_pfnFree
0x180015130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015135  mov     eax, ebx
0x180015137  mov     rcx, [rbp+60h+var_40]
0x18001513b  xor     rcx, rbp; StackCookie
0x18001513e  call    __security_check_cookie
0x180015143  lea     rsp, [rbp+30h]
0x180015147  pop     r15
0x180015149  pop     r13
0x18001514b  pop     r12
0x18001514d  pop     rdi
0x18001514e  pop     rsi
0x18001514f  pop     rbx
0x180015150  pop     rbp
0x180015151  retn
```
