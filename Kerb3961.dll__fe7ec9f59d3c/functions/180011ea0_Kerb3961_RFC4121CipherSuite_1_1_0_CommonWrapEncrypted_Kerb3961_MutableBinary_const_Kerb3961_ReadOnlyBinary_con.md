# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonWrapEncrypted(Kerb3961::MutableBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x180011ea0`
- end: `0x18001224f`
- name: `?CommonWrapEncrypted@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMutableBinary@2@AEBUReadOnlyBinary@2@_KI1_N3PEA_K@Z`
- size: `943`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c34`
- `0x180002c4c`
- `0x180002c64`
- `0x180002fc0`
- `0x180004118`
- `0x180006ee0`
- `0x1800092a4`
- `0x1800101b8`
- `0x180011ea0`
- `0x18001d360`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,0>::CommonWrapEncrypted(
        __int64 a1,
        __int64 a2,
        void **a3,
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
  void *v25; // rcx
  __int64 v26; // rbx
  int v27; // r8d
  void *v28; // rcx
  int v29; // eax
  int v30; // ebx
  __int64 v31; // rax
  __int64 v32; // r9
  char *v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  char *v35; // [rsp+50h] [rbp-B0h]
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  void *v37; // [rsp+60h] [rbp-A0h]
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
  void *v48; // [rsp+A8h] [rbp-58h]
  __int128 v49; // [rsp+B0h] [rbp-50h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+D0h] [rbp-30h]
  _BYTE v52[8]; // [rsp+E0h] [rbp-20h] BYREF
  void *v53; // [rsp+E8h] [rbp-18h]
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
    v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 368LL))(a1, (__int64)*a3 + 16);
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
          operator delete(v48, 0);
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
            operator delete(v37, 0);
          v36 = *(_QWORD *)v26;
          v28 = *(void **)(v26 + 8);
          *(_QWORD *)v26 = 0;
          v37 = v28;
          v29 = *(_DWORD *)(v26 + 16);
          *(_QWORD *)(v26 + 8) = 0;
          LODWORD(v38) = v29;
          *(_DWORD *)(v26 + 16) = -1073741823;
          if ( v48 )
            operator delete(v48, 0);
          if ( v53 )
            operator delete(v53, 0);
          v30 = (int)v38;
          if ( (int)v38 >= 0 )
          {
            v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 376LL))(a1);
            v32 = v36 - (_QWORD)*a3;
            v48 = *a3;
            v47 = v31;
            *(_QWORD *)&v49 = v15 & -(__int64)(a10 != 0);
            *((_QWORD *)&v49 + 1) = v32 - v31 - v49;
            v45 = __ROR2__(WORD4(v49), 8);
            Kerb3961::Split<4>(&v56, &v36, &v47);
            memcpy_0(a3[1], Src, (size_t)*a3);
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
            operator delete(v25, 0);
        }
        if ( v37 )
          operator delete(v37, 0);
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
0x180011ea0  push    rbp
0x180011ea2  push    rbx
0x180011ea3  push    rsi
0x180011ea4  push    rdi
0x180011ea5  push    r12
0x180011ea7  push    r13
0x180011ea9  push    r14
0x180011eab  push    r15
0x180011ead  lea     rbp, [rsp-58h]
0x180011eb2  sub     rsp, 158h
0x180011eb9  mov     rbx, [rbp+90h+arg_30]
0x180011ec0  xor     r14d, r14d
0x180011ec3  mov     r13, r9
0x180011ec6  mov     r15, [rbp+90h+arg_48]
0x180011ecd  mov     r12, r8
0x180011ed0  mov     rdi, rdx
0x180011ed3  mov     rsi, rcx
0x180011ed6  cmp     [rbp+90h+arg_28], r14d
0x180011edd  jz      short loc_180011EFE
0x180011edf  lea     rcx, aQop0; "QOP == 0"
0x180011ee6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180011eeb  mov     [rdi], r14
0x180011eee  mov     [rdi+8], r14
0x180011ef2  mov     dword ptr [rdi+10h], 0C000000Dh
0x180011ef9  jmp     loc_180012238
0x180011efe  mov     rax, [rcx]
0x180011f01  mov     rdx, [r8]
0x180011f04  add     rdx, 10h
0x180011f08  mov     rax, [rax+170h]
0x180011f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f14  mov     r14, rax
0x180011f17  test    r15, r15
0x180011f1a  jz      short loc_180011F1F
0x180011f1c  mov     [r15], rax
0x180011f1f  xor     ecx, ecx
0x180011f21  mov     [rbp+90h+var_105], 0FFh
0x180011f25  mov     [rbp+90h+var_102], cx
0x180011f29  mov     eax, 405h
0x180011f2e  mov     [rbp+90h+var_108], ax
0x180011f32  movzx   ecx, r14w
0x180011f36  mov     rax, [rbp+90h+arg_20]
0x180011f3d  mov     edx, 3
0x180011f42  ror     cx, 8
0x180011f46  bswap   rax
0x180011f49  mov     [rbp+90h+var_100], rax
0x180011f4d  mov     al, 2
0x180011f4f  mov     [rbp+90h+var_104], cx
0x180011f53  movzx   ecx, [rbp+90h+arg_38]
0x180011f5a  test    cl, cl
0x180011f5c  movzx   eax, al
0x180011f5f  cmovz   eax, edx
0x180011f62  cmp     [rbp+90h+arg_40], 0
0x180011f69  mov     [rbp+90h+var_106], al
0x180011f6c  jz      short loc_180011F73
0x180011f6e  or      al, 4
0x180011f70  mov     [rbp+90h+var_106], al
0x180011f73  lea     rax, [rbp+90h+var_108]
0x180011f77  mov     [rbp+90h+var_98], 10h
0x180011f7f  mov     [rbp+90h+var_90], rax
0x180011f83  lea     r9, ds:16h[rcx*2]
0x180011f8b  mov     rax, [rsi]
0x180011f8e  lea     rdx, [rsp+190h+var_150]
0x180011f93  mov     r8, rbx
0x180011f96  mov     dword ptr [rsp+190h+var_170], 1
0x180011f9e  mov     rcx, rsi
0x180011fa1  mov     rax, [rax+0A8h]
0x180011fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fad  mov     ebx, dword ptr [rsp+190h+var_140]
0x180011fb1  test    ebx, ebx
0x180011fb3  jns     short loc_180011FDA
0x180011fb5  mov     edx, ebx; char *
0x180011fb7  lea     rcx, aSpecifickey; "specificKey"
0x180011fbe  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180011fc3  mov     qword ptr [rdi], 0
0x180011fca  mov     qword ptr [rdi+8], 0
0x180011fd2  mov     [rdi+10h], ebx
0x180011fd5  jmp     loc_180012224
0x180011fda  mov     rax, [rsi]
0x180011fdd  lea     r8, [rsp+190h+var_150]
0x180011fe2  mov     r9b, 1
0x180011fe5  lea     rdx, [rsp+190h+var_120]
0x180011fea  mov     rcx, rsi
0x180011fed  mov     rax, [rax+0B8h]
0x180011ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ff9  mov     ebx, dword ptr [rbp+90h+var_110]
0x180011ffc  test    ebx, ebx
0x180011ffe  jns     short loc_180012025
0x180012000  mov     edx, ebx; char *
0x180012002  lea     rcx, aState; "state"
0x180012009  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001200e  mov     qword ptr [rdi], 0
0x180012015  mov     qword ptr [rdi+8], 0
0x18001201d  mov     [rdi+10h], ebx
0x180012020  jmp     loc_180012210
0x180012025  mov     rdx, r14
0x180012028  mov     [rsp+190h+var_138], 0
0x180012031  lea     rcx, [rbp+90h+var_F0]
0x180012035  mov     [rsp+190h+var_130], 0
0x18001203e  mov     dword ptr [rsp+190h+var_128], 0C0000001h
0x180012046  call    ?RandomBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::RandomBuffer(unsigned __int64)
0x18001204b  lea     r9, [rbp+90h+var_98]
0x18001204f  mov     r8, rax
0x180012052  mov     rdx, r12
0x180012055  lea     rcx, [rbp+90h+var_B0]
0x180012059  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18001205e  mov     rcx, [rbp+90h+var_E8]; void *
0x180012062  test    rcx, rcx
0x180012065  jz      short loc_18001206E
0x180012067  xor     edx, edx; struct std::nothrow_t *
0x180012069  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001206e  mov     ebx, dword ptr [rbp+90h+var_A0]
0x180012071  test    ebx, ebx
0x180012073  jns     short loc_1800120AE
0x180012075  mov     edx, ebx; char *
0x180012077  lea     rcx, aEncryptbuffer; "encryptBuffer"
0x18001207e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180012083  mov     rcx, [rbp+90h+var_A8]; void *
0x180012087  mov     qword ptr [rdi], 0
0x18001208e  mov     qword ptr [rdi+8], 0
0x180012096  mov     [rdi+10h], ebx
0x180012099  test    rcx, rcx
0x18001209c  jz      loc_1800121FF
0x1800120a2  xor     edx, edx; struct std::nothrow_t *
0x1800120a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800120a9  jmp     loc_1800121FF
0x1800120ae  mov     rax, [rsi]
0x1800120b1  lea     rcx, [rbp+90h+var_B0]
0x1800120b5  mov     [rsp+190h+var_168], r13
0x1800120ba  lea     r9, [rsp+190h+var_120]
0x1800120bf  mov     [rsp+190h+var_170], rcx
0x1800120c4  lea     r8, [rsp+190h+var_150]
0x1800120c9  lea     rdx, [rbp+90h+var_F0]
0x1800120cd  mov     rcx, rsi
0x1800120d0  mov     rax, [rax+0C8h]
0x1800120d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120dc  mov     rcx, [rsp+190h+var_130]; void *
0x1800120e1  xor     r13d, r13d
0x1800120e4  mov     rbx, rax
0x1800120e7  test    rcx, rcx
0x1800120ea  jz      short loc_1800120F3
0x1800120ec  xor     edx, edx; struct std::nothrow_t *
0x1800120ee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800120f3  mov     rcx, [rbx]
0x1800120f6  mov     [rsp+190h+var_138], rcx
0x1800120fb  mov     rcx, [rbx+8]
0x1800120ff  mov     [rbx], r13
0x180012102  mov     [rsp+190h+var_130], rcx
0x180012107  mov     eax, [rbx+10h]
0x18001210a  mov     [rbx+8], r13
0x18001210e  mov     dword ptr [rsp+190h+var_128], eax
0x180012112  mov     dword ptr [rbx+10h], 0C0000001h
0x180012119  mov     rcx, [rbp+90h+var_E8]; void *
0x18001211d  test    rcx, rcx
0x180012120  jz      short loc_180012129
0x180012122  xor     edx, edx; struct std::nothrow_t *
0x180012124  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012129  mov     rcx, [rbp+90h+var_A8]; void *
0x18001212d  test    rcx, rcx
0x180012130  jz      short loc_180012139
0x180012132  xor     edx, edx; struct std::nothrow_t *
0x180012134  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012139  mov     ebx, dword ptr [rsp+190h+var_128]
0x18001213d  test    ebx, ebx
0x18001213f  jns     short loc_18001215E
0x180012141  mov     edx, ebx; char *
0x180012143  lea     rcx, aEncryption; "encryption"
0x18001214a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001214f  mov     [rdi], r13
0x180012152  mov     [rdi+8], r13
0x180012156  mov     [rdi+10h], ebx
0x180012159  jmp     loc_1800121FF
0x18001215e  mov     rax, [rsi]
0x180012161  neg     r15
0x180012164  mov     rcx, rsi
0x180012167  sbb     rbx, rbx
0x18001216a  and     rbx, r14
0x18001216d  mov     rax, [rax+178h]
0x180012174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012179  mov     r8, [r12]
0x18001217d  lea     rcx, [rbp+90h+var_80]
0x180012181  mov     r9, [rsp+190h+var_138]
0x180012186  sub     r9, r8
0x180012189  mov     [rbp+90h+var_E8], r8
0x18001218d  sub     r9, rax
0x180012190  mov     [rbp+90h+var_F0], rax
0x180012194  sub     r9, rbx
0x180012197  mov     qword ptr [rbp+90h+var_E0], rbx
0x18001219b  movzx   edx, r9w
0x18001219f  mov     qword ptr [rbp+90h+var_E0+8], r9
0x1800121a3  ror     dx, 8
0x1800121a7  lea     r8, [rbp+90h+var_F0]
0x1800121ab  mov     [rbp+90h+var_102], dx
0x1800121af  lea     rdx, [rsp+190h+var_138]
0x1800121b4  call    ??$Split@$03@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$03@utl@@AEBUMutableBinary@0@U?$array@_K$03@2@@Z; Kerb3961::Split<4>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,4>)
0x1800121b9  mov     r8, [r12]; Size
0x1800121bd  mov     rdx, [rbp+90h+Src]; Src
0x1800121c1  mov     rcx, [r12+8]; void *
0x1800121c6  call    memcpy_0
0x1800121cb  movaps  xmm0, [rbp+90h+var_50]
0x1800121cf  lea     rax, [rbp+90h+var_108]
0x1800121d3  movaps  xmm1, [rbp+90h+var_80]
0x1800121d7  lea     rdx, [rbp+90h+var_F0]
0x1800121db  movaps  xmm2, [rbp+90h+var_60]
0x1800121df  mov     rcx, rdi
0x1800121e2  mov     [rbp+90h+var_E8], rax
0x1800121e6  movaps  [rbp+90h+var_E0], xmm0
0x1800121ea  movaps  [rbp+90h+var_D0], xmm1
0x1800121ee  movaps  [rbp+90h+var_C0], xmm2
0x1800121f2  mov     [rbp+90h+var_F0], 10h
0x1800121fa  call    ??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z; Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)
0x1800121ff  mov     rcx, [rsp+190h+var_130]; void *
0x180012204  test    rcx, rcx
0x180012207  jz      short loc_180012210
0x180012209  xor     edx, edx; struct std::nothrow_t *
0x18001220b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012210  mov     rdx, [rsp+190h+var_118]
0x180012215  test    rdx, rdx
0x180012218  jz      short loc_180012224
0x18001221a  mov     rcx, [rsp+190h+var_120]
0x18001221f  call    ??_9EncryptionAlgorithm@Kerb3961@@$BLA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}
0x180012224  mov     rdx, [rsp+190h+var_148]
0x180012229  test    rdx, rdx
0x18001222c  jz      short loc_180012238
0x18001222e  mov     rcx, [rsp+190h+var_150]
0x180012233  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180012238  mov     rax, rdi
0x18001223b  add     rsp, 158h
0x180012242  pop     r15
0x180012244  pop     r14
0x180012246  pop     r13
0x180012248  pop     r12
0x18001224a  pop     rdi
0x18001224b  pop     rsi
0x18001224c  pop     rbx
0x18001224d  pop     rbp
0x18001224e  retn
```
