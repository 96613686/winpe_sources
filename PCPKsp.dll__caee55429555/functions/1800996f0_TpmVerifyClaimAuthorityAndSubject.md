# TpmVerifyClaimAuthorityAndSubject

- ea: `0x1800996f0`
- end: `0x180099c08`
- name: `TpmVerifyClaimAuthorityAndSubject`
- size: `1304`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, size_t, __int64, size_t, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180061f70`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x180063cdc`
- `0x1800764d0`
- `0x180077028`
- `0x18007c528`
- `0x1800928b8`
- `0x18009481c`
- `0x180096564`
- `0x180097028`
- `0x1800979d4`
- `0x180097ad8`
- `0x1800983d0`
- `0x1800984a8`
- `0x180098550`
- `0x1800996f0`

## import_xrefs

- `bcrypt!BCryptVerifySignature` at `0x18009998c`
- `bcrypt!BCryptVerifySignature` at `0x18009998c`
- `bcrypt!BCryptDestroyKey` at `0x180099b97`
- `bcrypt!BCryptDestroyKey` at `0x180099b97`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180099bae`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180099bae`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180099892`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180099892`

## pseudocode

```c
__int64 __fastcall TpmVerifyClaimAuthorityAndSubject(
        __int64 a1,
        void *a2,
        _DWORD *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        size_t a6,
        unsigned __int8 *a7,
        size_t a8,
        __int64 a9)
{
  BCRYPT_KEY_HANDLE v11; // rsi
  unsigned int v12; // r15d
  int v13; // ecx
  unsigned int v14; // r14d
  __int64 v15; // rdx
  UCHAR *v16; // rbx
  char *v17; // rdi
  bool v18; // zf
  const WCHAR *v19; // rdx
  NTSTATUS v20; // eax
  int v21; // eax
  __int64 v22; // r13
  ULONG v23; // r12d
  ULONG v24; // esi
  int v25; // r13d
  NTSTATUS v26; // eax
  unsigned __int8 *v27; // rax
  int Activation12; // eax
  unsigned int v29; // r9d
  unsigned int v30; // ebx
  PUCHAR pbSignature; // [rsp+20h] [rbp-E0h]
  ULONG cbSignaturea; // [rsp+28h] [rbp-D8h]
  ULONG cbSignature[2]; // [rsp+28h] [rbp-D8h]
  int KeyDigestFromBCryptKey; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v36; // [rsp+74h] [rbp-8Ch] BYREF
  ULONG dwFlags; // [rsp+78h] [rbp-88h]
  unsigned int v38; // [rsp+7Ch] [rbp-84h]
  size_t Size; // [rsp+80h] [rbp-80h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+88h] [rbp-78h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+90h] [rbp-70h] BYREF
  ULONG v42; // [rsp+98h] [rbp-68h]
  void *pPaddingInfo; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v44; // [rsp+A8h] [rbp-58h]
  __int64 v45; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v48; // [rsp+C8h] [rbp-38h] BYREF
  BCRYPT_KEY_HANDLE v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+D8h] [rbp-28h]
  int *v51[3]; // [rsp+E0h] [rbp-20h] BYREF
  UCHAR pbHash[16]; // [rsp+F8h] [rbp-8h] BYREF
  int v53; // [rsp+108h] [rbp+8h]
  unsigned __int8 Buf2[32]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int8 Buf1[32]; // [rsp+130h] [rbp+30h] BYREF

  v46 = a5;
  v44 = a7;
  v49 = a2;
  v50 = a9;
  KeyDigestFromBCryptKey = -2147467259;
  KspFunctionLogger::KspFunctionLogger(
    (KspFunctionLogger *)v51,
    L"TpmVerifyClaimAuthorityAndSubject",
    &KeyDigestFromBCryptKey);
  v53 = 0;
  v48 = L"SHA1";
  phAlgorithm = 0;
  v11 = 0;
  hKey = 0;
  v36 = 0;
  LODWORD(Size) = 0;
  *(_OWORD *)pbHash = 0;
  if ( !a3 )
    goto LABEL_44;
  if ( a4 < 0x1C )
    goto LABEL_44;
  if ( *a3 != 1414742347 )
    goto LABEL_44;
  v12 = a3[5];
  v13 = a3[6];
  v14 = a3[4];
  v15 = (unsigned int)a3[3];
  if ( a4 != (_DWORD)v15 + v14 + v13 + v12 || !v13 || !v14 || !v12 )
    goto LABEL_44;
  if ( v12 < 0x18
    || (v16 = (UCHAR *)a3 + v14 + (unsigned int)v15, *(_DWORD *)v16 != 1396982091)
    || v12 != *((_DWORD *)v16 + 4) + *((_DWORD *)v16 + 2) + *((_DWORD *)v16 + 3) + *((_DWORD *)v16 + 5) )
  {
    KeyDigestFromBCryptKey = -2147024809;
    goto LABEL_49;
  }
  v17 = (char *)a3 + v15;
  dwFlags = 2;
  v18 = *((_DWORD *)v16 + 1) == 2;
  pPaddingInfo = &v48;
  if ( !v18 )
    goto LABEL_18;
  if ( v14 < 4 )
  {
    KeyDigestFromBCryptKey = -2146893785;
    goto LABEL_49;
  }
  if ( (HIBYTE(*((unsigned __int16 *)v17 + 1)) | ((unsigned __int8)*((_WORD *)v17 + 1) << 8)) == 1 )
  {
LABEL_18:
    v19 = L"RSA";
  }
  else
  {
    if ( (HIBYTE(*((unsigned __int16 *)v17 + 1)) | ((unsigned __int8)*((_WORD *)v17 + 1) << 8)) != 0x23 )
    {
      KeyDigestFromBCryptKey = -2146893783;
      goto LABEL_49;
    }
    v19 = L"ECDSA";
    pPaddingInfo = 0;
    dwFlags = 0;
  }
  v20 = BCryptOpenAlgorithmProvider(&phAlgorithm, v19, L"Microsoft Primitive Provider", 0);
  KeyDigestFromBCryptKey = SecurityStatusFromNtStatus(v20);
  if ( KeyDigestFromBCryptKey >= 0 )
  {
    KeyDigestFromBCryptKey = TpmAttPubKeyFromIdBinding((unsigned __int8 *)v17, v14, phAlgorithm, &hKey);
    if ( KeyDigestFromBCryptKey < 0 )
      goto LABEL_50;
    if ( *((_DWORD *)v16 + 1) == 1 )
    {
      v21 = ValidatePubKeyFromIdBinding12((unsigned __int8 *)v17, v14);
LABEL_25:
      KeyDigestFromBCryptKey = v21;
      if ( v21 >= 0 )
      {
        v22 = *((unsigned int *)v16 + 2);
        v23 = *((_DWORD *)v16 + 3);
        v24 = *((_DWORD *)v16 + 4);
        v38 = *((_DWORD *)v16 + 5);
        v45 = v22;
        v42 = v24;
        KeyDigestFromBCryptKey = TpmAttiShaHash((wchar_t *)L"SHA1", 0, 0, &v16[v22], v23, pbHash, 0x14u, &v47);
        if ( KeyDigestFromBCryptKey >= 0 )
        {
          v25 = v23 + v22;
          cbSignaturea = v24;
          v11 = hKey;
          v26 = BCryptVerifySignature(hKey, pPaddingInfo, pbHash, 0x14u, &v16[v25], cbSignaturea, dwFlags);
          KeyDigestFromBCryptKey = SecurityStatusFromNtStatus(v26);
          if ( KeyDigestFromBCryptKey >= 0 )
          {
            v27 = &v16[v25 + v42];
            if ( *((_DWORD *)v16 + 1) == 1 )
            {
              v36 = 20;
              KeyDigestFromBCryptKey = ValidateKeyAttest12(&v16[v45], v23, v44, a8, v27, v38, 0, 0, Buf2, 0x14u, &v36);
              if ( KeyDigestFromBCryptKey < 0 )
                goto LABEL_45;
              Activation12 = GenerateActivation12(0, (unsigned __int8 *)v17, v14, v46, a6, 0, 0, 0, 0, 0);
            }
            else
            {
              if ( *((_DWORD *)v16 + 1) != 2 )
              {
                KeyDigestFromBCryptKey = -2144795619;
                goto LABEL_45;
              }
              cbSignature[0] = a8;
              v36 = 32;
              KeyDigestFromBCryptKey = ValidateKeyAttest20(
                                         &v16[v45],
                                         v23,
                                         0,
                                         0,
                                         v44,
                                         *(size_t *)cbSignature,
                                         v27,
                                         v38,
                                         0,
                                         4u,
                                         0,
                                         Buf2,
                                         0x20u,
                                         &v36);
              if ( KeyDigestFromBCryptKey < 0 )
                goto LABEL_45;
              LODWORD(pbSignature) = a6;
              Activation12 = GenerateActivation20(0, (wchar_t *)v17, v14, v46, (size_t)pbSignature, 0, 0, 0, 0, 0);
            }
            KeyDigestFromBCryptKey = Activation12;
            if ( Activation12 >= 0 )
            {
              KeyDigestFromBCryptKey = GetKeyDigestFromBCryptKey(
                                         v49,
                                         *((_DWORD *)v16 + 1),
                                         Buf1,
                                         v29,
                                         (unsigned int *)&Size);
              if ( KeyDigestFromBCryptKey >= 0 )
              {
                if ( (_DWORD)Size == v36 && !memcmp_0(Buf1, Buf2, (unsigned int)Size) )
                {
                  if ( !v50
                    || (KeyDigestFromBCryptKey = TpmAttGetKeyAttestationProperties(v16, v12, v50),
                        KeyDigestFromBCryptKey >= 0) )
                  {
                    KeyDigestFromBCryptKey = 0;
                  }
                  goto LABEL_45;
                }
                goto LABEL_44;
              }
            }
          }
LABEL_45:
          if ( v11 )
            BCryptDestroyKey(v11);
          goto LABEL_47;
        }
      }
LABEL_50:
      v11 = hKey;
      goto LABEL_45;
    }
    if ( *((_DWORD *)v16 + 1) == 2 )
    {
      v21 = ValidatePubKeyFromIdBinding20((unsigned __int8 *)v17, v14);
      goto LABEL_25;
    }
    v11 = hKey;
LABEL_44:
    KeyDigestFromBCryptKey = -2147024809;
    goto LABEL_45;
  }
LABEL_47:
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
LABEL_49:
  v30 = KeyDigestFromBCryptKey;
  KspFunctionLogger::~KspFunctionLogger(v51);
  return v30;
}

```

## disassembly

```asm
0x1800996f0  mov     [rsp-8+arg_0], rbx
0x1800996f5  push    rbp
0x1800996f6  push    rsi
0x1800996f7  push    rdi
0x1800996f8  push    r12
0x1800996fa  push    r13
0x1800996fc  push    r14
0x1800996fe  push    r15
0x180099700  lea     rbp, [rsp-60h]
0x180099705  sub     rsp, 160h
0x18009970c  mov     rax, cs:__security_cookie
0x180099713  xor     rax, rsp
0x180099716  mov     [rbp+90h+var_40], rax
0x18009971a  mov     rax, [rbp+90h+arg_20]
0x180099721  lea     rcx, [rbp+90h+var_B0]; this
0x180099725  mov     [rbp+90h+var_D8], rax
0x180099729  mov     rdi, r8
0x18009972c  mov     rax, [rbp+90h+arg_30]
0x180099733  lea     r8, [rsp+190h+var_120]; int *
0x180099738  mov     [rbp+90h+var_E8], rax
0x18009973c  mov     ebx, r9d
0x18009973f  mov     rax, [rbp+90h+arg_40]
0x180099746  mov     [rbp+90h+var_C0], rdx
0x18009974a  lea     rdx, aTpmverifyclaim; "TpmVerifyClaimAuthorityAndSubject"
0x180099751  mov     [rbp+90h+var_B8], rax
0x180099755  mov     [rsp+190h+var_120], 80004005h
0x18009975d  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180099762  xor     r13d, r13d
0x180099765  xor     eax, eax
0x180099767  mov     [rbp+90h+var_88], eax
0x18009976a  lea     rax, aSha1_0; "SHA1"
0x180099771  mov     [rbp+90h+var_C8], rax
0x180099775  xorps   xmm0, xmm0
0x180099778  mov     [rbp+90h+phAlgorithm], r13
0x18009977c  mov     esi, r13d
0x18009977f  mov     [rbp+90h+hKey], r13
0x180099783  mov     [rsp+190h+var_11C], r13d
0x180099788  mov     dword ptr [rbp+90h+Size], r13d
0x18009978c  movups  xmmword ptr [rbp+90h+pbHash], xmm0
0x180099790  test    rdi, rdi
0x180099793  jz      loc_180099B87
0x180099799  cmp     ebx, 1Ch
0x18009979c  jb      loc_180099B87
0x1800997a2  cmp     dword ptr [rdi], 5453414Bh
0x1800997a8  jnz     loc_180099B87
0x1800997ae  mov     r15d, [rdi+14h]
0x1800997b2  mov     ecx, [rdi+18h]
0x1800997b5  mov     r14d, [rdi+10h]
0x1800997b9  mov     edx, [rdi+0Ch]
0x1800997bc  lea     eax, [rcx+r15]
0x1800997c0  add     eax, r14d
0x1800997c3  add     eax, edx
0x1800997c5  cmp     ebx, eax
0x1800997c7  jnz     loc_180099B87
0x1800997cd  test    ecx, ecx
0x1800997cf  jz      loc_180099B87
0x1800997d5  test    r14d, r14d
0x1800997d8  jz      loc_180099B87
0x1800997de  test    r15d, r15d
0x1800997e1  jz      loc_180099B87
0x1800997e7  cmp     r15d, 18h
0x1800997eb  jb      loc_180099BFE
0x1800997f1  lea     ebx, [r14+rdx]
0x1800997f5  add     rbx, rdi
0x1800997f8  cmp     dword ptr [rbx], 5344414Bh
0x1800997fe  jnz     loc_180099BFE
0x180099804  mov     eax, [rbx+14h]
0x180099807  add     eax, [rbx+0Ch]
0x18009980a  add     eax, [rbx+8]
0x18009980d  add     eax, [rbx+10h]
0x180099810  cmp     r15d, eax
0x180099813  jnz     loc_180099BFE
0x180099819  add     rdi, rdx
0x18009981c  mov     [rsp+190h+var_118], 2
0x180099824  cmp     dword ptr [rbx+4], 2
0x180099828  lea     rsi, [rbp+90h+var_C8]
0x18009982c  mov     [rbp+90h+pPaddingInfo], rsi
0x180099830  jnz     short loc_18009987D
0x180099832  cmp     r14d, 4
0x180099836  jnb     short loc_180099845
0x180099838  mov     [rsp+190h+var_120], 80090027h
0x180099840  jmp     loc_180099BBE
0x180099845  movzx   eax, word ptr [rdi+2]
0x180099849  movzx   ecx, al
0x18009984c  shl     ecx, 8
0x18009984f  shr     eax, 8
0x180099852  or      ecx, eax
0x180099854  sub     ecx, 1
0x180099857  jz      short loc_18009987D
0x180099859  cmp     ecx, 22h ; '"'
0x18009985c  jz      short loc_18009986B
0x18009985e  mov     [rsp+190h+var_120], 80090029h
0x180099866  jmp     loc_180099BBE
0x18009986b  lea     rdx, aEcdsa; "ECDSA"
0x180099872  mov     [rbp+90h+pPaddingInfo], r13
0x180099876  mov     [rsp+190h+var_118], r13d
0x18009987b  jmp     short loc_180099884
0x18009987d  lea     rdx, aRsa; "RSA"
0x180099884  xor     r9d, r9d; dwFlags
0x180099887  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009988e  lea     rcx, [rbp+90h+phAlgorithm]; phAlgorithm
0x180099892  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180099899  nop     dword ptr [rax+rax+00h]
0x18009989e  mov     ecx, eax; Status
0x1800998a0  call    ?SecurityStatusFromNtStatus@@YAJJ@Z; SecurityStatusFromNtStatus(long)
0x1800998a5  mov     [rsp+190h+var_120], eax
0x1800998a9  test    eax, eax
0x1800998ab  js      loc_180099BA3
0x1800998b1  mov     r8, [rbp+90h+phAlgorithm]; hAlgorithm
0x1800998b5  lea     r9, [rbp+90h+hKey]; void **
0x1800998b9  mov     edx, r14d; unsigned int
0x1800998bc  mov     rcx, rdi; unsigned __int8 *
0x1800998bf  call    TpmAttPubKeyFromIdBinding
0x1800998c4  mov     [rsp+190h+var_120], eax
0x1800998c8  test    eax, eax
0x1800998ca  js      loc_180099BF8
0x1800998d0  cmp     dword ptr [rbx+4], 1
0x1800998d4  jnz     short loc_1800998E3
0x1800998d6  mov     edx, r14d; unsigned int
0x1800998d9  mov     rcx, rdi; unsigned __int8 *
0x1800998dc  call    ?ValidatePubKeyFromIdBinding12@@YAJPEAEI@Z; ValidatePubKeyFromIdBinding12(uchar *,uint)
0x1800998e1  jmp     short loc_1800998F8
0x1800998e3  cmp     dword ptr [rbx+4], 2
0x1800998e7  jnz     loc_180099B83
0x1800998ed  mov     edx, r14d; unsigned int
0x1800998f0  mov     rcx, rdi; unsigned __int8 *
0x1800998f3  call    ?ValidatePubKeyFromIdBinding20@@YAJPEAEI@Z; ValidatePubKeyFromIdBinding20(uchar *,uint)
0x1800998f8  mov     [rsp+190h+var_120], eax
0x1800998fc  test    eax, eax
0x1800998fe  js      loc_180099BF8
0x180099904  mov     r13d, [rbx+8]
0x180099908  lea     rdx, [rbp+90h+var_D0]
0x18009990c  mov     ecx, [rbx+14h]
0x18009990f  xor     r8d, r8d; cbSecret
0x180099912  mov     r12d, [rbx+0Ch]
0x180099916  mov     esi, [rbx+10h]
0x180099919  mov     [rsp+190h+var_158], rdx; __int64
0x18009991e  lea     r9, [rbx+r13]; pbInput
0x180099922  mov     [rsp+190h+var_114], ecx
0x180099926  xor     edx, edx; pbSecret
0x180099928  lea     rcx, [rbp+90h+pbHash]
0x18009992c  mov     [rsp+190h+dwFlags], 14h; cbOutput
0x180099934  mov     qword ptr [rsp+190h+cbSignature], rcx; PUCHAR
0x180099939  lea     rcx, aSha1_0; "SHA1"
0x180099940  mov     [rbp+90h+var_E0], r13
0x180099944  mov     [rbp+90h+var_F8], esi
0x180099947  mov     dword ptr [rsp+190h+pbSignature], r12d; cbInput
0x18009994c  call    TpmAttiShaHash
0x180099951  mov     [rsp+190h+var_120], eax
0x180099955  test    eax, eax
0x180099957  js      loc_180099BF5
0x18009995d  mov     ecx, [rsp+190h+var_118]
0x180099961  lea     r8, [rbp+90h+pbHash]; pbHash
0x180099965  mov     rdx, [rbp+90h+pPaddingInfo]; pPaddingInfo
0x180099969  add     r13d, r12d
0x18009996c  mov     [rsp+190h+dwFlags], ecx; dwFlags
0x180099970  mov     r9d, 14h; cbHash
0x180099976  mov     [rsp+190h+cbSignature], esi; cbSignature
0x18009997a  mov     rsi, [rbp+90h+hKey]
0x18009997e  mov     eax, r13d
0x180099981  mov     rcx, rsi; hKey
0x180099984  add     rax, rbx
0x180099987  mov     [rsp+190h+pbSignature], rax; pbSignature
0x18009998c  call    cs:__imp_BCryptVerifySignature
0x180099993  nop     dword ptr [rax+rax+00h]
0x180099998  mov     ecx, eax; Status
0x18009999a  call    ?SecurityStatusFromNtStatus@@YAJJ@Z; SecurityStatusFromNtStatus(long)
0x18009999f  mov     [rsp+190h+var_120], eax
0x1800999a3  test    eax, eax
0x1800999a5  js      loc_180099B7E
0x1800999ab  mov     eax, [rbp+90h+var_F8]
0x1800999ae  add     eax, r13d
0x1800999b1  xor     r13d, r13d
0x1800999b4  add     rax, rbx
0x1800999b7  cmp     dword ptr [rbx+4], 1
0x1800999bb  jnz     loc_180099A57
0x1800999c1  mov     r9d, dword ptr [rbp+90h+arg_38]; unsigned int
0x1800999c8  lea     edx, [r13+14h]
0x1800999cc  mov     r8, [rbp+90h+var_E8]; unsigned __int8 *
0x1800999d0  lea     rcx, [rsp+190h+var_11C]
0x1800999d5  mov     [rsp+190h+var_140], rcx; unsigned int *
0x1800999da  lea     rcx, [rbp+90h+Buf2]
0x1800999de  mov     dword ptr [rsp+190h+var_148], edx; unsigned int
0x1800999e2  mov     qword ptr [rsp+190h+var_150], rcx; unsigned __int8 *
0x1800999e7  mov     ecx, [rsp+190h+var_114]
0x1800999eb  mov     [rsp+190h+var_158], r13; unsigned __int8 *
0x1800999f0  mov     [rsp+190h+dwFlags], r13d; unsigned int
0x1800999f5  mov     [rsp+190h+cbSignature], ecx; unsigned int
0x1800999f9  mov     rcx, [rbp+90h+var_E0]
0x1800999fd  mov     [rsp+190h+var_11C], edx
0x180099a01  add     rcx, rbx; unsigned __int8 *
0x180099a04  mov     edx, r12d; unsigned int
0x180099a07  mov     [rsp+190h+pbSignature], rax; unsigned __int8 *
0x180099a0c  call    ?ValidateKeyAttest12@@YAJPEAEI0I0II00IPEAI@Z; ValidateKeyAttest12(uchar *,uint,uchar *,uint,uchar *,uint,uint,uchar *,uchar *,uint,uint *)
0x180099a11  mov     [rsp+190h+var_120], eax
0x180099a15  test    eax, eax
0x180099a17  js      loc_180099B8F
0x180099a1d  mov     eax, dword ptr [rbp+90h+arg_28]
0x180099a23  mov     r8d, r14d; unsigned int
0x180099a26  mov     r9, [rbp+90h+var_D8]; unsigned __int8 *
0x180099a2a  mov     rdx, rdi; unsigned __int8 *
0x180099a2d  mov     [rsp+190h+var_148], r13; unsigned int *
0x180099a32  xor     ecx, ecx; hObject
0x180099a34  mov     [rsp+190h+var_150], r13d; ULONG
0x180099a39  mov     [rsp+190h+var_158], r13; PUCHAR
0x180099a3e  mov     word ptr [rsp+190h+dwFlags], r13w; unsigned __int16
0x180099a44  mov     qword ptr [rsp+190h+cbSignature], r13; unsigned __int8 *
0x180099a49  mov     dword ptr [rsp+190h+pbSignature], eax; unsigned int
0x180099a4d  call    ?GenerateActivation12@@YAJPEAXPEAEIPEBEI1G1IPEAI@Z; GenerateActivation12(void *,uchar *,uint,uchar const *,uint,uchar *,ushort,uchar *,uint,uint *)
0x180099a52  jmp     loc_180099B08
0x180099a57  cmp     dword ptr [rbx+4], 2
0x180099a5b  jnz     loc_180099B74
0x180099a61  mov     edx, 20h ; ' '
0x180099a66  lea     rcx, [rsp+190h+var_11C]
0x180099a6b  mov     [rsp+190h+var_128], rcx; unsigned int *
0x180099a70  xor     r9d, r9d; unsigned int
0x180099a73  mov     [rsp+190h+var_130], edx; ULONG
0x180099a77  lea     rcx, [rbp+90h+Buf2]
0x180099a7b  mov     [rsp+190h+var_138], rcx; unsigned __int8 *
0x180099a80  xor     r8d, r8d; unsigned __int8 *
0x180099a83  mov     ecx, [rsp+190h+var_114]
0x180099a87  mov     [rsp+190h+var_140], r13; unsigned __int8 *
0x180099a8c  mov     word ptr [rsp+190h+var_148], 4; unsigned __int16
0x180099a93  mov     [rsp+190h+var_150], r13d; unsigned int
0x180099a98  mov     dword ptr [rsp+190h+var_158], ecx; unsigned int
0x180099a9c  mov     rcx, [rbp+90h+var_E0]
0x180099aa0  mov     qword ptr [rsp+190h+dwFlags], rax; unsigned __int8 *
0x180099aa5  add     rcx, rbx; unsigned __int8 *
0x180099aa8  mov     eax, dword ptr [rbp+90h+arg_38]
0x180099aae  mov     [rsp+190h+cbSignature], eax; Size
0x180099ab2  mov     rax, [rbp+90h+var_E8]
0x180099ab6  mov     [rsp+190h+var_11C], edx
0x180099aba  mov     edx, r12d; unsigned int
0x180099abd  mov     [rsp+190h+pbSignature], rax; Buf1
0x180099ac2  call    ?ValidateKeyAttest20@@YAJPEAEI0I0I0IIG00IPEAI@Z; ValidateKeyAttest20(uchar *,uint,uchar *,uint,uchar *,uint,uchar *,uint,uint,ushort,uchar *,uchar *,uint,uint *)
0x180099ac7  mov     [rsp+190h+var_120], eax
0x180099acb  test    eax, eax
0x180099acd  js      loc_180099B8F
0x180099ad3  mov     eax, dword ptr [rbp+90h+arg_28]
0x180099ad9  mov     r8d, r14d; unsigned int
0x180099adc  mov     r9, [rbp+90h+var_D8]; unsigned __int8 *
0x180099ae0  mov     rdx, rdi; unsigned __int8 *
0x180099ae3  mov     [rsp+190h+var_148], r13; unsigned int *
0x180099ae8  xor     ecx, ecx; hObject
0x180099aea  mov     [rsp+190h+var_150], r13d; unsigned int
0x180099aef  mov     [rsp+190h+var_158], r13; unsigned __int8 *
0x180099af4  mov     word ptr [rsp+190h+dwFlags], r13w; unsigned __int16
0x180099afa  mov     qword ptr [rsp+190h+cbSignature], r13; unsigned __int8 *
0x180099aff  mov     dword ptr [rsp+190h+pbSignature], eax; Size
0x180099b03  call    ?GenerateActivation20@@YAJPEAXPEAEIPEBEI1G1IPEAI@Z; GenerateActivation20(void *,uchar *,uint,uchar const *,uint,uchar *,ushort,uchar *,uint,uint *)
0x180099b08  mov     [rsp+190h+var_120], eax
0x180099b0c  test    eax, eax
0x180099b0e  js      short loc_180099B8F
0x180099b10  mov     edx, [rbx+4]; unsigned int
0x180099b13  lea     rax, [rbp+90h+Size]
0x180099b17  mov     rcx, [rbp+90h+var_C0]; hKey
0x180099b1b  lea     r8, [rbp+90h+Buf1]; unsigned __int8 *
0x180099b1f  mov     [rsp+190h+pbSignature], rax; unsigned int *
0x180099b24  call    ?GetKeyDigestFromBCryptKey@@YAJPEAXKPEAEKPEAI@Z; GetKeyDigestFromBCryptKey(void *,ulong,uchar *,ulong,uint *)
0x180099b29  mov     [rsp+190h+var_120], eax
0x180099b2d  test    eax, eax
0x180099b2f  js      short loc_180099B8F
0x180099b31  mov     eax, dword ptr [rbp+90h+Size]
0x180099b34  cmp     eax, [rsp+190h+var_11C]
0x180099b38  jnz     short loc_180099B87
0x180099b3a  mov     r8d, eax; Size
0x180099b3d  lea     rdx, [rbp+90h+Buf2]; Buf2
0x180099b41  lea     rcx, [rbp+90h+Buf1]; Buf1
0x180099b45  call    memcmp_0
0x180099b4a  test    eax, eax
0x180099b4c  jnz     short loc_180099B87
0x180099b4e  mov     rax, [rbp+90h+var_B8]
0x180099b52  test    rax, rax
0x180099b55  jz      short loc_180099B6D
0x180099b57  mov     r8, rax
0x180099b5a  mov     edx, r15d
0x180099b5d  mov     rcx, rbx
0x180099b60  call    TpmAttGetKeyAttestationProperties
0x180099b65  mov     [rsp+190h+var_120], eax
0x180099b69  test    eax, eax
0x180099b6b  js      short loc_180099B8F
0x180099b6d  mov     [rsp+190h+var_120], r13d
0x180099b72  jmp     short loc_180099B8F
0x180099b74  mov     [rsp+190h+var_120], 8029041Dh
0x180099b7c  jmp     short loc_180099B8F
0x180099b7e  xor     r13d, r13d
0x180099b81  jmp     short loc_180099B8F
0x180099b83  mov     rsi, [rbp+90h+hKey]
0x180099b87  mov     [rsp+190h+var_120], 80070057h
0x180099b8f  test    rsi, rsi
0x180099b92  jz      short loc_180099BA3
0x180099b94  mov     rcx, rsi; hKey
0x180099b97  call    cs:__imp_BCryptDestroyKey
0x180099b9e  nop     dword ptr [rax+rax+00h]
0x180099ba3  mov     rcx, [rbp+90h+phAlgorithm]; hAlgorithm
0x180099ba7  test    rcx, rcx
0x180099baa  jz      short loc_180099BBE
0x180099bac  xor     edx, edx; dwFlags
0x180099bae  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180099bb5  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
