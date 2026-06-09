# CryptXmlVerifySignature

- ea: `0x1800094a0`
- end: `0x180009a07`
- name: `CryptXmlVerifySignature`
- size: `1383`
- prototype: `HRESULT __stdcall(HCRYPTXML hSignature, BCRYPT_KEY_HANDLE hKey, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800057a0`
- `0x1800070d0`
- `0x180009310`
- `0x180009478`
- `0x1800094a0`
- `0x180009f80`
- `0x18000b1a0`
- `0x18000fe50`
- `0x180014ce0`
- `0x180014e14`
- `0x180015280`
- `0x180018601`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009939`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009939`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009950`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009950`

## string_xrefs

- `0x1800094d7`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180009523`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180009582`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000961d`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180009688`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x1800096dd`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180009741`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x1800097b9`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180009844`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x1800098dd`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180009903`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000996b`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x1800099da`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlVerifySignature(HCRYPTXML hSignature, BCRYPT_KEY_HANDLE hKey, DWORD dwFlags)
{
  DWORD v3; // r13d
  const char *v7; // r8
  char v8; // dl
  const char *v9; // r9
  bool v10; // zf
  const char *v12; // rax
  int *i; // rdi
  const char *v14; // r8
  char v15; // al
  const char *v16; // rdx
  bool v17; // zf
  int v18; // r9d
  char *v19; // r14
  __int64 v20; // rcx
  const WCHAR *HMACAlgName; // r12
  PUCHAR v22; // rbx
  int CryptoInterface; // r12d
  const char *v24; // r8
  int v25; // r9d
  const char *v26; // rax
  unsigned int v27; // eax
  const char *v28; // rax
  __int64 v29; // rdx
  __int64 (__fastcall *v30)(__int64, BCRYPT_KEY_HANDLE, _QWORD, _QWORD, _QWORD, _DWORD); // rax
  __int64 v31; // r8
  unsigned int v32; // ebx
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rbp
  _WORD *v36; // rdx
  const char *v37; // rax
  const char *v38; // rax
  const char *v39; // rax
  HANDLE ProcessHeap; // rax
  char v41; // al
  const char *v42; // rdx
  bool v43; // zf
  void (__fastcall *v44)(HCRYPTXML); // rax
  CRYPT_XML_DATA_PROVIDER pDataProviderIn; // [rsp+40h] [rbp-58h] BYREF
  int pbOutput; // [rsp+A0h] [rbp+8h] BYREF
  UCHAR *v47; // [rsp+B8h] [rbp+20h] BYREF

  v3 = 0;
  v47 = 0;
  pbOutput = 0;
  memset(&pDataProviderIn, 0, sizeof(pDataProviderIn));
  if ( hSignature )
  {
    if ( *(_DWORD *)hSignature != 1145324610 )
    {
      v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885370, v12, 1474);
      return -2146885370;
    }
    for ( i = (int *)hSignature; ; i = (int *)*((_QWORD *)i + 10) )
    {
      if ( !i )
      {
        v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        v18 = 1483;
LABEL_71:
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885370, v14, v18);
        return -2146885370;
      }
      if ( *i == 1145324609 )
        break;
    }
    if ( i[18] < 0 )
    {
      v14 = "";
      while ( 1 )
      {
        v15 = *(v14 - 1);
        v16 = v14--;
        v17 = v15 == 92;
        if ( v15 == 92 )
          break;
        if ( v14 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
        {
          v17 = v15 == 92;
          break;
        }
      }
      if ( v17 )
        v14 = v16;
      v18 = 1490;
      goto LABEL_71;
    }
    I_CryptXmlLock();
    *((_DWORD *)hSignature + 17) |= 0x10000u;
    v19 = (char *)hSignature + 144;
    *((_DWORD *)hSignature + 18) &= ~0x10000u;
    if ( hKey || (HMACAlgName = (const WCHAR *)GetHMACAlgName(*(PCNZWCH *)(*(_QWORD *)v19 + 80LL))) == 0 )
    {
      v29 = 0x10000000;
      if ( (dwFlags & 0x10000000) != 0 || (i[15] & 0x10000000) != 0 )
        v19 = (char *)hSignature + 144;
      else
        v29 = 0;
      CryptoInterface = I_CryptXmlGetCryptoInterface(*(_QWORD *)v19 + 72LL, v29, &v47);
      if ( CryptoInterface < 0 )
      {
        v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        v25 = 1566;
        goto LABEL_66;
      }
      if ( !v47
        || (v30 = (__int64 (__fastcall *)(__int64, BCRYPT_KEY_HANDLE, _QWORD, _QWORD, _QWORD, _DWORD))*((_QWORD *)v47 + 7)) == 0 )
      {
        CryptoInterface = -2146885372;
        v24 = "";
        while ( 1 )
        {
          v41 = *(v24 - 1);
          v42 = v24--;
          v43 = v41 == 92;
          if ( v41 == 92 )
            break;
          if ( v24 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
          {
            v43 = v41 == 92;
            break;
          }
        }
        if ( v43 )
          v24 = v42;
        v25 = 1574;
        goto LABEL_66;
      }
      v31 = *(_QWORD *)v19;
      v47 = 0;
      CryptoInterface = v30(
                          v31 + 72,
                          hKey,
                          *(_QWORD *)(v31 + 128),
                          *(unsigned int *)(v31 + 124),
                          *(_QWORD *)(v31 + 144),
                          *(_DWORD *)(v31 + 136));
      if ( CryptoInterface < 0 )
      {
        v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        v25 = 1594;
        goto LABEL_66;
      }
    }
    else
    {
      pbOutput = 2048;
      v47 = (UCHAR *)CryptXmlAlloc(v20, 2048);
      v22 = v47;
      if ( !v47 )
      {
        CryptoInterface = -2147024882;
        v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        v25 = 1514;
LABEL_66:
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CryptoInterface, v24, v25);
        goto LABEL_67;
      }
      CryptoInterface = I_CryptXmlHMACSign(
                          HMACAlgName,
                          *(PUCHAR *)(*(_QWORD *)v19 + 128LL),
                          *(_DWORD *)(*(_QWORD *)v19 + 124LL),
                          *((PUCHAR *)hSignature + 276),
                          *((_DWORD *)hSignature + 554),
                          v47,
                          pbOutput,
                          (PUCHAR)&pbOutput);
      if ( CryptoInterface < 0 )
      {
        v26 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CryptoInterface, v26, 1530);
LABEL_58:
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 8u, v22);
LABEL_67:
        v44 = (void (__fastcall *)(HCRYPTXML))*((_QWORD *)hSignature + 16);
        if ( v44 )
          v44(hSignature);
        return CryptoInterface;
      }
      v27 = *(_DWORD *)(*(_QWORD *)v19 + 136LL);
      if ( v27 != pbOutput || memcmp_0(v22, *(const void **)(*(_QWORD *)v19 + 144LL), v27) )
      {
        CryptoInterface = -2146885363;
        v28 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885363, v28, 1541);
        goto LABEL_58;
      }
    }
    v32 = 0;
    v33 = *((_DWORD *)hSignature + 17) & 0xFFFEFFFF;
    *((_DWORD *)hSignature + 18) |= 0x10000u;
    *((_DWORD *)hSignature + 17) = v33;
    while ( v32 < *(_DWORD *)(*(_QWORD *)v19 + 104LL) )
    {
      v34 = *(_QWORD *)(8LL * v32 + *(_QWORD *)(*(_QWORD *)v19 + 112LL));
      v35 = *(_QWORD *)(v34 + 8);
      if ( (*(_DWORD *)(v35 + 72) & 9) == 1 )
      {
        v36 = *(_WORD **)(v34 + 24);
        *(_DWORD *)(v35 + 68) |= 1u;
        if ( *v36 )
        {
          if ( *v36 == 35 )
            ++v36;
          LOBYTE(v3) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v19 + 112LL) + 8LL * v32) + 88LL) == 0;
          CryptoInterface = I_CryptXmlResolveByIdOrElementName(i, v36, 35, v3, &pDataProviderIn);
          if ( CryptoInterface < 0 )
          {
            v39 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CryptoInterface, v39, 1669);
            goto LABEL_57;
          }
        }
        else
        {
          CryptoInterface = I_CryptXmlResolveEmptyReference(i, &pDataProviderIn, 35);
          if ( CryptoInterface < 0 )
          {
            v37 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CryptoInterface, v37, 1634);
            goto LABEL_57;
          }
        }
        *(_DWORD *)(v35 + 68) &= ~1u;
        CryptoInterface = CryptXmlDigestReference(
                            *(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v19 + 112LL) + 8LL * v32) + 8LL),
                            v3,
                            &pDataProviderIn);
        if ( CryptoInterface < 0 )
        {
          v38 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CryptoInterface, v38, 1683);
          goto LABEL_57;
        }
        v3 = 0;
      }
      ++v32;
    }
    CryptoInterface = 0;
LABEL_57:
    v22 = v47;
    if ( !v47 )
      goto LABEL_67;
    goto LABEL_58;
  }
  v7 = "";
  while ( 1 )
  {
    v8 = *(v7 - 1);
    v9 = v7--;
    v10 = v8 == 92;
    if ( v8 == 92 )
      break;
    if ( v7 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
    {
      v10 = v8 == 92;
      break;
    }
  }
  if ( v10 )
    v7 = v9;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v7, 1467);
  return -2147024809;
}

```

## disassembly

```asm
0x1800094a0  mov     rax, rsp
0x1800094a3  push    rbx
0x1800094a4  push    rbp
0x1800094a5  push    rsi
0x1800094a6  push    r13
0x1800094a8  sub     rsp, 78h
0x1800094ac  xor     r13d, r13d
0x1800094af  xorps   xmm0, xmm0
0x1800094b2  mov     [rax+20h], r13
0x1800094b6  mov     ebx, r8d
0x1800094b9  mov     [rax+8], r13d
0x1800094bd  mov     rbp, rdx
0x1800094c0  mov     rsi, rcx
0x1800094c3  movups  xmmword ptr [rax-58h], xmm0
0x1800094c7  movups  xmmword ptr [rax-48h], xmm0
0x1800094cb  test    rcx, rcx
0x1800094ce  jnz     short loc_18000951B
0x1800094d0  lea     r8, aOnecoreDsSecur_11+33h; ""
0x1800094d7  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800094de  movzx   edx, byte ptr [r8-1]
0x1800094e3  mov     r9, r8
0x1800094e6  dec     r8
0x1800094e9  cmp     dl, 5Ch ; '\'
0x1800094ec  jz      short loc_1800094F6
0x1800094ee  cmp     r8, rcx
0x1800094f1  ja      short loc_1800094DE
0x1800094f3  cmp     dl, 5Ch ; '\'
0x1800094f6  cmovz   r8, r9
0x1800094fa  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180009501  mov     r9d, 5BBh
0x180009507  mov     edx, 80070057h
0x18000950c  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009511  mov     eax, 80070057h
0x180009516  jmp     loc_1800099CF
0x18000951b  cmp     dword ptr [rcx], 44444442h
0x180009521  jz      short loc_180009553
0x180009523  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000952a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000952f  mov     r8, rax
0x180009532  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180009539  mov     edx, 80092106h
0x18000953e  mov     r9d, 5C2h
0x180009544  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009549  mov     eax, 80092106h
0x18000954e  jmp     loc_1800099CF
0x180009553  mov     [rsp+98h+arg_8], rdi
0x18000955b  mov     rdi, rsi
0x18000955e  test    rdi, rdi
0x180009561  jz      loc_1800099DA
0x180009567  cmp     dword ptr [rdi], 44444441h
0x18000956d  jz      short loc_180009575
0x18000956f  mov     rdi, [rdi+50h]
0x180009573  jmp     short loc_18000955E
0x180009575  cmp     [rdi+48h], r13d
0x180009579  jge     short loc_1800095AE
0x18000957b  lea     r8, aOnecoreDsSecur_11+33h; ""
0x180009582  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180009589  movzx   eax, byte ptr [r8-1]
0x18000958e  mov     rdx, r8
0x180009591  dec     r8
0x180009594  cmp     al, 5Ch ; '\'
0x180009596  jz      short loc_18000959F
0x180009598  cmp     r8, rcx
0x18000959b  ja      short loc_180009589
0x18000959d  cmp     al, 5Ch ; '\'
0x18000959f  cmovz   r8, rdx
0x1800095a3  mov     r9d, 5D2h
0x1800095a9  jmp     loc_1800099EF
0x1800095ae  mov     [rsp+98h+var_28], r12
0x1800095b3  mov     [rsp+98h+var_30], r14
0x1800095b8  mov     [rsp+98h+var_38], r15
0x1800095bd  call    I_CryptXmlLock
0x1800095c2  or      dword ptr [rsi+44h], 10000h
0x1800095c9  lea     r14, [rsi+90h]
0x1800095d0  and     dword ptr [rsi+48h], 0FFFEFFFFh
0x1800095d7  test    rbp, rbp
0x1800095da  jnz     loc_18000970C
0x1800095e0  mov     rcx, [r14]
0x1800095e3  mov     rcx, [rcx+50h]; lpString1
0x1800095e7  call    _GetHMACAlgName
0x1800095ec  mov     r12, rax
0x1800095ef  test    rax, rax
0x1800095f2  jz      loc_18000970C
0x1800095f8  mov     edx, 800h
0x1800095fd  mov     [rsp+98h+arg_0], 800h
0x180009608  call    CryptXmlAlloc
0x18000960d  mov     [rsp+98h+arg_18], rax
0x180009615  mov     rbx, rax
0x180009618  test    rax, rax
0x18000961b  jnz     short loc_18000963D
0x18000961d  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180009624  mov     r12d, 8007000Eh
0x18000962a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000962f  mov     r8, rax
0x180009632  mov     r9d, 5EAh
0x180009638  jmp     loc_180009992
0x18000963d  mov     rdx, [r14]
0x180009640  lea     rax, [rsp+98h+arg_0]
0x180009648  mov     r9, [rsi+8A0h]; pbSecret
0x18000964f  mov     rcx, r12; pszAlgId
0x180009652  mov     [rsp+98h+pbOutput], rax; pbOutput
0x180009657  mov     eax, [rsp+98h+arg_0]
0x18000965e  mov     r8d, [rdx+7Ch]; cbInput
0x180009662  mov     rdx, [rdx+80h]; pbInput
0x180009669  mov     [rsp+98h+var_68], eax; int
0x18000966d  mov     eax, [rsi+8A8h]
0x180009673  mov     [rsp+98h+var_70], rbx; PUCHAR
0x180009678  mov     [rsp+98h+cbSecret], eax; cbSecret
0x18000967c  call    I_CryptXmlHMACSign
0x180009681  mov     r12d, eax
0x180009684  test    eax, eax
0x180009686  jns     short loc_1800096B1
0x180009688  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000968f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009694  mov     r8, rax
0x180009697  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000969e  mov     edx, r12d
0x1800096a1  mov     r9d, 5FAh
0x1800096a7  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800096ac  jmp     loc_180009939
0x1800096b1  mov     rdx, [r14]
0x1800096b4  mov     eax, [rdx+88h]
0x1800096ba  cmp     eax, [rsp+98h+arg_0]
0x1800096c1  jnz     short loc_1800096DD
0x1800096c3  mov     rdx, [rdx+90h]; Buf2
0x1800096ca  mov     r8d, eax; Size
0x1800096cd  mov     rcx, rbx; Buf1
0x1800096d0  call    memcmp_0
0x1800096d5  test    eax, eax
0x1800096d7  jz      loc_1800097D3
0x1800096dd  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800096e4  mov     r12d, 8009210Dh
0x1800096ea  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800096ef  mov     r8, rax
0x1800096f2  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800096f9  mov     edx, r12d
0x1800096fc  mov     r9d, 605h
0x180009702  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009707  jmp     loc_180009939
0x18000970c  mov     edx, 10000000h
0x180009711  test    edx, ebx
0x180009713  jnz     short loc_18000971F
0x180009715  test    [rdi+3Ch], edx
0x180009718  jnz     short loc_18000971F
0x18000971a  mov     edx, r13d
0x18000971d  jmp     short loc_180009726
0x18000971f  lea     r14, [rsi+90h]
0x180009726  mov     rcx, [r14]
0x180009729  lea     r8, [rsp+98h+arg_18]
0x180009731  add     rcx, 48h ; 'H'
0x180009735  call    I_CryptXmlGetCryptoInterface
0x18000973a  mov     r12d, eax
0x18000973d  test    eax, eax
0x18000973f  jns     short loc_18000975B
0x180009741  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180009748  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000974d  mov     r8, rax
0x180009750  mov     r9d, 61Eh
0x180009756  jmp     loc_180009992
0x18000975b  mov     rax, [rsp+98h+arg_18]
0x180009763  test    rax, rax
0x180009766  jz      loc_18000995E
0x18000976c  mov     rax, [rax+38h]
0x180009770  test    rax, rax
0x180009773  jz      loc_18000995E
0x180009779  mov     r8, [r14]
0x18000977c  mov     [rsp+98h+arg_18], r13
0x180009784  mov     edx, [r8+88h]
0x18000978b  lea     rcx, [r8+48h]
0x18000978f  mov     r9d, [r8+7Ch]
0x180009793  mov     dword ptr [rsp+98h+var_70], edx
0x180009797  mov     rdx, [r8+90h]
0x18000979e  mov     r8, [r8+80h]
0x1800097a5  mov     qword ptr [rsp+98h+cbSecret], rdx
0x1800097aa  mov     rdx, rbp
0x1800097ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097b2  mov     r12d, eax
0x1800097b5  test    eax, eax
0x1800097b7  jns     short loc_1800097D3
0x1800097b9  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800097c0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800097c5  mov     r8, rax
0x1800097c8  mov     r9d, 63Ah
0x1800097ce  jmp     loc_180009992
0x1800097d3  lea     rax, [rsi+44h]
0x1800097d7  mov     ebx, r13d
0x1800097da  mov     eax, [rax]
0x1800097dc  mov     r8d, 23h ; '#'
0x1800097e2  btr     eax, 10h
0x1800097e6  or      dword ptr [rsi+48h], 10000h
0x1800097ed  mov     [rsi+44h], eax
0x1800097f0  mov     rax, [r14]
0x1800097f3  cmp     ebx, [rax+68h]
0x1800097f6  jnb     loc_180009929
0x1800097fc  mov     ecx, ebx
0x1800097fe  lea     r15, ds:0[rcx*8]
0x180009806  mov     rcx, [rax+70h]
0x18000980a  mov     rdx, [r15+rcx]
0x18000980e  mov     rbp, [rdx+8]
0x180009812  mov     eax, [rbp+48h]
0x180009815  and     al, 9
0x180009817  cmp     al, 1
0x180009819  jnz     loc_1800098D6
0x18000981f  mov     rdx, [rdx+18h]
0x180009823  or      dword ptr [rbp+44h], 1
0x180009827  movzx   ecx, word ptr [rdx]
0x18000982a  cmp     r13w, cx
0x18000982e  jnz     short loc_18000986D
0x180009830  lea     rdx, [rsp+98h+pDataProviderIn]
0x180009835  mov     rcx, rdi
0x180009838  call    I_CryptXmlResolveEmptyReference
0x18000983d  mov     r12d, eax
0x180009840  test    eax, eax
0x180009842  jns     short loc_1800098A6
0x180009844  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000984b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009850  mov     r8, rax
0x180009853  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000985a  mov     edx, r12d
0x18000985d  mov     r9d, 662h
0x180009863  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009868  jmp     loc_18000992C
0x18000986d  cmp     r8w, cx
0x180009871  jnz     short loc_180009877
0x180009873  add     rdx, 2
0x180009877  mov     rax, [r14]
0x18000987a  mov     rcx, [rax+70h]
0x18000987e  mov     rax, [rcx+r15]
0x180009882  mov     rcx, rdi
0x180009885  cmp     dword ptr [rax+58h], 0
0x180009889  lea     rax, [rsp+98h+pDataProviderIn]
0x18000988e  mov     qword ptr [rsp+98h+cbSecret], rax
0x180009893  setz    r13b
0x180009897  mov     r9d, r13d
0x18000989a  call    I_CryptXmlResolveByIdOrElementName
0x18000989f  mov     r12d, eax
0x1800098a2  test    eax, eax
0x1800098a4  js      short loc_180009903
0x1800098a6  and     dword ptr [rbp+44h], 0FFFFFFFEh
0x1800098aa  lea     r8, [rsp+98h+pDataProviderIn]; pDataProviderIn
0x1800098af  mov     rax, [r14]
0x1800098b2  mov     edx, r13d; dwFlags
0x1800098b5  mov     rcx, [rax+70h]
0x1800098b9  mov     rcx, [rcx+r15]
0x1800098bd  mov     rcx, [rcx+8]; hReference
0x1800098c1  call    CryptXmlDigestReference
0x1800098c6  mov     r12d, eax
0x1800098c9  test    eax, eax
0x1800098cb  js      short loc_1800098DD
0x1800098cd  xor     r13d, r13d
0x1800098d0  mov     r8d, 23h ; '#'
0x1800098d6  inc     ebx
0x1800098d8  jmp     loc_1800097F0
0x1800098dd  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800098e4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800098e9  mov     r8, rax
0x1800098ec  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800098f3  mov     edx, r12d
0x1800098f6  mov     r9d, 693h
0x1800098fc  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009901  jmp     short loc_18000992C
0x180009903  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000990a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000990f  mov     r8, rax
0x180009912  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180009919  mov     edx, r12d
0x18000991c  mov     r9d, 685h
0x180009922  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009927  jmp     short loc_18000992C
0x180009929  mov     r12d, r13d
0x18000992c  mov     rbx, [rsp+98h+arg_18]
0x180009934  test    rbx, rbx
0x180009937  jz      short loc_1800099A1
0x180009939  call    cs:__imp_GetProcessHeap
0x180009940  nop     dword ptr [rax+rax+00h]
0x180009945  mov     r8, rbx; lpMem
0x180009948  mov     edx, 8; dwFlags
0x18000994d  mov     rcx, rax; hHeap
0x180009950  call    cs:__imp_HeapFree
0x180009957  nop     dword ptr [rax+rax+00h]
0x18000995c  jmp     short loc_1800099A1
0x18000995e  mov     r12d, 80092104h
0x180009964  lea     r8, aOnecoreDsSecur_11+33h; ""
0x18000996b  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180009972  movzx   eax, byte ptr [r8-1]
0x180009977  mov     rdx, r8
0x18000997a  dec     r8
0x18000997d  cmp     al, 5Ch ; '\'
0x18000997f  jz      short loc_180009988
0x180009981  cmp     r8, rcx
0x180009984  ja      short loc_180009972
0x180009986  cmp     al, 5Ch ; '\'
0x180009988  cmovz   r8, rdx
0x18000998c  mov     r9d, 626h
0x180009992  mov     edx, r12d
0x180009995  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000999c  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800099a1  mov     rax, [rsi+80h]
0x1800099a8  mov     r15, [rsp+98h+var_38]
0x1800099ad  mov     r14, [rsp+98h+var_30]
  ... truncated ...
```
