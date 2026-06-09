# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapConfidential(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180007338`
- end: `0x180007703`
- name: `?CommonUnwrapConfidential@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z`
- size: `971`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800070e0`

## callees

- `0x1800015f0`
- `0x180001684`
- `0x180001700`
- `0x1800018e8`
- `0x180001900`
- `0x1800037e0`
- `0x180007338`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapConfidential(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rdx
  __int16 v10; // r15
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rtt
  int v13; // edi
  __int64 *v14; // rdx
  __int64 v15; // r15
  char v16; // di
  int v17; // r8d
  int v18; // esi
  int v19; // r8d
  int v20; // esi
  unsigned __int16 v21; // r15
  __int64 (__fastcall *v22)(__int64, __int64 *, char **, char **, _BYTE *, __int64); // rax
  const char *v23; // rdx
  __int64 v24; // rsi
  int v25; // r8d
  __int64 v26; // rax
  int v27; // esi
  unsigned __int64 v28; // rcx
  char *v29; // rcx
  __int64 v30; // rsi
  char v31; // r8
  __int64 v32; // rax
  unsigned __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h]
  char *v36; // [rsp+50h] [rbp-B0h]
  char *v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v38; // [rsp+68h] [rbp-98h]
  __int64 v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+78h] [rbp-88h]
  int v41; // [rsp+80h] [rbp-80h]
  char *v42[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v43; // [rsp+98h] [rbp-68h]
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h]
  char *v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v49; // [rsp+D0h] [rbp-30h]
  _QWORD v50[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v51[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v52[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v53[16]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v54[2]; // [rsp+120h] [rbp+20h] BYREF

  v6 = a3[1];
  v10 = *(_WORD *)(v6 + 6);
  v39 = 0;
  v40 = 0;
  v41 = -1073741823;
  if ( v10 )
  {
    v11 = *a3 - 16;
    v12 = (unsigned __int16)__ROR2__(*(_WORD *)(v6 + 6), 8);
    v47 = 16;
    v48 = v12 % v11;
    v49 = v11 - v12 % v11;
    Kerb3961::Split<3>((Kerb3961::ReadOnlyBinary *)v52);
    Kerb3961::Concatenate(&v44, v52, v54, v53);
    v13 = (int)v46;
    v39 = v44;
    v40 = v45;
    v41 = (int)v46;
    if ( (int)v46 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"unrotatedBuffer",
        (const char *)(unsigned int)v46,
        0);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v13;
      goto LABEL_34;
    }
    *(_WORD *)(v45 + 6) = 0;
  }
  v47 = 16;
  v14 = &v39;
  if ( !v10 )
    v14 = a3;
  v15 = v14[1];
  v48 = *v14 - 16;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v50);
  v16 = 1;
  (*(void (__fastcall **)(__int64, char **, __int64, __int64, int))(*(_QWORD *)a1 + 168LL))(
    a1,
    v37,
    a5,
    2LL * ((*(_BYTE *)(v15 + 2) & 1) == 0) + 22,
    1);
  v18 = (int)v38;
  if ( (int)v38 >= 0 )
  {
    (*(void (__fastcall **)(__int64, char **, char **, _QWORD))(*(_QWORD *)a1 + 184LL))(a1, v42, v37, 0);
    v20 = (int)v43;
    if ( (int)v43 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"state",
        (const char *)(unsigned int)v43,
        v19);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v20;
      goto LABEL_30;
    }
    v21 = __ROR2__(*(_WORD *)(v15 + 4), 8);
    v22 = *(__int64 (__fastcall **)(__int64, __int64 *, char **, char **, _BYTE *, __int64))(*(_QWORD *)a1 + 208LL);
    v34 = 0;
    v35 = 0;
    LODWORD(v36) = 0;
    v24 = v22(a1, &v44, v37, v42, v51, a4);
    v34 = *(_QWORD *)v24;
    v26 = *(_QWORD *)(v24 + 8);
    *(_QWORD *)v24 = 0;
    v35 = v26;
    LODWORD(v26) = *(_DWORD *)(v24 + 16);
    *(_QWORD *)(v24 + 8) = 0;
    LODWORD(v36) = v26;
    *(_DWORD *)(v24 + 16) = -1073741823;
    if ( v45 )
      Kerb3961Free(v45);
    v27 = (int)v36;
    if ( (int)v36 >= 0 )
    {
      v28 = v21 + 16LL;
      if ( v34 >= v28 )
      {
        v30 = v34 - v28;
        v45 = v21;
        v44 = v34 - v28;
        v46 = (char *)16;
        Kerb3961::Split<3>(v52, &v34, &v44);
        if ( v50[0] != v54[0] )
          goto LABEL_26;
        if ( v50[0] )
        {
          if ( v50[0] > 0xFFFFFFFF )
            goto LABEL_26;
          v31 = 0;
          LODWORD(v23) = 0;
          do
          {
            v32 = (unsigned int)v23;
            v23 = (const char *)(unsigned int)((_DWORD)v23 + 1);
            v31 |= *(_BYTE *)(v50[1] + v32) ^ *(_BYTE *)(v54[1] + v32);
          }
          while ( (unsigned int)v23 < LODWORD(v50[0]) );
          if ( v31 )
LABEL_26:
            v16 = 0;
        }
        if ( v16 )
        {
          *(_DWORD *)(a2 + 16) = (_DWORD)v36;
          *(_QWORD *)(a2 + 8) = v35;
          LODWORD(v36) = -1073741823;
          *(_QWORD *)a2 = v30;
          v34 = 0;
          v35 = 0;
LABEL_30:
          if ( v42[1] )
             Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v42[0]);
          goto LABEL_32;
        }
        v29 = "SecureEqualBuffer(headerBuffer, decryptedHeader)";
      }
      else
      {
        v29 = "decryption.length >= trailerSize";
      }
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v29, v23);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -2146893041;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"decryption",
        (const char *)(unsigned int)v36,
        v25);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v27;
    }
    if ( v35 )
      Kerb3961Free(v35);
    goto LABEL_30;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"specificKey",
    (const char *)(unsigned int)v38,
    v17);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v18;
LABEL_32:
  if ( v37[1] )
     Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v37[0]);
LABEL_34:
  if ( v40 )
    Kerb3961Free(v40);
  return a2;
}

```

## disassembly

```asm
0x180007338  push    rbp
0x18000733a  push    rbx
0x18000733b  push    rsi
0x18000733c  push    rdi
0x18000733d  push    r12
0x18000733f  push    r13
0x180007341  push    r14
0x180007343  push    r15
0x180007345  lea     rbp, [rsp-48h]
0x18000734a  sub     rsp, 148h
0x180007351  mov     rax, cs:__security_cookie
0x180007358  xor     rax, rsp
0x18000735b  mov     [rbp+80h+var_50], rax
0x18000735f  mov     r13, [rbp+80h+arg_20]
0x180007366  mov     rbx, rdx
0x180007369  mov     rdx, [r8+8]
0x18000736d  mov     rsi, r8
0x180007370  xor     r8d, r8d
0x180007373  mov     r12, r9
0x180007376  mov     r14, rcx
0x180007379  movzx   r15d, word ptr [rdx+6]
0x18000737e  mov     [rsp+180h+var_110], r8
0x180007383  mov     [rsp+180h+var_108], r8
0x180007388  mov     [rbp+80h+var_100], 0C0000001h
0x18000738f  test    r15w, r15w
0x180007393  jz      loc_180007444
0x180007399  movzx   eax, word ptr [rdx+6]
0x18000739d  lea     r8, [rbp+80h+var_C0]
0x1800073a1  mov     rcx, [rsi]
0x1800073a4  xor     edx, edx
0x1800073a6  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1800073aa  ror     ax, 8
0x1800073ae  movzx   eax, ax
0x1800073b1  div     rcx
0x1800073b4  mov     [rbp+80h+var_C0], 10h
0x1800073bc  sub     rcx, rdx
0x1800073bf  mov     [rbp+80h+var_B8], rdx
0x1800073c3  mov     [rbp+80h+var_B0], rcx
0x1800073c7  mov     rdx, rsi
0x1800073ca  lea     rcx, [rbp+80h+var_80]; this
0x1800073ce  call    ??$Split@$02@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$02@utl@@AEBUReadOnlyBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,3>)
0x1800073d3  lea     r9, [rbp+80h+var_70]
0x1800073d7  lea     r8, [rbp+80h+var_60]
0x1800073db  lea     rdx, [rbp+80h+var_80]
0x1800073df  lea     rcx, [rbp+80h+var_E0]
0x1800073e3  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800073e8  mov     rcx, [rsp+180h+var_108]
0x1800073ed  xor     r8d, r8d
0x1800073f0  test    rcx, rcx
0x1800073f3  jz      short loc_1800073FD
0x1800073f5  call    Kerb3961Free
0x1800073fa  xor     r8d, r8d; int
0x1800073fd  mov     rdi, [rbp+80h+var_D0]
0x180007401  mov     rax, [rbp+80h+var_E0]
0x180007405  mov     rcx, [rbp+80h+var_D8]
0x180007409  mov     [rsp+180h+var_110], rax
0x18000740e  mov     [rsp+180h+var_108], rcx
0x180007413  mov     [rbp+80h+var_100], edi
0x180007416  test    edi, edi
0x180007418  jns     short loc_18000743F
0x18000741a  mov     edx, edi; char *
0x18000741c  lea     rcx, aUnrotatedbuffe; "unrotatedBuffer"
0x180007423  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007428  mov     qword ptr [rbx], 0
0x18000742f  mov     qword ptr [rbx+8], 0
0x180007437  mov     [rbx+10h], edi
0x18000743a  jmp     loc_1800076D0
0x18000743f  mov     [rcx+6], r8w
0x180007444  test    r15w, r15w
0x180007448  mov     [rbp+80h+var_C0], 10h
0x180007450  lea     rdx, [rsp+180h+var_110]
0x180007455  cmovz   rdx, rsi
0x180007459  lea     r8, [rbp+80h+var_C0]
0x18000745d  lea     rcx, [rbp+80h+var_A0]; this
0x180007461  mov     rax, [rdx]
0x180007464  mov     r15, [rdx+8]
0x180007468  sub     rax, 10h
0x18000746c  mov     [rbp+80h+var_B8], rax
0x180007470  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x180007475  mov     r9b, [r15+2]
0x180007479  lea     rdx, [rsp+180h+var_128]
0x18000747e  mov     rax, [r14]
0x180007481  not     r9b
0x180007484  mov     edi, 1
0x180007489  mov     r8, r13
0x18000748c  and     r9, rdi
0x18000748f  mov     dword ptr [rsp+180h+var_160], edi
0x180007493  mov     rcx, r14
0x180007496  mov     rax, [rax+0A8h]
0x18000749d  lea     r9, ds:16h[r9*2]
0x1800074a5  call    _guard_dispatch_icall
0x1800074aa  mov     esi, dword ptr [rsp+180h+var_118]
0x1800074ae  xor     r13d, r13d
0x1800074b1  test    esi, esi
0x1800074b3  jns     short loc_1800074D2
0x1800074b5  mov     edx, esi; char *
0x1800074b7  lea     rcx, aSpecifickey; "specificKey"
0x1800074be  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800074c3  mov     [rbx], r13
0x1800074c6  mov     [rbx+8], r13
0x1800074ca  mov     [rbx+10h], esi
0x1800074cd  jmp     loc_1800076BC
0x1800074d2  mov     rax, [r14]
0x1800074d5  lea     r8, [rsp+180h+var_128]
0x1800074da  xor     r9d, r9d
0x1800074dd  lea     rdx, [rbp+80h+var_F8]
0x1800074e1  mov     rcx, r14
0x1800074e4  mov     rax, [rax+0B8h]
0x1800074eb  call    _guard_dispatch_icall
0x1800074f0  mov     esi, dword ptr [rbp+80h+var_E8]
0x1800074f3  test    esi, esi
0x1800074f5  jns     short loc_180007514
0x1800074f7  mov     edx, esi; char *
0x1800074f9  lea     rcx, aState; "state"
0x180007500  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007505  mov     [rbx], r13
0x180007508  mov     [rbx+8], r13
0x18000750c  mov     [rbx+10h], esi
0x18000750f  jmp     loc_1800076AA
0x180007514  movzx   r15d, word ptr [r15+4]
0x180007519  lea     rcx, [rbp+80h+var_90]
0x18000751d  mov     rax, [r14]
0x180007520  lea     r9, [rbp+80h+var_F8]
0x180007524  mov     [rsp+180h+var_158], r12
0x180007529  lea     r8, [rsp+180h+var_128]
0x18000752e  mov     [rsp+180h+var_160], rcx
0x180007533  lea     rdx, [rbp+80h+var_E0]
0x180007537  mov     rcx, r14
0x18000753a  ror     r15w, 8
0x18000753f  mov     rax, [rax+0D0h]
0x180007546  mov     [rsp+180h+var_140], r13
0x18000754b  mov     [rsp+180h+var_138], r13
0x180007550  mov     dword ptr [rsp+180h+var_130], r13d
0x180007555  call    _guard_dispatch_icall
0x18000755a  mov     rcx, [rsp+180h+var_138]
0x18000755f  mov     rsi, rax
0x180007562  test    rcx, rcx
0x180007565  jz      short loc_18000756C
0x180007567  call    Kerb3961Free
0x18000756c  mov     rax, [rsi]
0x18000756f  mov     r14d, 0C0000001h
0x180007575  mov     [rsp+180h+var_140], rax
0x18000757a  mov     rax, [rsi+8]
0x18000757e  mov     [rsi], r13
0x180007581  mov     [rsp+180h+var_138], rax
0x180007586  mov     eax, [rsi+10h]
0x180007589  mov     [rsi+8], r13
0x18000758d  mov     dword ptr [rsp+180h+var_130], eax
0x180007591  mov     [rsi+10h], r14d
0x180007595  mov     rcx, [rbp+80h+var_D8]
0x180007599  test    rcx, rcx
0x18000759c  jz      short loc_1800075A3
0x18000759e  call    Kerb3961Free
0x1800075a3  mov     esi, dword ptr [rsp+180h+var_130]
0x1800075a7  test    esi, esi
0x1800075a9  jns     short loc_1800075DB
0x1800075ab  mov     edx, esi; char *
0x1800075ad  lea     rcx, aDecryption; "decryption"
0x1800075b4  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800075b9  mov     [rbx], r13
0x1800075bc  mov     [rbx+8], r13
0x1800075c0  mov     [rbx+10h], esi
0x1800075c3  mov     rcx, [rsp+180h+var_138]
0x1800075c8  test    rcx, rcx
0x1800075cb  jz      loc_1800076AA
0x1800075d1  call    Kerb3961Free
0x1800075d6  jmp     loc_1800076AA
0x1800075db  mov     rsi, [rsp+180h+var_140]
0x1800075e0  movzx   eax, r15w
0x1800075e4  lea     rcx, [rax+10h]
0x1800075e8  cmp     rsi, rcx
0x1800075eb  jnb     short loc_180007609
0x1800075ed  lea     rcx, aDecryptionLeng; "decryption.length >= trailerSize"
0x1800075f4  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800075f9  mov     [rbx], r13
0x1800075fc  mov     [rbx+8], r13
0x180007600  mov     dword ptr [rbx+10h], 8009030Fh
0x180007607  jmp     short loc_1800075C3
0x180007609  sub     rsi, rcx
0x18000760c  mov     [rbp+80h+var_D8], rax
0x180007610  lea     rcx, [rbp+80h+var_80]
0x180007614  mov     [rbp+80h+var_E0], rsi
0x180007618  lea     r8, [rbp+80h+var_E0]
0x18000761c  mov     [rbp+80h+var_D0], 10h
0x180007624  lea     rdx, [rsp+180h+var_140]
0x180007629  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x18000762e  mov     rax, [rbp+80h+var_A0]
0x180007632  cmp     rax, [rbp+80h+var_60]
0x180007636  jnz     short loc_180007674
0x180007638  test    rax, rax
0x18000763b  jz      short loc_180007677
0x18000763d  mov     ecx, 0FFFFFFFFh
0x180007642  cmp     rax, rcx
0x180007645  ja      short loc_180007674
0x180007647  mov     r9, [rbp+80h+var_98]
0x18000764b  mov     r8b, r13b
0x18000764e  mov     r10, [rbp+80h+var_58]
0x180007652  mov     edx, r13d
0x180007655  test    eax, eax
0x180007657  jz      short loc_180007677
0x180007659  mov     eax, edx
0x18000765b  add     edx, edi
0x18000765d  mov     cl, [r10+rax]
0x180007661  mov     al, [r9+rax]
0x180007665  xor     cl, al
0x180007667  or      r8b, cl
0x18000766a  cmp     edx, dword ptr [rbp+80h+var_A0]
0x18000766d  jb      short loc_180007659
0x18000766f  test    r8b, r8b
0x180007672  jz      short loc_180007677
0x180007674  mov     dil, r13b
0x180007677  test    dil, dil
0x18000767a  jnz     short loc_180007688
0x18000767c  lea     rcx, aSecureequalbuf_4; "SecureEqualBuffer(headerBuffer, decrypt"...
0x180007683  jmp     loc_1800075F4
0x180007688  mov     eax, dword ptr [rsp+180h+var_130]
0x18000768c  mov     [rbx+10h], eax
0x18000768f  mov     rax, [rsp+180h+var_138]
0x180007694  mov     [rbx+8], rax
0x180007698  mov     dword ptr [rsp+180h+var_130], r14d
0x18000769d  mov     [rbx], rsi
0x1800076a0  mov     [rsp+180h+var_140], r13
0x1800076a5  mov     [rsp+180h+var_138], r13
0x1800076aa  mov     rdx, [rbp+80h+var_F0]
0x1800076ae  test    rdx, rdx
0x1800076b1  jz      short loc_1800076BC
0x1800076b3  mov     rcx, [rbp+80h+var_F8]
0x1800076b7  call    ??_9EncryptionAlgorithm@Kerb3961@@$BLA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}
0x1800076bc  mov     rdx, [rsp+180h+var_120]
0x1800076c1  test    rdx, rdx
0x1800076c4  jz      short loc_1800076D0
0x1800076c6  mov     rcx, [rsp+180h+var_128]
0x1800076cb  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x1800076d0  mov     rcx, [rsp+180h+var_108]
0x1800076d5  test    rcx, rcx
0x1800076d8  jz      short loc_1800076DF
0x1800076da  call    Kerb3961Free
0x1800076df  mov     rax, rbx
0x1800076e2  mov     rcx, [rbp+80h+var_50]
0x1800076e6  xor     rcx, rsp; StackCookie
0x1800076e9  call    __security_check_cookie
0x1800076ee  add     rsp, 148h
0x1800076f5  pop     r15
0x1800076f7  pop     r14
0x1800076f9  pop     r13
0x1800076fb  pop     r12
0x1800076fd  pop     rdi
0x1800076fe  pop     rsi
0x1800076ff  pop     rbx
0x180007700  pop     rbp
0x180007701  retn
```
