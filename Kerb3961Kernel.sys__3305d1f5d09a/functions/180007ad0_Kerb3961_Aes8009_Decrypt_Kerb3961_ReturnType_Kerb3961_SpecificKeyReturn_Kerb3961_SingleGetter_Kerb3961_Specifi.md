# Kerb3961::Aes8009::Decrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180007ad0`
- end: `0x180007e96`
- name: `?Decrypt@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `966`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001580`
- `0x1800015f0`
- `0x180005b1c`
- `0x180007ad0`
- `0x180007e9c`
- `0x180009c48`
- `0x18000a6c0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::Decrypt(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5, _QWORD *a6)
{
  __int64 v7; // rax
  size_t v9; // r13
  int v10; // r8d
  int v11; // r12d
  __int64 *v12; // r8
  __int64 v13; // rbx
  int v14; // r8d
  void *v15; // rcx
  int v16; // eax
  int v17; // ebx
  unsigned __int64 v18; // r8
  int v19; // ebx
  const char *v20; // rcx
  const char *v21; // rdx
  const char *v22; // r15
  char v23; // r9
  __int64 v24; // rax
  int v25; // r8d
  int v26; // ebx
  void *v27; // rbx
  void *v28; // rcx
  __int64 v30; // [rsp+30h] [rbp-B9h] BYREF
  const char *v31; // [rsp+38h] [rbp-B1h]
  char *v32; // [rsp+40h] [rbp-A9h]
  const char *v33; // [rsp+50h] [rbp-99h] BYREF
  __int64 v34; // [rsp+58h] [rbp-91h] BYREF
  void *v35; // [rsp+60h] [rbp-89h]
  char *v36; // [rsp+68h] [rbp-81h]
  char v37[8]; // [rsp+70h] [rbp-79h] BYREF
  void *v38; // [rsp+78h] [rbp-71h]
  char *v39; // [rsp+80h] [rbp-69h]
  __int64 v40; // [rsp+88h] [rbp-61h]
  char v41[8]; // [rsp+90h] [rbp-59h] BYREF
  __int64 v42; // [rsp+98h] [rbp-51h]
  void *v43; // [rsp+A8h] [rbp-41h]
  char v44[8]; // [rsp+B0h] [rbp-39h] BYREF
  _OWORD *v45; // [rsp+B8h] [rbp-31h]
  _QWORD v46[2]; // [rsp+C0h] [rbp-29h] BYREF
  char v47[8]; // [rsp+D0h] [rbp-19h] BYREF
  void *Src; // [rsp+D8h] [rbp-11h]
  const char *v49; // [rsp+E0h] [rbp-9h]
  __int64 v50; // [rsp+E8h] [rbp-1h]

  v7 = *(_QWORD *)(a1 + 88);
  if ( *a5 < (unsigned __int64)(v7 + 16) )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"cipherText.length >= m_micLength + AES_BLOCK_SIZE",
      (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
    return a2;
  }
  v9 = *a5 - v7;
  v40 = *(_QWORD *)(a3 + 8);
  v33 = *(const char **)(a4 + 8);
  Kerb3961::MakeBuffer(v37);
  v11 = (int)v39;
  if ( (int)v39 >= 0 )
  {
    Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v47);
    v30 = 16;
    v31 = (const char *)v9;
    Kerb3961::Split<2>(v44, v37, &v30);
    *v45 = *(_OWORD *)v33;
    memmove((void *)v46[1], Src, v9);
    v12 = (__int64 *)(v40 + 48);
    v34 = 0;
    v35 = 0;
    LODWORD(v36) = -1073741823;
    if ( *a6 )
    {
      v30 = 3;
      v31 = "tag";
      v13 = Kerb3961::Aes8009::DeriveKey(a1, (unsigned int)v41, (_DWORD)v12, (unsigned int)&v30, (__int64)a6, *v12);
      if ( v35 )
        Kerb3961Free(v35);
      v34 = *(_QWORD *)v13;
      v15 = *(void **)(v13 + 8);
      *(_QWORD *)v13 = 0;
      v35 = v15;
      v16 = *(_DWORD *)(v13 + 16);
      *(_QWORD *)(v13 + 8) = 0;
      LODWORD(v36) = v16;
      *(_DWORD *)(v13 + 16) = -1073741823;
      if ( v42 )
        Kerb3961Free(v42);
      v17 = (int)v36;
      if ( (int)v36 < 0 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"derivedIntegrityKey",
          (const char *)(unsigned int)v36,
          v14);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v17;
        goto LABEL_34;
      }
      v12 = &v34;
    }
    Kerb3961::GetHmac(
      (unsigned int)&v30,
      *(_QWORD *)(a1 + 152),
      (_DWORD)v12,
      (unsigned int)v37,
      *(unsigned int *)(a1 + 160));
    v19 = (int)v32;
    if ( (int)v32 >= 0 )
    {
      v21 = *(const char **)(a1 + 88);
      v22 = v31;
      if ( v21 != v49 )
        goto LABEL_30;
      if ( !v21 )
        goto LABEL_22;
      if ( (unsigned __int64)v21 > 0xFFFFFFFF )
        goto LABEL_30;
      v23 = 0;
      LODWORD(v18) = 0;
      do
      {
        v24 = (unsigned int)v18;
        v18 = (unsigned int)(v18 + 1);
        v23 |= v31[v24] ^ *(_BYTE *)(v24 + v50);
      }
      while ( (unsigned int)v18 < (unsigned int)v21 );
      if ( v23 )
      {
LABEL_30:
        Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"SecureEqualBuffer(hmac, MIC)", v21);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -2146893041;
      }
      else
      {
LABEL_22:
        v31 = v33;
        v30 = 16;
        if ( v46[0] >= 0x10u )
        {
          Kerb3961::DecryptCTS(
            (NTSTATUS *)&v33,
            *(char **)(a1 + 144),
            (void *)v18,
            (_QWORD *)(v40 + 24),
            &v30,
            (unsigned int *)v46);
          v26 = (int)v33;
        }
        else
        {
          Kerb3961::Logging::Verify::ConditionFailed(
            (Kerb3961::Logging::Verify *)"cipherText.length >= AES_BLOCK_SIZE",
            v21);
          v26 = -1073741789;
        }
        if ( v26 >= 0 )
        {
          v30 = 16;
          v31 = (const char *)(v9 - 16);
          Kerb3961::Split<2>(v41, v46, &v30);
          v27 = v38;
          memmove(v38, v43, v9 - 16);
          *(_DWORD *)(a2 + 16) = v11;
          *(_QWORD *)a2 = v9 - 16;
          *(_QWORD *)(a2 + 8) = v27;
          if ( v22 )
            Kerb3961Free(v22);
          v28 = v35;
          goto LABEL_37;
        }
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"BlockDecrypt(key->Ke, {AES_BLOCK_SIZE, IV}, ciphertextHMAC)",
          (const char *)(unsigned int)v26,
          v25);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v26;
      }
      if ( !v22 )
        goto LABEL_34;
      v20 = v22;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v32, v18);
      v20 = v31;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v19;
      if ( !v20 )
        goto LABEL_34;
    }
    Kerb3961Free(v20);
LABEL_34:
    if ( v35 )
      Kerb3961Free(v35);
    goto LABEL_36;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"hmacBuffer",
    (const char *)(unsigned int)v39,
    v10);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v11;
LABEL_36:
  v28 = v38;
LABEL_37:
  if ( v28 )
    Kerb3961Free(v28);
  return a2;
}

```

## disassembly

```asm
0x180007ad0  mov     [rsp-8+arg_18], rbx
0x180007ad5  push    rbp
0x180007ad6  push    rsi
0x180007ad7  push    rdi
0x180007ad8  push    r12
0x180007ada  push    r13
0x180007adc  push    r14
0x180007ade  push    r15
0x180007ae0  lea     rbp, [rsp-17h]
0x180007ae5  sub     rsp, 100h
0x180007aec  mov     rax, cs:__security_cookie
0x180007af3  xor     rax, rsp
0x180007af6  mov     [rbp+47h+var_40], rax
0x180007afa  mov     rbx, [rbp+47h+arg_20]
0x180007afe  mov     rdi, rcx
0x180007b01  mov     rax, [rcx+58h]
0x180007b05  mov     r14, rdx
0x180007b08  mov     r15, [rbp+47h+arg_28]
0x180007b0c  mov     r13, [rbx]
0x180007b0f  lea     rcx, [rax+10h]
0x180007b13  cmp     r13, rcx
0x180007b16  jnb     short loc_180007B3A
0x180007b18  lea     rcx, aCiphertextLeng_2; "cipherText.length >= m_micLength + AES_"...
0x180007b1f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007b24  xor     esi, esi
0x180007b26  mov     [r14], rsi
0x180007b29  mov     [r14+8], rsi
0x180007b2d  mov     dword ptr [r14+10h], 0C000000Dh
0x180007b35  jmp     loc_180007E6B
0x180007b3a  sub     r13, rax
0x180007b3d  lea     rcx, [rbp+47h+var_C0]
0x180007b41  mov     rax, [r8+8]
0x180007b45  mov     [rbp+47h+var_A8], rax
0x180007b49  mov     rax, [r9+8]
0x180007b4d  lea     rdx, [r13+10h]
0x180007b51  mov     [rsp+130h+var_E0], rax
0x180007b56  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180007b5b  mov     r12, [rbp+47h+var_B0]
0x180007b5f  xor     esi, esi
0x180007b61  test    r12d, r12d
0x180007b64  jns     short loc_180007B85
0x180007b66  mov     edx, r12d; char *
0x180007b69  lea     rcx, aHmacbuffer; "hmacBuffer"
0x180007b70  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007b75  mov     [r14], rsi
0x180007b78  mov     [r14+8], rsi
0x180007b7c  mov     [r14+10h], r12d
0x180007b80  jmp     loc_180007E5D
0x180007b85  mov     rax, [rdi+58h]
0x180007b89  lea     r8, [rsp+130h+var_100]
0x180007b8e  mov     rdx, rbx
0x180007b91  mov     [rsp+130h+var_F8], rax
0x180007b96  lea     rcx, [rbp+47h+var_60]; this
0x180007b9a  mov     [rsp+130h+var_100], r13
0x180007b9f  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x180007ba4  lea     r8, [rsp+130h+var_100]
0x180007ba9  mov     [rsp+130h+var_100], 10h
0x180007bb2  lea     rdx, [rbp+47h+var_C0]
0x180007bb6  mov     [rsp+130h+var_F8], r13
0x180007bbb  lea     rcx, [rbp+47h+var_80]
0x180007bbf  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180007bc4  mov     rax, [rsp+130h+var_E0]
0x180007bc9  mov     r8, r13; Size
0x180007bcc  movups  xmm0, xmmword ptr [rax]
0x180007bcf  mov     rax, [rbp+47h+var_78]
0x180007bd3  movdqu  xmmword ptr [rax], xmm0
0x180007bd7  mov     rdx, [rbp+47h+Src]; Src
0x180007bdb  mov     rcx, [rbp+47h+var_68]; void *
0x180007bdf  call    memmove
0x180007be4  mov     r8, [rbp+47h+var_A8]
0x180007be8  add     r8, 30h ; '0'
0x180007bec  mov     [rsp+130h+var_D8], rsi
0x180007bf1  mov     [rsp+130h+var_D0], rsi
0x180007bf6  mov     dword ptr [rsp+130h+var_C8], 0C0000001h
0x180007bfe  cmp     [r15], rsi
0x180007c01  jz      loc_180007CAB
0x180007c07  lea     rax, aTag; "tag"
0x180007c0e  mov     [rsp+130h+var_100], 3
0x180007c17  mov     [rsp+130h+var_F8], rax
0x180007c1c  lea     r9, [rsp+130h+var_100]
0x180007c21  mov     rax, [r8]
0x180007c24  lea     rdx, [rbp+47h+var_A0]
0x180007c28  mov     [rsp+130h+var_108], rax
0x180007c2d  mov     rcx, rdi
0x180007c30  mov     [rsp+130h+var_110], r15
0x180007c35  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z; Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180007c3a  mov     rcx, [rsp+130h+var_D0]
0x180007c3f  mov     rbx, rax
0x180007c42  test    rcx, rcx
0x180007c45  jz      short loc_180007C4C
0x180007c47  call    Kerb3961Free
0x180007c4c  mov     rcx, [rbx]
0x180007c4f  mov     [rsp+130h+var_D8], rcx
0x180007c54  mov     rcx, [rbx+8]
0x180007c58  mov     [rbx], rsi
0x180007c5b  mov     [rsp+130h+var_D0], rcx
0x180007c60  mov     eax, [rbx+10h]
0x180007c63  mov     [rbx+8], rsi
0x180007c67  mov     dword ptr [rsp+130h+var_C8], eax
0x180007c6b  mov     dword ptr [rbx+10h], 0C0000001h
0x180007c72  mov     rcx, [rbp+47h+var_98]
0x180007c76  test    rcx, rcx
0x180007c79  jz      short loc_180007C80
0x180007c7b  call    Kerb3961Free
0x180007c80  mov     ebx, dword ptr [rsp+130h+var_C8]
0x180007c84  test    ebx, ebx
0x180007c86  jns     short loc_180007CA6
0x180007c88  mov     edx, ebx; char *
0x180007c8a  lea     rcx, aDerivedintegri; "derivedIntegrityKey"
0x180007c91  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007c96  mov     [r14], rsi
0x180007c99  mov     [r14+8], rsi
0x180007c9d  mov     [r14+10h], ebx
0x180007ca1  jmp     loc_180007E4E
0x180007ca6  lea     r8, [rsp+130h+var_D8]
0x180007cab  mov     eax, [rdi+0A0h]
0x180007cb1  lea     r9, [rbp+47h+var_C0]
0x180007cb5  mov     rdx, [rdi+98h]
0x180007cbc  lea     rcx, [rsp+130h+var_100]
0x180007cc1  mov     [rsp+130h+var_110], rax
0x180007cc6  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180007ccb  mov     ebx, dword ptr [rsp+130h+var_F0]
0x180007ccf  test    ebx, ebx
0x180007cd1  jns     short loc_180007CFF
0x180007cd3  mov     edx, ebx; char *
0x180007cd5  lea     rcx, aHmac; "hmac"
0x180007cdc  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007ce1  mov     rcx, [rsp+130h+var_F8]
0x180007ce6  mov     [r14], rsi
0x180007ce9  mov     [r14+8], rsi
0x180007ced  mov     [r14+10h], ebx
0x180007cf1  test    rcx, rcx
0x180007cf4  jz      loc_180007E4E
0x180007cfa  jmp     loc_180007E49
0x180007cff  mov     rdx, [rdi+58h]; char *
0x180007d03  mov     r15, [rsp+130h+var_F8]
0x180007d08  cmp     rdx, [rbp+47h+var_50]
0x180007d0c  jnz     loc_180007E26
0x180007d12  test    rdx, rdx
0x180007d15  jz      short loc_180007D54
0x180007d17  mov     eax, 0FFFFFFFFh
0x180007d1c  cmp     rdx, rax
0x180007d1f  ja      loc_180007E26
0x180007d25  mov     r10, [rbp+47h+var_48]
0x180007d29  mov     r9b, sil
0x180007d2c  mov     r8d, esi
0x180007d2f  test    edx, edx
0x180007d31  jz      short loc_180007D54
0x180007d33  mov     eax, r8d
0x180007d36  inc     r8d
0x180007d39  mov     cl, [rax+r10]
0x180007d3d  mov     al, [rax+r15]
0x180007d41  xor     cl, al
0x180007d43  or      r9b, cl
0x180007d46  cmp     r8d, edx
0x180007d49  jb      short loc_180007D33
0x180007d4b  test    r9b, r9b
0x180007d4e  jnz     loc_180007E26
0x180007d54  cmp     [rbp+47h+var_70], 10h
0x180007d59  mov     rax, [rsp+130h+var_E0]
0x180007d5e  mov     [rsp+130h+var_F8], rax
0x180007d63  mov     [rsp+130h+var_100], 10h
0x180007d6c  jnb     short loc_180007D81
0x180007d6e  lea     rcx, aCiphertextLeng_1; "cipherText.length >= AES_BLOCK_SIZE"
0x180007d75  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007d7a  mov     ebx, 0C0000023h
0x180007d7f  jmp     short loc_180007DB1
0x180007d81  mov     r9, [rbp+47h+var_A8]
0x180007d85  lea     rax, [rbp+47h+var_70]
0x180007d89  mov     rdx, [rdi+90h]
0x180007d90  lea     rcx, [rsp+130h+var_E0]
0x180007d95  mov     [rsp+130h+var_108], rax
0x180007d9a  add     r9, 18h
0x180007d9e  lea     rax, [rsp+130h+var_100]
0x180007da3  mov     [rsp+130h+var_110], rax
0x180007da8  call    ?DecryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::DecryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x180007dad  mov     ebx, dword ptr [rsp+130h+var_E0]
0x180007db1  test    ebx, ebx
0x180007db3  jns     short loc_180007DD0
0x180007db5  mov     edx, ebx; char *
0x180007db7  lea     rcx, aBlockdecryptKe; "BlockDecrypt(key->Ke, {AES_BLOCK_SIZE, "...
0x180007dbe  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007dc3  mov     [r14], rsi
0x180007dc6  mov     [r14+8], rsi
0x180007dca  mov     [r14+10h], ebx
0x180007dce  jmp     short loc_180007E41
0x180007dd0  lea     rdi, [r13-10h]
0x180007dd4  mov     [rsp+130h+var_100], 10h
0x180007ddd  lea     r8, [rsp+130h+var_100]
0x180007de2  mov     [rsp+130h+var_F8], rdi
0x180007de7  lea     rdx, [rbp+47h+var_70]
0x180007deb  lea     rcx, [rbp+47h+var_A0]
0x180007def  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180007df4  mov     rbx, [rbp+47h+var_B8]
0x180007df8  mov     r8, rdi; Size
0x180007dfb  mov     rdx, [rbp+47h+var_88]; Src
0x180007dff  mov     rcx, rbx; void *
0x180007e02  call    memmove
0x180007e07  mov     [r14+10h], r12d
0x180007e0b  mov     [r14], rdi
0x180007e0e  mov     [r14+8], rbx
0x180007e12  test    r15, r15
0x180007e15  jz      short loc_180007E1F
0x180007e17  mov     rcx, r15
0x180007e1a  call    Kerb3961Free
0x180007e1f  mov     rcx, [rsp+130h+var_D0]
0x180007e24  jmp     short loc_180007E61
0x180007e26  lea     rcx, aSecureequalbuf_0; "SecureEqualBuffer(hmac, MIC)"
0x180007e2d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007e32  mov     [r14], rsi
0x180007e35  mov     [r14+8], rsi
0x180007e39  mov     dword ptr [r14+10h], 8009030Fh
0x180007e41  test    r15, r15
0x180007e44  jz      short loc_180007E4E
0x180007e46  mov     rcx, r15
0x180007e49  call    Kerb3961Free
0x180007e4e  mov     rcx, [rsp+130h+var_D0]
0x180007e53  test    rcx, rcx
0x180007e56  jz      short loc_180007E5D
0x180007e58  call    Kerb3961Free
0x180007e5d  mov     rcx, [rbp+47h+var_B8]
0x180007e61  test    rcx, rcx
0x180007e64  jz      short loc_180007E6B
0x180007e66  call    Kerb3961Free
0x180007e6b  mov     rax, r14
0x180007e6e  mov     rcx, [rbp+47h+var_40]
0x180007e72  xor     rcx, rsp; StackCookie
0x180007e75  call    __security_check_cookie
0x180007e7a  mov     rbx, [rsp+130h+arg_18]
0x180007e82  add     rsp, 100h
0x180007e89  pop     r15
0x180007e8b  pop     r14
0x180007e8d  pop     r13
0x180007e8f  pop     r12
0x180007e91  pop     rdi
0x180007e92  pop     rsi
0x180007e93  pop     rbp
0x180007e94  retn
```
