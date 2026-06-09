# GenerateSpecifiedSecretAgreementSecret

- ea: `0x1800190b4`
- end: `0x18001926e`
- name: `GenerateSpecifiedSecretAgreementSecret`
- size: `442`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018c7c`

## callees

- `0x18000dfc0`
- `0x18000e540`
- `0x18000e644`
- `0x1800190b4`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18001923e`
- `bcrypt!BCryptDestroyKey` at `0x18001924c`
- `bcrypt!BCryptDestroyKey` at `0x18001923e`
- `bcrypt!BCryptDestroyKey` at `0x18001924c`

## string_xrefs

- `0x1800191b4`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180019218`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall GenerateSpecifiedSecretAgreementSecret(
        unsigned int *a1,
        __int64 a2,
        struct _INFORMATIONCARD_CRYPTO_HANDLE *a3,
        unsigned __int16 *a4,
        __int64 a5,
        int a6,
        unsigned __int8 *a7,
        ULONG a8)
{
  UCHAR *v8; // r12
  __int64 v9; // rbp
  BCRYPT_KEY_HANDLE v10; // rdi
  DWORD v11; // r14d
  unsigned int v15; // ebx
  unsigned int v16; // r9d
  unsigned int v17; // ecx
  signed int v18; // eax
  int SecretFromSecretAgreement; // eax
  BYTE *pLabel; // [rsp+20h] [rbp-68h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+90h] [rbp+8h] BYREF
  BCRYPT_KEY_HANDLE hPrivKey; // [rsp+98h] [rbp+10h] BYREF

  v8 = 0;
  v9 = a1[11];
  v10 = 0;
  v11 = 0;
  a8 = a1[13];
  hKey = 0;
  hPrivKey = 0;
  if ( a8 )
    v8 = (UCHAR *)a1 + v9 + a1[12] + a1[10] + 80;
  if ( (_DWORD)v9 )
    v11 = (_DWORD)a1 + a1[10] + 80;
  if ( GenerateSecretAgreementPubKey(a4, (unsigned __int8 *)(a2 + 52), *(_DWORD *)(a2 + 40), &hKey) < 0 )
  {
    v15 = -2146893821;
    v16 = 739;
    v17 = -2146893821;
LABEL_11:
    SidKeyDebugTraceError(v17, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx", v16);
    goto LABEL_12;
  }
  v18 = GenerateSecretAgreementPrivateKey(a5, a4, a3, v11, v9, v8, a8, (a1[14] + 7) >> 3, a1[15], a6, &hPrivKey, 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    SidKeyDebugTraceError(
      v18,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      0x2F6u);
    v10 = hPrivKey;
    goto LABEL_12;
  }
  v10 = hPrivKey;
  LODWORD(pLabel) = v9;
  SecretFromSecretAgreement = GenerateSecretFromSecretAgreement(hKey, hPrivKey, a3, v11, pLabel);
  v15 = SecretFromSecretAgreement;
  if ( SecretFromSecretAgreement < 0 )
  {
    v16 = 773;
    v17 = SecretFromSecretAgreement;
    goto LABEL_11;
  }
LABEL_12:
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v10 )
    BCryptDestroyKey(v10);
  return v15;
}

```

## disassembly

```asm
0x1800190b4  mov     r11, rsp
0x1800190b7  mov     [r11+18h], rbx
0x1800190bb  mov     [r11+20h], rbp
0x1800190bf  push    rdi
0x1800190c0  push    r12
0x1800190c2  push    r13
0x1800190c4  push    r14
0x1800190c6  push    r15
0x1800190c8  sub     rsp, 60h
0x1800190cc  mov     eax, [rcx+34h]
0x1800190cf  xor     r12d, r12d
0x1800190d2  mov     ebp, [rcx+2Ch]
0x1800190d5  xor     edi, edi
0x1800190d7  xor     r14d, r14d
0x1800190da  mov     [rsp+88h+arg_38], eax
0x1800190e1  mov     [r11+8], r12
0x1800190e5  mov     r15, r8
0x1800190e8  mov     [r11+10h], rdi
0x1800190ec  mov     r13, r9
0x1800190ef  mov     r8, rdx
0x1800190f2  mov     rbx, rcx
0x1800190f5  test    eax, eax
0x1800190f7  jz      short loc_18001910D
0x1800190f9  mov     ecx, [rcx+30h]
0x1800190fc  lea     r12, [rbx+rbp]
0x180019100  mov     eax, [rbx+28h]
0x180019103  add     r12, rcx
0x180019106  add     rax, 50h ; 'P'
0x18001910a  add     r12, rax
0x18001910d  test    ebp, ebp
0x18001910f  jz      short loc_18001911C
0x180019111  mov     r14d, [rbx+28h]
0x180019115  add     r14, 50h ; 'P'
0x180019119  add     r14, rbx
0x18001911c  mov     r8d, [r8+28h]; unsigned int
0x180019120  lea     r9, [rsp+88h+hKey]; void **
0x180019128  add     rdx, 34h ; '4'; unsigned __int8 *
0x18001912c  mov     rcx, r13; unsigned __int16 *
0x18001912f  call    ?GenerateSecretAgreementPubKey@@YAJPEAGPEAEKPEAPEAX@Z; GenerateSecretAgreementPubKey(ushort *,uchar *,ulong,void * *)
0x180019134  test    eax, eax
0x180019136  jns     short loc_18001914D
0x180019138  mov     ebx, 80090003h
0x18001913d  mov     r9d, 2E3h
0x180019143  mov     ecx, 80090003h
0x180019148  jmp     loc_180019218
0x18001914d  mov     ecx, [rbx+38h]
0x180019150  lea     rax, [rsp+88h+hPrivKey]
0x180019158  mov     [rsp+88h+var_30], rdi
0x18001915d  add     ecx, 7
0x180019160  mov     [rsp+88h+var_38], rax
0x180019165  mov     r9, r14
0x180019168  mov     eax, [rsp+88h+arg_28]
0x18001916f  mov     r8, r15
0x180019172  mov     [rsp+88h+var_40], eax
0x180019176  mov     rdx, r13
0x180019179  mov     eax, [rbx+3Ch]
0x18001917c  mov     [rsp+88h+var_48], eax
0x180019180  mov     eax, [rsp+88h+arg_38]
0x180019187  shr     ecx, 3
0x18001918a  mov     [rsp+88h+var_50], ecx
0x18001918e  mov     rcx, [rsp+88h+arg_20]
0x180019196  mov     [rsp+88h+var_58], eax
0x18001919a  mov     [rsp+88h+var_60], r12
0x18001919f  mov     dword ptr [rsp+88h+pLabel], ebp
0x1800191a3  call    ?GenerateSecretAgreementPrivateKey@@YAJQEAEPEAG1PEAEK2KKKW4_SID_KEY_BLOB_VER@@PEAPEAXPEAPEAG@Z; GenerateSecretAgreementPrivateKey(uchar * const,ushort *,ushort *,uchar *,ulong,uchar *,ulong,ulong,ulong,_SID_KEY_BLOB_VER,void * *,ushort * *)
0x1800191a8  mov     ebx, eax
0x1800191aa  test    eax, eax
0x1800191ac  jns     short loc_1800191D3
0x1800191ae  mov     r9d, 2F6h; unsigned int
0x1800191b4  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800191bb  lea     rdx, aHr; "hr"
0x1800191c2  mov     ecx, eax; unsigned int
0x1800191c4  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800191c9  mov     rdi, [rsp+88h+hPrivKey]
0x1800191d1  jmp     short loc_18001922B
0x1800191d3  mov     rax, [rsp+88h+arg_30]
0x1800191db  mov     r9, r14; cbLabel
0x1800191de  mov     rdi, [rsp+88h+hPrivKey]
0x1800191e6  mov     r8, r15; hCrypto
0x1800191e9  mov     rcx, [rsp+88h+hKey]; hPubKey
0x1800191f1  mov     rdx, rdi; hPrivKey
0x1800191f4  mov     [rsp+88h+var_58], 20h ; ' '; unsigned int
0x1800191fc  mov     [rsp+88h+var_60], rax; unsigned __int8 *
0x180019201  mov     dword ptr [rsp+88h+pLabel], ebp; pLabel
0x180019205  call    ?GenerateSecretFromSecretAgreement@@YAJPEAX0PEBGPEAEK2K@Z; GenerateSecretFromSecretAgreement(void *,void *,ushort const *,uchar *,ulong,uchar *,ulong)
0x18001920a  mov     ebx, eax
0x18001920c  test    eax, eax
0x18001920e  jns     short loc_18001922B
0x180019210  mov     r9d, 305h; unsigned int
0x180019216  mov     ecx, eax; unsigned int
0x180019218  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001921f  lea     rdx, aHr; "hr"
0x180019226  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001922b  cmp     [rsp+88h+hKey], 0
0x180019234  jz      short loc_180019244
0x180019236  mov     rcx, [rsp+88h+hKey]; hKey
0x18001923e  call    cs:__imp_BCryptDestroyKey
0x180019244  test    rdi, rdi
0x180019247  jz      short loc_180019252
0x180019249  mov     rcx, rdi; hKey
0x18001924c  call    cs:__imp_BCryptDestroyKey
0x180019252  lea     r11, [rsp+88h+var_28]
0x180019257  mov     eax, ebx
0x180019259  mov     rbx, [r11+40h]
0x18001925d  mov     rbp, [r11+48h]
0x180019261  mov     rsp, r11
0x180019264  pop     r15
0x180019266  pop     r14
0x180019268  pop     r13
0x18001926a  pop     r12
0x18001926c  pop     rdi
0x18001926d  retn
```
