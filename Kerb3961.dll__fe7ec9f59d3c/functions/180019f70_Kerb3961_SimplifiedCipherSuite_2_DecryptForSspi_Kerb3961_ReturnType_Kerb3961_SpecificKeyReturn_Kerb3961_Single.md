# Kerb3961::SimplifiedCipherSuite<2>::DecryptForSspi(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,unsigned __int64)

- ea: `0x180019f70`
- end: `0x18001a345`
- name: `?DecryptForSspi@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@_K@Z`
- size: `981`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x180004750`
- `0x1800047e4`
- `0x180006ee0`
- `0x18000700c`
- `0x18000712c`
- `0x180019f70`
- `0x18001e010`

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
  void *v13; // r9
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
  _BYTE *v25; // rsi
  int v26; // r15d
  int v27; // r8d
  int v28; // r14d
  void *v29; // rcx
  __int64 v30; // rax
  char v31; // r8
  __int64 v32; // rax
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  void *v35; // [rsp+38h] [rbp-C8h]
  char *v36; // [rsp+40h] [rbp-C0h]
  char v37[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v38; // [rsp+58h] [rbp-A8h]
  char *v39; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  void *v41; // [rsp+70h] [rbp-90h]
  char *v42; // [rsp+78h] [rbp-88h]
  char v43[32]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v44[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v45[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *v46; // [rsp+B8h] [rbp-48h]
  _BYTE v47[16]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-28h]
  __int64 v49; // [rsp+E0h] [rbp-20h]
  _BYTE v50[16]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v51[16]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v52[16]; // [rsp+108h] [rbp+8h] BYREF

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
  v44[0] = v10;
  v44[1] = v11;
  if ( !*(_QWORD *)(v9 + 24) && !*(_QWORD *)(v9 + 48) )
  {
    v12 = "key->Ke.length > 0 || key->Ki.length > 0";
LABEL_7:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v12, (const char *)a2);
    goto LABEL_3;
  }
  v13 = (void *)a1[10];
  if ( *a5 < (unsigned __int64)v13 + v10 )
  {
    v12 = "cipherText.length >= m_hmacSize + m_cipherBlockSize";
    goto LABEL_7;
  }
  v14 = *a5 - (_QWORD)v13;
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
  v34 = *a5 - (_QWORD)v13;
  v35 = v13;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v47);
  Kerb3961::CopyBuffer((__int64)v37, (__int64)v47);
  v17 = (int)v39;
  if ( (int)v39 >= 0 )
  {
    v17 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, char *, __int64, _QWORD *, char *))(*a1 + 440LL))(
                       a1,
                       v43,
                       v9 + 24,
                       v44,
                       v37);
    if ( v17 < 0 )
    {
      v18 = "BlockDecrypt(key->Ke, IV, decrypted)";
      goto LABEL_16;
    }
    v34 = a1[12];
    v36 = a7;
    v35 = (void *)(v15 - (_QWORD)a7);
    Kerb3961::Split<3>(v50, v37, &v34);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a6 + 32LL))(a6) )
      __int2c();
    (*(void (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)a6 + 24LL))(a6, &v40, v51);
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
    if ( v40 )
    {
      Kerb3961::Concatenate(&v34, v50, &v40, v52);
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
      v30 = (*(__int64 (__fastcall **)(_QWORD *, char *, __int64, __int64 *))(*a1 + 424LL))(a1, v45, v9 + 48, &v34);
      v24 = *(_QWORD *)v30;
      v25 = *(_BYTE **)(v30 + 8);
      v26 = *(_DWORD *)(v30 + 16);
      *(_QWORD *)v30 = 0;
      *(_QWORD *)(v30 + 8) = 0;
      *(_DWORD *)(v30 + 16) = -1073741823;
      if ( v46 )
        operator delete(v46, 0);
    }
    else
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, __int64, char *))(*a1 + 424LL))(a1, &v34, v9 + 48, v37);
      v24 = *(_QWORD *)v21;
      v25 = *(_BYTE **)(v21 + 8);
      v26 = *(_DWORD *)(v21 + 16);
      *(_QWORD *)v21 = 0;
      *(_QWORD *)(v21 + 8) = 0;
      *(_DWORD *)(v21 + 16) = -1073741823;
    }
    if ( v35 )
      operator delete(v35, 0);
    if ( v26 >= 0 )
    {
      if ( v24 != v48 )
        goto LABEL_43;
      if ( !v24 )
        goto LABEL_40;
      if ( v24 > 0xFFFFFFFF )
        goto LABEL_43;
      v31 = 0;
      LODWORD(v22) = 0;
      do
      {
        v32 = (unsigned int)v22;
        v22 = (const char *)(unsigned int)((_DWORD)v22 + 1);
        v31 |= v25[v32] ^ *(_BYTE *)(v49 + v32);
      }
      while ( (unsigned int)v22 < (unsigned int)v24 );
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
          Kerb3961::Concatenate(v7, v51, v52);
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
    operator delete(v29, 0);
LABEL_47:
    if ( v41 )
      operator delete(v41, 0);
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
    operator delete(v38, 0);
  return v7;
}

```

## disassembly

```asm
0x180019f70  mov     [rsp-8+arg_18], rbx
0x180019f75  push    rbp
0x180019f76  push    rsi
0x180019f77  push    rdi
0x180019f78  push    r12
0x180019f7a  push    r13
0x180019f7c  push    r14
0x180019f7e  push    r15
0x180019f80  lea     rbp, [rsp-20h]
0x180019f85  sub     rsp, 120h
0x180019f8c  mov     rax, cs:__security_cookie
0x180019f93  xor     rax, rsp
0x180019f96  mov     [rbp+50h+var_38], rax
0x180019f9a  mov     rdi, rdx
0x180019f9d  mov     r10, [rbp+50h+arg_20]
0x180019fa4  mov     rsi, rcx
0x180019fa7  mov     r15, [rbp+50h+arg_28]
0x180019fae  cmp     [r8], rcx
0x180019fb1  jz      short loc_180019FD4
0x180019fb3  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x180019fba  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180019fbf  xor     ebx, ebx
0x180019fc1  mov     [rdi], rbx
0x180019fc4  mov     [rdi+8], rbx
0x180019fc8  mov     dword ptr [rdi+10h], 0C000000Dh
0x180019fcf  jmp     loc_18001A31B
0x180019fd4  mov     r13, [r8+8]
0x180019fd8  xor     ebx, ebx
0x180019fda  mov     r8, [rcx+60h]
0x180019fde  mov     rax, [r9+8]
0x180019fe2  mov     [rbp+50h+var_B0], r8
0x180019fe6  mov     [rbp+50h+var_A8], rax
0x180019fea  cmp     [r13+18h], rbx
0x180019fee  ja      short loc_18001A004
0x180019ff0  cmp     [r13+30h], rbx
0x180019ff4  ja      short loc_18001A004
0x180019ff6  lea     rcx, aKeyKeLength0Ke_0; "key->Ke.length > 0 || key->Ki.length > "...
0x180019ffd  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001a002  jmp     short loc_180019FC1
0x18001a004  mov     r9, [rcx+50h]
0x18001a008  mov     rcx, [r10]
0x18001a00b  lea     rax, [r9+r8]
0x18001a00f  cmp     rcx, rax
0x18001a012  jnb     short loc_18001A01D
0x18001a014  lea     rcx, aCiphertextLeng; "cipherText.length >= m_hmacSize + m_cip"...
0x18001a01b  jmp     short loc_180019FFD
0x18001a01d  sub     rcx, r9
0x18001a020  xor     edx, edx
0x18001a022  mov     rax, rcx
0x18001a025  div     qword ptr [rsi+58h]
0x18001a029  test    rdx, rdx
0x18001a02c  jz      short loc_18001A037
0x18001a02e  lea     rcx, aEncryptsizeMMe; "encryptSize % m_messageBlockSize == 0"
0x18001a035  jmp     short loc_180019FFD
0x18001a037  mov     r12, rcx
0x18001a03a  sub     r12, r8
0x18001a03d  cmp     r12, [rbp+50h+arg_30]
0x18001a044  jnb     short loc_18001A04F
0x18001a046  lea     rcx, aDecryptsizeTra; "decryptSize >= trailerSize"
0x18001a04d  jmp     short loc_180019FFD
0x18001a04f  mov     [rsp+150h+var_120], rcx
0x18001a054  lea     r8, [rsp+150h+var_120]
0x18001a059  lea     rcx, [rbp+50h+var_88]; this
0x18001a05d  mov     [rsp+150h+var_118], r9
0x18001a062  mov     rdx, r10
0x18001a065  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x18001a06a  lea     rdx, [rbp+50h+var_88]
0x18001a06e  lea     rcx, [rsp+150h+var_100]
0x18001a073  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x18001a078  mov     r14d, dword ptr [rsp+150h+var_F0]
0x18001a07d  test    r14d, r14d
0x18001a080  jns     short loc_18001A0A1
0x18001a082  lea     rcx, aDecrypted; "decrypted"
0x18001a089  mov     edx, r14d; char *
0x18001a08c  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a091  mov     [rdi], rbx
0x18001a094  mov     [rdi+8], rbx
0x18001a098  mov     [rdi+10h], r14d
0x18001a09c  jmp     loc_18001A30A
0x18001a0a1  mov     rax, [rsi]
0x18001a0a4  lea     rcx, [rsp+150h+var_100]
0x18001a0a9  mov     [rsp+150h+var_130], rcx
0x18001a0ae  lea     r9, [rbp+50h+var_B0]
0x18001a0b2  lea     r8, [r13+18h]
0x18001a0b6  mov     rcx, rsi
0x18001a0b9  lea     rdx, [rbp+50h+var_D0]
0x18001a0bd  mov     rax, [rax+1B8h]
0x18001a0c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0c9  mov     r14d, [rax]
0x18001a0cc  test    r14d, r14d
0x18001a0cf  jns     short loc_18001A0DA
0x18001a0d1  lea     rcx, aBlockdecryptKe_0; "BlockDecrypt(key->Ke, IV, decrypted)"
0x18001a0d8  jmp     short loc_18001A089
0x18001a0da  mov     rax, [rsi+60h]
0x18001a0de  lea     r8, [rsp+150h+var_120]
0x18001a0e3  mov     rcx, [rbp+50h+arg_30]
0x18001a0ea  lea     rdx, [rsp+150h+var_100]
0x18001a0ef  mov     [rsp+150h+var_120], rax
0x18001a0f4  mov     rax, r12
0x18001a0f7  sub     rax, rcx
0x18001a0fa  mov     [rsp+150h+var_110], rcx
0x18001a0ff  lea     rcx, [rbp+50h+var_68]
0x18001a103  mov     [rsp+150h+var_118], rax
0x18001a108  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x18001a10d  mov     rax, [r15]
0x18001a110  mov     rcx, r15
0x18001a113  mov     rax, [rax+20h]
0x18001a117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a11c  test    al, al
0x18001a11e  jnz     short loc_18001A122
0x18001a120  int     2Ch; Windows NT - assertion failure
0x18001a122  mov     rax, [r15]
0x18001a125  lea     r8, [rbp+50h+var_58]
0x18001a129  lea     rdx, [rsp+150h+var_E8]
0x18001a12e  mov     rcx, r15
0x18001a131  mov     rax, [rax+18h]
0x18001a135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a13a  mov     r14d, dword ptr [rsp+150h+var_D8]
0x18001a13f  test    r14d, r14d
0x18001a142  jns     short loc_18001A163
0x18001a144  mov     edx, r14d; char *
0x18001a147  lea     rcx, aChecksumdata; "checksumData"
0x18001a14e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a153  mov     [rdi], rbx
0x18001a156  mov     [rdi+8], rbx
0x18001a15a  mov     [rdi+10h], r14d
0x18001a15e  jmp     loc_18001A2F9
0x18001a163  cmp     [rsp+150h+var_E8], rbx
0x18001a168  jnz     short loc_18001A1A8
0x18001a16a  mov     rax, [rsi]
0x18001a16d  lea     r8, [r13+30h]
0x18001a171  lea     r9, [rsp+150h+var_100]
0x18001a176  mov     rcx, rsi
0x18001a179  lea     rdx, [rsp+150h+var_120]
0x18001a17e  mov     rax, [rax+1A8h]
0x18001a185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a18a  mov     r14, [rax]
0x18001a18d  mov     rsi, [rax+8]
0x18001a191  mov     r15d, [rax+10h]
0x18001a195  mov     [rax], rbx
0x18001a198  mov     [rax+8], rbx
0x18001a19c  mov     dword ptr [rax+10h], 0C0000001h
0x18001a1a3  jmp     loc_18001A23E
0x18001a1a8  lea     r9, [rbp+50h+var_48]
0x18001a1ac  lea     r8, [rsp+150h+var_E8]
0x18001a1b1  lea     rdx, [rbp+50h+var_68]
0x18001a1b5  lea     rcx, [rsp+150h+var_120]
0x18001a1ba  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18001a1bf  mov     r14d, dword ptr [rsp+150h+var_110]
0x18001a1c4  test    r14d, r14d
0x18001a1c7  jns     short loc_18001A1F6
0x18001a1c9  mov     edx, r14d; char *
0x18001a1cc  lea     rcx, aTotalchecksumi; "totalChecksumInput"
0x18001a1d3  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a1d8  mov     rcx, [rsp+150h+var_118]
0x18001a1dd  mov     [rdi], rbx
0x18001a1e0  mov     [rdi+8], rbx
0x18001a1e4  mov     [rdi+10h], r14d
0x18001a1e8  test    rcx, rcx
0x18001a1eb  jz      loc_18001A2F9
0x18001a1f1  jmp     loc_18001A2F2
0x18001a1f6  mov     rax, [rsi]
0x18001a1f9  lea     r8, [r13+30h]
0x18001a1fd  lea     r9, [rsp+150h+var_120]
0x18001a202  mov     rcx, rsi
0x18001a205  lea     rdx, [rbp+50h+var_A0]
0x18001a209  mov     rax, [rax+1A8h]
0x18001a210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a215  mov     r14, [rax]
0x18001a218  mov     rsi, [rax+8]
0x18001a21c  mov     r15d, [rax+10h]
0x18001a220  mov     [rax], rbx
0x18001a223  mov     [rax+8], rbx
0x18001a227  mov     dword ptr [rax+10h], 0C0000001h
0x18001a22e  mov     rcx, [rbp+50h+var_98]; void *
0x18001a232  test    rcx, rcx
0x18001a235  jz      short loc_18001A23E
0x18001a237  xor     edx, edx; struct std::nothrow_t *
0x18001a239  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a23e  mov     rcx, [rsp+150h+var_118]; void *
0x18001a243  test    rcx, rcx
0x18001a246  jz      short loc_18001A24F
0x18001a248  xor     edx, edx; struct std::nothrow_t *
0x18001a24a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a24f  test    r15d, r15d
0x18001a252  jns     short loc_18001A270
0x18001a254  mov     edx, r15d; char *
0x18001a257  lea     rcx, aHmac; "hmac"
0x18001a25e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a263  mov     [rdi], rbx
0x18001a266  mov     [rdi+8], rbx
0x18001a26a  mov     [rdi+10h], r15d
0x18001a26e  jmp     short loc_18001A2EA
0x18001a270  cmp     r14, [rbp+50h+var_78]
0x18001a274  jnz     short loc_18001A2D0
0x18001a276  test    r14, r14
0x18001a279  jz      short loc_18001A2AD
0x18001a27b  mov     eax, 0FFFFFFFFh
0x18001a280  cmp     r14, rax
0x18001a283  ja      short loc_18001A2D0
0x18001a285  mov     r9, [rbp+50h+var_70]
0x18001a289  mov     r8b, bl
0x18001a28c  mov     edx, ebx
0x18001a28e  test    r14d, r14d
0x18001a291  jz      short loc_18001A2AD
0x18001a293  mov     eax, edx
0x18001a295  inc     edx
0x18001a297  mov     cl, [r9+rax]
0x18001a29b  mov     al, [rsi+rax]
0x18001a29e  xor     cl, al
0x18001a2a0  or      r8b, cl
0x18001a2a3  cmp     edx, r14d
0x18001a2a6  jb      short loc_18001A293
0x18001a2a8  test    r8b, r8b
0x18001a2ab  jnz     short loc_18001A2D0
0x18001a2ad  test    r12, r12
0x18001a2b0  jnz     short loc_18001A2BE
0x18001a2b2  mov     [rdi], rbx
0x18001a2b5  mov     [rdi+8], rbx
0x18001a2b9  mov     [rdi+10h], ebx
0x18001a2bc  jmp     short loc_18001A2EA
0x18001a2be  lea     r8, [rbp+50h+var_48]
0x18001a2c2  mov     rcx, rdi
0x18001a2c5  lea     rdx, [rbp+50h+var_58]
0x18001a2c9  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18001a2ce  jmp     short loc_18001A2EA
0x18001a2d0  lea     rcx, aSecureequalbuf_3; "SecureEqualBuffer(hmac, checksum)"
0x18001a2d7  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001a2dc  mov     [rdi], rbx
0x18001a2df  mov     [rdi+8], rbx
0x18001a2e3  mov     dword ptr [rdi+10h], 8009030Fh
0x18001a2ea  test    rsi, rsi
0x18001a2ed  jz      short loc_18001A2F9
0x18001a2ef  mov     rcx, rsi; void *
0x18001a2f2  xor     edx, edx; struct std::nothrow_t *
0x18001a2f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a2f9  mov     rcx, [rsp+150h+var_E0]; void *
0x18001a2fe  test    rcx, rcx
0x18001a301  jz      short loc_18001A30A
0x18001a303  xor     edx, edx; struct std::nothrow_t *
0x18001a305  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a30a  mov     rcx, [rsp+150h+var_F8]; void *
0x18001a30f  test    rcx, rcx
0x18001a312  jz      short loc_18001A31B
0x18001a314  xor     edx, edx; struct std::nothrow_t *
0x18001a316  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a31b  mov     rax, rdi
0x18001a31e  mov     rcx, [rbp+50h+var_38]
0x18001a322  xor     rcx, rsp; StackCookie
0x18001a325  call    __security_check_cookie
0x18001a32a  mov     rbx, [rsp+150h+arg_18]
0x18001a332  add     rsp, 120h
0x18001a339  pop     r15
0x18001a33b  pop     r14
0x18001a33d  pop     r13
0x18001a33f  pop     r12
0x18001a341  pop     rdi
0x18001a342  pop     rsi
0x18001a343  pop     rbp
0x18001a344  retn
```
