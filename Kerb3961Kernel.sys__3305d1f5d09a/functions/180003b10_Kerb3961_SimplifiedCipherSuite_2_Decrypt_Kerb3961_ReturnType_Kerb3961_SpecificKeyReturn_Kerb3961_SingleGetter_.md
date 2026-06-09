# Kerb3961::SimplifiedCipherSuite<2>::Decrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180003b10`
- end: `0x180003dad`
- name: `?Decrypt@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `669`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001580`
- `0x1800015f0`
- `0x180003a38`
- `0x180003a54`
- `0x180003b10`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::Decrypt(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v6; // rdi
  __int64 v8; // r13
  __int64 v9; // r12
  __int64 v10; // rax
  char *v11; // rcx
  __int64 v12; // rcx
  unsigned __int64 v13; // rsi
  int v14; // r8d
  int v15; // r15d
  char *v16; // rcx
  const char *v17; // rdx
  int v18; // r8d
  int v19; // r15d
  char v20; // r9
  unsigned int v21; // r8d
  __int64 v22; // rax
  const char *v23; // rdx
  __int64 v24; // rsi
  const char *v25; // rcx
  char v27[8]; // [rsp+30h] [rbp-99h] BYREF
  __int64 v28; // [rsp+38h] [rbp-91h]
  char *v29; // [rsp+40h] [rbp-89h]
  unsigned __int64 v30; // [rsp+50h] [rbp-79h] BYREF
  __int64 v31; // [rsp+58h] [rbp-71h]
  unsigned __int64 v32; // [rsp+60h] [rbp-69h] BYREF
  const char *v33; // [rsp+68h] [rbp-61h]
  char *v34; // [rsp+70h] [rbp-59h]
  char v35[8]; // [rsp+78h] [rbp-51h] BYREF
  _QWORD v36[2]; // [rsp+80h] [rbp-49h] BYREF
  char v37[16]; // [rsp+90h] [rbp-39h] BYREF
  char v38[16]; // [rsp+A0h] [rbp-29h] BYREF
  _BYTE v39[16]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-9h]
  __int64 v41; // [rsp+C8h] [rbp-1h]

  v6 = a2;
  if ( (_QWORD *)*a3 != a1 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"specificKey.algorithm == this",
      (const char *)a2);
LABEL_3:
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = -1073741811;
    return v6;
  }
  if ( *a6 )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"Must implement decryption with tag before it can be used",
      (const unsigned __int16 *)a2);
  v8 = a3[1];
  v9 = a1[12];
  v10 = *(_QWORD *)(a4 + 8);
  v36[0] = v9;
  v36[1] = v10;
  if ( !*(_QWORD *)(v8 + 24) && !*(_QWORD *)(v8 + 48) )
  {
    v11 = "key->Ke.length > 0 || key->Ki.length > 0";
LABEL_8:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v11, (const char *)a2);
    goto LABEL_3;
  }
  v12 = a1[10];
  if ( *a5 < (unsigned __int64)(v12 + v9) )
  {
    v11 = "cipherText.length >= m_hmacSize + m_cipherBlockSize";
    goto LABEL_8;
  }
  v13 = *a5 - v12;
  a2 = v13 % a1[11];
  if ( a2 )
  {
    v11 = "encryptSize % m_messageBlockSize == 0";
    goto LABEL_8;
  }
  v31 = v12;
  v30 = v13;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v39);
  Kerb3961::CopyBuffer((__int64)v27, (__int64)v39);
  v15 = (int)v29;
  if ( (int)v29 < 0 )
  {
    v16 = "decrypted";
LABEL_15:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v16, (const char *)(unsigned int)v15, v14);
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = v15;
    goto LABEL_34;
  }
  v15 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, char *, __int64, _QWORD *, char *))(*a1 + 440LL))(
                     a1,
                     v35,
                     v8 + 24,
                     v36,
                     v27);
  if ( v15 < 0 )
  {
    v16 = "BlockDecrypt(key->Ke, IV, decrypted)";
    goto LABEL_15;
  }
  (*(void (__fastcall **)(_QWORD *, unsigned __int64 *, __int64, char *))(*a1 + 424LL))(a1, &v32, v8 + 48, v27);
  v19 = (int)v34;
  if ( (int)v34 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v34, v18);
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = v19;
    goto LABEL_32;
  }
  if ( v32 != v40 )
    goto LABEL_31;
  if ( v32 )
  {
    if ( v32 > 0xFFFFFFFF )
      goto LABEL_31;
    v17 = v33;
    v20 = 0;
    v21 = 0;
    do
    {
      v22 = v21++;
      v20 |= v33[v22] ^ *(_BYTE *)(v22 + v41);
    }
    while ( v21 < (unsigned int)v32 );
    if ( v20 )
    {
LABEL_31:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"SecureEqualBuffer(hmac, checksum)", v17);
      *(_QWORD *)v6 = 0;
      *(_QWORD *)(v6 + 8) = 0;
      *(_DWORD *)(v6 + 16) = -2146893041;
LABEL_32:
      v25 = v33;
      if ( !v33 )
        goto LABEL_34;
      goto LABEL_33;
    }
  }
  v23 = v33;
  v24 = v13 - v9;
  if ( v24 )
  {
    v30 = a1[12];
    v31 = v24;
    Kerb3961::Split<2>(v37, v27, &v30);
    Kerb3961::CopyBuffer(v6, (__int64)v38);
    goto LABEL_32;
  }
  *(_QWORD *)v6 = 0;
  *(_QWORD *)(v6 + 8) = 0;
  *(_DWORD *)(v6 + 16) = 0;
  if ( !v23 )
    goto LABEL_34;
  v25 = v23;
LABEL_33:
  Kerb3961Free(v25);
LABEL_34:
  if ( v28 )
    Kerb3961Free(v28);
  return v6;
}

```

## disassembly

```asm
0x180003b10  mov     [rsp-8+arg_18], rbx
0x180003b15  push    rbp
0x180003b16  push    rsi
0x180003b17  push    rdi
0x180003b18  push    r12
0x180003b1a  push    r13
0x180003b1c  push    r14
0x180003b1e  push    r15
0x180003b20  lea     rbp, [rsp-17h]
0x180003b25  sub     rsp, 0E0h
0x180003b2c  mov     rax, cs:__security_cookie
0x180003b33  xor     rax, rsp
0x180003b36  mov     [rbp+47h+var_40], rax
0x180003b3a  mov     rdi, rdx
0x180003b3d  mov     r10, [rbp+47h+arg_20]
0x180003b41  mov     r14, rcx
0x180003b44  cmp     [r8], rcx
0x180003b47  jz      short loc_180003B6A
0x180003b49  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x180003b50  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180003b55  xor     ebx, ebx
0x180003b57  mov     [rdi], rbx
0x180003b5a  mov     [rdi+8], rbx
0x180003b5e  mov     dword ptr [rdi+10h], 0C000000Dh
0x180003b65  jmp     loc_180003D75
0x180003b6a  mov     rax, [rbp+47h+arg_28]
0x180003b6e  xor     ebx, ebx
0x180003b70  cmp     [rax], rbx
0x180003b73  jnz     loc_180003DA0
0x180003b79  mov     r13, [r8+8]
0x180003b7d  mov     r12, [rcx+60h]
0x180003b81  mov     rax, [r9+8]
0x180003b85  mov     [rbp+47h+var_90], r12
0x180003b89  mov     [rbp+47h+var_88], rax
0x180003b8d  cmp     [r13+18h], rbx
0x180003b91  ja      short loc_180003BA7
0x180003b93  cmp     [r13+30h], rbx
0x180003b97  ja      short loc_180003BA7
0x180003b99  lea     rcx, aKeyKeLength0Ke_0; "key->Ke.length > 0 || key->Ki.length > "...
0x180003ba0  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180003ba5  jmp     short loc_180003B57
0x180003ba7  mov     rcx, [rcx+50h]
0x180003bab  mov     rsi, [r10]
0x180003bae  lea     rax, [rcx+r12]
0x180003bb2  cmp     rsi, rax
0x180003bb5  jnb     short loc_180003BC0
0x180003bb7  lea     rcx, aCiphertextLeng; "cipherText.length >= m_hmacSize + m_cip"...
0x180003bbe  jmp     short loc_180003BA0
0x180003bc0  sub     rsi, rcx
0x180003bc3  xor     edx, edx
0x180003bc5  mov     rax, rsi
0x180003bc8  div     qword ptr [r14+58h]
0x180003bcc  test    rdx, rdx
0x180003bcf  jz      short loc_180003BDA
0x180003bd1  lea     rcx, aEncryptsizeMMe; "encryptSize % m_messageBlockSize == 0"
0x180003bd8  jmp     short loc_180003BA0
0x180003bda  mov     [rbp+47h+var_B8], rcx
0x180003bde  lea     r8, [rbp+47h+var_C0]
0x180003be2  lea     rcx, [rbp+47h+var_60]; this
0x180003be6  mov     [rbp+47h+var_C0], rsi
0x180003bea  mov     rdx, r10
0x180003bed  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x180003bf2  lea     rdx, [rbp+47h+var_60]
0x180003bf6  lea     rcx, [rsp+110h+var_E0]
0x180003bfb  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180003c00  mov     r15d, dword ptr [rsp+110h+var_D0]
0x180003c05  test    r15d, r15d
0x180003c08  jns     short loc_180003C29
0x180003c0a  lea     rcx, aDecrypted; "decrypted"
0x180003c11  mov     edx, r15d; char *
0x180003c14  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180003c19  mov     [rdi], rbx
0x180003c1c  mov     [rdi+8], rbx
0x180003c20  mov     [rdi+10h], r15d
0x180003c24  jmp     loc_180003D66
0x180003c29  mov     rax, [r14]
0x180003c2c  lea     rcx, [rsp+110h+var_E0]
0x180003c31  mov     [rsp+110h+var_F0], rcx
0x180003c36  lea     r9, [rbp+47h+var_90]
0x180003c3a  lea     r8, [r13+18h]
0x180003c3e  mov     rcx, r14
0x180003c41  lea     rdx, [rbp+47h+var_98]
0x180003c45  mov     rax, [rax+1B8h]
0x180003c4c  call    _guard_dispatch_icall
0x180003c51  mov     r15d, [rax]
0x180003c54  test    r15d, r15d
0x180003c57  jns     short loc_180003C62
0x180003c59  lea     rcx, aBlockdecryptKe_0; "BlockDecrypt(key->Ke, IV, decrypted)"
0x180003c60  jmp     short loc_180003C11
0x180003c62  mov     rax, [r14]
0x180003c65  lea     r8, [r13+30h]
0x180003c69  lea     r9, [rsp+110h+var_E0]
0x180003c6e  mov     rcx, r14
0x180003c71  lea     rdx, [rbp+47h+var_B0]
0x180003c75  mov     rax, [rax+1A8h]
0x180003c7c  call    _guard_dispatch_icall
0x180003c81  mov     r15d, dword ptr [rbp+47h+var_A0]
0x180003c85  test    r15d, r15d
0x180003c88  jns     short loc_180003CA9
0x180003c8a  mov     edx, r15d; char *
0x180003c8d  lea     rcx, aHmac; "hmac"
0x180003c94  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180003c99  mov     [rdi], rbx
0x180003c9c  mov     [rdi+8], rbx
0x180003ca0  mov     [rdi+10h], r15d
0x180003ca4  jmp     loc_180003D58
0x180003ca9  mov     rax, [rbp+47h+var_B0]
0x180003cad  cmp     rax, [rbp+47h+var_50]
0x180003cb1  jnz     loc_180003D3E
0x180003cb7  test    rax, rax
0x180003cba  jz      short loc_180003CF5
0x180003cbc  mov     ecx, 0FFFFFFFFh
0x180003cc1  cmp     rax, rcx
0x180003cc4  ja      short loc_180003D3E
0x180003cc6  mov     rdx, [rbp+47h+var_A8]
0x180003cca  mov     r9b, bl
0x180003ccd  mov     r10, [rbp+47h+var_48]
0x180003cd1  mov     r8d, ebx
0x180003cd4  test    eax, eax
0x180003cd6  jz      short loc_180003CF9
0x180003cd8  mov     eax, r8d
0x180003cdb  inc     r8d
0x180003cde  mov     cl, [rax+r10]
0x180003ce2  mov     al, [rax+rdx]
0x180003ce5  xor     cl, al
0x180003ce7  or      r9b, cl
0x180003cea  cmp     r8d, dword ptr [rbp+47h+var_B0]
0x180003cee  jb      short loc_180003CD8
0x180003cf0  test    r9b, r9b
0x180003cf3  jnz     short loc_180003D3E
0x180003cf5  mov     rdx, [rbp+47h+var_A8]
0x180003cf9  sub     rsi, r12
0x180003cfc  jnz     short loc_180003D12
0x180003cfe  mov     [rdi], rbx
0x180003d01  mov     [rdi+8], rbx
0x180003d05  mov     [rdi+10h], ebx
0x180003d08  test    rdx, rdx
0x180003d0b  jz      short loc_180003D66
0x180003d0d  mov     rcx, rdx
0x180003d10  jmp     short loc_180003D61
0x180003d12  mov     rax, [r14+60h]
0x180003d16  lea     r8, [rbp+47h+var_C0]
0x180003d1a  lea     rdx, [rsp+110h+var_E0]
0x180003d1f  mov     [rbp+47h+var_C0], rax
0x180003d23  lea     rcx, [rbp+47h+var_80]
0x180003d27  mov     [rbp+47h+var_B8], rsi
0x180003d2b  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180003d30  lea     rdx, [rbp+47h+var_70]
0x180003d34  mov     rcx, rdi
0x180003d37  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180003d3c  jmp     short loc_180003D58
0x180003d3e  lea     rcx, aSecureequalbuf_3; "SecureEqualBuffer(hmac, checksum)"
0x180003d45  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180003d4a  mov     [rdi], rbx
0x180003d4d  mov     [rdi+8], rbx
0x180003d51  mov     dword ptr [rdi+10h], 8009030Fh
0x180003d58  mov     rcx, [rbp+47h+var_A8]
0x180003d5c  test    rcx, rcx
0x180003d5f  jz      short loc_180003D66
0x180003d61  call    Kerb3961Free
0x180003d66  mov     rcx, [rsp+110h+var_D8]
0x180003d6b  test    rcx, rcx
0x180003d6e  jz      short loc_180003D75
0x180003d70  call    Kerb3961Free
0x180003d75  mov     rax, rdi
0x180003d78  mov     rcx, [rbp+47h+var_40]
0x180003d7c  xor     rcx, rsp; StackCookie
0x180003d7f  call    __security_check_cookie
0x180003d84  mov     rbx, [rsp+110h+arg_18]
0x180003d8c  add     rsp, 0E0h
0x180003d93  pop     r15
0x180003d95  pop     r14
0x180003d97  pop     r13
0x180003d99  pop     r12
0x180003d9b  pop     rdi
0x180003d9c  pop     rsi
0x180003d9d  pop     rbp
0x180003d9e  retn
0x180003da0  lea     rcx, aMustImplementD; "Must implement decryption with tag befo"...
0x180003da7  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
