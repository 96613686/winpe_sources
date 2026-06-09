# Kerb3961::RC4_4757::Encrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000f730`
- end: `0x18000fa05`
- name: `?Encrypt@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `725`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001580`
- `0x180005b1c`
- `0x18000f730`
- `0x18000fe44`
- `0x180010290`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012300`

## import_xrefs

- `cng!BCryptGenRandom` at `0x18000f81b`
- `cng!BCryptGenRandom` at `0x18000f81b`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::Encrypt(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4, __int64 a5)
{
  char *v7; // rcx
  int v8; // r8d
  int v9; // r12d
  __int64 v10; // rcx
  __int64 v11; // r14
  NTSTATUS v12; // eax
  int v13; // r8d
  NTSTATUS v14; // ebx
  int v15; // r8d
  int v16; // ebx
  int v17; // r8d
  int v18; // ebx
  int *v19; // rcx
  int *v20; // rbx
  int v21; // r8d
  int v22; // r13d
  int v23; // r8d
  int v24; // r15d
  int *v25; // rcx
  __int64 v26; // rax
  __int64 v28; // [rsp+20h] [rbp-79h] BYREF
  int *v29; // [rsp+28h] [rbp-71h]
  char *v30; // [rsp+30h] [rbp-69h]
  int v31; // [rsp+40h] [rbp-59h] BYREF
  _QWORD *v32; // [rsp+48h] [rbp-51h] BYREF
  __int64 v33; // [rsp+50h] [rbp-49h] BYREF
  __int64 v34; // [rsp+58h] [rbp-41h]
  char *v35; // [rsp+60h] [rbp-39h]
  __int64 v36; // [rsp+68h] [rbp-31h]
  __int64 v37; // [rsp+70h] [rbp-29h] BYREF
  __int64 v38; // [rsp+78h] [rbp-21h]
  char *v39; // [rsp+80h] [rbp-19h]
  _BYTE v40[8]; // [rsp+88h] [rbp-11h] BYREF
  _OWORD *v41; // [rsp+90h] [rbp-9h]
  _BYTE v42[72]; // [rsp+98h] [rbp-1h] BYREF

  if ( a1 == *a3 )
  {
    if ( a1 != *a4 )
    {
      v7 = "this == cipherState.algorithm";
      goto LABEL_3;
    }
    v32 = (_QWORD *)a3[1];
    v31 = *((_DWORD *)v32 + 6);
    if ( *(_QWORD *)a5 > 0xFFFFFFE7 )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"static_cast<size_t>(clearData.length) <= static_cast<size_t>(utl::numeric_limits<ui"
                                     "nt32_t>::max() - EncryptionHeaderSize)",
        (const char *)a2);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -1073741675;
      return a2;
    }
    v36 = *(_QWORD *)a5 + 24LL;
    Kerb3961::MakeBuffer(&v37);
    v9 = (int)v39;
    if ( (int)v39 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"result",
        (const char *)(unsigned int)v39,
        v8);
      v10 = v38;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v9;
      goto LABEL_31;
    }
    v11 = v38;
    v12 = BCryptGenRandom(0, (PUCHAR)(v38 + 16), 8u, 2u);
    v14 = v12;
    if ( v12 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"RandomFill({sizeof(header.confounder), header.confounder})",
        (const char *)(unsigned int)v12,
        v13);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v14;
LABEL_12:
      if ( !v11 )
        return a2;
      v10 = v11;
LABEL_32:
      Kerb3961Free(v10);
      return a2;
    }
    memmove((void *)(v11 + 24), *(const void **)(a5 + 8), *(_QWORD *)a5);
    v29 = &v31;
    v28 = 4;
    Kerb3961::RC4_4757::HmacData(a1, (__int64)&v33, v32, (__int64)&v28);
    v16 = (int)v35;
    if ( (int)v35 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"K1", (const char *)(unsigned int)v35, v15);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v16;
      goto LABEL_16;
    }
    v28 = 16;
    v29 = (int *)(v36 - 16);
    Kerb3961::Split<2>(v40, &v37, &v28);
    Kerb3961::RC4_4757::HmacData(a1, (__int64)&v28, &v33, (__int64)v42);
    v18 = (int)v30;
    if ( (int)v30 >= 0 )
    {
      v20 = v29;
      *v41 = *(_OWORD *)v29;
      Kerb3961::RC4_4757::HmacData(a1, (__int64)&v28, &v33, (__int64)v40);
      v22 = (int)v30;
      if ( (int)v30 >= 0 )
      {
        v24 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, &v32, &v28, v42);
        if ( v24 >= 0 )
        {
          v25 = v29;
          v26 = v37;
          *(_DWORD *)(a2 + 16) = v9;
          *(_QWORD *)a2 = v26;
          *(_QWORD *)(a2 + 8) = v11;
          if ( v25 )
            Kerb3961Free(v25);
          Kerb3961Free(v20);
          v10 = v34;
LABEL_31:
          if ( !v10 )
            return a2;
          goto LABEL_32;
        }
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"RC4Data(K3, encryptedPart)",
          (const char *)(unsigned int)v24,
          v23);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v24;
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"K3", (const char *)(unsigned int)v30, v21);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v22;
      }
      if ( v29 )
        Kerb3961Free(v29);
      v19 = v20;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"checksum",
        (const char *)(unsigned int)v30,
        v17);
      v19 = v29;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v18;
      if ( !v19 )
        goto LABEL_16;
    }
    Kerb3961Free(v19);
LABEL_16:
    if ( v34 )
      Kerb3961Free(v34);
    goto LABEL_12;
  }
  v7 = "this == specificKey.algorithm";
LABEL_3:
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, (const char *)a2);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = -1073741811;
  return a2;
}

```

## disassembly

```asm
0x18000f730  mov     [rsp-8+arg_18], rbx
0x18000f735  push    rbp
0x18000f736  push    rsi
0x18000f737  push    rdi
0x18000f738  push    r12
0x18000f73a  push    r13
0x18000f73c  push    r14
0x18000f73e  push    r15
0x18000f740  lea     rbp, [rsp-17h]
0x18000f745  sub     rsp, 0B0h
0x18000f74c  mov     rsi, rdx
0x18000f74f  mov     r13, [rbp+47h+arg_20]
0x18000f753  mov     r15, rcx
0x18000f756  cmp     rcx, [r8]
0x18000f759  jz      short loc_18000F77C
0x18000f75b  lea     rcx, aThisSpecificke; "this == specificKey.algorithm"
0x18000f762  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f767  xor     edi, edi
0x18000f769  mov     [rsi], rdi
0x18000f76c  mov     [rsi+8], rdi
0x18000f770  mov     dword ptr [rsi+10h], 0C000000Dh
0x18000f777  jmp     loc_18000F9E6
0x18000f77c  cmp     r15, [r9]
0x18000f77f  jz      short loc_18000F78A
0x18000f781  lea     rcx, aThisCipherstat; "this == cipherState.algorithm"
0x18000f788  jmp     short loc_18000F762
0x18000f78a  mov     rax, [r8+8]
0x18000f78e  mov     ecx, 0FFFFFFE7h
0x18000f793  mov     [rbp+47h+var_98], rax
0x18000f797  mov     eax, [rax+18h]
0x18000f79a  mov     [rbp+47h+var_A0], eax
0x18000f79d  mov     rax, [r13+0]
0x18000f7a1  cmp     rax, rcx
0x18000f7a4  jbe     short loc_18000F7C7
0x18000f7a6  lea     rcx, aStaticCastSize_2; "static_cast<size_t>(clearData.length) <"...
0x18000f7ad  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f7b2  xor     edi, edi
0x18000f7b4  mov     [rsi], rdi
0x18000f7b7  mov     [rsi+8], rdi
0x18000f7bb  mov     dword ptr [rsi+10h], 0C0000095h
0x18000f7c2  jmp     loc_18000F9E6
0x18000f7c7  add     rax, 18h
0x18000f7cb  lea     rcx, [rbp+47h+var_70]
0x18000f7cf  mov     rdx, rax
0x18000f7d2  mov     [rbp+47h+var_78], rax
0x18000f7d6  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000f7db  mov     r12d, dword ptr [rbp+47h+var_60]
0x18000f7df  xor     edi, edi
0x18000f7e1  test    r12d, r12d
0x18000f7e4  jns     short loc_18000F809
0x18000f7e6  mov     edx, r12d; char *
0x18000f7e9  lea     rcx, aResult; "result"
0x18000f7f0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f7f5  mov     rcx, [rbp+47h+var_68]
0x18000f7f9  mov     [rsi], rdi
0x18000f7fc  mov     [rsi+8], rdi
0x18000f800  mov     [rsi+10h], r12d
0x18000f804  jmp     loc_18000F9DC
0x18000f809  mov     r14, [rbp+47h+var_68]
0x18000f80d  xor     ecx, ecx; hAlgorithm
0x18000f80f  lea     rdx, [r14+10h]; pbBuffer
0x18000f813  lea     r9d, [rcx+2]; dwFlags
0x18000f817  lea     r8d, [rcx+8]; cbBuffer
0x18000f81b  call    cs:__imp_BCryptGenRandom
0x18000f822  nop     dword ptr [rax+rax+00h]
0x18000f827  mov     ebx, eax
0x18000f829  test    eax, eax
0x18000f82b  jns     short loc_18000F856
0x18000f82d  mov     edx, eax; char *
0x18000f82f  lea     rcx, aRandomfillSize; "RandomFill({sizeof(header.confounder), "...
0x18000f836  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f83b  mov     [rsi], rdi
0x18000f83e  mov     [rsi+8], rdi
0x18000f842  mov     [rsi+10h], ebx
0x18000f845  test    r14, r14
0x18000f848  jz      loc_18000F9E6
0x18000f84e  mov     rcx, r14
0x18000f851  jmp     loc_18000F9E1
0x18000f856  mov     r8, [r13+0]; Size
0x18000f85a  lea     rcx, [r14+18h]; void *
0x18000f85e  mov     rdx, [r13+8]; Src
0x18000f862  call    memmove
0x18000f867  mov     r8, [rbp+47h+var_98]
0x18000f86b  lea     rax, [rbp+47h+var_A0]
0x18000f86f  lea     r9, [rbp+47h+var_C0]
0x18000f873  mov     [rbp+47h+var_B8], rax
0x18000f877  lea     rdx, [rbp+47h+var_90]
0x18000f87b  mov     [rbp+47h+var_C0], 4
0x18000f883  mov     rcx, r15
0x18000f886  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000f88b  mov     ebx, dword ptr [rbp+47h+var_80]
0x18000f88e  test    ebx, ebx
0x18000f890  jns     short loc_18000F8BA
0x18000f892  mov     edx, ebx; char *
0x18000f894  lea     rcx, aK1; "K1"
0x18000f89b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f8a0  mov     [rsi], rdi
0x18000f8a3  mov     [rsi+8], rdi
0x18000f8a7  mov     [rsi+10h], ebx
0x18000f8aa  mov     rcx, [rbp+47h+var_88]
0x18000f8ae  test    rcx, rcx
0x18000f8b1  jz      short loc_18000F845
0x18000f8b3  call    Kerb3961Free
0x18000f8b8  jmp     short loc_18000F845
0x18000f8ba  mov     rax, [rbp+47h+var_78]
0x18000f8be  lea     r8, [rbp+47h+var_C0]
0x18000f8c2  add     rax, 0FFFFFFFFFFFFFFF0h
0x18000f8c6  mov     [rbp+47h+var_C0], 10h
0x18000f8ce  lea     rdx, [rbp+47h+var_70]
0x18000f8d2  mov     [rbp+47h+var_B8], rax
0x18000f8d6  lea     rcx, [rbp+47h+var_58]
0x18000f8da  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x18000f8df  lea     r9, [rbp+47h+var_48]
0x18000f8e3  mov     rcx, r15
0x18000f8e6  lea     r8, [rbp+47h+var_90]
0x18000f8ea  lea     rdx, [rbp+47h+var_C0]
0x18000f8ee  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000f8f3  mov     ebx, dword ptr [rbp+47h+var_B0]
0x18000f8f6  test    ebx, ebx
0x18000f8f8  jns     short loc_18000F922
0x18000f8fa  mov     edx, ebx; char *
0x18000f8fc  lea     rcx, aChecksum; "checksum"
0x18000f903  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f908  mov     rcx, [rbp+47h+var_B8]
0x18000f90c  mov     [rsi], rdi
0x18000f90f  mov     [rsi+8], rdi
0x18000f913  mov     [rsi+10h], ebx
0x18000f916  test    rcx, rcx
0x18000f919  jz      short loc_18000F8AA
0x18000f91b  call    Kerb3961Free
0x18000f920  jmp     short loc_18000F8AA
0x18000f922  mov     rbx, [rbp+47h+var_B8]
0x18000f926  lea     r9, [rbp+47h+var_58]
0x18000f92a  mov     rax, [rbp+47h+var_50]
0x18000f92e  lea     r8, [rbp+47h+var_90]
0x18000f932  lea     rdx, [rbp+47h+var_C0]
0x18000f936  mov     rcx, r15
0x18000f939  movups  xmm0, xmmword ptr [rbx]
0x18000f93c  movdqu  xmmword ptr [rax], xmm0
0x18000f940  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000f945  mov     r13d, dword ptr [rbp+47h+var_B0]
0x18000f949  test    r13d, r13d
0x18000f94c  jns     short loc_18000F97B
0x18000f94e  mov     edx, r13d; char *
0x18000f951  lea     rcx, aK3; "K3"
0x18000f958  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f95d  mov     [rsi], rdi
0x18000f960  mov     [rsi+8], rdi
0x18000f964  mov     [rsi+10h], r13d
0x18000f968  mov     rcx, [rbp+47h+var_B8]
0x18000f96c  test    rcx, rcx
0x18000f96f  jz      short loc_18000F976
0x18000f971  call    Kerb3961Free
0x18000f976  mov     rcx, rbx
0x18000f979  jmp     short loc_18000F91B
0x18000f97b  lea     r9, [rbp+47h+var_48]
0x18000f97f  mov     rcx, r15
0x18000f982  lea     r8, [rbp+47h+var_C0]
0x18000f986  lea     rdx, [rbp+47h+var_98]
0x18000f98a  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x18000f98f  mov     r15d, [rax]
0x18000f992  test    r15d, r15d
0x18000f995  jns     short loc_18000F9B3
0x18000f997  mov     edx, r15d; char *
0x18000f99a  lea     rcx, aRc4dataK3Encry; "RC4Data(K3, encryptedPart)"
0x18000f9a1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f9a6  mov     [rsi], rdi
0x18000f9a9  mov     [rsi+8], rdi
0x18000f9ad  mov     [rsi+10h], r15d
0x18000f9b1  jmp     short loc_18000F968
0x18000f9b3  mov     rcx, [rbp+47h+var_B8]
0x18000f9b7  mov     rax, [rbp+47h+var_70]
0x18000f9bb  mov     [rsi+10h], r12d
0x18000f9bf  mov     [rsi], rax
0x18000f9c2  mov     [rsi+8], r14
0x18000f9c6  test    rcx, rcx
0x18000f9c9  jz      short loc_18000F9D0
0x18000f9cb  call    Kerb3961Free
0x18000f9d0  mov     rcx, rbx
0x18000f9d3  call    Kerb3961Free
0x18000f9d8  mov     rcx, [rbp+47h+var_88]
0x18000f9dc  test    rcx, rcx
0x18000f9df  jz      short loc_18000F9E6
0x18000f9e1  call    Kerb3961Free
0x18000f9e6  mov     rbx, [rsp+0E0h+arg_18]
0x18000f9ee  mov     rax, rsi
0x18000f9f1  add     rsp, 0B0h
0x18000f9f8  pop     r15
0x18000f9fa  pop     r14
0x18000f9fc  pop     r13
0x18000f9fe  pop     r12
0x18000fa00  pop     rdi
0x18000fa01  pop     rsi
0x18000fa02  pop     rbp
0x18000fa03  retn
```
