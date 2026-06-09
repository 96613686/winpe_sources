# Kerb3961::Aes8009::Decrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800126e0`
- end: `0x180012ab1`
- name: `?Decrypt@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `977`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800046e0`
- `0x180004750`
- `0x18000901c`
- `0x18000eee8`
- `0x18000f908`
- `0x1800126e0`
- `0x180012ab8`
- `0x18001d360`
- `0x18001d36c`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::Decrypt(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5, _QWORD *a6)
{
  __int64 v7; // rax
  char *v9; // r13
  int v10; // r8d
  int v11; // r12d
  __int64 *v12; // r8
  __int64 v13; // rbx
  int v14; // r8d
  void *v15; // rcx
  int v16; // eax
  int v17; // ebx
  __int64 v18; // r8
  int v19; // ebx
  void *v20; // rcx
  const char *v21; // rdx
  void *v22; // r15
  char v23; // r9
  __int64 v24; // rax
  int v25; // r8d
  int v26; // ebx
  void *v27; // rbx
  void *v28; // rcx
  __int64 v30; // [rsp+30h] [rbp-B9h] BYREF
  void *v31; // [rsp+38h] [rbp-B1h]
  char *v32; // [rsp+40h] [rbp-A9h]
  _OWORD *v33; // [rsp+50h] [rbp-99h] BYREF
  __int64 v34; // [rsp+58h] [rbp-91h] BYREF
  void *v35; // [rsp+60h] [rbp-89h]
  char *v36; // [rsp+68h] [rbp-81h]
  _BYTE v37[8]; // [rsp+70h] [rbp-79h] BYREF
  void *v38; // [rsp+78h] [rbp-71h]
  char *v39; // [rsp+80h] [rbp-69h]
  __int64 v40; // [rsp+88h] [rbp-61h]
  _BYTE v41[8]; // [rsp+90h] [rbp-59h] BYREF
  void *v42; // [rsp+98h] [rbp-51h]
  void *v43; // [rsp+A8h] [rbp-41h]
  _BYTE v44[8]; // [rsp+B0h] [rbp-39h] BYREF
  _OWORD *v45; // [rsp+B8h] [rbp-31h]
  _QWORD v46[2]; // [rsp+C0h] [rbp-29h] BYREF
  _BYTE v47[8]; // [rsp+D0h] [rbp-19h] BYREF
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
  v9 = (char *)(*a5 - v7);
  v40 = *(_QWORD *)(a3 + 8);
  v33 = *(_OWORD **)(a4 + 8);
  Kerb3961::MakeBuffer(v37);
  v11 = (int)v39;
  if ( (int)v39 >= 0 )
  {
    Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v47);
    v30 = 16;
    v31 = v9;
    Kerb3961::Split<2>(v44, v37, &v30);
    *v45 = *v33;
    memcpy_0((void *)v46[1], Src, (size_t)v9);
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
        operator delete(v35, 0);
      v34 = *(_QWORD *)v13;
      v15 = *(void **)(v13 + 8);
      *(_QWORD *)v13 = 0;
      v35 = v15;
      v16 = *(_DWORD *)(v13 + 16);
      *(_QWORD *)(v13 + 8) = 0;
      LODWORD(v36) = v16;
      *(_DWORD *)(v13 + 16) = -1073741823;
      if ( v42 )
        operator delete(v42, 0);
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
        v23 |= *((_BYTE *)v31 + v24) ^ *(_BYTE *)(v24 + v50);
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
          ((void (__fastcall *)(_OWORD **, _QWORD, __int64, __int64, __int64 *, _QWORD *))Kerb3961::DecryptCTS)(
            &v33,
            *(_QWORD *)(a1 + 144),
            v18,
            v40 + 24,
            &v30,
            v46);
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
          v31 = v9 - 16;
          Kerb3961::Split<2>(v41, v46, &v30);
          v27 = v38;
          memmove_0(v38, v43, (size_t)(v9 - 16));
          *(_DWORD *)(a2 + 16) = v11;
          *(_QWORD *)a2 = v9 - 16;
          *(_QWORD *)(a2 + 8) = v27;
          if ( v22 )
            operator delete(v22, 0);
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
    operator delete(v20, 0);
LABEL_34:
    if ( v35 )
      operator delete(v35, 0);
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
    operator delete(v28, 0);
  return a2;
}

```

## disassembly

```asm
0x1800126e0  mov     [rsp-8+arg_18], rbx
0x1800126e5  push    rbp
0x1800126e6  push    rsi
0x1800126e7  push    rdi
0x1800126e8  push    r12
0x1800126ea  push    r13
0x1800126ec  push    r14
0x1800126ee  push    r15
0x1800126f0  lea     rbp, [rsp-17h]
0x1800126f5  sub     rsp, 100h
0x1800126fc  mov     rax, cs:__security_cookie
0x180012703  xor     rax, rsp
0x180012706  mov     [rbp+47h+var_40], rax
0x18001270a  mov     rbx, [rbp+47h+arg_20]
0x18001270e  mov     rdi, rcx
0x180012711  mov     rax, [rcx+58h]
0x180012715  mov     r14, rdx
0x180012718  mov     r15, [rbp+47h+arg_28]
0x18001271c  mov     r13, [rbx]
0x18001271f  lea     rcx, [rax+10h]
0x180012723  cmp     r13, rcx
0x180012726  jnb     short loc_18001274A
0x180012728  lea     rcx, aCiphertextLeng_2; "cipherText.length >= m_micLength + AES_"...
0x18001272f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180012734  xor     esi, esi
0x180012736  mov     [r14], rsi
0x180012739  mov     [r14+8], rsi
0x18001273d  mov     dword ptr [r14+10h], 0C000000Dh
0x180012745  jmp     loc_180012A87
0x18001274a  sub     r13, rax
0x18001274d  lea     rcx, [rbp+47h+var_C0]
0x180012751  mov     rax, [r8+8]
0x180012755  mov     [rbp+47h+var_A8], rax
0x180012759  mov     rax, [r9+8]
0x18001275d  lea     rdx, [r13+10h]
0x180012761  mov     [rsp+130h+var_E0], rax
0x180012766  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001276b  mov     r12, [rbp+47h+var_B0]
0x18001276f  xor     esi, esi
0x180012771  test    r12d, r12d
0x180012774  jns     short loc_180012795
0x180012776  mov     edx, r12d; char *
0x180012779  lea     rcx, aHmacbuffer; "hmacBuffer"
0x180012780  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180012785  mov     [r14], rsi
0x180012788  mov     [r14+8], rsi
0x18001278c  mov     [r14+10h], r12d
0x180012790  jmp     loc_180012A77
0x180012795  mov     rax, [rdi+58h]
0x180012799  lea     r8, [rsp+130h+var_100]
0x18001279e  mov     rdx, rbx
0x1800127a1  mov     [rsp+130h+var_F8], rax
0x1800127a6  lea     rcx, [rbp+47h+var_60]; this
0x1800127aa  mov     [rsp+130h+var_100], r13
0x1800127af  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x1800127b4  lea     r8, [rsp+130h+var_100]
0x1800127b9  mov     [rsp+130h+var_100], 10h
0x1800127c2  lea     rdx, [rbp+47h+var_C0]
0x1800127c6  mov     [rsp+130h+var_F8], r13
0x1800127cb  lea     rcx, [rbp+47h+var_80]
0x1800127cf  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x1800127d4  mov     rax, [rsp+130h+var_E0]
0x1800127d9  mov     r8, r13; Size
0x1800127dc  movups  xmm0, xmmword ptr [rax]
0x1800127df  mov     rax, [rbp+47h+var_78]
0x1800127e3  movdqu  xmmword ptr [rax], xmm0
0x1800127e7  mov     rdx, [rbp+47h+Src]; Src
0x1800127eb  mov     rcx, [rbp+47h+var_68]; void *
0x1800127ef  call    memcpy_0
0x1800127f4  mov     r8, [rbp+47h+var_A8]
0x1800127f8  add     r8, 30h ; '0'
0x1800127fc  mov     [rsp+130h+var_D8], rsi
0x180012801  mov     [rsp+130h+var_D0], rsi
0x180012806  mov     dword ptr [rsp+130h+var_C8], 0C0000001h
0x18001280e  cmp     [r15], rsi
0x180012811  jz      loc_1800128BF
0x180012817  lea     rax, aTag; "tag"
0x18001281e  mov     [rsp+130h+var_100], 3
0x180012827  mov     [rsp+130h+var_F8], rax
0x18001282c  lea     r9, [rsp+130h+var_100]
0x180012831  mov     rax, [r8]
0x180012834  lea     rdx, [rbp+47h+var_A0]
0x180012838  mov     [rsp+130h+var_108], rax
0x18001283d  mov     rcx, rdi
0x180012840  mov     [rsp+130h+var_110], r15
0x180012845  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z; Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x18001284a  mov     rcx, [rsp+130h+var_D0]; void *
0x18001284f  mov     rbx, rax
0x180012852  test    rcx, rcx
0x180012855  jz      short loc_18001285E
0x180012857  xor     edx, edx; struct std::nothrow_t *
0x180012859  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001285e  mov     rcx, [rbx]
0x180012861  mov     [rsp+130h+var_D8], rcx
0x180012866  mov     rcx, [rbx+8]
0x18001286a  mov     [rbx], rsi
0x18001286d  mov     [rsp+130h+var_D0], rcx
0x180012872  mov     eax, [rbx+10h]
0x180012875  mov     [rbx+8], rsi
0x180012879  mov     dword ptr [rsp+130h+var_C8], eax
0x18001287d  mov     dword ptr [rbx+10h], 0C0000001h
0x180012884  mov     rcx, [rbp+47h+var_98]; void *
0x180012888  test    rcx, rcx
0x18001288b  jz      short loc_180012894
0x18001288d  xor     edx, edx; struct std::nothrow_t *
0x18001288f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012894  mov     ebx, dword ptr [rsp+130h+var_C8]
0x180012898  test    ebx, ebx
0x18001289a  jns     short loc_1800128BA
0x18001289c  mov     edx, ebx; char *
0x18001289e  lea     rcx, aDerivedintegri; "derivedIntegrityKey"
0x1800128a5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800128aa  mov     [r14], rsi
0x1800128ad  mov     [r14+8], rsi
0x1800128b1  mov     [r14+10h], ebx
0x1800128b5  jmp     loc_180012A66
0x1800128ba  lea     r8, [rsp+130h+var_D8]
0x1800128bf  mov     eax, [rdi+0A0h]
0x1800128c5  lea     r9, [rbp+47h+var_C0]
0x1800128c9  mov     rdx, [rdi+98h]
0x1800128d0  lea     rcx, [rsp+130h+var_100]
0x1800128d5  mov     [rsp+130h+var_110], rax
0x1800128da  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x1800128df  mov     ebx, dword ptr [rsp+130h+var_F0]
0x1800128e3  test    ebx, ebx
0x1800128e5  jns     short loc_180012913
0x1800128e7  mov     edx, ebx; char *
0x1800128e9  lea     rcx, aHmac; "hmac"
0x1800128f0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800128f5  mov     rcx, [rsp+130h+var_F8]
0x1800128fa  mov     [r14], rsi
0x1800128fd  mov     [r14+8], rsi
0x180012901  mov     [r14+10h], ebx
0x180012905  test    rcx, rcx
0x180012908  jz      loc_180012A66
0x18001290e  jmp     loc_180012A5F
0x180012913  mov     rdx, [rdi+58h]; char *
0x180012917  mov     r15, [rsp+130h+var_F8]
0x18001291c  cmp     rdx, [rbp+47h+var_50]
0x180012920  jnz     loc_180012A3C
0x180012926  test    rdx, rdx
0x180012929  jz      short loc_180012968
0x18001292b  mov     eax, 0FFFFFFFFh
0x180012930  cmp     rdx, rax
0x180012933  ja      loc_180012A3C
0x180012939  mov     r10, [rbp+47h+var_48]
0x18001293d  mov     r9b, sil
0x180012940  mov     r8d, esi
0x180012943  test    edx, edx
0x180012945  jz      short loc_180012968
0x180012947  mov     eax, r8d
0x18001294a  inc     r8d
0x18001294d  mov     cl, [rax+r10]
0x180012951  mov     al, [rax+r15]
0x180012955  xor     cl, al
0x180012957  or      r9b, cl
0x18001295a  cmp     r8d, edx
0x18001295d  jb      short loc_180012947
0x18001295f  test    r9b, r9b
0x180012962  jnz     loc_180012A3C
0x180012968  cmp     [rbp+47h+var_70], 10h
0x18001296d  mov     rax, [rsp+130h+var_E0]
0x180012972  mov     [rsp+130h+var_F8], rax
0x180012977  mov     [rsp+130h+var_100], 10h
0x180012980  jnb     short loc_180012995
0x180012982  lea     rcx, aCiphertextLeng_1; "cipherText.length >= AES_BLOCK_SIZE"
0x180012989  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001298e  mov     ebx, 0C0000023h
0x180012993  jmp     short loc_1800129C5
0x180012995  mov     r9, [rbp+47h+var_A8]
0x180012999  lea     rax, [rbp+47h+var_70]
0x18001299d  mov     rdx, [rdi+90h]
0x1800129a4  lea     rcx, [rsp+130h+var_E0]
0x1800129a9  mov     [rsp+130h+var_108], rax
0x1800129ae  add     r9, 18h
0x1800129b2  lea     rax, [rsp+130h+var_100]
0x1800129b7  mov     [rsp+130h+var_110], rax
0x1800129bc  call    ?DecryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::DecryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x1800129c1  mov     ebx, dword ptr [rsp+130h+var_E0]
0x1800129c5  test    ebx, ebx
0x1800129c7  jns     short loc_1800129E4
0x1800129c9  mov     edx, ebx; char *
0x1800129cb  lea     rcx, aBlockdecryptKe; "BlockDecrypt(key->Ke, {AES_BLOCK_SIZE, "...
0x1800129d2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800129d7  mov     [r14], rsi
0x1800129da  mov     [r14+8], rsi
0x1800129de  mov     [r14+10h], ebx
0x1800129e2  jmp     short loc_180012A57
0x1800129e4  lea     rdi, [r13-10h]
0x1800129e8  mov     [rsp+130h+var_100], 10h
0x1800129f1  lea     r8, [rsp+130h+var_100]
0x1800129f6  mov     [rsp+130h+var_F8], rdi
0x1800129fb  lea     rdx, [rbp+47h+var_70]
0x1800129ff  lea     rcx, [rbp+47h+var_A0]
0x180012a03  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180012a08  mov     rbx, [rbp+47h+var_B8]
0x180012a0c  mov     r8, rdi; Size
0x180012a0f  mov     rdx, [rbp+47h+var_88]; Src
0x180012a13  mov     rcx, rbx; void *
0x180012a16  call    memmove_0
0x180012a1b  mov     [r14+10h], r12d
0x180012a1f  mov     [r14], rdi
0x180012a22  mov     [r14+8], rbx
0x180012a26  test    r15, r15
0x180012a29  jz      short loc_180012A35
0x180012a2b  xor     edx, edx; struct std::nothrow_t *
0x180012a2d  mov     rcx, r15; void *
0x180012a30  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012a35  mov     rcx, [rsp+130h+var_D0]
0x180012a3a  jmp     short loc_180012A7B
0x180012a3c  lea     rcx, aSecureequalbuf_0; "SecureEqualBuffer(hmac, MIC)"
0x180012a43  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180012a48  mov     [r14], rsi
0x180012a4b  mov     [r14+8], rsi
0x180012a4f  mov     dword ptr [r14+10h], 8009030Fh
0x180012a57  test    r15, r15
0x180012a5a  jz      short loc_180012A66
0x180012a5c  mov     rcx, r15; void *
0x180012a5f  xor     edx, edx; struct std::nothrow_t *
0x180012a61  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012a66  mov     rcx, [rsp+130h+var_D0]; void *
0x180012a6b  test    rcx, rcx
0x180012a6e  jz      short loc_180012A77
0x180012a70  xor     edx, edx; struct std::nothrow_t *
0x180012a72  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012a77  mov     rcx, [rbp+47h+var_B8]; void *
0x180012a7b  test    rcx, rcx
0x180012a7e  jz      short loc_180012A87
0x180012a80  xor     edx, edx; struct std::nothrow_t *
0x180012a82  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012a87  mov     rax, r14
0x180012a8a  mov     rcx, [rbp+47h+var_40]
0x180012a8e  xor     rcx, rsp; StackCookie
0x180012a91  call    __security_check_cookie
0x180012a96  mov     rbx, [rsp+130h+arg_18]
0x180012a9e  add     rsp, 100h
0x180012aa5  pop     r15
0x180012aa7  pop     r14
0x180012aa9  pop     r13
0x180012aab  pop     r12
0x180012aad  pop     rdi
0x180012aae  pop     rsi
0x180012aaf  pop     rbp
0x180012ab0  retn
```
