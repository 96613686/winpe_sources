# GenerateLatestSecretAgreementSecret

- ea: `0x1800189b8`
- end: `0x180018b7f`
- name: `GenerateLatestSecretAgreementSecret`
- size: `455`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018c7c`

## callees

- `0x18000dc90`
- `0x18000de80`
- `0x18000e540`
- `0x18000e644`
- `0x180010950`
- `0x1800189b8`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x180018b4d`
- `bcrypt!BCryptDestroyKey` at `0x180018b5b`
- `bcrypt!BCryptDestroyKey` at `0x180018b4d`
- `bcrypt!BCryptDestroyKey` at `0x180018b5b`

## string_xrefs

- `0x180018a5f`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180018a9a`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180018b13`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 GenerateLatestSecretAgreementSecret(
        unsigned int *a1,
        struct _INFORMATIONCARD_CRYPTO_HANDLE *a2,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        ...)
{
  __int64 v5; // r12
  unsigned __int8 *v7; // rdx
  DWORD v8; // r13d
  BCRYPT_KEY_HANDLE v9; // rsi
  unsigned __int8 *v10; // r14
  signed int SecretFromSecretAgreement; // eax
  unsigned int v12; // ebx
  unsigned int v13; // r9d
  signed int v14; // eax
  signed int v15; // eax
  BYTE *pLabel; // [rsp+20h] [rbp-30h]
  BCRYPT_KEY_HANDLE hPubKey; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int8 *v19; // [rsp+48h] [rbp-8h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+90h] [rbp+40h] BYREF
  PINFORMATIONCARD_CRYPTO_HANDLE hCrypto; // [rsp+98h] [rbp+48h]
  unsigned __int16 *v22; // [rsp+A0h] [rbp+50h]
  unsigned __int8 *v23; // [rsp+A8h] [rbp+58h]
  __int64 v24; // [rsp+B8h] [rbp+68h] BYREF
  va_list va; // [rsp+B8h] [rbp+68h]
  unsigned __int8 **v26; // [rsp+C0h] [rbp+70h]
  _DWORD *v27; // [rsp+C8h] [rbp+78h]
  va_list va1; // [rsp+D0h] [rbp+80h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v24 = va_arg(va1, _QWORD);
  v26 = va_arg(va1, unsigned __int8 **);
  v27 = va_arg(va1, _DWORD *);
  v23 = a4;
  v22 = a3;
  hCrypto = a2;
  v5 = a1[11];
  v7 = 0;
  v8 = 0;
  v9 = 0;
  hKey = 0;
  v10 = 0;
  hPubKey = 0;
  v19 = 0;
  LODWORD(v24) = 0;
  if ( a1[13] )
    v7 = (unsigned __int8 *)a1 + v5 + a1[12] + a1[10] + 80;
  if ( (_DWORD)v5 )
    v8 = (_DWORD)a1 + a1[10] + 80;
  SecretFromSecretAgreement = GenerateEphemeralKeyPair(a3, v7, a1[13], (a1[14] + 7) >> 3, a1[15], &hKey);
  v12 = SecretFromSecretAgreement;
  if ( SecretFromSecretAgreement < 0 )
  {
    v13 = 636;
LABEL_7:
    SidKeyDebugTraceError(
      SecretFromSecretAgreement,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      v13);
    goto LABEL_15;
  }
  v14 = GenerateSecretAgreementPubKey(v22, v23, a1[17], &hPubKey);
  v12 = v14;
  if ( v14 >= 0 )
  {
    v9 = hPubKey;
    LODWORD(pLabel) = v5;
    SecretFromSecretAgreement = GenerateSecretFromSecretAgreement(hPubKey, hKey, hCrypto, v8, pLabel);
    v12 = SecretFromSecretAgreement;
    if ( SecretFromSecretAgreement < 0 )
    {
      v13 = 661;
      goto LABEL_7;
    }
    v15 = GenerateSIDPublicKeyBlob(hKey, &v19, (unsigned int *)va);
    v12 = v15;
    if ( v15 >= 0 )
    {
      *v26 = v19;
      *v27 = v24;
    }
    else
    {
      SidKeyDebugTraceError(
        v15,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
        0x29Fu);
      v10 = v19;
    }
  }
  else
  {
    SidKeyDebugTraceError(
      v14,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      0x287u);
    v9 = hPubKey;
  }
LABEL_15:
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v9 )
    BCryptDestroyKey(v9);
  if ( v10 )
    SIDKeyProvFree(v10);
  return v12;
}

```

## disassembly

```asm
0x1800189b8  mov     [rsp-38h+arg_18], r9
0x1800189bd  mov     [rsp-38h+arg_10], r8
0x1800189c2  mov     [rsp-38h+hCrypto], rdx
0x1800189c7  push    rbp
0x1800189c8  push    rbx
0x1800189c9  push    rsi
0x1800189ca  push    rdi
0x1800189cb  push    r12
0x1800189cd  push    r13
0x1800189cf  push    r14
0x1800189d1  mov     rbp, rsp
0x1800189d4  sub     rsp, 50h
0x1800189d8  mov     r12d, [rcx+2Ch]
0x1800189dc  xor     r9d, r9d
0x1800189df  mov     r10, r8
0x1800189e2  mov     rdi, rcx
0x1800189e5  mov     edx, r9d
0x1800189e8  mov     r13d, r9d
0x1800189eb  mov     esi, r9d
0x1800189ee  mov     [rbp+hKey], r9
0x1800189f2  mov     r14d, r9d
0x1800189f5  mov     [rbp+hPubKey], r9
0x1800189f9  mov     [rbp+var_8], r9
0x1800189fd  mov     dword ptr [rbp+arg_28], r9d
0x180018a01  cmp     [rcx+34h], r9d
0x180018a05  jz      short loc_180018A1B
0x180018a07  mov     ecx, [rcx+30h]
0x180018a0a  lea     rdx, [rdi+r12]
0x180018a0e  mov     eax, [rdi+28h]
0x180018a11  add     rdx, rcx
0x180018a14  add     rax, 50h ; 'P'
0x180018a18  add     rdx, rax; unsigned __int8 *
0x180018a1b  test    r12d, r12d
0x180018a1e  jz      short loc_180018A2B
0x180018a20  mov     r13d, [rdi+28h]
0x180018a24  add     r13, 50h ; 'P'
0x180018a28  add     r13, rdi
0x180018a2b  mov     r9d, [rdi+38h]
0x180018a2f  lea     rax, [rbp+hKey]
0x180018a33  mov     r8d, [rdi+34h]; unsigned int
0x180018a37  add     r9d, 7
0x180018a3b  mov     [rsp+50h+var_28], rax; void **
0x180018a40  mov     rcx, r10; unsigned __int16 *
0x180018a43  mov     eax, [rdi+3Ch]
0x180018a46  shr     r9d, 3; unsigned int
0x180018a4a  mov     dword ptr [rsp+50h+pLabel], eax; unsigned int
0x180018a4e  call    ?GenerateEphemeralKeyPair@@YAJPEAGPEAEKKKPEAPEAX@Z; GenerateEphemeralKeyPair(ushort *,uchar *,ulong,ulong,ulong,void * *)
0x180018a53  mov     ebx, eax
0x180018a55  test    eax, eax
0x180018a57  jns     short loc_180018A79
0x180018a59  mov     r9d, 27Ch; unsigned int
0x180018a5f  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018a66  mov     ecx, eax; unsigned int
0x180018a68  lea     rdx, aHr; "hr"
0x180018a6f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018a74  jmp     loc_180018B42
0x180018a79  mov     r8d, [rdi+44h]; unsigned int
0x180018a7d  lea     r9, [rbp+hPubKey]; void **
0x180018a81  mov     rdx, [rbp+arg_18]; unsigned __int8 *
0x180018a85  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x180018a89  call    ?GenerateSecretAgreementPubKey@@YAJPEAGPEAEKPEAPEAX@Z; GenerateSecretAgreementPubKey(ushort *,uchar *,ulong,void * *)
0x180018a8e  mov     ebx, eax
0x180018a90  test    eax, eax
0x180018a92  jns     short loc_180018AB8
0x180018a94  mov     r9d, 287h; unsigned int
0x180018a9a  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018aa1  lea     rdx, aHr; "hr"
0x180018aa8  mov     ecx, eax; unsigned int
0x180018aaa  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018aaf  mov     rsi, [rbp+hPubKey]
0x180018ab3  jmp     loc_180018B42
0x180018ab8  mov     rax, [rbp+arg_20]
0x180018abc  mov     r9, r13; cbLabel
0x180018abf  mov     rsi, [rbp+hPubKey]
0x180018ac3  mov     r8, [rbp+hCrypto]; hCrypto
0x180018ac7  mov     rcx, rsi; hPubKey
0x180018aca  mov     rdx, [rbp+hKey]; hPrivKey
0x180018ace  mov     [rsp+50h+var_20], 20h ; ' '; unsigned int
0x180018ad6  mov     [rsp+50h+var_28], rax; unsigned __int8 *
0x180018adb  mov     dword ptr [rsp+50h+pLabel], r12d; pLabel
0x180018ae0  call    ?GenerateSecretFromSecretAgreement@@YAJPEAX0PEBGPEAEK2K@Z; GenerateSecretFromSecretAgreement(void *,void *,ushort const *,uchar *,ulong,uchar *,ulong)
0x180018ae5  mov     ebx, eax
0x180018ae7  test    eax, eax
0x180018ae9  jns     short loc_180018AF6
0x180018aeb  mov     r9d, 295h
0x180018af1  jmp     loc_180018A5F
0x180018af6  mov     rcx, [rbp+hKey]; hKey
0x180018afa  lea     r8, [rbp+arg_28]; unsigned int *
0x180018afe  lea     rdx, [rbp+var_8]; unsigned __int8 **
0x180018b02  call    ?GenerateSIDPublicKeyBlob@@YAJPEAXPEAPEAEPEAK@Z; GenerateSIDPublicKeyBlob(void *,uchar * *,ulong *)
0x180018b07  mov     ebx, eax
0x180018b09  test    eax, eax
0x180018b0b  jns     short loc_180018B2E
0x180018b0d  mov     r9d, 29Fh; unsigned int
0x180018b13  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018b1a  lea     rdx, aHr; "hr"
0x180018b21  mov     ecx, eax; unsigned int
0x180018b23  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018b28  mov     r14, [rbp+var_8]
0x180018b2c  jmp     short loc_180018B42
0x180018b2e  mov     rdx, [rbp+arg_30]
0x180018b32  mov     rax, [rbp+var_8]
0x180018b36  mov     [rdx], rax
0x180018b39  mov     rdx, [rbp+arg_38]
0x180018b3d  mov     eax, dword ptr [rbp+arg_28]
0x180018b40  mov     [rdx], eax
0x180018b42  cmp     [rbp+hKey], 0
0x180018b47  jz      short loc_180018B53
0x180018b49  mov     rcx, [rbp+hKey]; hKey
0x180018b4d  call    cs:__imp_BCryptDestroyKey
0x180018b53  test    rsi, rsi
0x180018b56  jz      short loc_180018B61
0x180018b58  mov     rcx, rsi; hKey
0x180018b5b  call    cs:__imp_BCryptDestroyKey
0x180018b61  test    r14, r14
0x180018b64  jz      short loc_180018B6E
0x180018b66  mov     rcx, r14; lpMem
0x180018b69  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180018b6e  mov     eax, ebx
0x180018b70  add     rsp, 50h
0x180018b74  pop     r14
0x180018b76  pop     r13
0x180018b78  pop     r12
0x180018b7a  pop     rdi
0x180018b7b  pop     rsi
0x180018b7c  pop     rbx
0x180018b7d  pop     rbp
0x180018b7e  retn
```
