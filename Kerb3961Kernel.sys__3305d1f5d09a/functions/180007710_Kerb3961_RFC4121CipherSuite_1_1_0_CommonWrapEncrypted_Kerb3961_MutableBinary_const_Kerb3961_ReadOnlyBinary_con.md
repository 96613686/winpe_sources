# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonWrapEncrypted(Kerb3961::MutableBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x180007710`
- end: `0x180007ab4`
- name: `?CommonWrapEncrypted@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMutableBinary@2@AEBUReadOnlyBinary@2@_KI1_N3PEA_K@Z`
- size: `932`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001464`
- `0x180001794`
- `0x1800018e8`
- `0x180001900`
- `0x1800037e0`
- `0x180005e34`
- `0x180007710`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,0>::CommonWrapEncrypted(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        int a6,
        __int64 a7,
        unsigned __int8 a8,
        char a9,
        __int64 *a10)
{
  __int64 v14; // rax
  __int64 v15; // r14
  char v16; // al
  int v17; // r8d
  __int64 v18; // r9
  int v19; // ebx
  int v20; // r8d
  int v21; // ebx
  __int64 v22; // rax
  int v23; // r8d
  int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rbx
  int v27; // r8d
  __int64 v28; // rcx
  int v29; // eax
  int v30; // ebx
  __int64 v31; // rax
  __int64 v32; // r9
  char *v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  char *v35; // [rsp+50h] [rbp-B0h]
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h]
  char *v38; // [rsp+68h] [rbp-98h]
  char *v39[2]; // [rsp+70h] [rbp-90h] BYREF
  char *v40; // [rsp+80h] [rbp-80h]
  __int16 v41; // [rsp+88h] [rbp-78h] BYREF
  char v42; // [rsp+8Ah] [rbp-76h]
  char v43; // [rsp+8Bh] [rbp-75h]
  __int16 v44; // [rsp+8Ch] [rbp-74h]
  __int16 v45; // [rsp+8Eh] [rbp-72h]
  unsigned __int64 v46; // [rsp+90h] [rbp-70h]
  __int64 v47; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v48; // [rsp+A8h] [rbp-58h]
  __int128 v49; // [rsp+B0h] [rbp-50h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+D0h] [rbp-30h]
  _BYTE v52[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v53; // [rsp+E8h] [rbp-18h]
  char *v54; // [rsp+F0h] [rbp-10h]
  _QWORD v55[3]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v56; // [rsp+110h] [rbp+10h] BYREF
  void *Src; // [rsp+128h] [rbp+28h]
  __int128 v58; // [rsp+130h] [rbp+30h]
  __int128 v59; // [rsp+140h] [rbp+40h]

  if ( a6 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"QOP == 0", (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 368LL))(a1, *(_QWORD *)a3 + 16LL);
    v15 = v14;
    if ( a10 )
      *a10 = v14;
    v43 = -1;
    v45 = 0;
    v41 = 1029;
    v46 = _byteswap_uint64(a5);
    v44 = __ROR2__(v14, 8);
    v16 = 2;
    if ( !a8 )
      v16 = 3;
    v42 = v16;
    if ( a9 )
      v42 = v16 | 4;
    v55[0] = 16;
    v55[1] = &v41;
    (*(void (__fastcall **)(__int64, char **, __int64, __int64, int))(*(_QWORD *)a1 + 168LL))(
      a1,
      v34,
      a7,
      2LL * a8 + 22,
      1);
    v19 = (int)v35;
    if ( (int)v35 >= 0 )
    {
      LOBYTE(v18) = 1;
      (*(void (__fastcall **)(__int64, char **, char **, __int64))(*(_QWORD *)a1 + 184LL))(a1, v39, v34, v18);
      v21 = (int)v40;
      if ( (int)v40 >= 0 )
      {
        v36 = 0;
        v37 = 0;
        LODWORD(v38) = -1073741823;
        v22 = Kerb3961::RandomBuffer(&v47, v15);
        Kerb3961::Concatenate(v52, a3, v22, v55);
        if ( v48 )
          Kerb3961Free(v48);
        v24 = (int)v54;
        if ( (int)v54 >= 0 )
        {
          v26 = (*(__int64 (__fastcall **)(__int64, __int64 *, char **, char **, _BYTE *, __int64))(*(_QWORD *)a1 + 200LL))(
                  a1,
                  &v47,
                  v34,
                  v39,
                  v52,
                  a4);
          if ( v37 )
            Kerb3961Free(v37);
          v36 = *(_QWORD *)v26;
          v28 = *(_QWORD *)(v26 + 8);
          *(_QWORD *)v26 = 0;
          v37 = v28;
          v29 = *(_DWORD *)(v26 + 16);
          *(_QWORD *)(v26 + 8) = 0;
          LODWORD(v38) = v29;
          *(_DWORD *)(v26 + 16) = -1073741823;
          if ( v48 )
            Kerb3961Free(v48);
          if ( v53 )
            Kerb3961Free(v53);
          v30 = (int)v38;
          if ( (int)v38 >= 0 )
          {
            v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 376LL))(a1);
            v32 = v36 - *(_QWORD *)a3;
            v48 = *(__int16 **)a3;
            v47 = v31;
            *(_QWORD *)&v49 = v15 & -(__int64)(a10 != 0);
            *((_QWORD *)&v49 + 1) = v32 - v31 - v49;
            v45 = __ROR2__(WORD4(v49), 8);
            Kerb3961::Split<4>(&v56, &v36, &v47);
            memmove(*(void **)(a3 + 8), Src, *(_QWORD *)a3);
            v48 = &v41;
            v49 = v59;
            v50 = v56;
            v51 = v58;
            v47 = 16;
            Kerb3961::Concatenate<4>(a2, &v47);
          }
          else
          {
            Kerb3961::Logging::Verify::StatusFailed(
              (Kerb3961::Logging::Verify *)"encryption",
              (const char *)(unsigned int)v38,
              v27);
            *(_QWORD *)a2 = 0;
            *(_QWORD *)(a2 + 8) = 0;
            *(_DWORD *)(a2 + 16) = v30;
          }
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"encryptBuffer",
            (const char *)(unsigned int)v54,
            v23);
          v25 = v53;
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v24;
          if ( v25 )
            Kerb3961Free(v25);
        }
        if ( v37 )
          Kerb3961Free(v37);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"state",
          (const char *)(unsigned int)v40,
          v20);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v21;
      }
      if ( v39[1] )
         Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v39[0]);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"specificKey",
        (const char *)(unsigned int)v35,
        v17);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v19;
    }
    if ( v34[1] )
       Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v34[0]);
  }
  return a2;
}

```

## disassembly

```asm
0x180007710  push    rbp
0x180007712  push    rbx
0x180007713  push    rsi
0x180007714  push    rdi
0x180007715  push    r12
0x180007717  push    r13
0x180007719  push    r14
0x18000771b  push    r15
0x18000771d  lea     rbp, [rsp-58h]
0x180007722  sub     rsp, 158h
0x180007729  mov     rbx, [rbp+90h+arg_30]
0x180007730  xor     r14d, r14d
0x180007733  mov     r13, r9
0x180007736  mov     r15, [rbp+90h+arg_48]
0x18000773d  mov     r12, r8
0x180007740  mov     rdi, rdx
0x180007743  mov     rsi, rcx
0x180007746  cmp     [rbp+90h+arg_28], r14d
0x18000774d  jz      short loc_18000776E
0x18000774f  lea     rcx, aQop0; "QOP == 0"
0x180007756  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000775b  mov     [rdi], r14
0x18000775e  mov     [rdi+8], r14
0x180007762  mov     dword ptr [rdi+10h], 0C000000Dh
0x180007769  jmp     loc_180007A9C
0x18000776e  mov     rax, [rcx]
0x180007771  mov     rdx, [r8]
0x180007774  add     rdx, 10h
0x180007778  mov     rax, [rax+170h]
0x18000777f  call    _guard_dispatch_icall
0x180007784  mov     r14, rax
0x180007787  test    r15, r15
0x18000778a  jz      short loc_18000778F
0x18000778c  mov     [r15], rax
0x18000778f  xor     ecx, ecx
0x180007791  mov     [rbp+90h+var_105], 0FFh
0x180007795  mov     [rbp+90h+var_102], cx
0x180007799  mov     eax, 405h
0x18000779e  mov     [rbp+90h+var_108], ax
0x1800077a2  movzx   ecx, r14w
0x1800077a6  mov     rax, [rbp+90h+arg_20]
0x1800077ad  mov     edx, 3
0x1800077b2  ror     cx, 8
0x1800077b6  bswap   rax
0x1800077b9  mov     [rbp+90h+var_100], rax
0x1800077bd  mov     al, 2
0x1800077bf  mov     [rbp+90h+var_104], cx
0x1800077c3  movzx   ecx, [rbp+90h+arg_38]
0x1800077ca  test    cl, cl
0x1800077cc  movzx   eax, al
0x1800077cf  cmovz   eax, edx
0x1800077d2  cmp     [rbp+90h+arg_40], 0
0x1800077d9  mov     [rbp+90h+var_106], al
0x1800077dc  jz      short loc_1800077E3
0x1800077de  or      al, 4
0x1800077e0  mov     [rbp+90h+var_106], al
0x1800077e3  lea     rax, [rbp+90h+var_108]
0x1800077e7  mov     [rbp+90h+var_98], 10h
0x1800077ef  mov     [rbp+90h+var_90], rax
0x1800077f3  lea     r9, ds:16h[rcx*2]
0x1800077fb  mov     rax, [rsi]
0x1800077fe  lea     rdx, [rsp+190h+var_150]
0x180007803  mov     r8, rbx
0x180007806  mov     dword ptr [rsp+190h+var_170], 1
0x18000780e  mov     rcx, rsi
0x180007811  mov     rax, [rax+0A8h]
0x180007818  call    _guard_dispatch_icall
0x18000781d  mov     ebx, dword ptr [rsp+190h+var_140]
0x180007821  test    ebx, ebx
0x180007823  jns     short loc_18000784A
0x180007825  mov     edx, ebx; char *
0x180007827  lea     rcx, aSpecifickey; "specificKey"
0x18000782e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007833  mov     qword ptr [rdi], 0
0x18000783a  mov     qword ptr [rdi+8], 0
0x180007842  mov     [rdi+10h], ebx
0x180007845  jmp     loc_180007A88
0x18000784a  mov     rax, [rsi]
0x18000784d  lea     r8, [rsp+190h+var_150]
0x180007852  mov     r9b, 1
0x180007855  lea     rdx, [rsp+190h+var_120]
0x18000785a  mov     rcx, rsi
0x18000785d  mov     rax, [rax+0B8h]
0x180007864  call    _guard_dispatch_icall
0x180007869  mov     ebx, dword ptr [rbp+90h+var_110]
0x18000786c  test    ebx, ebx
0x18000786e  jns     short loc_180007895
0x180007870  mov     edx, ebx; char *
0x180007872  lea     rcx, aState; "state"
0x180007879  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000787e  mov     qword ptr [rdi], 0
0x180007885  mov     qword ptr [rdi+8], 0
0x18000788d  mov     [rdi+10h], ebx
0x180007890  jmp     loc_180007A74
0x180007895  mov     rdx, r14
0x180007898  mov     [rsp+190h+var_138], 0
0x1800078a1  lea     rcx, [rbp+90h+var_F0]
0x1800078a5  mov     [rsp+190h+var_130], 0
0x1800078ae  mov     dword ptr [rsp+190h+var_128], 0C0000001h
0x1800078b6  call    ?RandomBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::RandomBuffer(unsigned __int64)
0x1800078bb  lea     r9, [rbp+90h+var_98]
0x1800078bf  mov     r8, rax
0x1800078c2  mov     rdx, r12
0x1800078c5  lea     rcx, [rbp+90h+var_B0]
0x1800078c9  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800078ce  mov     rcx, [rbp+90h+var_E8]
0x1800078d2  test    rcx, rcx
0x1800078d5  jz      short loc_1800078DC
0x1800078d7  call    Kerb3961Free
0x1800078dc  mov     ebx, dword ptr [rbp+90h+var_A0]
0x1800078df  test    ebx, ebx
0x1800078e1  jns     short loc_18000791A
0x1800078e3  mov     edx, ebx; char *
0x1800078e5  lea     rcx, aEncryptbuffer; "encryptBuffer"
0x1800078ec  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800078f1  mov     rcx, [rbp+90h+var_A8]
0x1800078f5  mov     qword ptr [rdi], 0
0x1800078fc  mov     qword ptr [rdi+8], 0
0x180007904  mov     [rdi+10h], ebx
0x180007907  test    rcx, rcx
0x18000790a  jz      loc_180007A65
0x180007910  call    Kerb3961Free
0x180007915  jmp     loc_180007A65
0x18000791a  mov     rax, [rsi]
0x18000791d  lea     rcx, [rbp+90h+var_B0]
0x180007921  mov     [rsp+190h+var_168], r13
0x180007926  lea     r9, [rsp+190h+var_120]
0x18000792b  mov     [rsp+190h+var_170], rcx
0x180007930  lea     r8, [rsp+190h+var_150]
0x180007935  lea     rdx, [rbp+90h+var_F0]
0x180007939  mov     rcx, rsi
0x18000793c  mov     rax, [rax+0C8h]
0x180007943  call    _guard_dispatch_icall
0x180007948  mov     rcx, [rsp+190h+var_130]
0x18000794d  xor     r13d, r13d
0x180007950  mov     rbx, rax
0x180007953  test    rcx, rcx
0x180007956  jz      short loc_18000795D
0x180007958  call    Kerb3961Free
0x18000795d  mov     rcx, [rbx]
0x180007960  mov     [rsp+190h+var_138], rcx
0x180007965  mov     rcx, [rbx+8]
0x180007969  mov     [rbx], r13
0x18000796c  mov     [rsp+190h+var_130], rcx
0x180007971  mov     eax, [rbx+10h]
0x180007974  mov     [rbx+8], r13
0x180007978  mov     dword ptr [rsp+190h+var_128], eax
0x18000797c  mov     dword ptr [rbx+10h], 0C0000001h
0x180007983  mov     rcx, [rbp+90h+var_E8]
0x180007987  test    rcx, rcx
0x18000798a  jz      short loc_180007991
0x18000798c  call    Kerb3961Free
0x180007991  mov     rcx, [rbp+90h+var_A8]
0x180007995  test    rcx, rcx
0x180007998  jz      short loc_18000799F
0x18000799a  call    Kerb3961Free
0x18000799f  mov     ebx, dword ptr [rsp+190h+var_128]
0x1800079a3  test    ebx, ebx
0x1800079a5  jns     short loc_1800079C4
0x1800079a7  mov     edx, ebx; char *
0x1800079a9  lea     rcx, aEncryption; "encryption"
0x1800079b0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800079b5  mov     [rdi], r13
0x1800079b8  mov     [rdi+8], r13
0x1800079bc  mov     [rdi+10h], ebx
0x1800079bf  jmp     loc_180007A65
0x1800079c4  mov     rax, [rsi]
0x1800079c7  neg     r15
0x1800079ca  mov     rcx, rsi
0x1800079cd  sbb     rbx, rbx
0x1800079d0  and     rbx, r14
0x1800079d3  mov     rax, [rax+178h]
0x1800079da  call    _guard_dispatch_icall
0x1800079df  mov     r8, [r12]
0x1800079e3  lea     rcx, [rbp+90h+var_80]
0x1800079e7  mov     r9, [rsp+190h+var_138]
0x1800079ec  sub     r9, r8
0x1800079ef  mov     [rbp+90h+var_E8], r8
0x1800079f3  sub     r9, rax
0x1800079f6  mov     [rbp+90h+var_F0], rax
0x1800079fa  sub     r9, rbx
0x1800079fd  mov     qword ptr [rbp+90h+var_E0], rbx
0x180007a01  movzx   edx, r9w
0x180007a05  mov     qword ptr [rbp+90h+var_E0+8], r9
0x180007a09  ror     dx, 8
0x180007a0d  lea     r8, [rbp+90h+var_F0]
0x180007a11  mov     [rbp+90h+var_102], dx
0x180007a15  lea     rdx, [rsp+190h+var_138]
0x180007a1a  call    ??$Split@$03@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$03@utl@@AEBUMutableBinary@0@U?$array@_K$03@2@@Z; Kerb3961::Split<4>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,4>)
0x180007a1f  mov     r8, [r12]; Size
0x180007a23  mov     rdx, [rbp+90h+Src]; Src
0x180007a27  mov     rcx, [r12+8]; void *
0x180007a2c  call    memmove
0x180007a31  movaps  xmm0, [rbp+90h+var_50]
0x180007a35  lea     rax, [rbp+90h+var_108]
0x180007a39  movaps  xmm1, [rbp+90h+var_80]
0x180007a3d  lea     rdx, [rbp+90h+var_F0]
0x180007a41  movaps  xmm2, [rbp+90h+var_60]
0x180007a45  mov     rcx, rdi
0x180007a48  mov     [rbp+90h+var_E8], rax
0x180007a4c  movaps  [rbp+90h+var_E0], xmm0
0x180007a50  movaps  [rbp+90h+var_D0], xmm1
0x180007a54  movaps  [rbp+90h+var_C0], xmm2
0x180007a58  mov     [rbp+90h+var_F0], 10h
0x180007a60  call    ??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z; Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)
0x180007a65  mov     rcx, [rsp+190h+var_130]
0x180007a6a  test    rcx, rcx
0x180007a6d  jz      short loc_180007A74
0x180007a6f  call    Kerb3961Free
0x180007a74  mov     rdx, [rsp+190h+var_118]
0x180007a79  test    rdx, rdx
0x180007a7c  jz      short loc_180007A88
0x180007a7e  mov     rcx, [rsp+190h+var_120]
0x180007a83  call    ??_9EncryptionAlgorithm@Kerb3961@@$BLA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}
0x180007a88  mov     rdx, [rsp+190h+var_148]
0x180007a8d  test    rdx, rdx
0x180007a90  jz      short loc_180007A9C
0x180007a92  mov     rcx, [rsp+190h+var_150]
0x180007a97  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180007a9c  mov     rax, rdi
0x180007a9f  add     rsp, 158h
0x180007aa6  pop     r15
0x180007aa8  pop     r14
0x180007aaa  pop     r13
0x180007aac  pop     r12
0x180007aae  pop     rdi
0x180007aaf  pop     rsi
0x180007ab0  pop     rbx
0x180007ab1  pop     rbp
0x180007ab2  retn
```
