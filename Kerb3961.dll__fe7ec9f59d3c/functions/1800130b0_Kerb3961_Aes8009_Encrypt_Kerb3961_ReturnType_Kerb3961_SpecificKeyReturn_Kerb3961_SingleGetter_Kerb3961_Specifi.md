# Kerb3961::Aes8009::Encrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800130b0`
- end: `0x1800134ca`
- name: `?Encrypt@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `1050`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800046e0`
- `0x18000901c`
- `0x18000f438`
- `0x18000f908`
- `0x180012ab8`
- `0x1800130b0`
- `0x18001d360`
- `0x18001d36c`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1800131f9`
- `bcrypt!BCryptGenRandom` at `0x1800131f9`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::Encrypt(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  __int64 v9; // rax
  const char *v10; // rdx
  size_t v11; // rbx
  const char *v12; // rdx
  int v13; // r8d
  int v14; // r12d
  __int64 v15; // r14
  __int64 *v16; // r14
  ULONG v17; // r8d
  UCHAR *v18; // rdx
  NTSTATUS v19; // ebx
  int v20; // r8d
  char *v21; // rcx
  const char *v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rbx
  int v25; // r8d
  void *v26; // rcx
  int v27; // eax
  int v28; // ebx
  void *v29; // rcx
  size_t v30; // r13
  void *v31; // rbx
  __int64 v32; // rdx
  int v33; // r8d
  int v34; // r14d
  PUCHAR v35; // rcx
  void *v36; // rcx
  PUCHAR v37; // r14
  size_t v39; // [rsp+30h] [rbp-B9h] BYREF
  const char *v40; // [rsp+38h] [rbp-B1h]
  __int64 v41; // [rsp+40h] [rbp-A9h] BYREF
  __int64 v42; // [rsp+48h] [rbp-A1h] BYREF
  void *v43; // [rsp+50h] [rbp-99h]
  char *v44; // [rsp+58h] [rbp-91h]
  __int64 v45; // [rsp+60h] [rbp-89h] BYREF
  void *v46; // [rsp+68h] [rbp-81h]
  char *v47; // [rsp+70h] [rbp-79h]
  ULONG cbBuffer; // [rsp+78h] [rbp-71h] BYREF
  PUCHAR pbBuffer; // [rsp+80h] [rbp-69h]
  char *v50; // [rsp+88h] [rbp-61h]
  void *v51; // [rsp+90h] [rbp-59h]
  __int64 v52; // [rsp+98h] [rbp-51h]
  _QWORD *v53; // [rsp+A0h] [rbp-49h]
  size_t Size; // [rsp+A8h] [rbp-41h]
  _BYTE v55[8]; // [rsp+B0h] [rbp-39h] BYREF
  void *v56; // [rsp+B8h] [rbp-31h]
  void *v57; // [rsp+C8h] [rbp-21h]
  _BYTE v58[8]; // [rsp+D0h] [rbp-19h] BYREF
  _OWORD *v59; // [rsp+D8h] [rbp-11h]
  _QWORD v60[2]; // [rsp+E0h] [rbp-9h] BYREF

  v53 = a6;
  v9 = *(_QWORD *)(a1 + 88);
  v41 = a4;
  v10 = *(const char **)a5;
  Size = *(_QWORD *)a5 + 16LL;
  v11 = Size;
  if ( Size + v9 <= (unsigned __int64)v10 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"resultSize > clearData.length", v10);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
    return a2;
  }
  Kerb3961::MakeBuffer(&v45);
  v14 = (int)v47;
  if ( (int)v47 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"resultBuffer",
      (const char *)(unsigned int)v47,
      v13);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v14;
LABEL_34:
    v36 = v46;
    goto LABEL_35;
  }
  v15 = *(_QWORD *)(a3 + 8);
  v52 = v15 + 24;
  if ( !*(_QWORD *)(v15 + 24) || (v16 = (__int64 *)(v15 + 48), !*v16) )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"key->Ke.length > 0 && key->Ki.length > 0",
      v12);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
    goto LABEL_34;
  }
  v39 = 16;
  v40 = (const char *)v11;
  v41 = *(_QWORD *)(v41 + 8);
  Kerb3961::Split<2>(v58, &v45, &v39);
  v40 = *(const char **)a5;
  v39 = 16;
  Kerb3961::Split<2>(&cbBuffer, v60, &v39);
  v17 = cbBuffer;
  v18 = pbBuffer;
  *v59 = *(_OWORD *)v41;
  v19 = BCryptGenRandom(0, v18, v17, 2u);
  if ( v19 < 0 )
  {
    v21 = "RandomFill(confounder)";
LABEL_9:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v21, (const char *)(unsigned int)v19, v20);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v19;
    goto LABEL_34;
  }
  memcpy_0(v51, *(const void **)(a5 + 8), *(_QWORD *)a5);
  v40 = (const char *)v41;
  v39 = 16;
  if ( v60[0] < 0x10u )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"clearText.length >= AES_BLOCK_SIZE", v22);
    v19 = -1073741789;
LABEL_13:
    v21 = "BlockEncrypt(key->Ke, {AES_BLOCK_SIZE, IV}, ciphertext)";
    goto LABEL_9;
  }
  ((void (__fastcall *)(__int64 *, _QWORD, __int64, __int64, size_t *, _QWORD *))Kerb3961::EncryptCTS)(
    &v41,
    *(_QWORD *)(a1 + 144),
    v23,
    v52,
    &v39,
    v60);
  v19 = v41;
  if ( (int)v41 < 0 )
    goto LABEL_13;
  v42 = 0;
  v43 = 0;
  LODWORD(v44) = -1073741823;
  if ( *v53 )
  {
    v39 = 3;
    v40 = "tag";
    v24 = Kerb3961::Aes8009::DeriveKey(a1, (unsigned int)&cbBuffer, (_DWORD)v16, (unsigned int)&v39, (__int64)v53, *v16);
    if ( v43 )
      operator delete(v43, 0);
    v42 = *(_QWORD *)v24;
    v26 = *(void **)(v24 + 8);
    *(_QWORD *)v24 = 0;
    v43 = v26;
    v27 = *(_DWORD *)(v24 + 16);
    *(_QWORD *)(v24 + 8) = 0;
    LODWORD(v44) = v27;
    *(_DWORD *)(v24 + 16) = -1073741823;
    if ( pbBuffer )
      operator delete(pbBuffer, 0);
    v28 = (int)v44;
    if ( (int)v44 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"derivedIntegrityKey",
        (const char *)(unsigned int)v44,
        v25);
      v29 = v43;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v28;
      if ( v29 )
        operator delete(v29, 0);
      goto LABEL_34;
    }
    v16 = &v42;
  }
  v30 = Size;
  v31 = v46;
  v32 = *(_QWORD *)(a1 + 152);
  v40 = (const char *)v46;
  v39 = Size + 16;
  Kerb3961::GetHmac((unsigned int)&cbBuffer, v32, (_DWORD)v16, (unsigned int)&v39, *(unsigned int *)(a1 + 160));
  v34 = (int)v50;
  if ( (int)v50 >= 0 )
  {
    v40 = *(const char **)(a1 + 88);
    v39 = v30;
    Kerb3961::Split<2>(v55, &v45, &v39);
    memmove_0(v56, (const void *)v60[1], v30);
    v37 = pbBuffer;
    memcpy_0(v57, pbBuffer, *(_QWORD *)(a1 + 88));
    *(_QWORD *)a2 = v45;
    *(_DWORD *)(a2 + 16) = v14;
    *(_QWORD *)(a2 + 8) = v31;
    if ( v37 )
      operator delete(v37, 0);
    v36 = v43;
LABEL_35:
    if ( !v36 )
      return a2;
LABEL_36:
    operator delete(v36, 0);
    return a2;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v50, v33);
  v35 = pbBuffer;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v34;
  if ( v35 )
    operator delete(v35, 0);
  if ( v43 )
    operator delete(v43, 0);
  if ( v31 )
  {
    v36 = v31;
    goto LABEL_36;
  }
  return a2;
}

```

## disassembly

```asm
0x1800130b0  mov     [rsp-8+arg_18], rbx
0x1800130b5  push    rbp
0x1800130b6  push    rsi
0x1800130b7  push    rdi
0x1800130b8  push    r12
0x1800130ba  push    r13
0x1800130bc  push    r14
0x1800130be  push    r15
0x1800130c0  lea     rbp, [rsp-17h]
0x1800130c5  sub     rsp, 100h
0x1800130cc  mov     rax, cs:__security_cookie
0x1800130d3  xor     rax, rsp
0x1800130d6  mov     [rbp+47h+var_40], rax
0x1800130da  mov     rax, [rbp+47h+arg_28]
0x1800130de  mov     rsi, rdx
0x1800130e1  mov     r13, [rbp+47h+arg_20]
0x1800130e5  mov     r14, r8
0x1800130e8  mov     [rbp+47h+var_90], rax
0x1800130ec  mov     r15, rcx
0x1800130ef  mov     rax, [rcx+58h]
0x1800130f3  mov     [rsp+130h+var_F0], r9
0x1800130f8  mov     rdx, [r13+0]; char *
0x1800130fc  lea     rbx, [rdx+10h]
0x180013100  add     rax, rbx
0x180013103  mov     [rbp+47h+Size], rbx
0x180013107  cmp     rax, rdx
0x18001310a  ja      short loc_18001312D
0x18001310c  lea     rcx, aResultsizeClea; "resultSize > clearData.length"
0x180013113  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180013118  xor     edi, edi
0x18001311a  mov     [rsi], rdi
0x18001311d  mov     [rsi+8], rdi
0x180013121  mov     dword ptr [rsi+10h], 0C0000095h
0x180013128  jmp     loc_1800134A0
0x18001312d  mov     rdx, rax
0x180013130  lea     rcx, [rsp+130h+var_D0]
0x180013135  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001313a  mov     r12, [rbp+47h+var_C0]
0x18001313e  xor     edi, edi
0x180013140  test    r12d, r12d
0x180013143  jns     short loc_180013164
0x180013145  mov     edx, r12d; char *
0x180013148  lea     rcx, aResultbuffer; "resultBuffer"
0x18001314f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180013154  mov     [rsi], rdi
0x180013157  mov     [rsi+8], rdi
0x18001315b  mov     [rsi+10h], r12d
0x18001315f  jmp     loc_18001348F
0x180013164  mov     r14, [r14+8]
0x180013168  lea     rax, [r14+18h]
0x18001316c  mov     [rbp+47h+var_98], rax
0x180013170  cmp     [rax], rdi
0x180013173  jbe     loc_180013475
0x180013179  add     r14, 30h ; '0'
0x18001317d  cmp     [r14], rdi
0x180013180  jbe     loc_180013475
0x180013186  mov     rax, [rsp+130h+var_F0]
0x18001318b  lea     r8, [rsp+130h+var_100]
0x180013190  lea     rdx, [rsp+130h+var_D0]
0x180013195  mov     [rsp+130h+var_100], 10h
0x18001319e  lea     rcx, [rbp+47h+var_60]
0x1800131a2  mov     [rsp+130h+var_F8], rbx
0x1800131a7  mov     rax, [rax+8]
0x1800131ab  mov     [rsp+130h+var_F0], rax
0x1800131b0  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x1800131b5  mov     rax, [r13+0]
0x1800131b9  lea     r8, [rsp+130h+var_100]
0x1800131be  lea     rdx, [rbp+47h+var_50]
0x1800131c2  mov     [rsp+130h+var_F8], rax
0x1800131c7  lea     rcx, [rbp+47h+cbBuffer]
0x1800131cb  mov     [rsp+130h+var_100], 10h
0x1800131d4  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x1800131d9  mov     rax, [rsp+130h+var_F0]
0x1800131de  mov     r9d, 2; dwFlags
0x1800131e4  mov     r8d, [rbp+47h+cbBuffer]; cbBuffer
0x1800131e8  xor     ecx, ecx; hAlgorithm
0x1800131ea  mov     rdx, [rbp+47h+pbBuffer]; pbBuffer
0x1800131ee  movups  xmm0, xmmword ptr [rax]
0x1800131f1  mov     rax, [rbp+47h+var_58]
0x1800131f5  movdqu  xmmword ptr [rax], xmm0
0x1800131f9  call    cs:__imp_BCryptGenRandom
0x1800131ff  mov     ebx, eax
0x180013201  test    eax, eax
0x180013203  jns     short loc_180013222
0x180013205  lea     rcx, aRandomfillConf_0; "RandomFill(confounder)"
0x18001320c  mov     edx, ebx; char *
0x18001320e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180013213  mov     [rsi], rdi
0x180013216  mov     [rsi+8], rdi
0x18001321a  mov     [rsi+10h], ebx
0x18001321d  jmp     loc_18001348F
0x180013222  mov     r8, [r13+0]; Size
0x180013226  mov     rdx, [r13+8]; Src
0x18001322a  mov     rcx, [rbp+47h+var_A0]; void *
0x18001322e  call    memcpy_0
0x180013233  cmp     [rbp+47h+var_50], 10h
0x180013238  mov     rax, [rsp+130h+var_F0]
0x18001323d  mov     [rsp+130h+var_F8], rax
0x180013242  mov     [rsp+130h+var_100], 10h
0x18001324b  jnb     short loc_180013260
0x18001324d  lea     rcx, aCleartextLengt; "clearText.length >= AES_BLOCK_SIZE"
0x180013254  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180013259  mov     ebx, 0C0000023h
0x18001325e  jmp     short loc_180013290
0x180013260  mov     r9, [rbp+47h+var_98]
0x180013264  lea     rax, [rbp+47h+var_50]
0x180013268  mov     rdx, [r15+90h]
0x18001326f  lea     rcx, [rsp+130h+var_F0]
0x180013274  mov     [rsp+130h+var_108], rax
0x180013279  lea     rax, [rsp+130h+var_100]
0x18001327e  mov     [rsp+130h+var_110], rax
0x180013283  call    ?EncryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::EncryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x180013288  mov     ebx, dword ptr [rsp+130h+var_F0]
0x18001328c  test    ebx, ebx
0x18001328e  jns     short loc_18001329C
0x180013290  lea     rcx, aBlockencryptKe; "BlockEncrypt(key->Ke, {AES_BLOCK_SIZE, "...
0x180013297  jmp     loc_18001320C
0x18001329c  mov     rcx, [rbp+47h+var_90]
0x1800132a0  mov     r13d, 0C0000001h
0x1800132a6  mov     [rsp+130h+var_E8], rdi
0x1800132ab  mov     [rsp+130h+var_E0], rdi
0x1800132b0  mov     dword ptr [rsp+130h+var_D8], r13d
0x1800132b5  cmp     [rcx], rdi
0x1800132b8  jz      loc_18001337A
0x1800132be  lea     rax, aTag; "tag"
0x1800132c5  mov     [rsp+130h+var_100], 3
0x1800132ce  mov     [rsp+130h+var_F8], rax
0x1800132d3  lea     r9, [rsp+130h+var_100]
0x1800132d8  mov     rax, [r14]
0x1800132db  lea     rdx, [rbp+47h+cbBuffer]
0x1800132df  mov     [rsp+130h+var_108], rax
0x1800132e4  mov     r8, r14
0x1800132e7  mov     [rsp+130h+var_110], rcx
0x1800132ec  mov     rcx, r15
0x1800132ef  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z; Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x1800132f4  mov     rcx, [rsp+130h+var_E0]; void *
0x1800132f9  mov     rbx, rax
0x1800132fc  test    rcx, rcx
0x1800132ff  jz      short loc_180013308
0x180013301  xor     edx, edx; struct std::nothrow_t *
0x180013303  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013308  mov     rcx, [rbx]
0x18001330b  mov     [rsp+130h+var_E8], rcx
0x180013310  mov     rcx, [rbx+8]
0x180013314  mov     [rbx], rdi
0x180013317  mov     [rsp+130h+var_E0], rcx
0x18001331c  mov     eax, [rbx+10h]
0x18001331f  mov     [rbx+8], rdi
0x180013323  mov     dword ptr [rsp+130h+var_D8], eax
0x180013327  mov     [rbx+10h], r13d
0x18001332b  mov     rcx, [rbp+47h+pbBuffer]; void *
0x18001332f  test    rcx, rcx
0x180013332  jz      short loc_18001333B
0x180013334  xor     edx, edx; struct std::nothrow_t *
0x180013336  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001333b  mov     ebx, dword ptr [rsp+130h+var_D8]
0x18001333f  test    ebx, ebx
0x180013341  jns     short loc_180013375
0x180013343  mov     edx, ebx; char *
0x180013345  lea     rcx, aDerivedintegri; "derivedIntegrityKey"
0x18001334c  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180013351  mov     rcx, [rsp+130h+var_E0]; void *
0x180013356  mov     [rsi], rdi
0x180013359  mov     [rsi+8], rdi
0x18001335d  mov     [rsi+10h], ebx
0x180013360  test    rcx, rcx
0x180013363  jz      loc_18001348F
0x180013369  xor     edx, edx; struct std::nothrow_t *
0x18001336b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013370  jmp     loc_18001348F
0x180013375  lea     r14, [rsp+130h+var_E8]
0x18001337a  mov     r13, [rbp+47h+Size]
0x18001337e  lea     r9, [rsp+130h+var_100]
0x180013383  mov     rbx, [rsp+130h+var_C8]
0x180013388  lea     rcx, [rbp+47h+cbBuffer]
0x18001338c  mov     rdx, [r15+98h]
0x180013393  mov     r8, r14
0x180013396  mov     [rsp+130h+var_F8], rbx
0x18001339b  lea     rax, [r13+10h]
0x18001339f  mov     [rsp+130h+var_100], rax
0x1800133a4  mov     eax, [r15+0A0h]
0x1800133ab  mov     [rsp+130h+var_110], rax
0x1800133b0  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x1800133b5  mov     r14d, dword ptr [rbp+47h+var_A8]
0x1800133b9  test    r14d, r14d
0x1800133bc  jns     short loc_18001340A
0x1800133be  mov     edx, r14d; char *
0x1800133c1  lea     rcx, aHmac; "hmac"
0x1800133c8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800133cd  mov     rcx, [rbp+47h+pbBuffer]; void *
0x1800133d1  mov     [rsi], rdi
0x1800133d4  mov     [rsi+8], rdi
0x1800133d8  mov     [rsi+10h], r14d
0x1800133dc  test    rcx, rcx
0x1800133df  jz      short loc_1800133E8
0x1800133e1  xor     edx, edx; struct std::nothrow_t *
0x1800133e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800133e8  mov     rcx, [rsp+130h+var_E0]; void *
0x1800133ed  test    rcx, rcx
0x1800133f0  jz      short loc_1800133F9
0x1800133f2  xor     edx, edx; struct std::nothrow_t *
0x1800133f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800133f9  test    rbx, rbx
0x1800133fc  jz      loc_1800134A0
0x180013402  mov     rcx, rbx
0x180013405  jmp     loc_180013499
0x18001340a  mov     rax, [r15+58h]
0x18001340e  lea     r8, [rsp+130h+var_100]
0x180013413  lea     rdx, [rsp+130h+var_D0]
0x180013418  mov     [rsp+130h+var_F8], rax
0x18001341d  lea     rcx, [rbp+47h+var_80]
0x180013421  mov     [rsp+130h+var_100], r13
0x180013426  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x18001342b  mov     rdx, [rbp+47h+Src]; Src
0x18001342f  mov     r8, r13; Size
0x180013432  mov     rcx, [rbp+47h+var_78]; void *
0x180013436  call    memmove_0
0x18001343b  mov     r14, [rbp+47h+pbBuffer]
0x18001343f  mov     r8, [r15+58h]; Size
0x180013443  mov     rdx, r14; Src
0x180013446  mov     rcx, [rbp+47h+var_68]; void *
0x18001344a  call    memcpy_0
0x18001344f  mov     rax, [rsp+130h+var_D0]
0x180013454  mov     [rsi], rax
0x180013457  mov     [rsi+10h], r12d
0x18001345b  mov     [rsi+8], rbx
0x18001345f  test    r14, r14
0x180013462  jz      short loc_18001346E
0x180013464  xor     edx, edx; struct std::nothrow_t *
0x180013466  mov     rcx, r14; void *
0x180013469  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001346e  mov     rcx, [rsp+130h+var_E0]
0x180013473  jmp     short loc_180013494
0x180013475  lea     rcx, aKeyKeLength0Ke; "key->Ke.length > 0 && key->Ki.length > "...
0x18001347c  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180013481  mov     [rsi], rdi
0x180013484  mov     [rsi+8], rdi
0x180013488  mov     dword ptr [rsi+10h], 0C000000Dh
0x18001348f  mov     rcx, [rsp+130h+var_C8]; void *
0x180013494  test    rcx, rcx
0x180013497  jz      short loc_1800134A0
0x180013499  xor     edx, edx; struct std::nothrow_t *
0x18001349b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800134a0  mov     rax, rsi
0x1800134a3  mov     rcx, [rbp+47h+var_40]
0x1800134a7  xor     rcx, rsp; StackCookie
0x1800134aa  call    __security_check_cookie
0x1800134af  mov     rbx, [rsp+130h+arg_18]
0x1800134b7  add     rsp, 100h
0x1800134be  pop     r15
0x1800134c0  pop     r14
0x1800134c2  pop     r13
0x1800134c4  pop     r12
0x1800134c6  pop     rdi
0x1800134c7  pop     rsi
0x1800134c8  pop     rbp
0x1800134c9  retn
```
