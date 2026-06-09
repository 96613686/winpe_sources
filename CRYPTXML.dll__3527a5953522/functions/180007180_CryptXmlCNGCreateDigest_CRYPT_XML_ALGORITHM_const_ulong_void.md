# CryptXmlCNGCreateDigest(_CRYPT_XML_ALGORITHM const *,ulong *,void * *)

- ea: `0x180007180`
- end: `0x180007721`
- name: `?CryptXmlCNGCreateDigest@@YAJPEBU_CRYPT_XML_ALGORITHM@@PEAKPEAPEAX@Z`
- size: `1441`
- prototype: `int(const struct _CRYPT_XML_ALGORITHM *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180007180`
- `0x18000f200`
- `0x180011540`
- `0x180014ce0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000731e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000731e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800072a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800072a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800074b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800074b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800074cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800074cb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007230`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800072ff`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007230`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800072ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007337`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800076f4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800076f4`
- `bcrypt!BCryptGetProperty` at `0x180007449`
- `bcrypt!BCryptGetProperty` at `0x18000755f`
- `bcrypt!BCryptGetProperty` at `0x180007449`
- `bcrypt!BCryptGetProperty` at `0x18000755f`
- `bcrypt!BCryptCreateHash` at `0x1800075c8`
- `bcrypt!BCryptCreateHash` at `0x1800075c8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800073cb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800073cb`

## string_xrefs

- `0x1800073dd`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x180007466`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x1800074eb`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x180007571`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x1800075da`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x180007679`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x1800071d2`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x1800073f7`: `BCryptOpenAlgorithmProvider`
- `0x1800075f4`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall CryptXmlCNGCreateDigest(const struct _CRYPT_XML_ALGORITHM *a1, UCHAR *a2, BCRYPT_HANDLE **a3)
{
  BCRYPT_HANDLE *v5; // rdi
  unsigned int i; // ebp
  __int64 v8; // r12
  int (__fastcall *v9)(const struct _CRYPT_XML_ALGORITHM *, HLOCAL *); // rax
  const char *v10; // rax
  int v11; // r10d
  unsigned int j; // ebp
  __int64 v13; // r12
  _OWORD *v14; // rax
  signed int LastError; // eax
  int v16; // ebx
  const char *v17; // rax
  NTSTATUS v18; // eax
  const char *v19; // rax
  NTSTATUS Property; // ebx
  const char *v21; // r8
  char v22; // al
  const char *v23; // rdx
  bool v24; // zf
  __int64 v25; // rbx
  HANDLE ProcessHeap; // rax
  BCRYPT_HANDLE *v27; // rax
  const char *v28; // r8
  char v29; // al
  const char *v30; // rdx
  bool v31; // zf
  int v32; // r9d
  NTSTATUS v33; // eax
  const char *v34; // rax
  NTSTATUS Hash; // eax
  const char *v36; // rax
  const char *v37; // r8
  int v38; // r9d
  char v39; // al
  const char *v40; // rcx
  bool v41; // zf
  char v42; // al
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-48h] BYREF
  unsigned int pbOutput; // [rsp+90h] [rbp+8h] BYREF
  ULONG pcbResult; // [rsp+98h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp+20h] BYREF

  v5 = 0;
  hMem = 0;
  v24 = dword_180022FC8 == 0;
  pbOutput = 0;
  phAlgorithm = 0;
  *(_DWORD *)a2 = 0;
  if ( v24 )
    LoadRegExtensions();
  if ( a1 )
  {
    hMem = 0;
    for ( i = 0; i < dword_180022FC0; ++i )
    {
      v8 = 8LL * i;
      if ( CompareStringW(
             0,
             1u,
             a1->wszAlgorithm,
             -1,
             *(PCNZWCH *)(*(_QWORD *)((char *)qword_180022FD8 + v8) + 8LL),
             -1) == 2 )
      {
        v9 = *(int (__fastcall **)(const struct _CRYPT_XML_ALGORITHM *, HLOCAL *))(*(_QWORD *)((char *)qword_180022FD8
                                                                                             + v8)
                                                                                 + 152LL);
        if ( v9 )
        {
          if ( v9(a1, &hMem) >= 0 )
            goto LABEL_22;
          v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v11, v10, 1118);
          if ( hMem )
          {
            LocalFree(hMem);
            hMem = 0;
          }
        }
      }
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= 0x11 )
      {
        v16 = -2146885372;
        v37 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        v38 = 1167;
        goto LABEL_51;
      }
      v13 = 9LL * j;
      if ( CompareStringW(0, 1u, a1->wszAlgorithm, -1, (PCNZWCH)qword_180022180[v13 + 1], -1) == 2 )
        break;
    }
    v14 = LocalAlloc(0x40u, 0x48u);
    hMem = v14;
    if ( v14 )
    {
      *v14 = *(_OWORD *)&qword_180022180[v13];
      v14[1] = *(_OWORD *)&qword_180022180[v13 + 2];
      v14[2] = *(_OWORD *)&qword_180022180[v13 + 4];
      v14[3] = *(_OWORD *)&qword_180022180[v13 + 6];
      *((_QWORD *)v14 + 8) = qword_180022180[v13 + 8];
      goto LABEL_22;
    }
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    v17 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v16, v17, 1155);
    if ( v16 < 0 )
      goto LABEL_52;
LABEL_22:
    v18 = BCryptOpenAlgorithmProvider(&phAlgorithm, *((LPCWSTR *)hMem + 4), 0, 0);
    if ( v18 < 0 )
    {
      v16 = v18 | 0x10000000;
      v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v16, v19, 98, "BCryptOpenAlgorithmProvider");
      goto LABEL_60;
    }
    pcbResult = 0;
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
    {
      v16 = Property | 0x10000000;
      v21 = "";
      while ( 1 )
      {
        v22 = *(v21 - 1);
        v23 = v21--;
        v24 = v22 == 92;
        if ( v22 == 92 )
          break;
        if ( v21 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp" )
        {
          v24 = v22 == 92;
          break;
        }
      }
      if ( v24 )
        v21 = v23;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v16, v21, 115, "BCryptGetProperty");
      goto LABEL_60;
    }
    v25 = pbOutput;
    ProcessHeap = GetProcessHeap();
    v27 = (BCRYPT_HANDLE *)HeapAlloc(ProcessHeap, 8u, v25 + 40);
    v5 = v27;
    if ( v27 )
    {
      *(_DWORD *)v27 = 40;
      v27[4] = v27 + 5;
      *((_DWORD *)v27 + 6) = pbOutput;
      v27[1] = phAlgorithm;
      phAlgorithm = 0;
      v33 = BCryptGetProperty(v27[1], L"HashDigestLength", a2, 4u, &pcbResult, 0);
      if ( v33 >= 0 )
      {
        Hash = BCryptCreateHash(v5[1], v5 + 2, (PUCHAR)v5[4], *((_DWORD *)v5 + 6), 0, 0, 0);
        if ( Hash >= 0 )
        {
          *a3 = v5;
          v16 = 0;
          v5 = 0;
        }
        else
        {
          v16 = Hash | 0x10000000;
          v36 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v16, v36, 163, "BCryptCreateHash");
        }
      }
      else
      {
        v16 = v33 | 0x10000000;
        v34 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v16, v34, 147, "BCryptGetProperty");
      }
      goto LABEL_60;
    }
    v16 = -2147024882;
    v28 = "";
    while ( 1 )
    {
      v29 = *(v28 - 1);
      v30 = v28--;
      v31 = v29 == 92;
      if ( v29 == 92 )
        break;
      if ( v28 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp" )
      {
        v31 = v29 == 92;
        break;
      }
    }
    v32 = 126;
  }
  else
  {
    v16 = -2147024809;
    v37 = "";
    while ( 1 )
    {
      v39 = *(v37 - 1);
      v40 = v37--;
      v41 = v39 == 92;
      if ( v39 == 92 )
        break;
      if ( v37 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
      {
        v41 = v39 == 92;
        break;
      }
    }
    if ( v41 )
      v37 = v40;
    v38 = 1086;
LABEL_51:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v16, v37, v38);
LABEL_52:
    v28 = "";
    while ( 1 )
    {
      v42 = *(v28 - 1);
      v30 = v28--;
      v31 = v42 == 92;
      if ( v42 == 92 )
        break;
      if ( v28 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp" )
      {
        v31 = v42 == 92;
        break;
      }
    }
    v32 = 85;
  }
  if ( v31 )
    v28 = v30;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v16, v28, v32);
LABEL_60:
  if ( hMem )
    LocalFree(hMem);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v5 )
    I_ReleaseCngDigestInfo(v5);
  if ( v16 < 0 )
    return (unsigned int)-2146885365;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180007180  mov     rax, rsp
0x180007183  push    rbx
0x180007184  push    rdi
0x180007185  sub     rsp, 78h
0x180007189  mov     [rax-18h], rsi
0x18000718d  mov     rbx, rcx
0x180007190  mov     [rax-28h], r13
0x180007194  mov     rsi, rdx
0x180007197  xor     r13d, r13d
0x18000719a  mov     [rax-30h], r14
0x18000719e  mov     edi, r13d
0x1800071a1  mov     [rax+20h], r13
0x1800071a5  cmp     cs:dword_180022FC8, edi
0x1800071ab  mov     r14, r8
0x1800071ae  mov     [rax+8], r13d
0x1800071b2  mov     [rax-48h], r13
0x1800071b6  mov     [rdx], r13d
0x1800071b9  jnz     short loc_1800071C0
0x1800071bb  call    _LoadRegExtensions
0x1800071c0  mov     [rsp+88h+arg_10], rbp
0x1800071c8  mov     [rsp+88h+var_20], r12
0x1800071cd  mov     [rsp+88h+var_38], r15
0x1800071d2  lea     r15, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800071d9  test    rbx, rbx
0x1800071dc  jz      loc_180007638
0x1800071e2  mov     [rsp+88h+hMem], r13
0x1800071ea  mov     ebp, r13d
0x1800071ed  cmp     ebp, cs:dword_180022FC0
0x1800071f3  jnb     loc_1800072BB
0x1800071f9  mov     r8, [rbx+8]; lpString1
0x1800071fd  mov     r9d, 0FFFFFFFFh; cchCount1
0x180007203  mov     eax, ebp
0x180007205  mov     edx, 1; dwCmpFlags
0x18000720a  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x180007212  xor     ecx, ecx; Locale
0x180007214  lea     r12, ds:0[rax*8]
0x18000721c  mov     rax, cs:qword_180022FD8
0x180007223  mov     rax, [r12+rax]
0x180007227  mov     rax, [rax+8]
0x18000722b  mov     [rsp+88h+lpString2], rax; lpString2
0x180007230  call    cs:__imp_CompareStringW
0x180007237  nop     dword ptr [rax+rax+00h]
0x18000723c  cmp     eax, 2
0x18000723f  jnz     short loc_1800072B4
0x180007241  mov     rax, cs:qword_180022FD8
0x180007248  mov     rcx, [r12+rax]
0x18000724c  mov     rax, [rcx+98h]
0x180007253  test    rax, rax
0x180007256  jz      short loc_1800072B4
0x180007258  lea     rdx, [rsp+88h+hMem]
0x180007260  mov     rcx, rbx
0x180007263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007268  mov     r10d, eax
0x18000726b  test    eax, eax
0x18000726d  jns     loc_1800073B4
0x180007273  mov     rcx, r15; char *
0x180007276  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000727b  mov     r8, rax
0x18000727e  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180007285  mov     edx, r10d
0x180007288  mov     r9d, 45Eh
0x18000728e  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180007293  mov     rcx, [rsp+88h+hMem]; hMem
0x18000729b  test    rcx, rcx
0x18000729e  jz      short loc_1800072B4
0x1800072a0  call    cs:__imp_LocalFree
0x1800072a7  nop     dword ptr [rax+rax+00h]
0x1800072ac  mov     [rsp+88h+hMem], r13
0x1800072b4  inc     ebp
0x1800072b6  jmp     loc_1800071ED
0x1800072bb  mov     ebp, r13d
0x1800072be  lea     rdx, qword_180022180
0x1800072c5  cmp     ebp, 11h
0x1800072c8  jnb     loc_180007620
0x1800072ce  mov     r8, [rbx+8]; lpString1
0x1800072d2  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800072d8  mov     eax, ebp
0x1800072da  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800072e2  lea     rcx, [rax+rax*8]
0x1800072e6  lea     r12, ds:0[rcx*8]
0x1800072ee  xor     ecx, ecx; Locale
0x1800072f0  mov     rax, [r12+rdx+8]
0x1800072f5  mov     edx, 1; dwCmpFlags
0x1800072fa  mov     [rsp+88h+lpString2], rax; lpString2
0x1800072ff  call    cs:__imp_CompareStringW
0x180007306  nop     dword ptr [rax+rax+00h]
0x18000730b  cmp     eax, 2
0x18000730e  jz      short loc_180007314
0x180007310  inc     ebp
0x180007312  jmp     short loc_1800072BE
0x180007314  mov     edx, 48h ; 'H'; uBytes
0x180007319  mov     ecx, 40h ; '@'; uFlags
0x18000731e  call    cs:__imp_LocalAlloc
0x180007325  nop     dword ptr [rax+rax+00h]
0x18000732a  mov     [rsp+88h+hMem], rax
0x180007332  test    rax, rax
0x180007335  jnz     short loc_18000737B
0x180007337  call    cs:__imp_GetLastError
0x18000733e  nop     dword ptr [rax+rax+00h]
0x180007343  mov     ebx, eax
0x180007345  test    eax, eax
0x180007347  jle     short loc_180007352
0x180007349  movzx   ebx, ax
0x18000734c  or      ebx, 80070000h
0x180007352  mov     rcx, r15; char *
0x180007355  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000735a  mov     r8, rax
0x18000735d  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180007364  mov     edx, ebx
0x180007366  mov     r9d, 483h
0x18000736c  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180007371  test    ebx, ebx
0x180007373  js      loc_180007672
0x180007379  jmp     short loc_1800073B4
0x18000737b  lea     rcx, qword_180022180
0x180007382  movups  xmm0, xmmword ptr [r12+rcx]
0x180007387  movups  xmmword ptr [rax], xmm0
0x18000738a  movups  xmm1, xmmword ptr [r12+rcx+10h]
0x180007390  movups  xmmword ptr [rax+10h], xmm1
0x180007394  movups  xmm0, xmmword ptr [r12+rcx+20h]
0x18000739a  movups  xmmword ptr [rax+20h], xmm0
0x18000739e  movups  xmm1, xmmword ptr [r12+rcx+30h]
0x1800073a4  movups  xmmword ptr [rax+30h], xmm1
0x1800073a8  movsd   xmm0, qword ptr [r12+rcx+40h]
0x1800073af  movsd   qword ptr [rax+40h], xmm0
0x1800073b4  mov     rdx, [rsp+88h+hMem]
0x1800073bc  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x1800073c1  xor     r9d, r9d; dwFlags
0x1800073c4  xor     r8d, r8d; pszImplementation
0x1800073c7  mov     rdx, [rdx+20h]; pszAlgId
0x1800073cb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800073d2  nop     dword ptr [rax+rax+00h]
0x1800073d7  mov     ebx, eax
0x1800073d9  test    eax, eax
0x1800073db  jns     short loc_180007415
0x1800073dd  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800073e4  bts     ebx, 1Ch
0x1800073e8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800073ed  mov     r8, rax
0x1800073f0  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x1800073f7  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x1800073fe  mov     r9d, 62h ; 'b'
0x180007404  mov     edx, ebx
0x180007406  mov     [rsp+88h+lpString2], rax
0x18000740b  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180007410  jmp     loc_1800076AE
0x180007415  mov     rcx, [rsp+88h+phAlgorithm]; hObject
0x18000741a  lea     rax, [rsp+88h+pcbResult]
0x180007422  mov     [rsp+88h+cchCount2], r13d; dwFlags
0x180007427  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x18000742f  mov     r9d, 4; cbOutput
0x180007435  mov     [rsp+88h+lpString2], rax; pcbResult
0x18000743a  lea     rdx, pszProperty; "ObjectLength"
0x180007441  mov     [rsp+88h+pcbResult], r13d
0x180007449  call    cs:__imp_BCryptGetProperty
0x180007450  nop     dword ptr [rax+rax+00h]
0x180007455  mov     ebx, eax
0x180007457  test    eax, eax
0x180007459  jns     short loc_1800074AC
0x18000745b  bts     ebx, 1Ch
0x18000745f  lea     r8, aOnecoreDsSecur_2+2Dh; ""
0x180007466  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000746d  movzx   eax, byte ptr [r8-1]
0x180007472  mov     rdx, r8
0x180007475  dec     r8
0x180007478  cmp     al, 5Ch ; '\'
0x18000747a  jz      short loc_180007483
0x18000747c  cmp     r8, rcx
0x18000747f  ja      short loc_18000746D
0x180007481  cmp     al, 5Ch ; '\'
0x180007483  cmovz   r8, rdx
0x180007487  lea     rax, aBcryptgetprope_0; "BCryptGetProperty"
0x18000748e  mov     edx, ebx
0x180007490  mov     [rsp+88h+lpString2], rax
0x180007495  mov     r9d, 73h ; 's'
0x18000749b  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x1800074a2  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800074a7  jmp     loc_1800076AE
0x1800074ac  mov     ebx, [rsp+88h+pbOutput]
0x1800074b3  call    cs:__imp_GetProcessHeap
0x1800074ba  nop     dword ptr [rax+rax+00h]
0x1800074bf  lea     r8, [rbx+28h]; dwBytes
0x1800074c3  mov     edx, 8; dwFlags
0x1800074c8  mov     rcx, rax; hHeap
0x1800074cb  call    cs:__imp_HeapAlloc
0x1800074d2  nop     dword ptr [rax+rax+00h]
0x1800074d7  mov     rdi, rax
0x1800074da  test    rax, rax
0x1800074dd  jnz     short loc_180007513
0x1800074df  mov     ebx, 8007000Eh
0x1800074e4  lea     r8, aOnecoreDsSecur_2+2Dh; ""
0x1800074eb  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800074f2  movzx   eax, byte ptr [r8-1]
0x1800074f7  mov     rdx, r8
0x1800074fa  dec     r8
0x1800074fd  cmp     al, 5Ch ; '\'
0x1800074ff  jz      short loc_180007508
0x180007501  cmp     r8, rcx
0x180007504  ja      short loc_1800074F2
0x180007506  cmp     al, 5Ch ; '\'
0x180007508  mov     r9d, 7Eh ; '~'
0x18000750e  jmp     loc_18000769C
0x180007513  mov     dword ptr [rax], 28h ; '('
0x180007519  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180007520  add     rax, 28h ; '('
0x180007524  mov     [rsp+88h+cchCount2], r13d; dwFlags
0x180007529  mov     [rdi+20h], rax
0x18000752d  mov     r9d, 4; cbOutput
0x180007533  mov     eax, [rsp+88h+pbOutput]
0x18000753a  mov     r8, rsi; pbOutput
0x18000753d  mov     [rdi+18h], eax
0x180007540  mov     rax, [rsp+88h+phAlgorithm]
0x180007545  mov     [rdi+8], rax
0x180007549  lea     rax, [rsp+88h+pcbResult]
0x180007551  mov     [rsp+88h+phAlgorithm], r13
0x180007556  mov     rcx, [rdi+8]; hObject
0x18000755a  mov     [rsp+88h+lpString2], rax; pcbResult
0x18000755f  call    cs:__imp_BCryptGetProperty
0x180007566  nop     dword ptr [rax+rax+00h]
0x18000756b  mov     ebx, eax
0x18000756d  test    eax, eax
0x18000756f  jns     short loc_1800075A9
0x180007571  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180007578  bts     ebx, 1Ch
0x18000757c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007581  mov     r8, rax
0x180007584  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x18000758b  lea     rax, aBcryptgetprope_0; "BCryptGetProperty"
0x180007592  mov     r9d, 93h
0x180007598  mov     edx, ebx
0x18000759a  mov     [rsp+88h+lpString2], rax
0x18000759f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800075a4  jmp     loc_1800076AE
0x1800075a9  mov     r9d, [rdi+18h]; cbHashObject
0x1800075ad  lea     rdx, [rdi+10h]; phHash
0x1800075b1  mov     r8, [rdi+20h]; pbHashObject
0x1800075b5  mov     rcx, [rdi+8]; hAlgorithm
0x1800075b9  mov     [rsp+88h+dwFlags], r13d; dwFlags
0x1800075be  mov     [rsp+88h+cchCount2], r13d; cbSecret
0x1800075c3  mov     [rsp+88h+lpString2], r13; pbSecret
0x1800075c8  call    cs:__imp_BCryptCreateHash
0x1800075cf  nop     dword ptr [rax+rax+00h]
0x1800075d4  mov     ebx, eax
0x1800075d6  test    eax, eax
0x1800075d8  jns     short loc_180007612
0x1800075da  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800075e1  bts     ebx, 1Ch
0x1800075e5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800075ea  mov     r8, rax
0x1800075ed  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x1800075f4  lea     rax, aBcryptcreateha_0; "BCryptCreateHash"
0x1800075fb  mov     r9d, 0A3h
0x180007601  mov     edx, ebx
0x180007603  mov     [rsp+88h+lpString2], rax
0x180007608  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000760d  jmp     loc_1800076AE
0x180007612  mov     [r14], rdi
0x180007615  mov     ebx, r13d
0x180007618  mov     rdi, r13
0x18000761b  jmp     loc_1800076AE
0x180007620  mov     rcx, r15; char *
0x180007623  mov     ebx, 80092104h
0x180007628  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000762d  mov     r8, rax
0x180007630  mov     r9d, 48Fh
0x180007636  jmp     short loc_180007664
0x180007638  mov     ebx, 80070057h
0x18000763d  lea     r8, aOnecoreDsSecur_6+30h; ""
0x180007644  movzx   eax, byte ptr [r8-1]
0x180007649  mov     rcx, r8
0x18000764c  dec     r8
0x18000764f  cmp     al, 5Ch ; '\'
0x180007651  jz      short loc_18000765A
0x180007653  cmp     r8, r15
0x180007656  ja      short loc_180007644
0x180007658  cmp     al, 5Ch ; '\'
0x18000765a  cmovz   r8, rcx
0x18000765e  mov     r9d, 43Eh
0x180007664  mov     edx, ebx
0x180007666  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000766d  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180007672  lea     r8, aOnecoreDsSecur_2+2Dh; ""
0x180007679  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180007680  movzx   eax, byte ptr [r8-1]
0x180007685  mov     rdx, r8
0x180007688  dec     r8
0x18000768b  cmp     al, 5Ch ; '\'
0x18000768d  jz      short loc_180007696
0x18000768f  cmp     r8, rcx
0x180007692  ja      short loc_180007680
0x180007694  cmp     al, 5Ch ; '\'
0x180007696  mov     r9d, 55h ; 'U'
0x18000769c  cmovz   r8, rdx
0x1800076a0  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800076a7  mov     edx, ebx
0x1800076a9  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800076ae  mov     rcx, [rsp+88h+hMem]; hMem
0x1800076b6  mov     r15, [rsp+88h+var_38]
0x1800076bb  mov     r14, [rsp+88h+var_30]
0x1800076c0  mov     r13, [rsp+88h+var_28]
  ... truncated ...
```
