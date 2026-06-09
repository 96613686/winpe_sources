# Kerb3961::RFC4121CipherSuite<1,1,2>::CommonWrapEncrypted(Kerb3961::MutableBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x180003240`
- end: `0x180003587`
- name: `?CommonWrapEncrypted@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMutableBinary@2@AEBUReadOnlyBinary@2@_KI1_N3PEA_K@Z`
- size: `839`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001464`
- `0x180001794`
- `0x1800018e8`
- `0x180001900`
- `0x180003240`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,2>::CommonWrapEncrypted(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        int a6,
        __int64 a7,
        unsigned __int8 a8,
        char a9,
        __int64 *a10)
{
  __int64 v14; // rax
  __int64 v15; // r15
  __int16 v16; // ax
  char v17; // al
  int v18; // r8d
  __int64 v19; // r9
  int v20; // ebx
  int v21; // r8d
  int v22; // ebx
  __int64 v23; // rax
  __int64 (__fastcall *v24)(__int64 *, __int64 *, char **, char **, __int64, _QWORD *, __int64 *); // rax
  __int64 v25; // rbx
  int v26; // r8d
  __int64 v27; // rcx
  int v28; // eax
  int v29; // ebx
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h]
  char *v35; // [rsp+50h] [rbp-B0h]
  char *v36[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v37; // [rsp+68h] [rbp-98h]
  __int16 v38; // [rsp+70h] [rbp-90h] BYREF
  char v39; // [rsp+72h] [rbp-8Eh]
  char v40; // [rsp+73h] [rbp-8Dh]
  __int16 v41; // [rsp+74h] [rbp-8Ch]
  __int16 v42; // [rsp+76h] [rbp-8Ah]
  unsigned __int64 v43; // [rsp+78h] [rbp-88h]
  char *v44[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v45; // [rsp+98h] [rbp-68h]
  __int64 v46; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v47; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  __int16 *v49; // [rsp+B8h] [rbp-48h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+D0h] [rbp-30h]
  __int128 v52; // [rsp+E0h] [rbp-20h]
  __int128 v53; // [rsp+F0h] [rbp-10h] BYREF
  void *Src; // [rsp+108h] [rbp+8h]
  __int128 v55; // [rsp+110h] [rbp+10h]
  __int128 v56; // [rsp+120h] [rbp+20h]

  if ( a6 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"QOP == 0", (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a1 + 384))(a1, *(_QWORD *)a3 + 16LL);
    v15 = v14;
    if ( a10 )
      *a10 = v14;
    v40 = -1;
    v38 = 1029;
    v42 = 0;
    if ( *a4 || !*(_QWORD *)a3 )
      v16 = 4096;
    else
      v16 = __ROR2__(v14, 8);
    v41 = v16;
    v43 = _byteswap_uint64(a5);
    v17 = 2;
    if ( !a8 )
      v17 = 3;
    v39 = v17;
    if ( a9 )
      v39 = v17 | 4;
    v46 = 16;
    v47 = &v38;
    (*(void (__fastcall **)(__int64 *, char **, __int64, __int64, int))(*a1 + 168))(a1, v36, a7, 2LL * a8 + 22, 1);
    v20 = (int)v37;
    if ( (int)v37 >= 0 )
    {
      LOBYTE(v19) = 1;
      (*(void (__fastcall **)(__int64 *, char **, char **, __int64))(*a1 + 184))(a1, v44, v36, v19);
      v22 = (int)v45;
      if ( (int)v45 >= 0 )
      {
        v23 = *a1;
        v33 = 0;
        v24 = *(__int64 (__fastcall **)(__int64 *, __int64 *, char **, char **, __int64, _QWORD *, __int64 *))(v23 + 368);
        v34 = 0;
        LODWORD(v35) = -1073741823;
        v25 = v24(a1, &v48, v36, v44, a3, a4, &v46);
        v33 = *(_QWORD *)v25;
        v27 = *(_QWORD *)(v25 + 8);
        *(_QWORD *)v25 = 0;
        v34 = v27;
        v28 = *(_DWORD *)(v25 + 16);
        *(_QWORD *)(v25 + 8) = 0;
        LODWORD(v35) = v28;
        *(_DWORD *)(v25 + 16) = -1073741823;
        if ( v49 )
          Kerb3961Free(v49);
        v29 = (int)v35;
        if ( (int)v35 >= 0 )
        {
          v30 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 392))(a1);
          v31 = v33 - *(_QWORD *)a3;
          v49 = *(__int16 **)a3;
          v48 = v30;
          *(_QWORD *)&v50 = v15 & -(__int64)(a10 != 0);
          *((_QWORD *)&v50 + 1) = v31 - v30 - v50;
          v42 = __ROR2__(WORD4(v50), 8);
          Kerb3961::Split<4>(&v53, &v33, &v48);
          memmove(*(void **)(a3 + 8), Src, *(_QWORD *)a3);
          v49 = v47;
          v48 = v46;
          v50 = v56;
          v51 = v53;
          v52 = v55;
          Kerb3961::Concatenate<4>(a2, &v48);
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"encryption",
            (const char *)(unsigned int)v35,
            v26);
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v29;
        }
        if ( v34 )
          Kerb3961Free(v34);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"state",
          (const char *)(unsigned int)v45,
          v21);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v22;
      }
      if ( v44[1] )
         Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v44[0]);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"specificKey",
        (const char *)(unsigned int)v37,
        v18);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v20;
    }
    if ( v36[1] )
       Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v36[0]);
  }
  return a2;
}

```

## disassembly

```asm
0x180003240  push    rbp
0x180003242  push    rbx
0x180003243  push    rsi
0x180003244  push    rdi
0x180003245  push    r12
0x180003247  push    r13
0x180003249  push    r14
0x18000324b  push    r15
0x18000324d  lea     rbp, [rsp-38h]
0x180003252  sub     rsp, 138h
0x180003259  mov     rbx, [rbp+70h+arg_30]
0x180003260  xor     r15d, r15d
0x180003263  mov     r13, r9
0x180003266  mov     r12, [rbp+70h+arg_48]
0x18000326d  mov     r14, r8
0x180003270  mov     rdi, rdx
0x180003273  mov     rsi, rcx
0x180003276  cmp     [rbp+70h+arg_28], r15d
0x18000327d  jz      short loc_18000329E
0x18000327f  lea     rcx, aQop0; "QOP == 0"
0x180003286  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000328b  mov     [rdi], r15
0x18000328e  mov     [rdi+8], r15
0x180003292  mov     dword ptr [rdi+10h], 0C000000Dh
0x180003299  jmp     loc_18000356F
0x18000329e  mov     rax, [rcx]
0x1800032a1  mov     rdx, [r8]
0x1800032a4  add     rdx, 10h
0x1800032a8  mov     rax, [rax+180h]
0x1800032af  call    _guard_dispatch_icall
0x1800032b4  xor     r8d, r8d
0x1800032b7  mov     r15, rax
0x1800032ba  test    r12, r12
0x1800032bd  jz      short loc_1800032C3
0x1800032bf  mov     [r12], rax
0x1800032c3  mov     eax, 405h
0x1800032c8  mov     [rsp+170h+var_FD], 0FFh
0x1800032cd  mov     [rsp+170h+var_100], ax
0x1800032d2  mov     [rsp+170h+var_FA], r8w
0x1800032d8  cmp     [r13+0], r8
0x1800032dc  jnz     short loc_1800032ED
0x1800032de  cmp     [r14], r8
0x1800032e1  jz      short loc_1800032ED
0x1800032e3  movzx   eax, r15w
0x1800032e7  ror     ax, 8
0x1800032eb  jmp     short loc_1800032F2
0x1800032ed  mov     eax, 1000h
0x1800032f2  movzx   ecx, [rbp+70h+arg_38]
0x1800032f9  mov     edx, 3
0x1800032fe  mov     [rsp+170h+var_FC], ax
0x180003303  test    cl, cl
0x180003305  mov     rax, [rbp+70h+arg_20]
0x18000330c  bswap   rax
0x18000330f  mov     [rsp+170h+var_F8], rax
0x180003314  mov     al, 2
0x180003316  movzx   eax, al
0x180003319  cmovz   eax, edx
0x18000331c  mov     [rsp+170h+var_FE], al
0x180003320  cmp     [rbp+70h+arg_40], r8b
0x180003327  jz      short loc_18000332F
0x180003329  or      al, 4
0x18000332b  mov     [rsp+170h+var_FE], al
0x18000332f  lea     rax, [rsp+170h+var_100]
0x180003334  mov     [rbp+70h+var_D0], 10h
0x18000333c  mov     [rbp+70h+var_C8], rax
0x180003340  lea     r9, ds:16h[rcx*2]
0x180003348  mov     rax, [rsi]
0x18000334b  lea     rdx, [rsp+170h+var_118]
0x180003350  mov     r8, rbx
0x180003353  mov     dword ptr [rsp+170h+var_150], 1
0x18000335b  mov     rcx, rsi
0x18000335e  mov     rax, [rax+0A8h]
0x180003365  call    _guard_dispatch_icall
0x18000336a  mov     ebx, dword ptr [rsp+170h+var_108]
0x18000336e  test    ebx, ebx
0x180003370  jns     short loc_180003397
0x180003372  mov     edx, ebx; char *
0x180003374  lea     rcx, aSpecifickey; "specificKey"
0x18000337b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180003380  mov     qword ptr [rdi], 0
0x180003387  mov     qword ptr [rdi+8], 0
0x18000338f  mov     [rdi+10h], ebx
0x180003392  jmp     loc_18000355B
0x180003397  mov     rax, [rsi]
0x18000339a  lea     r8, [rsp+170h+var_118]
0x18000339f  mov     r9b, 1
0x1800033a2  lea     rdx, [rbp+70h+var_E8]
0x1800033a6  mov     rcx, rsi
0x1800033a9  mov     rax, [rax+0B8h]
0x1800033b0  call    _guard_dispatch_icall
0x1800033b5  mov     ebx, dword ptr [rbp+70h+var_D8]
0x1800033b8  test    ebx, ebx
0x1800033ba  jns     short loc_1800033E1
0x1800033bc  mov     edx, ebx; char *
0x1800033be  lea     rcx, aState; "state"
0x1800033c5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800033ca  mov     qword ptr [rdi], 0
0x1800033d1  mov     qword ptr [rdi+8], 0
0x1800033d9  mov     [rdi+10h], ebx
0x1800033dc  jmp     loc_180003549
0x1800033e1  mov     rax, [rsi]
0x1800033e4  lea     rcx, [rbp+70h+var_D0]
0x1800033e8  mov     [rsp+170h+var_140], rcx
0x1800033ed  lea     r9, [rbp+70h+var_E8]
0x1800033f1  mov     [rsp+170h+var_148], r13
0x1800033f6  lea     r8, [rsp+170h+var_118]
0x1800033fb  lea     rdx, [rbp+70h+var_C0]
0x1800033ff  mov     [rsp+170h+var_130], 0
0x180003408  mov     rax, [rax+170h]
0x18000340f  mov     rcx, rsi
0x180003412  mov     [rsp+170h+var_128], 0
0x18000341b  mov     dword ptr [rsp+170h+var_120], 0C0000001h
0x180003423  mov     [rsp+170h+var_150], r14
0x180003428  call    _guard_dispatch_icall
0x18000342d  mov     rcx, [rsp+170h+var_128]
0x180003432  xor     r13d, r13d
0x180003435  mov     rbx, rax
0x180003438  test    rcx, rcx
0x18000343b  jz      short loc_180003442
0x18000343d  call    Kerb3961Free
0x180003442  mov     rcx, [rbx]
0x180003445  mov     [rsp+170h+var_130], rcx
0x18000344a  mov     rcx, [rbx+8]
0x18000344e  mov     [rbx], r13
0x180003451  mov     [rsp+170h+var_128], rcx
0x180003456  mov     eax, [rbx+10h]
0x180003459  mov     [rbx+8], r13
0x18000345d  mov     dword ptr [rsp+170h+var_120], eax
0x180003461  mov     dword ptr [rbx+10h], 0C0000001h
0x180003468  mov     rcx, [rbp+70h+var_B8]
0x18000346c  test    rcx, rcx
0x18000346f  jz      short loc_180003476
0x180003471  call    Kerb3961Free
0x180003476  mov     ebx, dword ptr [rsp+170h+var_120]
0x18000347a  test    ebx, ebx
0x18000347c  jns     short loc_18000349B
0x18000347e  mov     edx, ebx; char *
0x180003480  lea     rcx, aEncryption; "encryption"
0x180003487  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000348c  mov     [rdi], r13
0x18000348f  mov     [rdi+8], r13
0x180003493  mov     [rdi+10h], ebx
0x180003496  jmp     loc_18000353A
0x18000349b  mov     rax, [rsi]
0x18000349e  neg     r12
0x1800034a1  mov     rcx, rsi
0x1800034a4  sbb     rbx, rbx
0x1800034a7  and     rbx, r15
0x1800034aa  mov     rax, [rax+188h]
0x1800034b1  call    _guard_dispatch_icall
0x1800034b6  mov     r8, [r14]
0x1800034b9  lea     rcx, [rbp+70h+var_80]
0x1800034bd  mov     r9, [rsp+170h+var_130]
0x1800034c2  sub     r9, r8
0x1800034c5  mov     [rbp+70h+var_B8], r8
0x1800034c9  sub     r9, rax
0x1800034cc  mov     [rbp+70h+var_C0], rax
0x1800034d0  sub     r9, rbx
0x1800034d3  mov     qword ptr [rbp+70h+var_B0], rbx
0x1800034d7  movzx   edx, r9w
0x1800034db  mov     qword ptr [rbp+70h+var_B0+8], r9
0x1800034df  ror     dx, 8
0x1800034e3  lea     r8, [rbp+70h+var_C0]
0x1800034e7  mov     [rsp+170h+var_FA], dx
0x1800034ec  lea     rdx, [rsp+170h+var_130]
0x1800034f1  call    ??$Split@$03@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$03@utl@@AEBUMutableBinary@0@U?$array@_K$03@2@@Z; Kerb3961::Split<4>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,4>)
0x1800034f6  mov     r8, [r14]; Size
0x1800034f9  mov     rdx, [rbp+70h+Src]; Src
0x1800034fd  mov     rcx, [r14+8]; void *
0x180003501  call    memmove
0x180003506  mov     rcx, [rbp+70h+var_C8]
0x18000350a  lea     rdx, [rbp+70h+var_C0]
0x18000350e  mov     rax, [rbp+70h+var_D0]
0x180003512  movaps  xmm0, [rbp+70h+var_50]
0x180003516  movaps  xmm1, [rbp+70h+var_80]
0x18000351a  movaps  xmm2, [rbp+70h+var_60]
0x18000351e  mov     [rbp+70h+var_B8], rcx
0x180003522  mov     rcx, rdi
0x180003525  mov     [rbp+70h+var_C0], rax
0x180003529  movaps  [rbp+70h+var_B0], xmm0
0x18000352d  movaps  [rbp+70h+var_A0], xmm1
0x180003531  movaps  [rbp+70h+var_90], xmm2
0x180003535  call    ??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z; Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)
0x18000353a  mov     rcx, [rsp+170h+var_128]
0x18000353f  test    rcx, rcx
0x180003542  jz      short loc_180003549
0x180003544  call    Kerb3961Free
0x180003549  mov     rdx, [rbp+70h+var_E0]
0x18000354d  test    rdx, rdx
0x180003550  jz      short loc_18000355B
0x180003552  mov     rcx, [rbp+70h+var_E8]
0x180003556  call    ??_9EncryptionAlgorithm@Kerb3961@@$BLA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}
0x18000355b  mov     rdx, [rsp+170h+var_110]
0x180003560  test    rdx, rdx
0x180003563  jz      short loc_18000356F
0x180003565  mov     rcx, [rsp+170h+var_118]
0x18000356a  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x18000356f  mov     rax, rdi
0x180003572  add     rsp, 138h
0x180003579  pop     r15
0x18000357b  pop     r14
0x18000357d  pop     r13
0x18000357f  pop     r12
0x180003581  pop     rdi
0x180003582  pop     rsi
0x180003583  pop     rbx
0x180003584  pop     rbp
0x180003585  retn
```
