# Kerb3961::SimplifiedCipherSuite<2>::EncryptForSspi(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001ade0`
- end: `0x18001b218`
- name: `?EncryptForSspi@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@22@Z`
- size: `1080`
- prototype: `__int64 __fastcall(int, int, int, int, char *, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x180004118`
- `0x1800046e0`
- `0x18000901c`
- `0x1800101b8`
- `0x18001ade0`
- `0x18001d360`
- `0x18001e010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18001afa9`
- `bcrypt!BCryptGenRandom` at `0x18001b008`
- `bcrypt!BCryptGenRandom` at `0x18001afa9`
- `bcrypt!BCryptGenRandom` at `0x18001b008`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::EncryptForSspi(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        char *a5,
        __int128 *a6,
        const void **a7)
{
  __int64 v9; // rcx
  __int64 v10; // r15
  unsigned __int64 v11; // r10
  unsigned __int64 v12; // r8
  size_t v13; // rbx
  const char *v14; // rdx
  int v15; // r8d
  int v16; // r12d
  void *v17; // rcx
  NTSTATUS v18; // ebx
  int v19; // r8d
  char *v20; // rcx
  __int64 v21; // rax
  int v22; // r8d
  size_t v23; // r13
  const void *v24; // rbx
  int v25; // r15d
  __int128 v26; // xmm0
  __int128 v27; // xmm0
  int v28; // r8d
  int v29; // ebx
  void *v30; // rcx
  __int64 v31; // rax
  int v32; // r8d
  int v33; // r14d
  char *v35; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  void *v37; // [rsp+40h] [rbp-C0h]
  char *v38; // [rsp+48h] [rbp-B8h]
  size_t v39; // [rsp+50h] [rbp-B0h] BYREF
  void *v40; // [rsp+58h] [rbp-A8h]
  char *v41; // [rsp+60h] [rbp-A0h]
  size_t v42; // [rsp+70h] [rbp-90h]
  unsigned __int64 v43; // [rsp+78h] [rbp-88h]
  __int64 v44; // [rsp+80h] [rbp-80h]
  __int128 *v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h]
  __int64 v47; // [rsp+A0h] [rbp-60h] BYREF
  void *v48; // [rsp+A8h] [rbp-58h]
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

  v45 = a6;
  v35 = a5;
  if ( *a3 == a1 )
  {
    v9 = *(_QWORD *)(a1 + 96);
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
    v12 = *(_QWORD *)(a1 + 88);
    v42 = (size_t)*a7;
    v43 = v11;
    v13 = v11 + v42 - 1 + v9 - (v11 + v42 - 1 + v9) % v12 + v12;
    if ( !v11 || *(_QWORD *)a6 )
      v13 += 16LL;
    v14 = (const char *)(v13 + *(_QWORD *)(a1 + 80));
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
    v40 = *(void **)(a1 + 80);
    v39 = v13;
    Kerb3961::Split<2>(v61, &v36, &v39);
    v47 = *(_QWORD *)(a1 + 96);
    *(_QWORD *)&v49 = v13 - v42 - v43 - v44;
    v48 = *(void **)v35;
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
    memcpy_0(v56, *((const void **)v35 + 1), *(_QWORD *)v35);
    memcpy_0(v59, a7[1], (size_t)*a7);
    v18 = BCryptGenRandom(0, v58, v57[0], 2u);
    if ( v18 < 0 )
    {
      v20 = "RandomFill(pad)";
      goto LABEL_18;
    }
    if ( *(_QWORD *)v45 )
    {
      v26 = *v45;
      v47 = cbBuffer;
      v48 = pbBuffer;
      v50 = v57[0];
      v49 = v26;
      v51 = v57[1];
      v27 = *(_OWORD *)a7;
      v52 = v58;
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
      v31 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, size_t *))(*(_QWORD *)a1 + 424LL))(
              a1,
              &v47,
              v10 + 48,
              &v39);
      v23 = *(_QWORD *)v31;
      v24 = *(const void **)(v31 + 8);
      v25 = *(_DWORD *)(v31 + 16);
      *(_QWORD *)v31 = 0;
      *(_QWORD *)(v31 + 8) = 0;
      *(_DWORD *)(v31 + 16) = -1073741823;
      if ( v48 )
        operator delete(v48, 0);
    }
    else
    {
      v21 = (*(__int64 (__fastcall **)(__int64, size_t *, __int64, _BYTE *))(*(_QWORD *)a1 + 424LL))(
              a1,
              &v39,
              v10 + 48,
              v61);
      v23 = *(_QWORD *)v21;
      v24 = *(const void **)(v21 + 8);
      v25 = *(_DWORD *)(v21 + 16);
      *(_QWORD *)v21 = 0;
      *(_QWORD *)(v21 + 8) = 0;
      *(_DWORD *)(v21 + 16) = -1073741823;
    }
    if ( v40 )
      operator delete(v40, 0);
    if ( v25 >= 0 )
    {
      memcpy_0(v62, v24, v23);
      v33 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, char **, __int64, _QWORD *, _BYTE *))(*(_QWORD *)a1 + 432LL))(
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
        v17 = (void *)v24;
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
      operator delete(v17, 0);
      return a2;
    }
    v30 = (void *)v24;
LABEL_25:
    operator delete(v30, 0);
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
0x18001ade0  mov     [rsp-8+arg_18], rbx
0x18001ade5  push    rbp
0x18001ade6  push    rsi
0x18001ade7  push    rdi
0x18001ade8  push    r12
0x18001adea  push    r13
0x18001adec  push    r14
0x18001adee  push    r15
0x18001adf0  lea     rbp, [rsp-70h]
0x18001adf5  sub     rsp, 170h
0x18001adfc  mov     rax, cs:__security_cookie
0x18001ae03  xor     rax, rsp
0x18001ae06  mov     [rbp+0A0h+var_38], rax
0x18001ae0a  mov     rax, r9
0x18001ae0d  mov     r9, [rbp+0A0h+arg_28]
0x18001ae14  mov     rsi, rdx
0x18001ae17  mov     rdx, [rbp+0A0h+arg_20]; char *
0x18001ae1e  mov     r14, rcx
0x18001ae21  mov     r13, [rbp+0A0h+arg_30]
0x18001ae28  mov     [rbp+0A0h+var_118], r9
0x18001ae2c  mov     [rsp+1A0h+var_170], rdx
0x18001ae31  cmp     [r8], rcx
0x18001ae34  jz      short loc_18001AE57
0x18001ae36  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x18001ae3d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001ae42  xor     edi, edi
0x18001ae44  mov     [rsi], rdi
0x18001ae47  mov     [rsi+8], rdi
0x18001ae4b  mov     dword ptr [rsi+10h], 0C000000Dh
0x18001ae52  jmp     loc_18001B1EE
0x18001ae57  mov     rax, [rax+8]
0x18001ae5b  xor     edi, edi
0x18001ae5d  mov     rcx, [rcx+60h]
0x18001ae61  mov     r15, [r8+8]
0x18001ae65  mov     [rbp+0A0h+var_78], rax
0x18001ae69  mov     [rbp+0A0h+var_80], rcx
0x18001ae6d  mov     [rbp+0A0h+var_120], rcx
0x18001ae71  lea     rax, [r15+18h]
0x18001ae75  mov     [rbp+0A0h+var_110], rax
0x18001ae79  cmp     [rax], rdi
0x18001ae7c  ja      short loc_18001AE92
0x18001ae7e  cmp     [r15+30h], rdi
0x18001ae82  ja      short loc_18001AE92
0x18001ae84  lea     rcx, aKeyKeLength0Ke_0; "key->Ke.length > 0 || key->Ki.length > "...
0x18001ae8b  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001ae90  jmp     short loc_18001AE44
0x18001ae92  mov     r10, [rdx]
0x18001ae95  xor     edx, edx
0x18001ae97  mov     rax, [r13+0]
0x18001ae9b  mov     r8, [r14+58h]
0x18001ae9f  mov     [rsp+1A0h+var_130], rax
0x18001aea4  dec     rax
0x18001aea7  add     rax, r10
0x18001aeaa  mov     [rsp+1A0h+var_128], r10
0x18001aeaf  add     rcx, rax
0x18001aeb2  mov     rax, rcx
0x18001aeb5  div     r8
0x18001aeb8  sub     rcx, rdx
0x18001aebb  lea     rbx, [rcx+r8]
0x18001aebf  test    r10, r10
0x18001aec2  jz      short loc_18001AEC9
0x18001aec4  cmp     [r9], rdi
0x18001aec7  jz      short loc_18001AECD
0x18001aec9  add     rbx, 10h
0x18001aecd  mov     rdx, [r14+50h]
0x18001aed1  add     rdx, rbx; char *
0x18001aed4  cmp     rdx, r10
0x18001aed7  ja      short loc_18001AEF8
0x18001aed9  lea     rcx, aFinalsizeClear; "finalSize > clearData.length"
0x18001aee0  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001aee5  mov     [rsi], rdi
0x18001aee8  mov     [rsi+8], rdi
0x18001aeec  mov     dword ptr [rsi+10h], 0C0000095h
0x18001aef3  jmp     loc_18001B1EE
0x18001aef8  lea     rcx, [rsp+1A0h+var_168]
0x18001aefd  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001af02  mov     r12, [rsp+1A0h+var_158]
0x18001af07  test    r12d, r12d
0x18001af0a  jns     short loc_18001AF39
0x18001af0c  mov     edx, r12d; char *
0x18001af0f  lea     rcx, aResult; "result"
0x18001af16  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001af1b  mov     [rsi], rdi
0x18001af1e  mov     [rsi+8], rdi
0x18001af22  mov     [rsi+10h], r12d
0x18001af26  mov     rcx, [rsp+1A0h+var_160]
0x18001af2b  test    rcx, rcx
0x18001af2e  jz      loc_18001B1EE
0x18001af34  jmp     loc_18001B1E7
0x18001af39  mov     rax, [r14+50h]
0x18001af3d  lea     r8, [rsp+1A0h+var_150]
0x18001af42  lea     rdx, [rsp+1A0h+var_168]
0x18001af47  mov     [rsp+1A0h+var_148], rax
0x18001af4c  lea     rcx, [rbp+0A0h+var_58]
0x18001af50  mov     [rsp+1A0h+var_150], rbx
0x18001af55  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x18001af5a  mov     rax, [r14+60h]
0x18001af5e  lea     r8, [rbp+0A0h+var_100]
0x18001af62  sub     rbx, [rsp+1A0h+var_130]
0x18001af67  lea     rdx, [rbp+0A0h+var_58]
0x18001af6b  sub     rbx, [rsp+1A0h+var_128]
0x18001af70  lea     rcx, [rbp+0A0h+cbBuffer]
0x18001af74  sub     rbx, [rbp+0A0h+var_120]
0x18001af78  mov     [rbp+0A0h+var_100], rax
0x18001af7c  mov     rax, [rsp+1A0h+var_170]
0x18001af81  mov     qword ptr [rbp+0A0h+var_F0], rbx
0x18001af85  mov     rax, [rax]
0x18001af88  mov     [rbp+0A0h+var_F8], rax
0x18001af8c  mov     rax, [r13+0]
0x18001af90  mov     qword ptr [rbp+0A0h+var_F0+8], rax
0x18001af94  call    ??$Split@$03@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$03@utl@@AEBUMutableBinary@0@U?$array@_K$03@2@@Z; Kerb3961::Split<4>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,4>)
0x18001af99  mov     r8d, dword ptr [rbp+0A0h+cbBuffer]; cbBuffer
0x18001af9d  mov     r9d, 2; dwFlags
0x18001afa3  mov     rdx, [rbp+0A0h+pbBuffer]; pbBuffer
0x18001afa7  xor     ecx, ecx; hAlgorithm
0x18001afa9  call    cs:__imp_BCryptGenRandom
0x18001afaf  mov     ebx, eax
0x18001afb1  test    eax, eax
0x18001afb3  jns     short loc_18001AFD2
0x18001afb5  lea     rcx, aRandomfillConf_0; "RandomFill(confounder)"
0x18001afbc  mov     edx, ebx; char *
0x18001afbe  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001afc3  mov     [rsi], rdi
0x18001afc6  mov     [rsi+8], rdi
0x18001afca  mov     [rsi+10h], ebx
0x18001afcd  jmp     loc_18001AF26
0x18001afd2  mov     rax, [rsp+1A0h+var_170]
0x18001afd7  mov     rcx, [rbp+0A0h+var_A8]; void *
0x18001afdb  mov     r8, [rax]; Size
0x18001afde  mov     rdx, [rax+8]; Src
0x18001afe2  call    memcpy_0
0x18001afe7  mov     r8, [r13+0]; Size
0x18001afeb  mov     rdx, [r13+8]; Src
0x18001afef  mov     rcx, [rbp+0A0h+var_88]; void *
0x18001aff3  call    memcpy_0
0x18001aff8  mov     r8d, [rbp+0A0h+var_A0]; cbBuffer
0x18001affc  mov     r9d, 2; dwFlags
0x18001b002  mov     rdx, [rbp+0A0h+var_98]; pbBuffer
0x18001b006  xor     ecx, ecx; hAlgorithm
0x18001b008  call    cs:__imp_BCryptGenRandom
0x18001b00e  mov     ebx, eax
0x18001b010  test    eax, eax
0x18001b012  jns     short loc_18001B01D
0x18001b014  lea     rcx, aRandomfillPad; "RandomFill(pad)"
0x18001b01b  jmp     short loc_18001AFBC
0x18001b01d  mov     rcx, [rbp+0A0h+var_118]
0x18001b021  cmp     [rcx], rdi
0x18001b024  jnz     short loc_18001B063
0x18001b026  mov     rax, [r14]
0x18001b029  lea     r8, [r15+30h]
0x18001b02d  lea     r9, [rbp+0A0h+var_58]
0x18001b031  mov     rcx, r14
0x18001b034  lea     rdx, [rsp+1A0h+var_150]
0x18001b039  mov     rax, [rax+1A8h]
0x18001b040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b045  mov     r13, [rax]
0x18001b048  mov     rbx, [rax+8]
0x18001b04c  mov     r15d, [rax+10h]
0x18001b050  mov     [rax], rdi
0x18001b053  mov     [rax+8], rdi
0x18001b057  mov     dword ptr [rax+10h], 0C0000001h
0x18001b05e  jmp     loc_18001B12E
0x18001b063  movups  xmm0, xmmword ptr [rcx]
0x18001b066  mov     eax, dword ptr [rbp+0A0h+cbBuffer]
0x18001b069  lea     rdx, [rbp+0A0h+var_100]
0x18001b06d  mov     dword ptr [rbp+0A0h+var_100], eax
0x18001b070  lea     rcx, [rsp+1A0h+var_150]
0x18001b075  mov     eax, dword ptr [rbp+0A0h+cbBuffer+4]
0x18001b078  mov     dword ptr [rbp+0A0h+var_100+4], eax
0x18001b07b  mov     rax, [rbp+0A0h+pbBuffer]
0x18001b07f  mov     [rbp+0A0h+var_F8], rax
0x18001b083  mov     rax, qword ptr [rbp+0A0h+var_A0]
0x18001b087  mov     [rbp+0A0h+var_E0], eax
0x18001b08a  mov     eax, [rbp+0A0h+var_A0+4]
0x18001b08d  movdqu  [rbp+0A0h+var_F0], xmm0
0x18001b092  mov     [rbp+0A0h+var_DC], eax
0x18001b095  movups  xmm0, xmmword ptr [r13+0]
0x18001b09a  mov     rax, [rbp+0A0h+var_98]
0x18001b09e  mov     [rbp+0A0h+var_D8], rax
0x18001b0a2  movdqu  [rbp+0A0h+var_D0], xmm0
0x18001b0a7  call    ??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z; Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)
0x18001b0ac  mov     ebx, dword ptr [rsp+1A0h+var_140]
0x18001b0b0  test    ebx, ebx
0x18001b0b2  jns     short loc_18001B0E6
0x18001b0b4  mov     edx, ebx; char *
0x18001b0b6  lea     rcx, aTotalchecksumi; "totalChecksumInput"
0x18001b0bd  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001b0c2  mov     rcx, [rsp+1A0h+var_148]; void *
0x18001b0c7  mov     [rsi], rdi
0x18001b0ca  mov     [rsi+8], rdi
0x18001b0ce  mov     [rsi+10h], ebx
0x18001b0d1  test    rcx, rcx
0x18001b0d4  jz      loc_18001AF26
0x18001b0da  xor     edx, edx; struct std::nothrow_t *
0x18001b0dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b0e1  jmp     loc_18001AF26
0x18001b0e6  mov     rax, [r14]
0x18001b0e9  lea     r8, [r15+30h]
0x18001b0ed  lea     r9, [rsp+1A0h+var_150]
0x18001b0f2  mov     rcx, r14
0x18001b0f5  lea     rdx, [rbp+0A0h+var_100]
0x18001b0f9  mov     rax, [rax+1A8h]
0x18001b100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b105  mov     r13, [rax]
0x18001b108  mov     rbx, [rax+8]
0x18001b10c  mov     r15d, [rax+10h]
0x18001b110  mov     [rax], rdi
0x18001b113  mov     [rax+8], rdi
0x18001b117  mov     dword ptr [rax+10h], 0C0000001h
0x18001b11e  mov     rcx, [rbp+0A0h+var_F8]; void *
0x18001b122  test    rcx, rcx
0x18001b125  jz      short loc_18001B12E
0x18001b127  xor     edx, edx; struct std::nothrow_t *
0x18001b129  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b12e  mov     rcx, [rsp+1A0h+var_148]; void *
0x18001b133  test    rcx, rcx
0x18001b136  jz      short loc_18001B13F
0x18001b138  xor     edx, edx; struct std::nothrow_t *
0x18001b13a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b13f  test    r15d, r15d
0x18001b142  jns     short loc_18001B16F
0x18001b144  mov     edx, r15d; char *
0x18001b147  lea     rcx, aHmac; "hmac"
0x18001b14e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001b153  mov     [rsi], rdi
0x18001b156  mov     [rsi+8], rdi
0x18001b15a  mov     [rsi+10h], r15d
0x18001b15e  test    rbx, rbx
0x18001b161  jz      loc_18001AF26
0x18001b167  mov     rcx, rbx
0x18001b16a  jmp     loc_18001B0DA
0x18001b16f  mov     rcx, [rbp+0A0h+var_40]; void *
0x18001b173  mov     r8, r13; Size
0x18001b176  mov     rdx, rbx; Src
0x18001b179  call    memcpy_0
0x18001b17e  mov     rax, [r14]
0x18001b181  lea     rcx, [rbp+0A0h+var_58]
0x18001b185  mov     r8, [rbp+0A0h+var_110]
0x18001b189  lea     r9, [rbp+0A0h+var_80]
0x18001b18d  mov     [rsp+1A0h+var_180], rcx
0x18001b192  lea     rdx, [rsp+1A0h+var_170]
0x18001b197  mov     rcx, r14
0x18001b19a  mov     rax, [rax+1B0h]
0x18001b1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1a6  mov     r14d, [rax]
0x18001b1a9  test    r14d, r14d
0x18001b1ac  jns     short loc_18001B1CA
0x18001b1ae  mov     edx, r14d; char *
0x18001b1b1  lea     rcx, aBlockencryptKe_0; "BlockEncrypt(key->Ke, IV, encryptedPart"...
0x18001b1b8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001b1bd  mov     [rsi], rdi
0x18001b1c0  mov     [rsi+8], rdi
0x18001b1c4  mov     [rsi+10h], r14d
0x18001b1c8  jmp     short loc_18001B15E
0x18001b1ca  mov     rax, [rsp+1A0h+var_168]
0x18001b1cf  mov     [rsi], rax
0x18001b1d2  mov     rax, [rsp+1A0h+var_160]
0x18001b1d7  mov     [rsi+8], rax
0x18001b1db  mov     [rsi+10h], r12d
0x18001b1df  test    rbx, rbx
0x18001b1e2  jz      short loc_18001B1EE
0x18001b1e4  mov     rcx, rbx; void *
0x18001b1e7  xor     edx, edx; struct std::nothrow_t *
0x18001b1e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b1ee  mov     rax, rsi
0x18001b1f1  mov     rcx, [rbp+0A0h+var_38]
0x18001b1f5  xor     rcx, rsp; StackCookie
0x18001b1f8  call    __security_check_cookie
0x18001b1fd  mov     rbx, [rsp+1A0h+arg_18]
0x18001b205  add     rsp, 170h
0x18001b20c  pop     r15
0x18001b20e  pop     r14
0x18001b210  pop     r13
0x18001b212  pop     r12
0x18001b214  pop     rdi
0x18001b215  pop     rsi
0x18001b216  pop     rbp
0x18001b217  retn
```
