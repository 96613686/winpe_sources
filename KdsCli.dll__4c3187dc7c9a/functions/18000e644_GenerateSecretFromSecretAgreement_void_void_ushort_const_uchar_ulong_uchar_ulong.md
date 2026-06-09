# GenerateSecretFromSecretAgreement(void *,void *,ushort const *,uchar *,ulong,uchar *,ulong)

- ea: `0x18000e644`
- end: `0x18000e892`
- name: `?GenerateSecretFromSecretAgreement@@YAJPEAX0PEBGPEAEK2K@Z`
- size: `590`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE hPubKey, BCRYPT_KEY_HANDLE hPrivKey, PINFORMATIONCARD_CRYPTO_HANDLE hCrypto, DWORD cbLabel, PBYTE pLabel, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e8a0`
- `0x1800189b8`
- `0x1800190b4`

## callees

- `0x180001630`
- `0x18000d6a0`
- `0x18000e644`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptSecretAgreement` at `0x18000e6ef`
- `bcrypt!BCryptSecretAgreement` at `0x18000e6ef`
- `bcrypt!BCryptDeriveKey` at `0x18000e742`
- `bcrypt!BCryptDeriveKey` at `0x18000e7a5`
- `bcrypt!BCryptDeriveKey` at `0x18000e742`
- `bcrypt!BCryptDeriveKey` at `0x18000e7a5`
- `bcrypt!BCryptDestroySecret` at `0x18000e84a`
- `bcrypt!BCryptDestroySecret` at `0x18000e84a`

## string_xrefs

- `0x18000e699`: `KDS service`
- `0x18000e701`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`
- `0x18000e82e`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`

## pseudocode

```c
__int64 __fastcall GenerateSecretFromSecretAgreement(
        BCRYPT_KEY_HANDLE hPubKey,
        BCRYPT_KEY_HANDLE hPrivKey,
        PINFORMATIONCARD_CRYPTO_HANDLE hCrypto,
        DWORD cbLabel,
        PBYTE pLabel)
{
  UCHAR *v7; // rdi
  NTSTATUS v8; // ebx
  unsigned int v9; // r9d
  unsigned int v10; // ebx
  unsigned int v11; // r9d
  unsigned int v12; // ecx
  HRESULT DerivedKey; // eax
  __int64 v14; // rax
  UCHAR *v15; // rcx
  BYTE *cbDerivedKey; // [rsp+20h] [rbp-A1h]
  PBYTE *ppKey; // [rsp+48h] [rbp-79h]
  ULONG pcbResult; // [rsp+70h] [rbp-51h] BYREF
  BCRYPT_SECRET_HANDLE phAgreedSecret; // [rsp+78h] [rbp-49h] BYREF
  BCryptBufferDesc pParameterList; // [rsp+80h] [rbp-41h] BYREF
  _DWORD v22[2]; // [rsp+90h] [rbp-31h] BYREF
  const wchar_t *v23; // [rsp+98h] [rbp-29h]
  int v24; // [rsp+A0h] [rbp-21h]
  int v25; // [rsp+A4h] [rbp-1Dh]
  const char *v26; // [rsp+A8h] [rbp-19h]
  int v27; // [rsp+B0h] [rbp-11h]
  int v28; // [rsp+B4h] [rbp-Dh]
  const wchar_t *v29; // [rsp+B8h] [rbp-9h]

  phAgreedSecret = 0;
  v23 = L"SHA512";
  pcbResult = 0;
  v26 = L"KDS public key";
  v22[1] = 8;
  v29 = L"KDS service";
  v22[0] = 14;
  pParameterList.pBuffers = (PBCryptBuffer)v22;
  v7 = 0;
  v25 = 9;
  v24 = 30;
  v28 = 10;
  v27 = 24;
  pParameterList.ulVersion = 0;
  pParameterList.cBuffers = 3;
  v8 = BCryptSecretAgreement(hPrivKey, hPubKey, &phAgreedSecret, 0);
  if ( v8 < 0 )
  {
    v9 = 701;
LABEL_3:
    SidKeyDebugTraceError(v8, "status", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx", v9);
    v10 = v8 | 0x10000000;
    goto LABEL_13;
  }
  v8 = BCryptDeriveKey(phAgreedSecret, L"SP800_56A_CONCAT", &pParameterList, 0, 0, &pcbResult, 0);
  if ( v8 < 0 )
  {
    v9 = 716;
    goto LABEL_3;
  }
  v7 = (UCHAR *)SIDKeyProvAlloc(pcbResult);
  if ( !v7 )
  {
    v10 = -2147024882;
    v11 = 725;
    v12 = -2147024882;
LABEL_12:
    SidKeyDebugTraceError(v12, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx", v11);
    goto LABEL_13;
  }
  v8 = BCryptDeriveKey(phAgreedSecret, L"SP800_56A_CONCAT", &pParameterList, v7, pcbResult, &pcbResult, 0);
  if ( v8 < 0 )
  {
    v9 = 740;
    goto LABEL_3;
  }
  LODWORD(ppKey) = 0;
  LODWORD(cbDerivedKey) = pcbResult;
  DerivedKey = GenerateDerivedKey(
                 hCrypto,
                 cbLabel,
                 (PBYTE)(unsigned int)pLabel,
                 (DWORD)v7,
                 cbDerivedKey,
                 (DWORD)L"KDS public key",
                 0x1Eu,
                 0,
                 0,
                 ppKey);
  v10 = DerivedKey;
  if ( DerivedKey < 0 )
  {
    v11 = 762;
    v12 = DerivedKey;
    goto LABEL_12;
  }
LABEL_13:
  if ( phAgreedSecret )
    BCryptDestroySecret(phAgreedSecret);
  if ( v7 )
  {
    v14 = pcbResult;
    v15 = v7;
    if ( pcbResult )
    {
      do
      {
        *v15++ = 0;
        --v14;
      }
      while ( v14 );
    }
    SIDKeyProvFree(v7);
  }
  return v10;
}

```

## disassembly

```asm
0x18000e644  push    rbp
0x18000e646  push    rbx
0x18000e647  push    rsi
0x18000e648  push    rdi
0x18000e649  push    r14
0x18000e64b  push    r15
0x18000e64d  lea     rbp, [rsp-17h]
0x18000e652  sub     rsp, 0D8h
0x18000e659  mov     rax, cs:__security_cookie
0x18000e660  xor     rax, rsp
0x18000e663  mov     [rbp+3Fh+var_40], rax
0x18000e667  mov     r15, [rbp+3Fh+arg_28]
0x18000e66b  mov     rax, rdx
0x18000e66e  lea     rdx, aSha512; "SHA512"
0x18000e675  mov     [rbp+3Fh+phAgreedSecret], 0
0x18000e67d  mov     [rbp+3Fh+var_68], rdx
0x18000e681  mov     r14, r9
0x18000e684  lea     rdx, derivedKeyLength; "KDS public key"
0x18000e68b  mov     [rbp+3Fh+var_90], 0
0x18000e692  mov     [rbp+3Fh+var_58], rdx
0x18000e696  mov     rsi, r8
0x18000e699  lea     rdx, aKdsService; "KDS service"
0x18000e6a0  mov     [rbp+3Fh+var_6C], 8
0x18000e6a7  mov     [rbp+3Fh+var_48], rdx
0x18000e6ab  lea     r8, [rbp+3Fh+phAgreedSecret]; phAgreedSecret
0x18000e6af  lea     rdx, [rbp+3Fh+var_70]
0x18000e6b3  mov     [rbp+3Fh+var_70], 0Eh
0x18000e6ba  mov     [rbp+3Fh+pParameterList.pBuffers], rdx
0x18000e6be  xor     edi, edi
0x18000e6c0  mov     rdx, rcx; hPubKey
0x18000e6c3  mov     [rbp+3Fh+var_5C], 9
0x18000e6ca  mov     rcx, rax; hPrivKey
0x18000e6cd  mov     [rbp+3Fh+var_60], 1Eh
0x18000e6d4  xor     r9d, r9d; dwFlags
0x18000e6d7  mov     [rbp+3Fh+var_4C], 0Ah
0x18000e6de  mov     [rbp+3Fh+var_50], 18h
0x18000e6e5  mov     [rbp+3Fh+pParameterList.ulVersion], edi
0x18000e6e8  mov     [rbp+3Fh+pParameterList.cBuffers], 3
0x18000e6ef  call    cs:__imp_BCryptSecretAgreement
0x18000e6f5  mov     ebx, eax
0x18000e6f7  test    eax, eax
0x18000e6f9  jns     short loc_18000E71F
0x18000e6fb  mov     r9d, 2BDh; unsigned int
0x18000e701  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000e708  mov     ecx, ebx; unsigned int
0x18000e70a  lea     rdx, aStatus; "status"
0x18000e711  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000e716  bts     ebx, 1Ch
0x18000e71a  jmp     loc_18000E841
0x18000e71f  mov     rcx, [rbp+3Fh+phAgreedSecret]; hSharedSecret
0x18000e723  lea     rax, [rbp+3Fh+var_90]
0x18000e727  mov     [rsp+100h+dwFlags], edi; dwFlags
0x18000e72b  lea     r8, [rbp+3Fh+pParameterList]; pParameterList
0x18000e72f  mov     [rsp+100h+pcbResult], rax; pcbResult
0x18000e734  lea     rdx, pwszKDF; "SP800_56A_CONCAT"
0x18000e73b  xor     r9d, r9d; pbDerivedKey
0x18000e73e  mov     dword ptr [rsp+100h+cbDerivedKey], edi; cbDerivedKey
0x18000e742  call    cs:__imp_BCryptDeriveKey
0x18000e748  mov     ebx, eax
0x18000e74a  test    eax, eax
0x18000e74c  jns     short loc_18000E756
0x18000e74e  mov     r9d, 2CCh
0x18000e754  jmp     short loc_18000E701
0x18000e756  mov     ecx, [rbp+3Fh+var_90]; unsigned __int64
0x18000e759  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000e75e  mov     rdi, rax
0x18000e761  test    rax, rax
0x18000e764  jnz     short loc_18000E77B
0x18000e766  mov     ebx, 8007000Eh
0x18000e76b  mov     r9d, 2D5h
0x18000e771  mov     ecx, 8007000Eh
0x18000e776  jmp     loc_18000E82E
0x18000e77b  mov     rcx, [rbp+3Fh+phAgreedSecret]; hSharedSecret
0x18000e77f  lea     rax, [rbp+3Fh+var_90]
0x18000e783  mov     [rsp+100h+dwFlags], 0; dwFlags
0x18000e78b  lea     r8, [rbp+3Fh+pParameterList]; pParameterList
0x18000e78f  mov     [rsp+100h+pcbResult], rax; pcbResult
0x18000e794  lea     rdx, pwszKDF; "SP800_56A_CONCAT"
0x18000e79b  mov     eax, [rbp+3Fh+var_90]
0x18000e79e  mov     r9, rdi; pbDerivedKey
0x18000e7a1  mov     dword ptr [rsp+100h+cbDerivedKey], eax; cbDerivedKey
0x18000e7a5  call    cs:__imp_BCryptDeriveKey
0x18000e7ab  mov     ebx, eax
0x18000e7ad  test    eax, eax
0x18000e7af  jns     short loc_18000E7BC
0x18000e7b1  mov     r9d, 2E4h
0x18000e7b7  jmp     loc_18000E701
0x18000e7bc  mov     eax, [rbp+3Fh+arg_30]
0x18000e7bf  mov     r9, rdi; cbNonce
0x18000e7c2  mov     r8d, dword ptr [rbp+3Fh+pLabel]; pLabel
0x18000e7c6  mov     rdx, r14; cbLabel
0x18000e7c9  mov     [rsp+100h+var_98], 0
0x18000e7d2  mov     rcx, rsi; hCrypto
0x18000e7d5  mov     [rsp+100h+var_A0], eax
0x18000e7d9  lea     rax, derivedKeyLength; "KDS public key"
0x18000e7e0  mov     [rsp+100h+var_A8], r15
0x18000e7e5  mov     [rsp+100h+var_B0], 1
0x18000e7ed  mov     dword ptr [rsp+100h+ppKey], 0; ppKey
0x18000e7f5  mov     [rsp+100h+pcbKey], 0; pcbKey
0x18000e7fe  mov     [rsp+100h+algId], 0; algId
0x18000e807  mov     [rsp+100h+dwFlags], 1Eh; offset
0x18000e80f  mov     [rsp+100h+pcbResult], rax; derivedKeyLength
0x18000e814  mov     eax, [rbp+3Fh+var_90]
0x18000e817  mov     dword ptr [rsp+100h+cbDerivedKey], eax; pNonce
0x18000e81b  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x18000e820  mov     ebx, eax
0x18000e822  test    eax, eax
0x18000e824  jns     short loc_18000E841
0x18000e826  mov     r9d, 2FAh; unsigned int
0x18000e82c  mov     ecx, eax; unsigned int
0x18000e82e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000e835  lea     rdx, aHr; "hr"
0x18000e83c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000e841  mov     rcx, [rbp+3Fh+phAgreedSecret]; hSecret
0x18000e845  test    rcx, rcx
0x18000e848  jz      short loc_18000E850
0x18000e84a  call    cs:__imp_BCryptDestroySecret
0x18000e850  test    rdi, rdi
0x18000e853  jz      short loc_18000E874
0x18000e855  mov     eax, [rbp+3Fh+var_90]
0x18000e858  mov     rcx, rdi
0x18000e85b  test    rax, rax
0x18000e85e  jz      short loc_18000E86C
0x18000e860  mov     byte ptr [rcx], 0
0x18000e863  inc     rcx
0x18000e866  sub     rax, 1
0x18000e86a  jnz     short loc_18000E860
0x18000e86c  mov     rcx, rdi; lpMem
0x18000e86f  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000e874  mov     eax, ebx
0x18000e876  mov     rcx, [rbp+3Fh+var_40]
0x18000e87a  xor     rcx, rsp; StackCookie
0x18000e87d  call    __security_check_cookie
0x18000e882  add     rsp, 0D8h
0x18000e889  pop     r15
0x18000e88b  pop     r14
0x18000e88d  pop     rdi
0x18000e88e  pop     rsi
0x18000e88f  pop     rbx
0x18000e890  pop     rbp
0x18000e891  retn
```
