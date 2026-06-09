# Kerb3961::RC4_4757::Encrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180007650`
- end: `0x18000792a`
- name: `?Encrypt@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `730`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800046e0`
- `0x180007650`
- `0x1800085cc`
- `0x18000901c`
- `0x180009190`
- `0x18001d360`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18000773b`
- `bcrypt!BCryptGenRandom` at `0x18000773b`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::Encrypt(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4, __int64 a5)
{
  char *v7; // rcx
  int v8; // r8d
  int v9; // r12d
  void *v10; // rcx
  UCHAR *v11; // r14
  NTSTATUS v12; // eax
  int v13; // r8d
  NTSTATUS v14; // ebx
  int v15; // r8d
  int v16; // ebx
  int v17; // r8d
  int v18; // ebx
  void *v19; // rcx
  void *v20; // rbx
  int v21; // r8d
  int v22; // r13d
  int v23; // r8d
  int v24; // r15d
  void *v25; // rcx
  __int64 v26; // rax
  __int64 v28; // [rsp+20h] [rbp-79h] BYREF
  void *v29; // [rsp+28h] [rbp-71h]
  char *v30; // [rsp+30h] [rbp-69h]
  int v31; // [rsp+40h] [rbp-59h] BYREF
  _QWORD *v32; // [rsp+48h] [rbp-51h] BYREF
  __int64 v33; // [rsp+50h] [rbp-49h] BYREF
  void *v34; // [rsp+58h] [rbp-41h]
  char *v35; // [rsp+60h] [rbp-39h]
  __int64 v36; // [rsp+68h] [rbp-31h]
  __int64 v37; // [rsp+70h] [rbp-29h] BYREF
  UCHAR *v38; // [rsp+78h] [rbp-21h]
  char *v39; // [rsp+80h] [rbp-19h]
  char v40[8]; // [rsp+88h] [rbp-11h] BYREF
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
    v12 = BCryptGenRandom(0, v38 + 16, 8u, 2u);
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
      operator delete(v10, 0);
      return a2;
    }
    memcpy_0(v11 + 24, *(const void **)(a5 + 8), *(_QWORD *)a5);
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
    v29 = (void *)(v36 - 16);
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
            operator delete(v25, 0);
          operator delete(v20, 0);
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
        operator delete(v29, 0);
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
    operator delete(v19, 0);
LABEL_16:
    if ( v34 )
      operator delete(v34, 0);
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
0x180007650  mov     [rsp-8+arg_18], rbx
0x180007655  push    rbp
0x180007656  push    rsi
0x180007657  push    rdi
0x180007658  push    r12
0x18000765a  push    r13
0x18000765c  push    r14
0x18000765e  push    r15
0x180007660  lea     rbp, [rsp-17h]
0x180007665  sub     rsp, 0B0h
0x18000766c  mov     rsi, rdx
0x18000766f  mov     r13, [rbp+47h+arg_20]
0x180007673  mov     r15, rcx
0x180007676  cmp     rcx, [r8]
0x180007679  jz      short loc_18000769C
0x18000767b  lea     rcx, aThisSpecificke; "this == specificKey.algorithm"
0x180007682  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007687  xor     edi, edi
0x180007689  mov     [rsi], rdi
0x18000768c  mov     [rsi+8], rdi
0x180007690  mov     dword ptr [rsi+10h], 0C000000Dh
0x180007697  jmp     loc_18000790C
0x18000769c  cmp     r15, [r9]
0x18000769f  jz      short loc_1800076AA
0x1800076a1  lea     rcx, aThisCipherstat; "this == cipherState.algorithm"
0x1800076a8  jmp     short loc_180007682
0x1800076aa  mov     rax, [r8+8]
0x1800076ae  mov     ecx, 0FFFFFFE7h
0x1800076b3  mov     [rbp+47h+var_98], rax
0x1800076b7  mov     eax, [rax+18h]
0x1800076ba  mov     [rbp+47h+var_A0], eax
0x1800076bd  mov     rax, [r13+0]
0x1800076c1  cmp     rax, rcx
0x1800076c4  jbe     short loc_1800076E7
0x1800076c6  lea     rcx, aStaticCastSize_4; "static_cast<size_t>(clearData.length) <"...
0x1800076cd  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800076d2  xor     edi, edi
0x1800076d4  mov     [rsi], rdi
0x1800076d7  mov     [rsi+8], rdi
0x1800076db  mov     dword ptr [rsi+10h], 0C0000095h
0x1800076e2  jmp     loc_18000790C
0x1800076e7  add     rax, 18h
0x1800076eb  lea     rcx, [rbp+47h+var_70]
0x1800076ef  mov     rdx, rax
0x1800076f2  mov     [rbp+47h+var_78], rax
0x1800076f6  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x1800076fb  mov     r12d, dword ptr [rbp+47h+var_60]
0x1800076ff  xor     edi, edi
0x180007701  test    r12d, r12d
0x180007704  jns     short loc_180007729
0x180007706  mov     edx, r12d; char *
0x180007709  lea     rcx, aResult; "result"
0x180007710  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007715  mov     rcx, [rbp+47h+var_68]
0x180007719  mov     [rsi], rdi
0x18000771c  mov     [rsi+8], rdi
0x180007720  mov     [rsi+10h], r12d
0x180007724  jmp     loc_180007900
0x180007729  mov     r14, [rbp+47h+var_68]
0x18000772d  xor     ecx, ecx; hAlgorithm
0x18000772f  lea     rdx, [r14+10h]; pbBuffer
0x180007733  lea     r9d, [rcx+2]; dwFlags
0x180007737  lea     r8d, [rcx+8]; cbBuffer
0x18000773b  call    cs:__imp_BCryptGenRandom
0x180007741  mov     ebx, eax
0x180007743  test    eax, eax
0x180007745  jns     short loc_180007770
0x180007747  mov     edx, eax; char *
0x180007749  lea     rcx, aRandomfillSize; "RandomFill({sizeof(header.confounder), "...
0x180007750  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007755  mov     [rsi], rdi
0x180007758  mov     [rsi+8], rdi
0x18000775c  mov     [rsi+10h], ebx
0x18000775f  test    r14, r14
0x180007762  jz      loc_18000790C
0x180007768  mov     rcx, r14
0x18000776b  jmp     loc_180007905
0x180007770  mov     r8, [r13+0]; Size
0x180007774  lea     rcx, [r14+18h]; void *
0x180007778  mov     rdx, [r13+8]; Src
0x18000777c  call    memcpy_0
0x180007781  mov     r8, [rbp+47h+var_98]
0x180007785  lea     rax, [rbp+47h+var_A0]
0x180007789  lea     r9, [rbp+47h+var_C0]
0x18000778d  mov     [rbp+47h+var_B8], rax
0x180007791  lea     rdx, [rbp+47h+var_90]
0x180007795  mov     [rbp+47h+var_C0], 4
0x18000779d  mov     rcx, r15
0x1800077a0  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800077a5  mov     ebx, dword ptr [rbp+47h+var_80]
0x1800077a8  test    ebx, ebx
0x1800077aa  jns     short loc_1800077D6
0x1800077ac  mov     edx, ebx; char *
0x1800077ae  lea     rcx, aK1; "K1"
0x1800077b5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800077ba  mov     [rsi], rdi
0x1800077bd  mov     [rsi+8], rdi
0x1800077c1  mov     [rsi+10h], ebx
0x1800077c4  mov     rcx, [rbp+47h+var_88]; void *
0x1800077c8  test    rcx, rcx
0x1800077cb  jz      short loc_18000775F
0x1800077cd  xor     edx, edx; struct std::nothrow_t *
0x1800077cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800077d4  jmp     short loc_18000775F
0x1800077d6  mov     rax, [rbp+47h+var_78]
0x1800077da  lea     r8, [rbp+47h+var_C0]
0x1800077de  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800077e2  mov     [rbp+47h+var_C0], 10h
0x1800077ea  lea     rdx, [rbp+47h+var_70]
0x1800077ee  mov     [rbp+47h+var_B8], rax
0x1800077f2  lea     rcx, [rbp+47h+var_58]
0x1800077f6  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x1800077fb  lea     r9, [rbp+47h+var_48]
0x1800077ff  mov     rcx, r15
0x180007802  lea     r8, [rbp+47h+var_90]
0x180007806  lea     rdx, [rbp+47h+var_C0]
0x18000780a  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000780f  mov     ebx, dword ptr [rbp+47h+var_B0]
0x180007812  test    ebx, ebx
0x180007814  jns     short loc_180007840
0x180007816  mov     edx, ebx; char *
0x180007818  lea     rcx, aChecksum; "checksum"
0x18000781f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007824  mov     rcx, [rbp+47h+var_B8]; void *
0x180007828  mov     [rsi], rdi
0x18000782b  mov     [rsi+8], rdi
0x18000782f  mov     [rsi+10h], ebx
0x180007832  test    rcx, rcx
0x180007835  jz      short loc_1800077C4
0x180007837  xor     edx, edx; struct std::nothrow_t *
0x180007839  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000783e  jmp     short loc_1800077C4
0x180007840  mov     rbx, [rbp+47h+var_B8]
0x180007844  lea     r9, [rbp+47h+var_58]
0x180007848  mov     rax, [rbp+47h+var_50]
0x18000784c  lea     r8, [rbp+47h+var_90]
0x180007850  lea     rdx, [rbp+47h+var_C0]
0x180007854  mov     rcx, r15
0x180007857  movups  xmm0, xmmword ptr [rbx]
0x18000785a  movdqu  xmmword ptr [rax], xmm0
0x18000785e  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180007863  mov     r13d, dword ptr [rbp+47h+var_B0]
0x180007867  test    r13d, r13d
0x18000786a  jns     short loc_18000789B
0x18000786c  mov     edx, r13d; char *
0x18000786f  lea     rcx, aK3; "K3"
0x180007876  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000787b  mov     [rsi], rdi
0x18000787e  mov     [rsi+8], rdi
0x180007882  mov     [rsi+10h], r13d
0x180007886  mov     rcx, [rbp+47h+var_B8]; void *
0x18000788a  test    rcx, rcx
0x18000788d  jz      short loc_180007896
0x18000788f  xor     edx, edx; struct std::nothrow_t *
0x180007891  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007896  mov     rcx, rbx
0x180007899  jmp     short loc_180007837
0x18000789b  lea     r9, [rbp+47h+var_48]
0x18000789f  mov     rcx, r15
0x1800078a2  lea     r8, [rbp+47h+var_C0]
0x1800078a6  lea     rdx, [rbp+47h+var_98]
0x1800078aa  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x1800078af  mov     r15d, [rax]
0x1800078b2  test    r15d, r15d
0x1800078b5  jns     short loc_1800078D3
0x1800078b7  mov     edx, r15d; char *
0x1800078ba  lea     rcx, aRc4dataK3Encry; "RC4Data(K3, encryptedPart)"
0x1800078c1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800078c6  mov     [rsi], rdi
0x1800078c9  mov     [rsi+8], rdi
0x1800078cd  mov     [rsi+10h], r15d
0x1800078d1  jmp     short loc_180007886
0x1800078d3  mov     rcx, [rbp+47h+var_B8]; void *
0x1800078d7  mov     rax, [rbp+47h+var_70]
0x1800078db  mov     [rsi+10h], r12d
0x1800078df  mov     [rsi], rax
0x1800078e2  mov     [rsi+8], r14
0x1800078e6  test    rcx, rcx
0x1800078e9  jz      short loc_1800078F2
0x1800078eb  xor     edx, edx; struct std::nothrow_t *
0x1800078ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800078f2  xor     edx, edx; struct std::nothrow_t *
0x1800078f4  mov     rcx, rbx; void *
0x1800078f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800078fc  mov     rcx, [rbp+47h+var_88]; void *
0x180007900  test    rcx, rcx
0x180007903  jz      short loc_18000790C
0x180007905  xor     edx, edx; struct std::nothrow_t *
0x180007907  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000790c  mov     rbx, [rsp+0E0h+arg_18]
0x180007914  mov     rax, rsi
0x180007917  add     rsp, 0B0h
0x18000791e  pop     r15
0x180007920  pop     r14
0x180007922  pop     r13
0x180007924  pop     r12
0x180007926  pop     rdi
0x180007927  pop     rsi
0x180007928  pop     rbp
0x180007929  retn
```
