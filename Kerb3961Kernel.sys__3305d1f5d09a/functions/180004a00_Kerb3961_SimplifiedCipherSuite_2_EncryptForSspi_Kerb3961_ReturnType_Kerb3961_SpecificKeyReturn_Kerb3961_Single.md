# Kerb3961::SimplifiedCipherSuite<2>::EncryptForSspi(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180004a00`
- end: `0x180004e3a`
- name: `?EncryptForSspi@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@22@Z`
- size: `1082`
- prototype: `__int64 __fastcall(int, int, int, int, char *, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180001464`
- `0x180001580`
- `0x180001794`
- `0x180004a00`
- `0x180005b1c`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`
- `0x180012300`

## import_xrefs

- `cng!BCryptGenRandom` at `0x180004bc6`
- `cng!BCryptGenRandom` at `0x180004c2b`
- `cng!BCryptGenRandom` at `0x180004bc6`
- `cng!BCryptGenRandom` at `0x180004c2b`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::EncryptForSspi(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        char *a5,
        __int128 *a6,
        const void **a7)
{
  __int64 v9; // rcx
  __int64 v10; // r15
  unsigned __int64 v11; // r9
  unsigned __int64 v12; // r8
  size_t v13; // rbx
  const char *v14; // rdx
  int v15; // r8d
  int v16; // r12d
  const void *v17; // rcx
  NTSTATUS v18; // ebx
  int v19; // r8d
  char *v20; // rcx
  __int64 v21; // rax
  int v22; // r8d
  size_t v23; // r13
  const void *v24; // rbx
  int v25; // r15d
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  int v28; // r8d
  int v29; // ebx
  const void *v30; // rcx
  __int64 v31; // rax
  int v32; // r8d
  int v33; // r14d
  char *v35; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  const void *v37; // [rsp+40h] [rbp-C0h]
  char *v38; // [rsp+48h] [rbp-B8h]
  size_t v39; // [rsp+50h] [rbp-B0h] BYREF
  const void *v40; // [rsp+58h] [rbp-A8h]
  char *v41; // [rsp+60h] [rbp-A0h]
  size_t v42; // [rsp+70h] [rbp-90h]
  unsigned __int64 v43; // [rsp+78h] [rbp-88h]
  __int64 v44; // [rsp+80h] [rbp-80h]
  __int128 *v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h]
  __int64 v47; // [rsp+A0h] [rbp-60h] BYREF
  size_t v48; // [rsp+A8h] [rbp-58h]
  __int128 v49; // [rsp+B0h] [rbp-50h]
  ULONG v50; // [rsp+C0h] [rbp-40h]
  ULONG v51; // [rsp+C4h] [rbp-3Ch]
  PUCHAR v52; // [rsp+C8h] [rbp-38h]
  __int128 v53; // [rsp+D0h] [rbp-30h]
  __int64 cbBuffer; // [rsp+E0h] [rbp-20h] BYREF
  PUCHAR pbBuffer; // [rsp+E8h] [rbp-18h]
  void *v56; // [rsp+F8h] [rbp-8h]
  ULONG v57[2]; // [rsp+100h] [rbp+0h]
  PUCHAR v58; // [rsp+108h] [rbp+8h]
  void *v59; // [rsp+118h] [rbp+18h]
  _QWORD v60[5]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v61[24]; // [rsp+148h] [rbp+48h] BYREF
  void *v62; // [rsp+160h] [rbp+60h]

  v35 = a5;
  v45 = a6;
  if ( (_QWORD *)*a3 == a1 )
  {
    v9 = a1[12];
    v10 = a3[1];
    v60[1] = *(_QWORD *)(a4 + 8);
    v60[0] = v9;
    v44 = v9;
    v46 = v10 + 24;
    if ( !*(_QWORD *)(v10 + 24) && !*(_QWORD *)(v10 + 48) )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"key->Ke.length > 0 || key->Ki.length > 0",
        a5);
      goto LABEL_3;
    }
    v11 = *(_QWORD *)a5;
    v12 = a1[11];
    v42 = (size_t)*a7;
    v43 = v11;
    v13 = v11 + v42 - 1 + v9 - (v11 + v42 - 1 + v9) % v12 + v12;
    if ( !v11 || *(_QWORD *)a6 )
      v13 += 16LL;
    v14 = (const char *)(v13 + a1[10]);
    if ( (unsigned __int64)v14 <= v11 )
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"finalSize > clearData.length", v14);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -1073741675;
      return a2;
    }
    Kerb3961::MakeBuffer(&v36);
    v16 = (int)v38;
    if ( (int)v38 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"result",
        (const char *)(unsigned int)v38,
        v15);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v16;
      goto LABEL_14;
    }
    v40 = (const void *)a1[10];
    v39 = v13;
    Kerb3961::Split<2>(v61, &v36, &v39);
    v47 = a1[12];
    *(_QWORD *)&v49 = v13 - v42 - v43 - v44;
    v48 = *(_QWORD *)v35;
    *((_QWORD *)&v49 + 1) = *a7;
    Kerb3961::Split<4>(&cbBuffer, v61, &v47);
    v18 = BCryptGenRandom(0, pbBuffer, cbBuffer, 2u);
    if ( v18 < 0 )
    {
      v20 = "RandomFill(confounder)";
LABEL_18:
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v20, (const char *)(unsigned int)v18, v19);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v18;
      goto LABEL_14;
    }
    memmove(v56, *((const void **)v35 + 1), *(_QWORD *)v35);
    memmove(v59, a7[1], (size_t)*a7);
    v18 = BCryptGenRandom(0, v58, v57[0], 2u);
    if ( v18 < 0 )
    {
      v20 = "RandomFill(pad)";
      goto LABEL_18;
    }
    if ( *(_QWORD *)v45 )
    {
      v26 = *v45;
      v27 = *(_OWORD *)a7;
      v47 = cbBuffer;
      v48 = (size_t)pbBuffer;
      v50 = v57[0];
      v51 = v57[1];
      v52 = v58;
      v49 = v26;
      v53 = v27;
      Kerb3961::Concatenate<4>(&v39, &v47);
      v29 = (int)v41;
      if ( (int)v41 < 0 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"totalChecksumInput",
          (const char *)(unsigned int)v41,
          v28);
        v30 = v40;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v29;
        if ( !v30 )
          goto LABEL_14;
        goto LABEL_25;
      }
      v31 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, __int64, size_t *))(*a1 + 424LL))(a1, &v47, v10 + 48, &v39);
      v23 = *(_QWORD *)v31;
      v24 = *(const void **)(v31 + 8);
      v25 = *(_DWORD *)(v31 + 16);
      *(_QWORD *)v31 = 0;
      *(_QWORD *)(v31 + 8) = 0;
      *(_DWORD *)(v31 + 16) = -1073741823;
      if ( v48 )
        Kerb3961Free(v48);
    }
    else
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD *, size_t *, __int64, _BYTE *))(*a1 + 424LL))(a1, &v39, v10 + 48, v61);
      v23 = *(_QWORD *)v21;
      v24 = *(const void **)(v21 + 8);
      v25 = *(_DWORD *)(v21 + 16);
      *(_QWORD *)v21 = 0;
      *(_QWORD *)(v21 + 8) = 0;
      *(_DWORD *)(v21 + 16) = -1073741823;
    }
    if ( v40 )
      Kerb3961Free(v40);
    if ( v25 >= 0 )
    {
      memmove(v62, v24, v23);
      v33 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, char **, __int64, _QWORD *, _BYTE *))(*a1 + 432LL))(
                         a1,
                         &v35,
                         v46,
                         v60,
                         v61);
      if ( v33 >= 0 )
      {
        *(_QWORD *)a2 = v36;
        *(_QWORD *)(a2 + 8) = v37;
        *(_DWORD *)(a2 + 16) = v16;
        if ( !v24 )
          return a2;
        v17 = v24;
        goto LABEL_38;
      }
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"BlockEncrypt(key->Ke, IV, encryptedPart)",
        (const char *)(unsigned int)v33,
        v32);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v33;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v25, v22);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v25;
    }
    if ( !v24 )
    {
LABEL_14:
      v17 = v37;
      if ( !v37 )
        return a2;
LABEL_38:
      Kerb3961Free(v17);
      return a2;
    }
    v30 = v24;
LABEL_25:
    Kerb3961Free(v30);
    goto LABEL_14;
  }
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"specificKey.algorithm == this", a5);
LABEL_3:
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = -1073741811;
  return a2;
}

```

## disassembly

```asm
0x180004a00  mov     [rsp-8+arg_18], rbx
0x180004a05  push    rbp
0x180004a06  push    rsi
0x180004a07  push    rdi
0x180004a08  push    r12
0x180004a0a  push    r13
0x180004a0c  push    r14
0x180004a0e  push    r15
0x180004a10  lea     rbp, [rsp-70h]
0x180004a15  sub     rsp, 170h
0x180004a1c  mov     rax, cs:__security_cookie
0x180004a23  xor     rax, rsp
0x180004a26  mov     [rbp+0A0h+var_38], rax
0x180004a2a  mov     rsi, rdx
0x180004a2d  mov     rdx, [rbp+0A0h+arg_20]; char *
0x180004a34  mov     r14, rcx
0x180004a37  mov     r10, [rbp+0A0h+arg_28]
0x180004a3e  mov     r13, [rbp+0A0h+arg_30]
0x180004a45  mov     [rsp+1A0h+var_170], rdx
0x180004a4a  mov     [rbp+0A0h+var_118], r10
0x180004a4e  cmp     [r8], rcx
0x180004a51  jz      short loc_180004A74
0x180004a53  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x180004a5a  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004a5f  xor     edi, edi
0x180004a61  mov     [rsi], rdi
0x180004a64  mov     [rsi+8], rdi
0x180004a68  mov     dword ptr [rsi+10h], 0C000000Dh
0x180004a6f  jmp     loc_180004E0F
0x180004a74  mov     rax, [r9+8]
0x180004a78  xor     edi, edi
0x180004a7a  mov     rcx, [rcx+60h]
0x180004a7e  mov     r15, [r8+8]
0x180004a82  mov     [rbp+0A0h+var_78], rax
0x180004a86  mov     [rbp+0A0h+var_80], rcx
0x180004a8a  mov     [rbp+0A0h+var_120], rcx
0x180004a8e  lea     rax, [r15+18h]
0x180004a92  mov     [rbp+0A0h+var_110], rax
0x180004a96  cmp     [rax], rdi
0x180004a99  ja      short loc_180004AAF
0x180004a9b  cmp     [r15+30h], rdi
0x180004a9f  ja      short loc_180004AAF
0x180004aa1  lea     rcx, aKeyKeLength0Ke_0; "key->Ke.length > 0 || key->Ki.length > "...
0x180004aa8  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004aad  jmp     short loc_180004A61
0x180004aaf  mov     r9, [rdx]
0x180004ab2  xor     edx, edx
0x180004ab4  mov     rax, [r13+0]
0x180004ab8  mov     r8, [r14+58h]
0x180004abc  mov     [rsp+1A0h+var_130], rax
0x180004ac1  dec     rax
0x180004ac4  add     rax, r9
0x180004ac7  mov     [rsp+1A0h+var_128], r9
0x180004acc  add     rcx, rax
0x180004acf  mov     rax, rcx
0x180004ad2  div     r8
0x180004ad5  sub     rcx, rdx
0x180004ad8  lea     rbx, [rcx+r8]
0x180004adc  test    r9, r9
0x180004adf  jz      short loc_180004AE6
0x180004ae1  cmp     [r10], rdi
0x180004ae4  jz      short loc_180004AEA
0x180004ae6  add     rbx, 10h
0x180004aea  mov     rdx, [r14+50h]
0x180004aee  add     rdx, rbx; char *
0x180004af1  cmp     rdx, r9
0x180004af4  ja      short loc_180004B15
0x180004af6  lea     rcx, aFinalsizeClear; "finalSize > clearData.length"
0x180004afd  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004b02  mov     [rsi], rdi
0x180004b05  mov     [rsi+8], rdi
0x180004b09  mov     dword ptr [rsi+10h], 0C0000095h
0x180004b10  jmp     loc_180004E0F
0x180004b15  lea     rcx, [rsp+1A0h+var_168]
0x180004b1a  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180004b1f  mov     r12, [rsp+1A0h+var_158]
0x180004b24  test    r12d, r12d
0x180004b27  jns     short loc_180004B56
0x180004b29  mov     edx, r12d; char *
0x180004b2c  lea     rcx, aResult; "result"
0x180004b33  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180004b38  mov     [rsi], rdi
0x180004b3b  mov     [rsi+8], rdi
0x180004b3f  mov     [rsi+10h], r12d
0x180004b43  mov     rcx, [rsp+1A0h+var_160]
0x180004b48  test    rcx, rcx
0x180004b4b  jz      loc_180004E0F
0x180004b51  jmp     loc_180004E0A
0x180004b56  mov     rax, [r14+50h]
0x180004b5a  lea     r8, [rsp+1A0h+var_150]
0x180004b5f  lea     rdx, [rsp+1A0h+var_168]
0x180004b64  mov     [rsp+1A0h+var_148], rax
0x180004b69  lea     rcx, [rbp+0A0h+var_58]
0x180004b6d  mov     [rsp+1A0h+var_150], rbx
0x180004b72  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180004b77  mov     rax, [r14+60h]
0x180004b7b  lea     r8, [rbp+0A0h+var_100]
0x180004b7f  sub     rbx, [rsp+1A0h+var_130]
0x180004b84  lea     rdx, [rbp+0A0h+var_58]
0x180004b88  sub     rbx, [rsp+1A0h+var_128]
0x180004b8d  lea     rcx, [rbp+0A0h+cbBuffer]
0x180004b91  sub     rbx, [rbp+0A0h+var_120]
0x180004b95  mov     [rbp+0A0h+var_100], rax
0x180004b99  mov     rax, [rsp+1A0h+var_170]
0x180004b9e  mov     qword ptr [rbp+0A0h+var_F0], rbx
0x180004ba2  mov     rax, [rax]
0x180004ba5  mov     [rbp+0A0h+var_F8], rax
0x180004ba9  mov     rax, [r13+0]
0x180004bad  mov     qword ptr [rbp+0A0h+var_F0+8], rax
0x180004bb1  call    ??$Split@$03@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$03@utl@@AEBUMutableBinary@0@U?$array@_K$03@2@@Z; Kerb3961::Split<4>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,4>)
0x180004bb6  mov     r8d, dword ptr [rbp+0A0h+cbBuffer]; cbBuffer
0x180004bba  mov     r9d, 2; dwFlags
0x180004bc0  mov     rdx, [rbp+0A0h+pbBuffer]; pbBuffer
0x180004bc4  xor     ecx, ecx; hAlgorithm
0x180004bc6  call    cs:__imp_BCryptGenRandom
0x180004bcd  nop     dword ptr [rax+rax+00h]
0x180004bd2  mov     ebx, eax
0x180004bd4  test    eax, eax
0x180004bd6  jns     short loc_180004BF5
0x180004bd8  lea     rcx, aRandomfillConf_0; "RandomFill(confounder)"
0x180004bdf  mov     edx, ebx; char *
0x180004be1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180004be6  mov     [rsi], rdi
0x180004be9  mov     [rsi+8], rdi
0x180004bed  mov     [rsi+10h], ebx
0x180004bf0  jmp     loc_180004B43
0x180004bf5  mov     rax, [rsp+1A0h+var_170]
0x180004bfa  mov     rcx, [rbp+0A0h+var_A8]; void *
0x180004bfe  mov     r8, [rax]; Size
0x180004c01  mov     rdx, [rax+8]; Src
0x180004c05  call    memmove
0x180004c0a  mov     r8, [r13+0]; Size
0x180004c0e  mov     rdx, [r13+8]; Src
0x180004c12  mov     rcx, [rbp+0A0h+var_88]; void *
0x180004c16  call    memmove
0x180004c1b  mov     r8d, [rbp+0A0h+var_A0]; cbBuffer
0x180004c1f  mov     r9d, 2; dwFlags
0x180004c25  mov     rdx, [rbp+0A0h+var_98]; pbBuffer
0x180004c29  xor     ecx, ecx; hAlgorithm
0x180004c2b  call    cs:__imp_BCryptGenRandom
0x180004c32  nop     dword ptr [rax+rax+00h]
0x180004c37  mov     ebx, eax
0x180004c39  test    eax, eax
0x180004c3b  jns     short loc_180004C46
0x180004c3d  lea     rcx, aRandomfillPad; "RandomFill(pad)"
0x180004c44  jmp     short loc_180004BDF
0x180004c46  mov     rax, [rbp+0A0h+var_118]
0x180004c4a  cmp     [rax], rdi
0x180004c4d  jnz     short loc_180004C8C
0x180004c4f  mov     rax, [r14]
0x180004c52  lea     r8, [r15+30h]
0x180004c56  lea     r9, [rbp+0A0h+var_58]
0x180004c5a  mov     rcx, r14
0x180004c5d  lea     rdx, [rsp+1A0h+var_150]
0x180004c62  mov     rax, [rax+1A8h]
0x180004c69  call    _guard_dispatch_icall
0x180004c6e  mov     r13, [rax]
0x180004c71  mov     rbx, [rax+8]
0x180004c75  mov     r15d, [rax+10h]
0x180004c79  mov     [rax], rdi
0x180004c7c  mov     [rax+8], rdi
0x180004c80  mov     dword ptr [rax+10h], 0C0000001h
0x180004c87  jmp     loc_180004D53
0x180004c8c  movups  xmm0, xmmword ptr [rax]
0x180004c8f  mov     eax, dword ptr [rbp+0A0h+cbBuffer]
0x180004c92  lea     rdx, [rbp+0A0h+var_100]
0x180004c96  movups  xmm1, xmmword ptr [r13+0]
0x180004c9b  mov     dword ptr [rbp+0A0h+var_100], eax
0x180004c9e  lea     rcx, [rsp+1A0h+var_150]
0x180004ca3  mov     eax, dword ptr [rbp+0A0h+cbBuffer+4]
0x180004ca6  mov     dword ptr [rbp+0A0h+var_100+4], eax
0x180004ca9  mov     rax, [rbp+0A0h+pbBuffer]
0x180004cad  mov     [rbp+0A0h+var_F8], rax
0x180004cb1  mov     rax, qword ptr [rbp+0A0h+var_A0]
0x180004cb5  mov     [rbp+0A0h+var_E0], eax
0x180004cb8  mov     eax, [rbp+0A0h+var_A0+4]
0x180004cbb  mov     [rbp+0A0h+var_DC], eax
0x180004cbe  mov     rax, [rbp+0A0h+var_98]
0x180004cc2  mov     [rbp+0A0h+var_D8], rax
0x180004cc6  movdqu  [rbp+0A0h+var_F0], xmm0
0x180004ccb  movdqu  [rbp+0A0h+var_D0], xmm1
0x180004cd0  call    ??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z; Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)
0x180004cd5  mov     ebx, dword ptr [rsp+1A0h+var_140]
0x180004cd9  test    ebx, ebx
0x180004cdb  jns     short loc_180004D0D
0x180004cdd  mov     edx, ebx; char *
0x180004cdf  lea     rcx, aTotalchecksumi; "totalChecksumInput"
0x180004ce6  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180004ceb  mov     rcx, [rsp+1A0h+var_148]
0x180004cf0  mov     [rsi], rdi
0x180004cf3  mov     [rsi+8], rdi
0x180004cf7  mov     [rsi+10h], ebx
0x180004cfa  test    rcx, rcx
0x180004cfd  jz      loc_180004B43
0x180004d03  call    Kerb3961Free
0x180004d08  jmp     loc_180004B43
0x180004d0d  mov     rax, [r14]
0x180004d10  lea     r8, [r15+30h]
0x180004d14  lea     r9, [rsp+1A0h+var_150]
0x180004d19  mov     rcx, r14
0x180004d1c  lea     rdx, [rbp+0A0h+var_100]
0x180004d20  mov     rax, [rax+1A8h]
0x180004d27  call    _guard_dispatch_icall
0x180004d2c  mov     r13, [rax]
0x180004d2f  mov     rbx, [rax+8]
0x180004d33  mov     r15d, [rax+10h]
0x180004d37  mov     [rax], rdi
0x180004d3a  mov     [rax+8], rdi
0x180004d3e  mov     dword ptr [rax+10h], 0C0000001h
0x180004d45  mov     rcx, [rbp+0A0h+var_F8]
0x180004d49  test    rcx, rcx
0x180004d4c  jz      short loc_180004D53
0x180004d4e  call    Kerb3961Free
0x180004d53  mov     rcx, [rsp+1A0h+var_148]
0x180004d58  test    rcx, rcx
0x180004d5b  jz      short loc_180004D62
0x180004d5d  call    Kerb3961Free
0x180004d62  test    r15d, r15d
0x180004d65  jns     short loc_180004D92
0x180004d67  mov     edx, r15d; char *
0x180004d6a  lea     rcx, aHmac; "hmac"
0x180004d71  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180004d76  mov     [rsi], rdi
0x180004d79  mov     [rsi+8], rdi
0x180004d7d  mov     [rsi+10h], r15d
0x180004d81  test    rbx, rbx
0x180004d84  jz      loc_180004B43
0x180004d8a  mov     rcx, rbx
0x180004d8d  jmp     loc_180004D03
0x180004d92  mov     rcx, [rbp+0A0h+var_40]; void *
0x180004d96  mov     r8, r13; Size
0x180004d99  mov     rdx, rbx; Src
0x180004d9c  call    memmove
0x180004da1  mov     rax, [r14]
0x180004da4  lea     rcx, [rbp+0A0h+var_58]
0x180004da8  mov     r8, [rbp+0A0h+var_110]
0x180004dac  lea     r9, [rbp+0A0h+var_80]
0x180004db0  mov     [rsp+1A0h+var_180], rcx
0x180004db5  lea     rdx, [rsp+1A0h+var_170]
0x180004dba  mov     rcx, r14
0x180004dbd  mov     rax, [rax+1B0h]
0x180004dc4  call    _guard_dispatch_icall
0x180004dc9  mov     r14d, [rax]
0x180004dcc  test    r14d, r14d
0x180004dcf  jns     short loc_180004DED
0x180004dd1  mov     edx, r14d; char *
0x180004dd4  lea     rcx, aBlockencryptKe_0; "BlockEncrypt(key->Ke, IV, encryptedPart"...
0x180004ddb  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180004de0  mov     [rsi], rdi
0x180004de3  mov     [rsi+8], rdi
0x180004de7  mov     [rsi+10h], r14d
0x180004deb  jmp     short loc_180004D81
0x180004ded  mov     rax, [rsp+1A0h+var_168]
0x180004df2  mov     [rsi], rax
0x180004df5  mov     rax, [rsp+1A0h+var_160]
0x180004dfa  mov     [rsi+8], rax
0x180004dfe  mov     [rsi+10h], r12d
0x180004e02  test    rbx, rbx
0x180004e05  jz      short loc_180004E0F
0x180004e07  mov     rcx, rbx
0x180004e0a  call    Kerb3961Free
0x180004e0f  mov     rax, rsi
0x180004e12  mov     rcx, [rbp+0A0h+var_38]
0x180004e16  xor     rcx, rsp; StackCookie
0x180004e19  call    __security_check_cookie
0x180004e1e  mov     rbx, [rsp+1A0h+arg_18]
0x180004e26  add     rsp, 170h
0x180004e2d  pop     r15
0x180004e2f  pop     r14
0x180004e31  pop     r13
0x180004e33  pop     r12
0x180004e35  pop     rdi
0x180004e36  pop     rsi
0x180004e37  pop     rbp
0x180004e38  retn
```
