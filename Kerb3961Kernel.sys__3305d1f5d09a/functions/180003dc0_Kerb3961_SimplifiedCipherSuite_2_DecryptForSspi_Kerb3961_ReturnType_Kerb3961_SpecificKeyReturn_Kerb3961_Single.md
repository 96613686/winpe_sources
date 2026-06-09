# Kerb3961::SimplifiedCipherSuite<2>::DecryptForSspi(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,unsigned __int64)

- ea: `0x180003dc0`
- end: `0x180004198`
- name: `?DecryptForSspi@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@_K@Z`
- size: `984`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800015f0`
- `0x180001684`
- `0x1800037e0`
- `0x180003910`
- `0x180003a54`
- `0x180003dc0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`

## pseudocode

```c
const char *__fastcall Kerb3961::SimplifiedCipherSuite<2>::DecryptForSspi(
        _QWORD *a1,
        unsigned __int64 a2,
        _QWORD *a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        char *a7)
{
  const char *v7; // rdi
  __int64 v9; // r13
  __int64 v10; // r8
  __int64 v11; // rax
  char *v12; // rcx
  __int64 v13; // r9
  unsigned __int64 v14; // rcx
  __int64 v15; // r12
  int v16; // r8d
  int v17; // r14d
  char *v18; // rcx
  int v19; // r8d
  int v20; // r14d
  __int64 v21; // rax
  const char *v22; // rdx
  int v23; // r8d
  unsigned __int64 v24; // r14
  __int64 v25; // rsi
  int v26; // r15d
  int v27; // r8d
  int v28; // r14d
  __int64 v29; // rcx
  __int64 v30; // rax
  char v31; // r8
  __int64 v32; // rax
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h]
  char *v36; // [rsp+40h] [rbp-C0h]
  char v37[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h]
  char *v39; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h]
  char *v42; // [rsp+78h] [rbp-88h]
  unsigned __int64 v43; // [rsp+80h] [rbp-80h]
  char v44[8]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v45[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v46[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-48h]
  _BYTE v48[16]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-28h]
  __int64 v50; // [rsp+E0h] [rbp-20h]
  _BYTE v51[16]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v52[16]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v53[16]; // [rsp+108h] [rbp+8h] BYREF

  v7 = (const char *)a2;
  if ( (_QWORD *)*a3 != a1 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"specificKey.algorithm == this",
      (const char *)a2);
LABEL_3:
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
    *((_DWORD *)v7 + 4) = -1073741811;
    return v7;
  }
  v9 = a3[1];
  v10 = a1[12];
  v11 = *(_QWORD *)(a4 + 8);
  v45[0] = v10;
  v45[1] = v11;
  if ( !*(_QWORD *)(v9 + 24) && !*(_QWORD *)(v9 + 48) )
  {
    v12 = "key->Ke.length > 0 || key->Ki.length > 0";
LABEL_7:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v12, (const char *)a2);
    goto LABEL_3;
  }
  v13 = a1[10];
  if ( *a5 < (unsigned __int64)(v13 + v10) )
  {
    v12 = "cipherText.length >= m_hmacSize + m_cipherBlockSize";
    goto LABEL_7;
  }
  v14 = *a5 - v13;
  a2 = v14 % a1[11];
  if ( a2 )
  {
    v12 = "encryptSize % m_messageBlockSize == 0";
    goto LABEL_7;
  }
  v15 = v14 - v10;
  if ( v14 - v10 < (unsigned __int64)a7 )
  {
    v12 = "decryptSize >= trailerSize";
    goto LABEL_7;
  }
  v34 = *a5 - v13;
  v35 = v13;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v48);
  Kerb3961::CopyBuffer((__int64)v37, (__int64)v48);
  v17 = (int)v39;
  if ( (int)v39 >= 0 )
  {
    v17 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, char *, __int64, _QWORD *, char *))(*a1 + 440LL))(
                       a1,
                       v44,
                       v9 + 24,
                       v45,
                       v37);
    if ( v17 < 0 )
    {
      v18 = "BlockDecrypt(key->Ke, IV, decrypted)";
      goto LABEL_16;
    }
    v34 = a1[12];
    v36 = a7;
    v35 = v15 - (_QWORD)a7;
    Kerb3961::Split<3>(v51, v37, &v34);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a6 + 32LL))(a6) )
      __int2c();
    (*(void (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)a6 + 24LL))(a6, &v40, v52);
    v20 = (int)v42;
    if ( (int)v42 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"checksumData",
        (const char *)(unsigned int)v42,
        v19);
      *(_QWORD *)v7 = 0;
      *((_QWORD *)v7 + 1) = 0;
      *((_DWORD *)v7 + 4) = v20;
      goto LABEL_47;
    }
    v43 = 0;
    if ( v40 )
    {
      Kerb3961::Concatenate(&v34, v51, &v40, v53);
      v28 = (int)v36;
      if ( (int)v36 < 0 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"totalChecksumInput",
          (const char *)(unsigned int)v36,
          v27);
        v29 = v35;
        *(_QWORD *)v7 = 0;
        *((_QWORD *)v7 + 1) = 0;
        *((_DWORD *)v7 + 4) = v28;
        if ( !v29 )
          goto LABEL_47;
        goto LABEL_46;
      }
      v30 = (*(__int64 (__fastcall **)(_QWORD *, char *, __int64, __int64 *))(*a1 + 424LL))(a1, v46, v9 + 48, &v34);
      v24 = *(_QWORD *)v30;
      v25 = *(_QWORD *)(v30 + 8);
      v26 = *(_DWORD *)(v30 + 16);
      *(_QWORD *)v30 = 0;
      *(_QWORD *)(v30 + 8) = 0;
      *(_DWORD *)(v30 + 16) = -1073741823;
      v43 = v24;
      if ( v47 )
        Kerb3961Free(v47);
    }
    else
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, __int64, char *))(*a1 + 424LL))(a1, &v34, v9 + 48, v37);
      v24 = *(_QWORD *)v21;
      v25 = *(_QWORD *)(v21 + 8);
      v26 = *(_DWORD *)(v21 + 16);
      v43 = *(_QWORD *)v21;
      *(_QWORD *)v21 = 0;
      *(_QWORD *)(v21 + 8) = 0;
      *(_DWORD *)(v21 + 16) = -1073741823;
    }
    if ( v35 )
      Kerb3961Free(v35);
    if ( v26 >= 0 )
    {
      if ( v24 != v49 )
        goto LABEL_43;
      if ( !v24 )
        goto LABEL_40;
      if ( v24 > 0xFFFFFFFF )
        goto LABEL_43;
      v31 = 0;
      LODWORD(v22) = 0;
      if ( !(_DWORD)v43 )
        goto LABEL_40;
      do
      {
        v32 = (unsigned int)v22;
        v22 = (const char *)(unsigned int)((_DWORD)v22 + 1);
        v31 |= *(_BYTE *)(v25 + v32) ^ *(_BYTE *)(v50 + v32);
      }
      while ( (unsigned int)v22 < (unsigned int)v43 );
      if ( v31 )
      {
LABEL_43:
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"SecureEqualBuffer(hmac, checksum)",
          v22);
        *(_QWORD *)v7 = 0;
        *((_QWORD *)v7 + 1) = 0;
        *((_DWORD *)v7 + 4) = -2146893041;
      }
      else
      {
LABEL_40:
        if ( v15 )
        {
          Kerb3961::Concatenate(v7, v52, v53);
        }
        else
        {
          *(_QWORD *)v7 = 0;
          *((_QWORD *)v7 + 1) = 0;
          *((_DWORD *)v7 + 4) = 0;
        }
      }
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v26, v23);
      *(_QWORD *)v7 = 0;
      *((_QWORD *)v7 + 1) = 0;
      *((_DWORD *)v7 + 4) = v26;
    }
    if ( !v25 )
      goto LABEL_47;
    v29 = v25;
LABEL_46:
    Kerb3961Free(v29);
LABEL_47:
    if ( v41 )
      Kerb3961Free(v41);
    goto LABEL_49;
  }
  v18 = "decrypted";
LABEL_16:
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v18, (const char *)(unsigned int)v17, v16);
  *(_QWORD *)v7 = 0;
  *((_QWORD *)v7 + 1) = 0;
  *((_DWORD *)v7 + 4) = v17;
LABEL_49:
  if ( v38 )
    Kerb3961Free(v38);
  return v7;
}

```

## disassembly

```asm
0x180003dc0  mov     [rsp-8+arg_18], rbx
0x180003dc5  push    rbp
0x180003dc6  push    rsi
0x180003dc7  push    rdi
0x180003dc8  push    r12
0x180003dca  push    r13
0x180003dcc  push    r14
0x180003dce  push    r15
0x180003dd0  lea     rbp, [rsp-20h]
0x180003dd5  sub     rsp, 120h
0x180003ddc  mov     rax, cs:__security_cookie
0x180003de3  xor     rax, rsp
0x180003de6  mov     [rbp+50h+var_38], rax
0x180003dea  mov     rdi, rdx
0x180003ded  mov     r10, [rbp+50h+arg_20]
0x180003df4  mov     rsi, rcx
0x180003df7  mov     r15, [rbp+50h+arg_28]
0x180003dfe  cmp     [r8], rcx
0x180003e01  jz      short loc_180003E24
0x180003e03  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x180003e0a  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180003e0f  xor     ebx, ebx
0x180003e11  mov     [rdi], rbx
0x180003e14  mov     [rdi+8], rbx
0x180003e18  mov     dword ptr [rdi+10h], 0C000000Dh
0x180003e1f  jmp     loc_18000416D
0x180003e24  mov     r13, [r8+8]
0x180003e28  xor     ebx, ebx
0x180003e2a  mov     r8, [rcx+60h]
0x180003e2e  mov     rax, [r9+8]
0x180003e32  mov     [rbp+50h+var_B0], r8
0x180003e36  mov     [rbp+50h+var_A8], rax
0x180003e3a  cmp     [r13+18h], rbx
0x180003e3e  ja      short loc_180003E54
0x180003e40  cmp     [r13+30h], rbx
0x180003e44  ja      short loc_180003E54
0x180003e46  lea     rcx, aKeyKeLength0Ke_0; "key->Ke.length > 0 || key->Ki.length > "...
0x180003e4d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180003e52  jmp     short loc_180003E11
0x180003e54  mov     r9, [rcx+50h]
0x180003e58  mov     rcx, [r10]
0x180003e5b  lea     rax, [r9+r8]
0x180003e5f  cmp     rcx, rax
0x180003e62  jnb     short loc_180003E6D
0x180003e64  lea     rcx, aCiphertextLeng; "cipherText.length >= m_hmacSize + m_cip"...
0x180003e6b  jmp     short loc_180003E4D
0x180003e6d  sub     rcx, r9
0x180003e70  xor     edx, edx
0x180003e72  mov     rax, rcx
0x180003e75  div     qword ptr [rsi+58h]
0x180003e79  test    rdx, rdx
0x180003e7c  jz      short loc_180003E87
0x180003e7e  lea     rcx, aEncryptsizeMMe; "encryptSize % m_messageBlockSize == 0"
0x180003e85  jmp     short loc_180003E4D
0x180003e87  mov     r12, rcx
0x180003e8a  sub     r12, r8
0x180003e8d  cmp     r12, [rbp+50h+arg_30]
0x180003e94  jnb     short loc_180003E9F
0x180003e96  lea     rcx, aDecryptsizeTra; "decryptSize >= trailerSize"
0x180003e9d  jmp     short loc_180003E4D
0x180003e9f  mov     [rsp+150h+var_120], rcx
0x180003ea4  lea     r8, [rsp+150h+var_120]
0x180003ea9  lea     rcx, [rbp+50h+var_88]; this
0x180003ead  mov     [rsp+150h+var_118], r9
0x180003eb2  mov     rdx, r10
0x180003eb5  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x180003eba  lea     rdx, [rbp+50h+var_88]
0x180003ebe  lea     rcx, [rsp+150h+var_100]
0x180003ec3  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180003ec8  mov     r14d, dword ptr [rsp+150h+var_F0]
0x180003ecd  test    r14d, r14d
0x180003ed0  jns     short loc_180003EF1
0x180003ed2  lea     rcx, aDecrypted; "decrypted"
0x180003ed9  mov     edx, r14d; char *
0x180003edc  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180003ee1  mov     [rdi], rbx
0x180003ee4  mov     [rdi+8], rbx
0x180003ee8  mov     [rdi+10h], r14d
0x180003eec  jmp     loc_18000415E
0x180003ef1  mov     rax, [rsi]
0x180003ef4  lea     rcx, [rsp+150h+var_100]
0x180003ef9  mov     [rsp+150h+var_130], rcx
0x180003efe  lea     r9, [rbp+50h+var_B0]
0x180003f02  lea     r8, [r13+18h]
0x180003f06  mov     rcx, rsi
0x180003f09  lea     rdx, [rbp+50h+var_B8]
0x180003f0d  mov     rax, [rax+1B8h]
0x180003f14  call    _guard_dispatch_icall
0x180003f19  mov     r14d, [rax]
0x180003f1c  test    r14d, r14d
0x180003f1f  jns     short loc_180003F2A
0x180003f21  lea     rcx, aBlockdecryptKe_0; "BlockDecrypt(key->Ke, IV, decrypted)"
0x180003f28  jmp     short loc_180003ED9
0x180003f2a  mov     rax, [rsi+60h]
0x180003f2e  lea     r8, [rsp+150h+var_120]
0x180003f33  mov     rcx, [rbp+50h+arg_30]
0x180003f3a  lea     rdx, [rsp+150h+var_100]
0x180003f3f  mov     [rsp+150h+var_120], rax
0x180003f44  mov     rax, r12
0x180003f47  sub     rax, rcx
0x180003f4a  mov     [rsp+150h+var_110], rcx
0x180003f4f  lea     rcx, [rbp+50h+var_68]
0x180003f53  mov     [rsp+150h+var_118], rax
0x180003f58  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x180003f5d  mov     rax, [r15]
0x180003f60  mov     rcx, r15
0x180003f63  mov     rax, [rax+20h]
0x180003f67  call    _guard_dispatch_icall
0x180003f6c  test    al, al
0x180003f6e  jnz     short loc_180003F72
0x180003f70  int     2Ch; Windows NT - assertion failure
0x180003f72  mov     rax, [r15]
0x180003f75  lea     r8, [rbp+50h+var_58]
0x180003f79  lea     rdx, [rsp+150h+var_E8]
0x180003f7e  mov     rcx, r15
0x180003f81  mov     rax, [rax+18h]
0x180003f85  call    _guard_dispatch_icall
0x180003f8a  mov     r14d, dword ptr [rsp+150h+var_D8]
0x180003f8f  test    r14d, r14d
0x180003f92  jns     short loc_180003FB3
0x180003f94  mov     edx, r14d; char *
0x180003f97  lea     rcx, aChecksumdata; "checksumData"
0x180003f9e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180003fa3  mov     [rdi], rbx
0x180003fa6  mov     [rdi+8], rbx
0x180003faa  mov     [rdi+10h], r14d
0x180003fae  jmp     loc_18000414F
0x180003fb3  mov     [rbp+50h+var_D0], rbx
0x180003fb7  cmp     [rsp+150h+var_E8], rbx
0x180003fbc  jnz     short loc_180004000
0x180003fbe  mov     rax, [rsi]
0x180003fc1  lea     r8, [r13+30h]
0x180003fc5  lea     r9, [rsp+150h+var_100]
0x180003fca  mov     rcx, rsi
0x180003fcd  lea     rdx, [rsp+150h+var_120]
0x180003fd2  mov     rax, [rax+1A8h]
0x180003fd9  call    _guard_dispatch_icall
0x180003fde  mov     r14, [rax]
0x180003fe1  mov     rsi, [rax+8]
0x180003fe5  mov     r15d, [rax+10h]
0x180003fe9  mov     [rbp+50h+var_D0], r14
0x180003fed  mov     [rax], rbx
0x180003ff0  mov     [rax+8], rbx
0x180003ff4  mov     dword ptr [rax+10h], 0C0000001h
0x180003ffb  jmp     loc_180004098
0x180004000  lea     r9, [rbp+50h+var_48]
0x180004004  lea     r8, [rsp+150h+var_E8]
0x180004009  lea     rdx, [rbp+50h+var_68]
0x18000400d  lea     rcx, [rsp+150h+var_120]
0x180004012  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180004017  mov     r14d, dword ptr [rsp+150h+var_110]
0x18000401c  test    r14d, r14d
0x18000401f  jns     short loc_18000404E
0x180004021  mov     edx, r14d; char *
0x180004024  lea     rcx, aTotalchecksumi; "totalChecksumInput"
0x18000402b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180004030  mov     rcx, [rsp+150h+var_118]
0x180004035  mov     [rdi], rbx
0x180004038  mov     [rdi+8], rbx
0x18000403c  mov     [rdi+10h], r14d
0x180004040  test    rcx, rcx
0x180004043  jz      loc_18000414F
0x180004049  jmp     loc_18000414A
0x18000404e  mov     rax, [rsi]
0x180004051  lea     r8, [r13+30h]
0x180004055  lea     r9, [rsp+150h+var_120]
0x18000405a  mov     rcx, rsi
0x18000405d  lea     rdx, [rbp+50h+var_A0]
0x180004061  mov     rax, [rax+1A8h]
0x180004068  call    _guard_dispatch_icall
0x18000406d  mov     r14, [rax]
0x180004070  mov     rsi, [rax+8]
0x180004074  mov     r15d, [rax+10h]
0x180004078  mov     [rax], rbx
0x18000407b  mov     [rax+8], rbx
0x18000407f  mov     dword ptr [rax+10h], 0C0000001h
0x180004086  mov     rcx, [rbp+50h+var_98]
0x18000408a  mov     [rbp+50h+var_D0], r14
0x18000408e  test    rcx, rcx
0x180004091  jz      short loc_180004098
0x180004093  call    Kerb3961Free
0x180004098  mov     rcx, [rsp+150h+var_118]
0x18000409d  test    rcx, rcx
0x1800040a0  jz      short loc_1800040A7
0x1800040a2  call    Kerb3961Free
0x1800040a7  test    r15d, r15d
0x1800040aa  jns     short loc_1800040C8
0x1800040ac  mov     edx, r15d; char *
0x1800040af  lea     rcx, aHmac; "hmac"
0x1800040b6  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800040bb  mov     [rdi], rbx
0x1800040be  mov     [rdi+8], rbx
0x1800040c2  mov     [rdi+10h], r15d
0x1800040c6  jmp     short loc_180004142
0x1800040c8  cmp     r14, [rbp+50h+var_78]
0x1800040cc  jnz     short loc_180004128
0x1800040ce  test    r14, r14
0x1800040d1  jz      short loc_180004105
0x1800040d3  mov     eax, 0FFFFFFFFh
0x1800040d8  cmp     r14, rax
0x1800040db  ja      short loc_180004128
0x1800040dd  mov     r8b, bl
0x1800040e0  mov     r9, [rbp+50h+var_70]
0x1800040e4  mov     edx, ebx
0x1800040e6  cmp     dword ptr [rbp+50h+var_D0], ebx
0x1800040e9  jbe     short loc_180004105
0x1800040eb  mov     eax, edx
0x1800040ed  inc     edx
0x1800040ef  mov     cl, [r9+rax]
0x1800040f3  mov     al, [rsi+rax]
0x1800040f6  xor     cl, al
0x1800040f8  or      r8b, cl
0x1800040fb  cmp     edx, dword ptr [rbp+50h+var_D0]
0x1800040fe  jb      short loc_1800040EB
0x180004100  test    r8b, r8b
0x180004103  jnz     short loc_180004128
0x180004105  test    r12, r12
0x180004108  jnz     short loc_180004116
0x18000410a  mov     [rdi], rbx
0x18000410d  mov     [rdi+8], rbx
0x180004111  mov     [rdi+10h], ebx
0x180004114  jmp     short loc_180004142
0x180004116  lea     r8, [rbp+50h+var_48]
0x18000411a  mov     rcx, rdi
0x18000411d  lea     rdx, [rbp+50h+var_58]
0x180004121  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180004126  jmp     short loc_180004142
0x180004128  lea     rcx, aSecureequalbuf_3; "SecureEqualBuffer(hmac, checksum)"
0x18000412f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004134  mov     [rdi], rbx
0x180004137  mov     [rdi+8], rbx
0x18000413b  mov     dword ptr [rdi+10h], 8009030Fh
0x180004142  test    rsi, rsi
0x180004145  jz      short loc_18000414F
0x180004147  mov     rcx, rsi
0x18000414a  call    Kerb3961Free
0x18000414f  mov     rcx, [rsp+150h+var_E0]
0x180004154  test    rcx, rcx
0x180004157  jz      short loc_18000415E
0x180004159  call    Kerb3961Free
0x18000415e  mov     rcx, [rsp+150h+var_F8]
0x180004163  test    rcx, rcx
0x180004166  jz      short loc_18000416D
0x180004168  call    Kerb3961Free
0x18000416d  mov     rax, rdi
0x180004170  mov     rcx, [rbp+50h+var_38]
0x180004174  xor     rcx, rsp; StackCookie
0x180004177  call    __security_check_cookie
0x18000417c  mov     rbx, [rsp+150h+arg_18]
0x180004184  add     rsp, 120h
0x18000418b  pop     r15
0x18000418d  pop     r14
0x18000418f  pop     r13
0x180004191  pop     r12
0x180004193  pop     rdi
0x180004194  pop     rsi
0x180004195  pop     rbp
0x180004196  retn
```
