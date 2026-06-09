# Kerb3961::Aes8009::Encrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800083f0`
- end: `0x180008803`
- name: `?Encrypt@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `1043`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001580`
- `0x180005b1c`
- `0x180007e9c`
- `0x1800083f0`
- `0x18000a1c8`
- `0x18000a6c0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012300`

## import_xrefs

- `cng!BCryptGenRandom` at `0x180008539`
- `cng!BCryptGenRandom` at `0x180008539`

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
  void *v23; // r8
  __int64 v24; // rbx
  int v25; // r8d
  const char *v26; // rcx
  int v27; // eax
  int v28; // ebx
  const char *v29; // rcx
  size_t v30; // r13
  const char *v31; // rbx
  __int64 v32; // rdx
  int v33; // r8d
  int v34; // r14d
  PUCHAR v35; // rcx
  const char *v36; // rcx
  PUCHAR v37; // r14
  size_t v39; // [rsp+30h] [rbp-B9h] BYREF
  const char *v40; // [rsp+38h] [rbp-B1h]
  __int64 v41; // [rsp+40h] [rbp-A9h] BYREF
  __int64 v42; // [rsp+48h] [rbp-A1h] BYREF
  const char *v43; // [rsp+50h] [rbp-99h]
  char *v44; // [rsp+58h] [rbp-91h]
  __int64 v45; // [rsp+60h] [rbp-89h] BYREF
  const char *v46; // [rsp+68h] [rbp-81h]
  char *v47; // [rsp+70h] [rbp-79h]
  ULONG cbBuffer; // [rsp+78h] [rbp-71h] BYREF
  PUCHAR pbBuffer; // [rsp+80h] [rbp-69h]
  char *v50; // [rsp+88h] [rbp-61h]
  void *v51; // [rsp+90h] [rbp-59h]
  _QWORD *v52; // [rsp+98h] [rbp-51h]
  _QWORD *v53; // [rsp+A0h] [rbp-49h]
  size_t Size; // [rsp+A8h] [rbp-41h]
  char v55[8]; // [rsp+B0h] [rbp-39h] BYREF
  void *v56; // [rsp+B8h] [rbp-31h]
  void *v57; // [rsp+C8h] [rbp-21h]
  char v58[8]; // [rsp+D0h] [rbp-19h] BYREF
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
  v52 = (_QWORD *)(v15 + 24);
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
  memmove(v51, *(const void **)(a5 + 8), *(_QWORD *)a5);
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
  Kerb3961::EncryptCTS((NTSTATUS *)&v41, *(char **)(a1 + 144), v23, v52, &v39, v60);
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
      Kerb3961Free(v43);
    v42 = *(_QWORD *)v24;
    v26 = *(const char **)(v24 + 8);
    *(_QWORD *)v24 = 0;
    v43 = v26;
    v27 = *(_DWORD *)(v24 + 16);
    *(_QWORD *)(v24 + 8) = 0;
    LODWORD(v44) = v27;
    *(_DWORD *)(v24 + 16) = -1073741823;
    if ( pbBuffer )
      Kerb3961Free(pbBuffer);
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
        Kerb3961Free(v29);
      goto LABEL_34;
    }
    v16 = &v42;
  }
  v30 = Size;
  v31 = v46;
  v32 = *(_QWORD *)(a1 + 152);
  v40 = v46;
  v39 = Size + 16;
  Kerb3961::GetHmac((unsigned int)&cbBuffer, v32, (_DWORD)v16, (unsigned int)&v39, *(unsigned int *)(a1 + 160));
  v34 = (int)v50;
  if ( (int)v50 >= 0 )
  {
    v40 = *(const char **)(a1 + 88);
    v39 = v30;
    Kerb3961::Split<2>(v55, &v45, &v39);
    memmove(v56, (const void *)v60[1], v30);
    v37 = pbBuffer;
    memmove(v57, pbBuffer, *(_QWORD *)(a1 + 88));
    *(_QWORD *)a2 = v45;
    *(_DWORD *)(a2 + 16) = v14;
    *(_QWORD *)(a2 + 8) = v31;
    if ( v37 )
      Kerb3961Free(v37);
    v36 = v43;
LABEL_35:
    if ( !v36 )
      return a2;
LABEL_36:
    Kerb3961Free(v36);
    return a2;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v50, v33);
  v35 = pbBuffer;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v34;
  if ( v35 )
    Kerb3961Free(v35);
  if ( v43 )
    Kerb3961Free(v43);
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
0x1800083f0  mov     [rsp-8+arg_18], rbx
0x1800083f5  push    rbp
0x1800083f6  push    rsi
0x1800083f7  push    rdi
0x1800083f8  push    r12
0x1800083fa  push    r13
0x1800083fc  push    r14
0x1800083fe  push    r15
0x180008400  lea     rbp, [rsp-17h]
0x180008405  sub     rsp, 100h
0x18000840c  mov     rax, cs:__security_cookie
0x180008413  xor     rax, rsp
0x180008416  mov     [rbp+47h+var_40], rax
0x18000841a  mov     rax, [rbp+47h+arg_28]
0x18000841e  mov     rsi, rdx
0x180008421  mov     r13, [rbp+47h+arg_20]
0x180008425  mov     r14, r8
0x180008428  mov     [rbp+47h+var_90], rax
0x18000842c  mov     r15, rcx
0x18000842f  mov     rax, [rcx+58h]
0x180008433  mov     [rsp+130h+var_F0], r9
0x180008438  mov     rdx, [r13+0]; char *
0x18000843c  lea     rbx, [rdx+10h]
0x180008440  add     rax, rbx
0x180008443  mov     [rbp+47h+Size], rbx
0x180008447  cmp     rax, rdx
0x18000844a  ja      short loc_18000846D
0x18000844c  lea     rcx, aResultsizeClea; "resultSize > clearData.length"
0x180008453  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180008458  xor     edi, edi
0x18000845a  mov     [rsi], rdi
0x18000845d  mov     [rsi+8], rdi
0x180008461  mov     dword ptr [rsi+10h], 0C0000095h
0x180008468  jmp     loc_1800087D8
0x18000846d  mov     rdx, rax
0x180008470  lea     rcx, [rsp+130h+var_D0]
0x180008475  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000847a  mov     r12, [rbp+47h+var_C0]
0x18000847e  xor     edi, edi
0x180008480  test    r12d, r12d
0x180008483  jns     short loc_1800084A4
0x180008485  mov     edx, r12d; char *
0x180008488  lea     rcx, aResultbuffer; "resultBuffer"
0x18000848f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180008494  mov     [rsi], rdi
0x180008497  mov     [rsi+8], rdi
0x18000849b  mov     [rsi+10h], r12d
0x18000849f  jmp     loc_1800087C9
0x1800084a4  mov     r14, [r14+8]
0x1800084a8  lea     rax, [r14+18h]
0x1800084ac  mov     [rbp+47h+var_98], rax
0x1800084b0  cmp     [rax], rdi
0x1800084b3  jbe     loc_1800087AF
0x1800084b9  add     r14, 30h ; '0'
0x1800084bd  cmp     [r14], rdi
0x1800084c0  jbe     loc_1800087AF
0x1800084c6  mov     rax, [rsp+130h+var_F0]
0x1800084cb  lea     r8, [rsp+130h+var_100]
0x1800084d0  lea     rdx, [rsp+130h+var_D0]
0x1800084d5  mov     [rsp+130h+var_100], 10h
0x1800084de  lea     rcx, [rbp+47h+var_60]
0x1800084e2  mov     [rsp+130h+var_F8], rbx
0x1800084e7  mov     rax, [rax+8]
0x1800084eb  mov     [rsp+130h+var_F0], rax
0x1800084f0  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x1800084f5  mov     rax, [r13+0]
0x1800084f9  lea     r8, [rsp+130h+var_100]
0x1800084fe  lea     rdx, [rbp+47h+var_50]
0x180008502  mov     [rsp+130h+var_F8], rax
0x180008507  lea     rcx, [rbp+47h+cbBuffer]
0x18000850b  mov     [rsp+130h+var_100], 10h
0x180008514  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180008519  mov     rax, [rsp+130h+var_F0]
0x18000851e  mov     r9d, 2; dwFlags
0x180008524  mov     r8d, [rbp+47h+cbBuffer]; cbBuffer
0x180008528  xor     ecx, ecx; hAlgorithm
0x18000852a  mov     rdx, [rbp+47h+pbBuffer]; pbBuffer
0x18000852e  movups  xmm0, xmmword ptr [rax]
0x180008531  mov     rax, [rbp+47h+var_58]
0x180008535  movdqu  xmmword ptr [rax], xmm0
0x180008539  call    cs:__imp_BCryptGenRandom
0x180008540  nop     dword ptr [rax+rax+00h]
0x180008545  mov     ebx, eax
0x180008547  test    eax, eax
0x180008549  jns     short loc_180008568
0x18000854b  lea     rcx, aRandomfillConf_0; "RandomFill(confounder)"
0x180008552  mov     edx, ebx; char *
0x180008554  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180008559  mov     [rsi], rdi
0x18000855c  mov     [rsi+8], rdi
0x180008560  mov     [rsi+10h], ebx
0x180008563  jmp     loc_1800087C9
0x180008568  mov     r8, [r13+0]; Size
0x18000856c  mov     rdx, [r13+8]; Src
0x180008570  mov     rcx, [rbp+47h+var_A0]; void *
0x180008574  call    memmove
0x180008579  cmp     [rbp+47h+var_50], 10h
0x18000857e  mov     rax, [rsp+130h+var_F0]
0x180008583  mov     [rsp+130h+var_F8], rax
0x180008588  mov     [rsp+130h+var_100], 10h
0x180008591  jnb     short loc_1800085A6
0x180008593  lea     rcx, aCleartextLengt; "clearText.length >= AES_BLOCK_SIZE"
0x18000859a  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000859f  mov     ebx, 0C0000023h
0x1800085a4  jmp     short loc_1800085D6
0x1800085a6  mov     r9, [rbp+47h+var_98]
0x1800085aa  lea     rax, [rbp+47h+var_50]
0x1800085ae  mov     rdx, [r15+90h]
0x1800085b5  lea     rcx, [rsp+130h+var_F0]
0x1800085ba  mov     [rsp+130h+var_108], rax
0x1800085bf  lea     rax, [rsp+130h+var_100]
0x1800085c4  mov     [rsp+130h+var_110], rax
0x1800085c9  call    ?EncryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::EncryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x1800085ce  mov     ebx, dword ptr [rsp+130h+var_F0]
0x1800085d2  test    ebx, ebx
0x1800085d4  jns     short loc_1800085E2
0x1800085d6  lea     rcx, aBlockencryptKe; "BlockEncrypt(key->Ke, {AES_BLOCK_SIZE, "...
0x1800085dd  jmp     loc_180008552
0x1800085e2  mov     rcx, [rbp+47h+var_90]
0x1800085e6  mov     r13d, 0C0000001h
0x1800085ec  mov     [rsp+130h+var_E8], rdi
0x1800085f1  mov     [rsp+130h+var_E0], rdi
0x1800085f6  mov     dword ptr [rsp+130h+var_D8], r13d
0x1800085fb  cmp     [rcx], rdi
0x1800085fe  jz      loc_1800086BA
0x180008604  lea     rax, aTag; "tag"
0x18000860b  mov     [rsp+130h+var_100], 3
0x180008614  mov     [rsp+130h+var_F8], rax
0x180008619  lea     r9, [rsp+130h+var_100]
0x18000861e  mov     rax, [r14]
0x180008621  lea     rdx, [rbp+47h+cbBuffer]
0x180008625  mov     [rsp+130h+var_108], rax
0x18000862a  mov     r8, r14
0x18000862d  mov     [rsp+130h+var_110], rcx
0x180008632  mov     rcx, r15
0x180008635  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z; Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x18000863a  mov     rcx, [rsp+130h+var_E0]
0x18000863f  mov     rbx, rax
0x180008642  test    rcx, rcx
0x180008645  jz      short loc_18000864C
0x180008647  call    Kerb3961Free
0x18000864c  mov     rcx, [rbx]
0x18000864f  mov     [rsp+130h+var_E8], rcx
0x180008654  mov     rcx, [rbx+8]
0x180008658  mov     [rbx], rdi
0x18000865b  mov     [rsp+130h+var_E0], rcx
0x180008660  mov     eax, [rbx+10h]
0x180008663  mov     [rbx+8], rdi
0x180008667  mov     dword ptr [rsp+130h+var_D8], eax
0x18000866b  mov     [rbx+10h], r13d
0x18000866f  mov     rcx, [rbp+47h+pbBuffer]
0x180008673  test    rcx, rcx
0x180008676  jz      short loc_18000867D
0x180008678  call    Kerb3961Free
0x18000867d  mov     ebx, dword ptr [rsp+130h+var_D8]
0x180008681  test    ebx, ebx
0x180008683  jns     short loc_1800086B5
0x180008685  mov     edx, ebx; char *
0x180008687  lea     rcx, aDerivedintegri; "derivedIntegrityKey"
0x18000868e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180008693  mov     rcx, [rsp+130h+var_E0]
0x180008698  mov     [rsi], rdi
0x18000869b  mov     [rsi+8], rdi
0x18000869f  mov     [rsi+10h], ebx
0x1800086a2  test    rcx, rcx
0x1800086a5  jz      loc_1800087C9
0x1800086ab  call    Kerb3961Free
0x1800086b0  jmp     loc_1800087C9
0x1800086b5  lea     r14, [rsp+130h+var_E8]
0x1800086ba  mov     r13, [rbp+47h+Size]
0x1800086be  lea     r9, [rsp+130h+var_100]
0x1800086c3  mov     rbx, [rsp+130h+var_C8]
0x1800086c8  lea     rcx, [rbp+47h+cbBuffer]
0x1800086cc  mov     rdx, [r15+98h]
0x1800086d3  mov     r8, r14
0x1800086d6  mov     [rsp+130h+var_F8], rbx
0x1800086db  lea     rax, [r13+10h]
0x1800086df  mov     [rsp+130h+var_100], rax
0x1800086e4  mov     eax, [r15+0A0h]
0x1800086eb  mov     [rsp+130h+var_110], rax
0x1800086f0  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x1800086f5  mov     r14d, dword ptr [rbp+47h+var_A8]
0x1800086f9  test    r14d, r14d
0x1800086fc  jns     short loc_180008746
0x1800086fe  mov     edx, r14d; char *
0x180008701  lea     rcx, aHmac; "hmac"
0x180008708  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000870d  mov     rcx, [rbp+47h+pbBuffer]
0x180008711  mov     [rsi], rdi
0x180008714  mov     [rsi+8], rdi
0x180008718  mov     [rsi+10h], r14d
0x18000871c  test    rcx, rcx
0x18000871f  jz      short loc_180008726
0x180008721  call    Kerb3961Free
0x180008726  mov     rcx, [rsp+130h+var_E0]
0x18000872b  test    rcx, rcx
0x18000872e  jz      short loc_180008735
0x180008730  call    Kerb3961Free
0x180008735  test    rbx, rbx
0x180008738  jz      loc_1800087D8
0x18000873e  mov     rcx, rbx
0x180008741  jmp     loc_1800087D3
0x180008746  mov     rax, [r15+58h]
0x18000874a  lea     r8, [rsp+130h+var_100]
0x18000874f  lea     rdx, [rsp+130h+var_D0]
0x180008754  mov     [rsp+130h+var_F8], rax
0x180008759  lea     rcx, [rbp+47h+var_80]
0x18000875d  mov     [rsp+130h+var_100], r13
0x180008762  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180008767  mov     rdx, [rbp+47h+Src]; Src
0x18000876b  mov     r8, r13; Size
0x18000876e  mov     rcx, [rbp+47h+var_78]; void *
0x180008772  call    memmove
0x180008777  mov     r14, [rbp+47h+pbBuffer]
0x18000877b  mov     r8, [r15+58h]; Size
0x18000877f  mov     rdx, r14; Src
0x180008782  mov     rcx, [rbp+47h+var_68]; void *
0x180008786  call    memmove
0x18000878b  mov     rax, [rsp+130h+var_D0]
0x180008790  mov     [rsi], rax
0x180008793  mov     [rsi+10h], r12d
0x180008797  mov     [rsi+8], rbx
0x18000879b  test    r14, r14
0x18000879e  jz      short loc_1800087A8
0x1800087a0  mov     rcx, r14
0x1800087a3  call    Kerb3961Free
0x1800087a8  mov     rcx, [rsp+130h+var_E0]
0x1800087ad  jmp     short loc_1800087CE
0x1800087af  lea     rcx, aKeyKeLength0Ke; "key->Ke.length > 0 && key->Ki.length > "...
0x1800087b6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800087bb  mov     [rsi], rdi
0x1800087be  mov     [rsi+8], rdi
0x1800087c2  mov     dword ptr [rsi+10h], 0C000000Dh
0x1800087c9  mov     rcx, [rsp+130h+var_C8]
0x1800087ce  test    rcx, rcx
0x1800087d1  jz      short loc_1800087D8
0x1800087d3  call    Kerb3961Free
0x1800087d8  mov     rax, rsi
0x1800087db  mov     rcx, [rbp+47h+var_40]
0x1800087df  xor     rcx, rsp; StackCookie
0x1800087e2  call    __security_check_cookie
0x1800087e7  mov     rbx, [rsp+130h+arg_18]
0x1800087ef  add     rsp, 100h
0x1800087f6  pop     r15
0x1800087f8  pop     r14
0x1800087fa  pop     r13
0x1800087fc  pop     r12
0x1800087fe  pop     rdi
0x1800087ff  pop     rsi
0x180008800  pop     rbp
0x180008801  retn
```
