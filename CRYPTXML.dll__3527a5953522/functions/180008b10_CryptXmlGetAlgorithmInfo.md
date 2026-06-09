# CryptXmlGetAlgorithmInfo

- ea: `0x180008b10`
- end: `0x180008db8`
- name: `CryptXmlGetAlgorithmInfo`
- size: `680`
- prototype: `HRESULT __stdcall(const CRYPT_XML_ALGORITHM *pXmlAlgorithm, DWORD dwFlags, CRYPT_XML_ALGORITHM_INFO **ppAlgInfo)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009180`

## callees

- `0x1800070d0`
- `0x180008b10`
- `0x18000f200`
- `0x180014ce0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008c13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008c13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d5f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008bf4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008cac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008bf4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cc4`

## string_xrefs

- `0x180008b3e`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180008b8c`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlGetAlgorithmInfo(
        const CRYPT_XML_ALGORITHM *pXmlAlgorithm,
        DWORD dwFlags,
        CRYPT_XML_ALGORITHM_INFO **ppAlgInfo)
{
  const char *v6; // r8
  char v7; // cl
  const char *v8; // rdx
  bool v9; // zf
  __int64 i; // rsi
  __int64 j; // rsi
  __int64 v13; // r14
  CRYPT_XML_ALGORITHM_INFO *v14; // rax
  signed int LastError; // eax
  HRESULT v16; // ebx
  const char *v17; // rax
  int (__fastcall *v18)(const CRYPT_XML_ALGORITHM *, CRYPT_XML_ALGORITHM_INFO **); // rax
  const char *v19; // rax
  int v20; // r10d
  const char *v21; // rax

  if ( !dword_180022FC8 )
    LoadRegExtensions();
  if ( pXmlAlgorithm && ppAlgInfo )
  {
    *ppAlgInfo = 0;
    if ( (dwFlags & 0x10000000) == 0 )
    {
      for ( i = 0; (unsigned int)i < dword_180022FC0; i = (unsigned int)(i + 1) )
      {
        if ( CompareStringW(
               0,
               1u,
               pXmlAlgorithm->wszAlgorithm,
               -1,
               *(PCNZWCH *)(*((_QWORD *)qword_180022FD8 + i) + 8LL),
               -1) == 2 )
        {
          v18 = *(int (__fastcall **)(const CRYPT_XML_ALGORITHM *, CRYPT_XML_ALGORITHM_INFO **))(*((_QWORD *)qword_180022FD8
                                                                                                 + i)
                                                                                               + 152LL);
          if ( v18 )
          {
            if ( v18(pXmlAlgorithm, ppAlgInfo) >= 0 )
              return 0;
            v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v20, v19, 1118);
            if ( *ppAlgInfo )
            {
              LocalFree(*ppAlgInfo);
              *ppAlgInfo = 0;
            }
          }
        }
      }
    }
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned int)j >= 0x11 )
      {
        v21 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885372, v21, 1167);
        return -2146885372;
      }
      v13 = 9 * j;
      if ( CompareStringW(0, 1u, pXmlAlgorithm->wszAlgorithm, -1, (PCNZWCH)qword_180022180[9 * j + 1], -1) == 2 )
        break;
    }
    v14 = (CRYPT_XML_ALGORITHM_INFO *)LocalAlloc(0x40u, 0x48u);
    *ppAlgInfo = v14;
    if ( v14 )
    {
      *(_OWORD *)&v14->cbSize = *(_OWORD *)&qword_180022180[v13];
      *(_OWORD *)&v14->wszName = *(_OWORD *)&qword_180022180[v13 + 2];
      *(_OWORD *)&v14->wszCNGAlgid = *(_OWORD *)&qword_180022180[v13 + 4];
      *(_OWORD *)&v14->dwSignFlags = *(_OWORD *)&qword_180022180[v13 + 6];
      v14->pvExtraInfo = (void *)qword_180022180[v13 + 8];
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      v17 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v16, v17, 1155);
      return v16;
    }
  }
  else
  {
    v6 = "";
    while ( 1 )
    {
      v7 = *(v6 - 1);
      v8 = v6--;
      v9 = v7 == 92;
      if ( v7 == 92 )
        break;
      if ( v6 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
      {
        v9 = v7 == 92;
        break;
      }
    }
    if ( v9 )
      v6 = v8;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v6, 1086);
    return -2147024809;
  }
}

```

## disassembly

```asm
0x180008b10  push    rbx
0x180008b12  push    rsi
0x180008b13  push    rdi
0x180008b14  sub     rsp, 30h
0x180008b18  cmp     cs:dword_180022FC8, 0
0x180008b1f  mov     rdi, r8
0x180008b22  mov     esi, edx
0x180008b24  mov     rbx, rcx
0x180008b27  jz      loc_180008D00
0x180008b2d  mov     [rsp+48h+arg_0], rbp
0x180008b32  test    rbx, rbx
0x180008b35  jnz     short loc_180008B82
0x180008b37  lea     r8, aOnecoreDsSecur_6+30h; ""
0x180008b3e  lea     rbp, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008b45  movzx   ecx, byte ptr [r8-1]
0x180008b4a  mov     rdx, r8
0x180008b4d  dec     r8
0x180008b50  cmp     cl, 5Ch ; '\'
0x180008b53  jz      short loc_180008B5D
0x180008b55  cmp     r8, rbp
0x180008b58  ja      short loc_180008B45
0x180008b5a  cmp     cl, 5Ch ; '\'
0x180008b5d  cmovz   r8, rdx
0x180008b61  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008b68  mov     edx, 80070057h
0x180008b6d  mov     r9d, 43Eh
0x180008b73  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008b78  mov     eax, 80070057h
0x180008b7d  jmp     loc_180008C69
0x180008b82  test    rdi, rdi
0x180008b85  jz      short loc_180008B37
0x180008b87  mov     [rsp+48h+arg_10], r14
0x180008b8c  lea     rbp, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008b93  mov     qword ptr [rdi], 0
0x180008b9a  bt      esi, 1Ch
0x180008b9e  jb      short loc_180008BAE
0x180008ba0  xor     esi, esi
0x180008ba2  cmp     esi, cs:dword_180022FC0
0x180008ba8  jb      loc_180008C77
0x180008bae  mov     [rsp+48h+arg_8], r12
0x180008bb3  xor     esi, esi
0x180008bb5  lea     r12, qword_180022180
0x180008bbc  cmp     esi, 11h
0x180008bbf  jnb     loc_180008D8C
0x180008bc5  mov     r8, [rbx+8]; lpString1
0x180008bc9  lea     rcx, [rsi+rsi*8]
0x180008bcd  lea     r14, ds:0[rcx*8]
0x180008bd5  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x180008bdd  mov     rax, [r14+r12+8]
0x180008be2  mov     r9d, 0FFFFFFFFh; cchCount1
0x180008be8  mov     edx, 1; dwCmpFlags
0x180008bed  mov     [rsp+48h+lpString2], rax; lpString2
0x180008bf2  xor     ecx, ecx; Locale
0x180008bf4  call    cs:__imp_CompareStringW
0x180008bfb  nop     dword ptr [rax+rax+00h]
0x180008c00  cmp     eax, 2
0x180008c03  jz      short loc_180008C09
0x180008c05  inc     esi
0x180008c07  jmp     short loc_180008BBC
0x180008c09  mov     edx, 48h ; 'H'; uBytes
0x180008c0e  mov     ecx, 40h ; '@'; uFlags
0x180008c13  call    cs:__imp_LocalAlloc
0x180008c1a  nop     dword ptr [rax+rax+00h]
0x180008c1f  mov     [rdi], rax
0x180008c22  test    rax, rax
0x180008c25  jz      loc_180008CC4
0x180008c2b  movups  xmm0, xmmword ptr [r14+r12]
0x180008c30  movups  xmmword ptr [rax], xmm0
0x180008c33  movups  xmm1, xmmword ptr [r14+r12+10h]
0x180008c39  movups  xmmword ptr [rax+10h], xmm1
0x180008c3d  movups  xmm0, xmmword ptr [r14+r12+20h]
0x180008c43  movups  xmmword ptr [rax+20h], xmm0
0x180008c47  movups  xmm1, xmmword ptr [r14+r12+30h]
0x180008c4d  movups  xmmword ptr [rax+30h], xmm1
0x180008c51  movsd   xmm0, qword ptr [r14+r12+40h]
0x180008c58  movsd   qword ptr [rax+40h], xmm0
0x180008c5d  xor     eax, eax
0x180008c5f  mov     r12, [rsp+48h+arg_8]
0x180008c64  mov     r14, [rsp+48h+arg_10]
0x180008c69  mov     rbp, [rsp+48h+arg_0]
0x180008c6e  add     rsp, 30h
0x180008c72  pop     rdi
0x180008c73  pop     rsi
0x180008c74  pop     rbx
0x180008c75  retn
0x180008c77  mov     rax, cs:qword_180022FD8
0x180008c7e  lea     r14, ds:0[rsi*8]
0x180008c86  mov     r8, [rbx+8]; lpString1
0x180008c8a  mov     r9d, 0FFFFFFFFh; cchCount1
0x180008c90  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x180008c98  mov     edx, 1; dwCmpFlags
0x180008c9d  xor     ecx, ecx; Locale
0x180008c9f  mov     rax, [r14+rax]
0x180008ca3  mov     rax, [rax+8]
0x180008ca7  mov     [rsp+48h+lpString2], rax; lpString2
0x180008cac  call    cs:__imp_CompareStringW
0x180008cb3  nop     dword ptr [rax+rax+00h]
0x180008cb8  cmp     eax, 2
0x180008cbb  jz      short loc_180008D0A
0x180008cbd  inc     esi
0x180008cbf  jmp     loc_180008BA2
0x180008cc4  call    cs:__imp_GetLastError
0x180008ccb  nop     dword ptr [rax+rax+00h]
0x180008cd0  mov     ebx, eax
0x180008cd2  test    eax, eax
0x180008cd4  jg      loc_180008D7E
0x180008cda  mov     rcx, rbp; char *
0x180008cdd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180008ce2  mov     r8, rax
0x180008ce5  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008cec  mov     edx, ebx
0x180008cee  mov     r9d, 483h
0x180008cf4  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008cf9  mov     eax, ebx
0x180008cfb  jmp     loc_180008C5F
0x180008d00  call    _LoadRegExtensions
0x180008d05  jmp     loc_180008B2D
0x180008d0a  mov     rax, cs:qword_180022FD8
0x180008d11  mov     rcx, [r14+rax]
0x180008d15  mov     rax, [rcx+98h]
0x180008d1c  test    rax, rax
0x180008d1f  jz      short loc_180008CBD
0x180008d21  mov     rdx, rdi
0x180008d24  mov     rcx, rbx
0x180008d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2c  mov     r10d, eax
0x180008d2f  test    eax, eax
0x180008d31  jns     short loc_180008D77
0x180008d33  mov     rcx, rbp; char *
0x180008d36  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180008d3b  mov     r8, rax
0x180008d3e  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008d45  mov     edx, r10d
0x180008d48  mov     r9d, 45Eh
0x180008d4e  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008d53  mov     rcx, [rdi]; hMem
0x180008d56  test    rcx, rcx
0x180008d59  jz      loc_180008CBD
0x180008d5f  call    cs:__imp_LocalFree
0x180008d66  nop     dword ptr [rax+rax+00h]
0x180008d6b  mov     qword ptr [rdi], 0
0x180008d72  jmp     loc_180008CBD
0x180008d77  xor     eax, eax
0x180008d79  jmp     loc_180008C64
0x180008d7e  movzx   ebx, ax
0x180008d81  or      ebx, 80070000h
0x180008d87  jmp     loc_180008CDA
0x180008d8c  mov     rcx, rbp; char *
0x180008d8f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180008d94  mov     r8, rax
0x180008d97  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008d9e  mov     edx, 80092104h
0x180008da3  mov     r9d, 48Fh
0x180008da9  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008dae  mov     eax, 80092104h
0x180008db3  jmp     loc_180008C5F
```
