# TestServerConfig(_KDS_CONFIGURATION *,ushort * *)

- ea: `0x18000e8a0`
- end: `0x18000eaaf`
- name: `?TestServerConfig@@YAJPEAU_KDS_CONFIGURATION@@PEAPEAG@Z`
- size: `527`
- prototype: `__int64 __fastcall(struct _KDS_CONFIGURATION *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x18000dc90`
- `0x18000de80`
- `0x18000dfc0`
- `0x18000e540`
- `0x18000e644`
- `0x18000e8a0`
- `0x180010950`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18000ea5a`
- `bcrypt!BCryptDestroyKey` at `0x18000ea69`
- `bcrypt!BCryptDestroyKey` at `0x18000ea77`
- `bcrypt!BCryptDestroyKey` at `0x18000ea5a`
- `bcrypt!BCryptDestroyKey` at `0x18000ea69`
- `bcrypt!BCryptDestroyKey` at `0x18000ea77`

## pseudocode

```c
__int64 __fastcall TestServerConfig(struct _KDS_CONFIGURATION *a1, unsigned __int16 **a2)
{
  __int64 v4; // r9
  struct _INFORMATIONCARD_CRYPTO_HANDLE *v5; // r8
  unsigned __int8 *v6; // rsi
  WCHAR *v7; // rdx
  BCRYPT_KEY_HANDLE v8; // r14
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  int SecretFromSecretAgreement; // eax
  unsigned int pLabela; // [rsp+20h] [rbp-89h]
  BYTE *pLabel; // [rsp+20h] [rbp-89h]
  void **v16; // [rsp+28h] [rbp-81h]
  ULONG v17; // [rsp+30h] [rbp-79h]
  unsigned int v18; // [rsp+38h] [rbp-71h]
  ULONG v19; // [rsp+40h] [rbp-69h]
  unsigned int v20; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int8 *v21; // [rsp+68h] [rbp-41h] BYREF
  BCRYPT_KEY_HANDLE hPubKey; // [rsp+70h] [rbp-39h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+78h] [rbp-31h] BYREF
  BCRYPT_KEY_HANDLE hPrivKey; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int8 v25[64]; // [rsp+90h] [rbp-19h] BYREF

  memset_0(v25, 0, sizeof(v25));
  v4 = *((_QWORD *)a1 + 2);
  v5 = (struct _INFORMATIONCARD_CRYPTO_HANDLE *)*((_QWORD *)a1 + 1);
  v6 = 0;
  v7 = (WCHAR *)*((_QWORD *)a1 + 4);
  v8 = 0;
  v19 = *((_DWORD *)a1 + 14);
  v18 = (unsigned int)(*((_DWORD *)a1 + 13) + 7) >> 3;
  v17 = *((_DWORD *)a1 + 12);
  v16 = (void **)*((_QWORD *)a1 + 5);
  pLabela = *((_DWORD *)a1 + 6);
  hKey = 0;
  hPrivKey = 0;
  hPubKey = 0;
  v21 = 0;
  v20 = 0;
  v9 = GenerateSecretAgreementPrivateKey((DWORD)v25, v7, v5, v4, pLabela, (UCHAR *)v16, v17, v18, v19, 2, &hKey, a2);
  if ( v9 >= 0 )
  {
    v9 = GenerateEphemeralKeyPair(
           *((unsigned __int16 **)a1 + 4),
           *((unsigned __int8 **)a1 + 5),
           *((_DWORD *)a1 + 12),
           (unsigned int)(*((_DWORD *)a1 + 13) + 7) >> 3,
           *((_DWORD *)a1 + 14),
           &hPrivKey);
    if ( v9 >= 0 )
    {
      v10 = GenerateSIDPublicKeyBlob(hKey, &v21, &v20);
      v9 = v10;
      if ( v10 < 0 )
      {
        if ( v10 == -2147024882 || v10 == -805306345 )
        {
          v6 = v21;
          goto LABEL_17;
        }
        v6 = v21;
        goto LABEL_16;
      }
      v6 = v21;
      v11 = GenerateSecretAgreementPubKey(*((unsigned __int16 **)a1 + 4), v21, v20, &hPubKey);
      v9 = v11;
      if ( v11 < 0 )
      {
        if ( v11 == -2147024882 || v11 == -805306345 )
        {
          v8 = hPubKey;
          goto LABEL_17;
        }
        v8 = hPubKey;
        goto LABEL_16;
      }
      v8 = hPubKey;
      LODWORD(pLabel) = *((_DWORD *)a1 + 6);
      SecretFromSecretAgreement = GenerateSecretFromSecretAgreement(
                                    hPubKey,
                                    hPrivKey,
                                    *((PINFORMATIONCARD_CRYPTO_HANDLE *)a1 + 1),
                                    *((_QWORD *)a1 + 2),
                                    pLabel);
      v9 = SecretFromSecretAgreement;
      if ( SecretFromSecretAgreement < 0
        && SecretFromSecretAgreement != -2147024882
        && SecretFromSecretAgreement != -805306345 )
      {
LABEL_16:
        *a2 = L"msKds-SecretAgreementAlgorithmID";
      }
    }
  }
LABEL_17:
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( hPrivKey )
    BCryptDestroyKey(hPrivKey);
  if ( v8 )
    BCryptDestroyKey(v8);
  if ( v6 )
    SIDKeyProvFree(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e8a0  mov     [rsp-8+arg_10], rbx
0x18000e8a5  push    rbp
0x18000e8a6  push    rsi
0x18000e8a7  push    rdi
0x18000e8a8  push    r14
0x18000e8aa  push    r15
0x18000e8ac  lea     rbp, [rsp-37h]
0x18000e8b1  sub     rsp, 0E0h
0x18000e8b8  mov     rax, cs:__security_cookie
0x18000e8bf  xor     rax, rsp
0x18000e8c2  mov     [rbp+57h+var_30], rax
0x18000e8c6  mov     r15, rdx
0x18000e8c9  mov     rdi, rcx
0x18000e8cc  xor     edx, edx; Val
0x18000e8ce  lea     rcx, [rbp+57h+var_70]; void *
0x18000e8d2  lea     r8d, [rdx+40h]; Size
0x18000e8d6  call    memset_0
0x18000e8db  mov     ecx, [rdi+34h]
0x18000e8de  lea     rax, [rbp+57h+hKey]
0x18000e8e2  mov     r9, [rdi+10h]
0x18000e8e6  add     ecx, 7
0x18000e8e9  mov     r8, [rdi+8]
0x18000e8ed  xor     esi, esi
0x18000e8ef  mov     rdx, [rdi+20h]
0x18000e8f3  xor     r14d, r14d
0x18000e8f6  mov     [rsp+100h+var_A8], r15
0x18000e8fb  mov     [rsp+100h+var_B0], rax
0x18000e900  mov     eax, [rdi+38h]
0x18000e903  mov     [rsp+100h+var_B8], 2
0x18000e90b  mov     [rsp+100h+var_C0], eax
0x18000e90f  mov     eax, [rdi+30h]
0x18000e912  shr     ecx, 3
0x18000e915  mov     [rsp+100h+var_C8], ecx
0x18000e919  lea     rcx, [rbp+57h+var_70]
0x18000e91d  mov     [rsp+100h+var_D0], eax
0x18000e921  mov     rax, [rdi+28h]
0x18000e925  mov     [rsp+100h+var_D8], rax
0x18000e92a  mov     eax, [rdi+18h]
0x18000e92d  mov     dword ptr [rsp+100h+pLabel], eax
0x18000e931  mov     [rbp+57h+hKey], 0
0x18000e939  mov     [rbp+57h+hPrivKey], 0
0x18000e941  mov     [rbp+57h+hPubKey], r14
0x18000e945  mov     [rbp+57h+var_98], rsi
0x18000e949  mov     [rbp+57h+var_A0], esi
0x18000e94c  call    ?GenerateSecretAgreementPrivateKey@@YAJQEAEPEAG1PEAEK2KKKW4_SID_KEY_BLOB_VER@@PEAPEAXPEAPEAG@Z; GenerateSecretAgreementPrivateKey(uchar * const,ushort *,ushort *,uchar *,ulong,uchar *,ulong,ulong,ulong,_SID_KEY_BLOB_VER,void * *,ushort * *)
0x18000e951  mov     ebx, eax
0x18000e953  test    eax, eax
0x18000e955  js      loc_18000EA4F
0x18000e95b  mov     r9d, [rdi+34h]
0x18000e95f  lea     rax, [rbp+57h+hPrivKey]
0x18000e963  mov     r8d, [rdi+30h]; unsigned int
0x18000e967  add     r9d, 7
0x18000e96b  mov     rdx, [rdi+28h]; unsigned __int8 *
0x18000e96f  mov     rcx, [rdi+20h]; unsigned __int16 *
0x18000e973  mov     [rsp+100h+var_D8], rax; void **
0x18000e978  mov     eax, [rdi+38h]
0x18000e97b  shr     r9d, 3; unsigned int
0x18000e97f  mov     dword ptr [rsp+100h+pLabel], eax; unsigned int
0x18000e983  call    ?GenerateEphemeralKeyPair@@YAJPEAGPEAEKKKPEAPEAX@Z; GenerateEphemeralKeyPair(ushort *,uchar *,ulong,ulong,ulong,void * *)
0x18000e988  mov     ebx, eax
0x18000e98a  test    eax, eax
0x18000e98c  js      loc_18000EA4F
0x18000e992  mov     rcx, [rbp+57h+hKey]; hKey
0x18000e996  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x18000e99a  lea     rdx, [rbp+57h+var_98]; unsigned __int8 **
0x18000e99e  call    ?GenerateSIDPublicKeyBlob@@YAJPEAXPEAPEAEPEAK@Z; GenerateSIDPublicKeyBlob(void *,uchar * *,ulong *)
0x18000e9a3  mov     ebx, eax
0x18000e9a5  test    eax, eax
0x18000e9a7  jns     short loc_18000E9C9
0x18000e9a9  cmp     eax, 8007000Eh
0x18000e9ae  jz      short loc_18000E9C0
0x18000e9b0  cmp     eax, 0D0000017h
0x18000e9b5  jz      short loc_18000E9C0
0x18000e9b7  mov     rsi, [rbp+57h+var_98]
0x18000e9bb  jmp     loc_18000EA45
0x18000e9c0  mov     rsi, [rbp+57h+var_98]
0x18000e9c4  jmp     loc_18000EA4F
0x18000e9c9  mov     rsi, [rbp+57h+var_98]
0x18000e9cd  lea     r9, [rbp+57h+hPubKey]; void **
0x18000e9d1  mov     r8d, [rbp+57h+var_A0]; unsigned int
0x18000e9d5  mov     rdx, rsi; unsigned __int8 *
0x18000e9d8  mov     rcx, [rdi+20h]; unsigned __int16 *
0x18000e9dc  call    ?GenerateSecretAgreementPubKey@@YAJPEAGPEAEKPEAPEAX@Z; GenerateSecretAgreementPubKey(ushort *,uchar *,ulong,void * *)
0x18000e9e1  mov     ebx, eax
0x18000e9e3  test    eax, eax
0x18000e9e5  jns     short loc_18000EA01
0x18000e9e7  cmp     eax, 8007000Eh
0x18000e9ec  jz      short loc_18000E9FB
0x18000e9ee  cmp     eax, 0D0000017h
0x18000e9f3  jz      short loc_18000E9FB
0x18000e9f5  mov     r14, [rbp+57h+hPubKey]
0x18000e9f9  jmp     short loc_18000EA45
0x18000e9fb  mov     r14, [rbp+57h+hPubKey]
0x18000e9ff  jmp     short loc_18000EA4F
0x18000ea01  mov     r14, [rbp+57h+hPubKey]
0x18000ea05  lea     rax, [rbp+57h+var_70]
0x18000ea09  mov     r9, [rdi+10h]; cbLabel
0x18000ea0d  mov     rcx, r14; hPubKey
0x18000ea10  mov     r8, [rdi+8]; hCrypto
0x18000ea14  mov     rdx, [rbp+57h+hPrivKey]; hPrivKey
0x18000ea18  mov     [rsp+100h+var_D0], 40h ; '@'; unsigned int
0x18000ea20  mov     [rsp+100h+var_D8], rax; unsigned __int8 *
0x18000ea25  mov     eax, [rdi+18h]
0x18000ea28  mov     dword ptr [rsp+100h+pLabel], eax; pLabel
0x18000ea2c  call    ?GenerateSecretFromSecretAgreement@@YAJPEAX0PEBGPEAEK2K@Z; GenerateSecretFromSecretAgreement(void *,void *,ushort const *,uchar *,ulong,uchar *,ulong)
0x18000ea31  mov     ebx, eax
0x18000ea33  test    eax, eax
0x18000ea35  jns     short loc_18000EA4F
0x18000ea37  cmp     eax, 8007000Eh
0x18000ea3c  jz      short loc_18000EA4F
0x18000ea3e  cmp     eax, 0D0000017h
0x18000ea43  jz      short loc_18000EA4F
0x18000ea45  lea     rax, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x18000ea4c  mov     [r15], rax
0x18000ea4f  cmp     [rbp+57h+hKey], 0
0x18000ea54  jz      short loc_18000EA60
0x18000ea56  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ea5a  call    cs:__imp_BCryptDestroyKey
0x18000ea60  mov     rcx, [rbp+57h+hPrivKey]; hKey
0x18000ea64  test    rcx, rcx
0x18000ea67  jz      short loc_18000EA6F
0x18000ea69  call    cs:__imp_BCryptDestroyKey
0x18000ea6f  test    r14, r14
0x18000ea72  jz      short loc_18000EA7D
0x18000ea74  mov     rcx, r14; hKey
0x18000ea77  call    cs:__imp_BCryptDestroyKey
0x18000ea7d  test    rsi, rsi
0x18000ea80  jz      short loc_18000EA8A
0x18000ea82  mov     rcx, rsi; lpMem
0x18000ea85  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000ea8a  mov     eax, ebx
0x18000ea8c  mov     rcx, [rbp+57h+var_30]
0x18000ea90  xor     rcx, rsp; StackCookie
0x18000ea93  call    __security_check_cookie
0x18000ea98  mov     rbx, [rsp+100h+arg_10]
0x18000eaa0  add     rsp, 0E0h
0x18000eaa7  pop     r15
0x18000eaa9  pop     r14
0x18000eaab  pop     rdi
0x18000eaac  pop     rsi
0x18000eaad  pop     rbp
0x18000eaae  retn
```
