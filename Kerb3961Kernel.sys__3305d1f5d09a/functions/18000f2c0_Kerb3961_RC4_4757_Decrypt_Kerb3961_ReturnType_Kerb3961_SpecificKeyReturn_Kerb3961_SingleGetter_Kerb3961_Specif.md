# Kerb3961::RC4_4757::Decrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000f2c0`
- end: `0x18000f5cb`
- name: `?Decrypt@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `779`
- prototype: `__int64 __fastcall(int, int, int, int, char *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800015f0`
- `0x180003a54`
- `0x18000f2c0`
- `0x18000fe44`
- `0x180010290`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::Decrypt(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4, char *a5)
{
  char *v7; // rcx
  __int64 v8; // rdi
  unsigned __int64 v9; // rax
  size_t v10; // r12
  int v11; // r8d
  int v12; // r14d
  int v13; // r8d
  int v14; // r14d
  int v15; // r8d
  int v16; // r15d
  void *v17; // rcx
  int v18; // r8d
  int v19; // r14d
  __int64 v20; // rdx
  int v21; // r8d
  int v22; // ebx
  void *v23; // rcx
  void *v24; // r14
  char v25; // r10
  unsigned int v26; // r9d
  __int64 v27; // rax
  char *v28; // rbx
  __int64 v30; // [rsp+20h] [rbp-89h] BYREF
  void *v31; // [rsp+28h] [rbp-81h]
  char *v32; // [rsp+30h] [rbp-79h]
  int v33; // [rsp+40h] [rbp-69h] BYREF
  char v34[8]; // [rsp+48h] [rbp-61h] BYREF
  __int64 v35; // [rsp+50h] [rbp-59h]
  char *v36; // [rsp+58h] [rbp-51h]
  char v37[8]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v38; // [rsp+68h] [rbp-41h]
  char *v39; // [rsp+70h] [rbp-39h]
  char v40[8]; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v41; // [rsp+80h] [rbp-29h] BYREF
  void *v42; // [rsp+88h] [rbp-21h]
  char *v43; // [rsp+90h] [rbp-19h]
  _QWORD v44[2]; // [rsp+98h] [rbp-11h] BYREF
  char v45[16]; // [rsp+A8h] [rbp-1h] BYREF

  if ( a1 != *a3 )
  {
    v7 = "this == specificKey.algorithm";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, a5);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
    return a2;
  }
  if ( a1 != *a4 )
  {
    v7 = "this == cipherState.algorithm";
    goto LABEL_3;
  }
  v8 = a3[1];
  v33 = *(_DWORD *)(v8 + 24);
  v9 = *(_QWORD *)a5;
  if ( *(_QWORD *)a5 > 0xFFFFFFFF )
  {
    v7 = "cipherText.length <= utl::numeric_limits<uint32_t>::max()";
    goto LABEL_3;
  }
  if ( v9 < 0x18 )
  {
    v7 = "cipherText.length >= EncryptionHeaderSize";
    goto LABEL_3;
  }
  v10 = v9 - 24;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v44);
  v30 = 4;
  v31 = &v33;
  Kerb3961::RC4_4757::HmacData(a1, v34, v8, &v30);
  v12 = (int)v36;
  if ( (int)v36 >= 0 )
  {
    Kerb3961::RC4_4757::HmacData(a1, v37, v34, v44);
    v14 = (int)v39;
    if ( (int)v39 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"K3", (const char *)(unsigned int)v39, v13);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v14;
      goto LABEL_37;
    }
    Kerb3961::CopyBuffer((__int64)&v30, (__int64)v45);
    v16 = (int)v32;
    if ( (int)v32 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"result",
        (const char *)(unsigned int)v32,
        v15);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v16;
      goto LABEL_16;
    }
    v19 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, v40, v37, &v30);
    if ( v19 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"RC4Data(K3, result)",
        (const char *)(unsigned int)v19,
        v18);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v19;
      goto LABEL_16;
    }
    Kerb3961::RC4_4757::HmacData(a1, &v41, v34, &v30);
    v22 = (int)v43;
    if ( (int)v43 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"checksum",
        (const char *)(unsigned int)v43,
        v21);
      v23 = v42;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v22;
      if ( !v23 )
        goto LABEL_16;
      goto LABEL_22;
    }
    v24 = v42;
    if ( v41 == v44[0] )
    {
      if ( !v41 )
      {
        v20 = 1;
LABEL_31:
        if ( (_BYTE)v20 )
        {
          v28 = (char *)v31;
          memmove(v31, (char *)v31 + 8, v10);
          *(_QWORD *)&v28[v10] = 0;
          *(_DWORD *)(a2 + 16) = v16;
          *(_QWORD *)a2 = v10;
          *(_QWORD *)(a2 + 8) = v28;
          if ( !v24 )
            goto LABEL_37;
          v17 = v24;
LABEL_36:
          Kerb3961Free(v17);
LABEL_37:
          if ( v38 )
            Kerb3961Free(v38);
          goto LABEL_39;
        }
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"SecureEqualBuffer(checksum, MIC)",
          (const char *)v20);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -2146893041;
        if ( !v24 )
        {
LABEL_16:
          v17 = v31;
          if ( !v31 )
            goto LABEL_37;
          goto LABEL_36;
        }
        v23 = v24;
LABEL_22:
        Kerb3961Free(v23);
        goto LABEL_16;
      }
      if ( v41 <= 0xFFFFFFFF )
      {
        v25 = 0;
        v26 = 0;
        v20 = 1;
        do
        {
          v27 = v26++;
          v25 |= *((_BYTE *)v42 + v27) ^ *(_BYTE *)(v27 + v44[1]);
        }
        while ( v26 < (unsigned int)v41 );
        if ( !v25 )
          goto LABEL_31;
      }
    }
    LOBYTE(v20) = 0;
    goto LABEL_31;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"K1", (const char *)(unsigned int)v36, v11);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v12;
LABEL_39:
  if ( v35 )
    Kerb3961Free(v35);
  return a2;
}

```

## disassembly

```asm
0x18000f2c0  mov     [rsp-8+arg_18], rbx
0x18000f2c5  push    rbp
0x18000f2c6  push    rsi
0x18000f2c7  push    rdi
0x18000f2c8  push    r12
0x18000f2ca  push    r13
0x18000f2cc  push    r14
0x18000f2ce  push    r15
0x18000f2d0  lea     rbp, [rsp-17h]
0x18000f2d5  sub     rsp, 0C0h
0x18000f2dc  mov     rax, cs:__security_cookie
0x18000f2e3  xor     rax, rsp
0x18000f2e6  mov     [rbp+47h+var_38], rax
0x18000f2ea  mov     rsi, rdx
0x18000f2ed  mov     rdx, [rbp+47h+arg_20]; char *
0x18000f2f1  mov     rbx, rcx
0x18000f2f4  cmp     rcx, [r8]
0x18000f2f7  jz      short loc_18000F31A
0x18000f2f9  lea     rcx, aThisSpecificke; "this == specificKey.algorithm"
0x18000f300  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f305  xor     edi, edi
0x18000f307  mov     [rsi], rdi
0x18000f30a  mov     [rsi+8], rdi
0x18000f30e  mov     dword ptr [rsi+10h], 0C000000Dh
0x18000f315  jmp     loc_18000F5A0
0x18000f31a  cmp     rbx, [r9]
0x18000f31d  jz      short loc_18000F328
0x18000f31f  lea     rcx, aThisCipherstat; "this == cipherState.algorithm"
0x18000f326  jmp     short loc_18000F300
0x18000f328  mov     rdi, [r8+8]
0x18000f32c  mov     r13d, 0FFFFFFFFh
0x18000f332  mov     eax, [rdi+18h]
0x18000f335  mov     [rbp+47h+var_B0], eax
0x18000f338  mov     rax, [rdx]
0x18000f33b  cmp     rax, r13
0x18000f33e  jbe     short loc_18000F349
0x18000f340  lea     rcx, aCiphertextLeng_3; "cipherText.length <= utl::numeric_limit"...
0x18000f347  jmp     short loc_18000F300
0x18000f349  cmp     rax, 18h
0x18000f34d  jnb     short loc_18000F358
0x18000f34f  lea     rcx, aCiphertextLeng_0; "cipherText.length >= EncryptionHeaderSi"...
0x18000f356  jmp     short loc_18000F300
0x18000f358  lea     r12, [rax-18h]
0x18000f35c  mov     [rsp+0F0h+var_D0], 10h
0x18000f365  lea     rax, [r12+8]
0x18000f36a  lea     r8, [rsp+0F0h+var_D0]
0x18000f36f  mov     [rsp+0F0h+var_C8], rax
0x18000f374  lea     rcx, [rbp+47h+var_58]; this
0x18000f378  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x18000f37d  lea     rax, [rbp+47h+var_B0]
0x18000f381  mov     [rsp+0F0h+var_D0], 4
0x18000f38a  lea     r9, [rsp+0F0h+var_D0]
0x18000f38f  mov     [rsp+0F0h+var_C8], rax
0x18000f394  mov     r8, rdi
0x18000f397  lea     rdx, [rbp+47h+var_A8]
0x18000f39b  mov     rcx, rbx
0x18000f39e  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000f3a3  mov     r14d, dword ptr [rbp+47h+var_98]
0x18000f3a7  xor     edi, edi
0x18000f3a9  test    r14d, r14d
0x18000f3ac  jns     short loc_18000F3CD
0x18000f3ae  mov     edx, r14d; char *
0x18000f3b1  lea     rcx, aK1; "K1"
0x18000f3b8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f3bd  mov     [rsi], rdi
0x18000f3c0  mov     [rsi+8], rdi
0x18000f3c4  mov     [rsi+10h], r14d
0x18000f3c8  jmp     loc_18000F592
0x18000f3cd  lea     r9, [rbp+47h+var_58]
0x18000f3d1  mov     rcx, rbx
0x18000f3d4  lea     r8, [rbp+47h+var_A8]
0x18000f3d8  lea     rdx, [rbp+47h+var_90]
0x18000f3dc  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000f3e1  mov     r14d, dword ptr [rbp+47h+var_80]
0x18000f3e5  test    r14d, r14d
0x18000f3e8  jns     short loc_18000F409
0x18000f3ea  mov     edx, r14d; char *
0x18000f3ed  lea     rcx, aK3; "K3"
0x18000f3f4  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f3f9  mov     [rsi], rdi
0x18000f3fc  mov     [rsi+8], rdi
0x18000f400  mov     [rsi+10h], r14d
0x18000f404  jmp     loc_18000F584
0x18000f409  lea     rdx, [rbp+47h+var_48]
0x18000f40d  lea     rcx, [rsp+0F0h+var_D0]
0x18000f412  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x18000f417  mov     r15, [rbp+47h+var_C0]
0x18000f41b  test    r15d, r15d
0x18000f41e  jns     short loc_18000F44D
0x18000f420  mov     edx, r15d; char *
0x18000f423  lea     rcx, aResult; "result"
0x18000f42a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f42f  mov     [rsi], rdi
0x18000f432  mov     [rsi+8], rdi
0x18000f436  mov     [rsi+10h], r15d
0x18000f43a  mov     rcx, [rsp+0F0h+var_C8]
0x18000f43f  test    rcx, rcx
0x18000f442  jz      loc_18000F584
0x18000f448  jmp     loc_18000F57F
0x18000f44d  lea     r9, [rsp+0F0h+var_D0]
0x18000f452  mov     rcx, rbx
0x18000f455  lea     r8, [rbp+47h+var_90]
0x18000f459  lea     rdx, [rbp+47h+var_78]
0x18000f45d  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x18000f462  mov     r14d, [rax]
0x18000f465  test    r14d, r14d
0x18000f468  jns     short loc_18000F486
0x18000f46a  mov     edx, r14d; char *
0x18000f46d  lea     rcx, aRc4dataK3Resul; "RC4Data(K3, result)"
0x18000f474  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f479  mov     [rsi], rdi
0x18000f47c  mov     [rsi+8], rdi
0x18000f480  mov     [rsi+10h], r14d
0x18000f484  jmp     short loc_18000F43A
0x18000f486  lea     r9, [rsp+0F0h+var_D0]
0x18000f48b  mov     rcx, rbx
0x18000f48e  lea     r8, [rbp+47h+var_A8]
0x18000f492  lea     rdx, [rbp+47h+var_70]
0x18000f496  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000f49b  mov     ebx, dword ptr [rbp+47h+var_60]
0x18000f49e  test    ebx, ebx
0x18000f4a0  jns     short loc_18000F4D1
0x18000f4a2  mov     edx, ebx; char *
0x18000f4a4  lea     rcx, aChecksum; "checksum"
0x18000f4ab  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f4b0  mov     rcx, [rbp+47h+var_68]
0x18000f4b4  mov     [rsi], rdi
0x18000f4b7  mov     [rsi+8], rdi
0x18000f4bb  mov     [rsi+10h], ebx
0x18000f4be  test    rcx, rcx
0x18000f4c1  jz      loc_18000F43A
0x18000f4c7  call    Kerb3961Free
0x18000f4cc  jmp     loc_18000F43A
0x18000f4d1  mov     r8, [rbp+47h+var_70]
0x18000f4d5  mov     r14, [rbp+47h+var_68]
0x18000f4d9  cmp     r8, [rbp+47h+var_58]
0x18000f4dd  jnz     short loc_18000F520
0x18000f4df  test    r8, r8
0x18000f4e2  jnz     short loc_18000F4EA
0x18000f4e4  lea     edx, [r8+1]
0x18000f4e8  jmp     short loc_18000F523
0x18000f4ea  cmp     r8, r13
0x18000f4ed  ja      short loc_18000F520
0x18000f4ef  mov     r11, [rbp+47h+var_50]
0x18000f4f3  mov     r10b, dil
0x18000f4f6  mov     r9d, edi
0x18000f4f9  mov     edx, 1
0x18000f4fe  test    r8d, r8d
0x18000f501  jz      short loc_18000F523
0x18000f503  mov     eax, r9d
0x18000f506  add     r9d, edx
0x18000f509  mov     cl, [rax+r11]
0x18000f50d  mov     al, [rax+r14]
0x18000f511  xor     cl, al
0x18000f513  or      r10b, cl
0x18000f516  cmp     r9d, r8d
0x18000f519  jb      short loc_18000F503
0x18000f51b  test    r10b, r10b
0x18000f51e  jz      short loc_18000F523
0x18000f520  mov     dl, dil; char *
0x18000f523  test    dl, dl
0x18000f525  jnz     short loc_18000F552
0x18000f527  lea     rcx, aSecureequalbuf_2; "SecureEqualBuffer(checksum, MIC)"
0x18000f52e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f533  mov     [rsi], rdi
0x18000f536  mov     [rsi+8], rdi
0x18000f53a  mov     dword ptr [rsi+10h], 8009030Fh
0x18000f541  test    r14, r14
0x18000f544  jz      loc_18000F43A
0x18000f54a  mov     rcx, r14
0x18000f54d  jmp     loc_18000F4C7
0x18000f552  mov     rbx, [rsp+0F0h+var_C8]
0x18000f557  mov     r8, r12; Size
0x18000f55a  mov     rcx, rbx; void *
0x18000f55d  lea     rdx, [rbx+8]; Src
0x18000f561  call    memmove
0x18000f566  xor     eax, eax
0x18000f568  mov     [r12+rbx], rax
0x18000f56c  mov     [rsi+10h], r15d
0x18000f570  mov     [rsi], r12
0x18000f573  mov     [rsi+8], rbx
0x18000f577  test    r14, r14
0x18000f57a  jz      short loc_18000F584
0x18000f57c  mov     rcx, r14
0x18000f57f  call    Kerb3961Free
0x18000f584  mov     rcx, [rbp+47h+var_88]
0x18000f588  test    rcx, rcx
0x18000f58b  jz      short loc_18000F592
0x18000f58d  call    Kerb3961Free
0x18000f592  mov     rcx, [rbp+47h+var_A0]
0x18000f596  test    rcx, rcx
0x18000f599  jz      short loc_18000F5A0
0x18000f59b  call    Kerb3961Free
0x18000f5a0  mov     rax, rsi
0x18000f5a3  mov     rcx, [rbp+47h+var_38]
0x18000f5a7  xor     rcx, rsp; StackCookie
0x18000f5aa  call    __security_check_cookie
0x18000f5af  mov     rbx, [rsp+0F0h+arg_18]
0x18000f5b7  add     rsp, 0C0h
0x18000f5be  pop     r15
0x18000f5c0  pop     r14
0x18000f5c2  pop     r13
0x18000f5c4  pop     r12
0x18000f5c6  pop     rdi
0x18000f5c7  pop     rsi
0x18000f5c8  pop     rbp
0x18000f5c9  retn
```
