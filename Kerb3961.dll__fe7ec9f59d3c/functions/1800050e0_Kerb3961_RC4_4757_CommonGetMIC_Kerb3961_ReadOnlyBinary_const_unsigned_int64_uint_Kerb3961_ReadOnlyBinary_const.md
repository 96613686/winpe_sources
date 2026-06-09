# Kerb3961::RC4_4757::CommonGetMIC(Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800050e0`
- end: `0x18000546c`
- name: `?CommonGetMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_KI0_N2@Z`
- size: `908`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002fc0`
- `0x1800033f4`
- `0x1800050e0`
- `0x180006ee0`
- `0x180008500`
- `0x1800085cc`
- `0x18000901c`
- `0x180009190`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::CommonGetMIC(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        char a7)
{
  int v11; // ebx
  const unsigned __int16 *v12; // rdx
  int v13; // r8d
  int v14; // r15d
  void *v15; // rcx
  _DWORD *v16; // rbx
  __int64 v17; // r8
  bool v18; // cf
  int v19; // r8d
  int v20; // esi
  int v21; // r8d
  int v22; // esi
  int v23; // r8d
  int v24; // esi
  int v25; // r8d
  int v26; // esi
  void *v27; // rcx
  void *v28; // r12
  __int64 v29; // r8
  int v30; // r8d
  int v31; // esi
  void *v32; // rcx
  __int64 v33; // rsi
  void *v34; // rcx
  int v35; // eax
  void *v36; // rcx
  __int64 v37; // rax
  __int64 v39; // [rsp+20h] [rbp-B1h] BYREF
  void *v40; // [rsp+28h] [rbp-A9h]
  char *v41; // [rsp+30h] [rbp-A1h]
  __int64 v42; // [rsp+38h] [rbp-99h] BYREF
  void *v43; // [rsp+40h] [rbp-91h]
  char *v44; // [rsp+48h] [rbp-89h]
  _BYTE v45[8]; // [rsp+50h] [rbp-81h] BYREF
  void *v46; // [rsp+58h] [rbp-79h]
  char *v47; // [rsp+60h] [rbp-71h]
  _BYTE v48[8]; // [rsp+68h] [rbp-69h] BYREF
  void *v49; // [rsp+70h] [rbp-61h]
  char *v50; // [rsp+78h] [rbp-59h]
  _BYTE v51[8]; // [rsp+80h] [rbp-51h] BYREF
  void *v52; // [rsp+88h] [rbp-49h]
  char *v53; // [rsp+90h] [rbp-41h]
  __int64 v54; // [rsp+98h] [rbp-39h] BYREF
  _QWORD *v55; // [rsp+A0h] [rbp-31h]
  char *v56; // [rsp+A8h] [rbp-29h]
  _BYTE v57[8]; // [rsp+B0h] [rbp-21h] BYREF
  void *v58; // [rsp+B8h] [rbp-19h]
  char v59; // [rsp+120h] [rbp+4Fh] BYREF

  v11 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v11 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v12);
  Kerb3961::MakeBuffer(&v54);
  v14 = (int)v56;
  if ( (int)v56 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"headerBuffer",
      (const char *)(unsigned int)v56,
      v13);
    v15 = v55;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v14;
    goto LABEL_37;
  }
  v16 = v55;
  v17 = a6;
  v18 = a7 != 0;
  a7 = -a7;
  v55[2] = 0;
  v16[1] = -1;
  *v16 = 1114369;
  v16[3] = v18 - 1;
  v16[2] = _byteswap_ulong(a4);
  Kerb3961::RC4_4757::HmacData(
    a1,
    v45,
    v17,
    &__S14__1__CommonGetMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__KI0_N2_Z_4U53_B);
  v20 = (int)v47;
  if ( (int)v47 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v47, v19);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v20;
    goto LABEL_6;
  }
  v39 = 8;
  v40 = v16;
  Kerb3961::Concatenate(
    v48,
    &__S15__1__CommonGetMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__KI0_N2_Z_4U53_B,
    &v39,
    a3);
  v22 = (int)v50;
  if ( (int)v50 >= 0 )
  {
    Kerb3961::RC4_4757::HashData(a1, v51, v48);
    v24 = (int)v53;
    if ( (int)v53 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hash", (const char *)(unsigned int)v53, v23);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v24;
      goto LABEL_16;
    }
    Kerb3961::RC4_4757::HmacData(a1, &v39, v45, v51);
    v26 = (int)v41;
    if ( (int)v41 >= 0 )
    {
      v28 = v40;
      v29 = a6;
      *((_QWORD *)v16 + 2) = *(_QWORD *)v40;
      Kerb3961::RC4_4757::HmacData(
        a1,
        &v42,
        v29,
        &__S17__1__CommonGetMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__KI0_N2_Z_4U53_B);
      v31 = (int)v44;
      if ( (int)v44 >= 0 )
      {
        v39 = 8;
        v40 = v16 + 4;
        v33 = Kerb3961::RC4_4757::HmacData(a1, v57, &v42, &v39);
        if ( v43 )
          operator delete(v43, 0);
        v42 = *(_QWORD *)v33;
        v34 = *(void **)(v33 + 8);
        *(_QWORD *)v33 = 0;
        v43 = v34;
        v35 = *(_DWORD *)(v33 + 16);
        *(_QWORD *)(v33 + 8) = 0;
        LODWORD(v44) = v35;
        *(_DWORD *)(v33 + 16) = -1073741823;
        if ( v58 )
          operator delete(v58, 0);
        v31 = (int)v44;
        if ( (int)v44 >= 0 )
        {
          v39 = 8;
          v40 = v16 + 2;
          Kerb3961::RC4_4757::RC4Data(a1, &v59, &v42, &v39);
          v36 = v43;
          v37 = v54;
          *(_DWORD *)(a2 + 16) = v14;
          *(_QWORD *)a2 = v37;
          *(_QWORD *)(a2 + 8) = v16;
          if ( v36 )
            operator delete(v36, 0);
          operator delete(v28, 0);
          if ( v52 )
            operator delete(v52, 0);
          if ( v49 )
            operator delete(v49, 0);
          v15 = v46;
LABEL_37:
          if ( v15 )
            goto LABEL_38;
          return a2;
        }
      }
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Kseq", (const char *)(unsigned int)v44, v30);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      v32 = v43;
      *(_DWORD *)(a2 + 16) = v31;
      if ( v32 )
        operator delete(v32, 0);
      v27 = v28;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"checksum",
        (const char *)(unsigned int)v41,
        v25);
      v27 = v40;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v26;
      if ( !v27 )
        goto LABEL_16;
    }
    operator delete(v27, 0);
LABEL_16:
    if ( v52 )
      operator delete(v52, 0);
    goto LABEL_12;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"signBuffer",
    (const char *)(unsigned int)v50,
    v21);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v22;
LABEL_12:
  if ( v49 )
    operator delete(v49, 0);
LABEL_6:
  if ( v46 )
    operator delete(v46, 0);
  if ( v16 )
  {
    v15 = v16;
LABEL_38:
    operator delete(v15, 0);
  }
  return a2;
}

```

## disassembly

```asm
0x1800050e0  push    rbp
0x1800050e2  push    rbx
0x1800050e3  push    rsi
0x1800050e4  push    rdi
0x1800050e5  push    r12
0x1800050e7  push    r13
0x1800050e9  push    r14
0x1800050eb  push    r15
0x1800050ed  lea     rbp, [rsp-7]
0x1800050f2  sub     rsp, 0D8h
0x1800050f9  mov     r14, rcx
0x1800050fc  mov     rsi, r9
0x1800050ff  add     rcx, 8
0x180005103  mov     r12, r8
0x180005106  mov     rdi, rdx
0x180005109  mov     rax, [rcx]
0x18000510c  mov     rax, [rax+68h]
0x180005110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005115  mov     r10, [r14]
0x180005118  mov     ebx, eax
0x18000511a  mov     rcx, r14
0x18000511d  mov     rax, [r10+0E0h]
0x180005124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005129  cmp     ebx, eax
0x18000512b  jnz     loc_18000545F
0x180005131  mov     edx, 18h
0x180005136  lea     rcx, [rbp+3Fh+var_78]
0x18000513a  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000513f  mov     r15, [rbp+3Fh+var_68]
0x180005143  xor     r13d, r13d
0x180005146  test    r15d, r15d
0x180005149  jns     short loc_18000516E
0x18000514b  mov     edx, r15d; char *
0x18000514e  lea     rcx, aHeaderbuffer; "headerBuffer"
0x180005155  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000515a  mov     rcx, [rbp+3Fh+var_70]
0x18000515e  mov     [rdi], r13
0x180005161  mov     [rdi+8], r13
0x180005165  mov     [rdi+10h], r15d
0x180005169  jmp     loc_18000543C
0x18000516e  mov     rbx, [rbp+3Fh+var_70]
0x180005172  lea     r9, ?$S14@?1??CommonGetMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_KI0_N2@Z@4U53@B
0x180005179  mov     r8, [rbp+3Fh+arg_28]
0x18000517d  or      edx, 0FFFFFFFFh
0x180005180  neg     [rbp+3Fh+arg_30]
0x180005183  mov     rcx, r14
0x180005186  bswap   esi
0x180005188  mov     [rbx+10h], r13
0x18000518c  sbb     eax, eax
0x18000518e  mov     [rbx+4], edx
0x180005191  not     eax
0x180005193  and     eax, edx
0x180005195  mov     dword ptr [rbx], 110101h
0x18000519b  mov     [rbx+0Ch], eax
0x18000519e  lea     rdx, [rsp+110h+var_C0]
0x1800051a3  mov     [rbx+8], esi
0x1800051a6  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800051ab  mov     esi, dword ptr [rbp+3Fh+var_B0]
0x1800051ae  test    esi, esi
0x1800051b0  jns     short loc_1800051EB
0x1800051b2  mov     edx, esi; char *
0x1800051b4  lea     rcx, aKsign; "Ksign"
0x1800051bb  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800051c0  mov     [rdi], r13
0x1800051c3  mov     [rdi+8], r13
0x1800051c7  mov     [rdi+10h], esi
0x1800051ca  mov     rcx, [rbp+3Fh+var_B8]; void *
0x1800051ce  test    rcx, rcx
0x1800051d1  jz      short loc_1800051DA
0x1800051d3  xor     edx, edx; struct std::nothrow_t *
0x1800051d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800051da  test    rbx, rbx
0x1800051dd  jz      loc_180005448
0x1800051e3  mov     rcx, rbx
0x1800051e6  jmp     loc_180005441
0x1800051eb  mov     r9, r12
0x1800051ee  mov     [rsp+110h+var_F0], 8
0x1800051f7  lea     r8, [rsp+110h+var_F0]
0x1800051fc  mov     [rsp+110h+var_E8], rbx
0x180005201  lea     rdx, ?$S15@?1??CommonGetMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_KI0_N2@Z@4U53@B
0x180005208  lea     rcx, [rbp+3Fh+var_A8]
0x18000520c  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005211  mov     esi, dword ptr [rbp+3Fh+var_98]
0x180005214  test    esi, esi
0x180005216  jns     short loc_180005242
0x180005218  mov     edx, esi; char *
0x18000521a  lea     rcx, aSignbuffer; "signBuffer"
0x180005221  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005226  mov     [rdi], r13
0x180005229  mov     [rdi+8], r13
0x18000522d  mov     [rdi+10h], esi
0x180005230  mov     rcx, [rbp+3Fh+var_A0]; void *
0x180005234  test    rcx, rcx
0x180005237  jz      short loc_1800051CA
0x180005239  xor     edx, edx; struct std::nothrow_t *
0x18000523b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005240  jmp     short loc_1800051CA
0x180005242  lea     r8, [rbp+3Fh+var_A8]
0x180005246  mov     rcx, r14
0x180005249  lea     rdx, [rbp+3Fh+var_90]
0x18000524d  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x180005252  mov     esi, dword ptr [rbp+3Fh+var_80]
0x180005255  test    esi, esi
0x180005257  jns     short loc_180005283
0x180005259  mov     edx, esi; char *
0x18000525b  lea     rcx, aHash; "hash"
0x180005262  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005267  mov     [rdi], r13
0x18000526a  mov     [rdi+8], r13
0x18000526e  mov     [rdi+10h], esi
0x180005271  mov     rcx, [rbp+3Fh+var_88]; void *
0x180005275  test    rcx, rcx
0x180005278  jz      short loc_180005230
0x18000527a  xor     edx, edx; struct std::nothrow_t *
0x18000527c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005281  jmp     short loc_180005230
0x180005283  lea     r9, [rbp+3Fh+var_90]
0x180005287  mov     rcx, r14
0x18000528a  lea     r8, [rsp+110h+var_C0]
0x18000528f  lea     rdx, [rsp+110h+var_F0]
0x180005294  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005299  mov     esi, dword ptr [rsp+110h+var_E0]
0x18000529d  test    esi, esi
0x18000529f  jns     short loc_1800052CC
0x1800052a1  mov     edx, esi; char *
0x1800052a3  lea     rcx, aChecksum; "checksum"
0x1800052aa  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800052af  mov     rcx, [rsp+110h+var_E8]; void *
0x1800052b4  mov     [rdi], r13
0x1800052b7  mov     [rdi+8], r13
0x1800052bb  mov     [rdi+10h], esi
0x1800052be  test    rcx, rcx
0x1800052c1  jz      short loc_180005271
0x1800052c3  xor     edx, edx; struct std::nothrow_t *
0x1800052c5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800052ca  jmp     short loc_180005271
0x1800052cc  mov     r12, [rsp+110h+var_E8]
0x1800052d1  lea     r13, [rbx+10h]
0x1800052d5  mov     r8, [rbp+3Fh+arg_28]
0x1800052d9  lea     r9, ?$S17@?1??CommonGetMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_KI0_N2@Z@4U53@B
0x1800052e0  lea     rdx, [rsp+110h+var_D8]
0x1800052e5  mov     rcx, r14
0x1800052e8  mov     rax, [r12]
0x1800052ec  mov     [r13+0], rax
0x1800052f0  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800052f5  mov     esi, dword ptr [rsp+110h+var_C8]
0x1800052f9  test    esi, esi
0x1800052fb  jns     short loc_180005333
0x1800052fd  mov     edx, esi; char *
0x1800052ff  lea     rcx, aKseq; "Kseq"
0x180005306  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000530b  mov     qword ptr [rdi], 0
0x180005312  mov     qword ptr [rdi+8], 0
0x18000531a  mov     rcx, [rsp+110h+var_D0]; void *
0x18000531f  mov     [rdi+10h], esi
0x180005322  test    rcx, rcx
0x180005325  jz      short loc_18000532E
0x180005327  xor     edx, edx; struct std::nothrow_t *
0x180005329  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000532e  mov     rcx, r12
0x180005331  jmp     short loc_1800052C3
0x180005333  lea     r9, [rsp+110h+var_F0]
0x180005338  mov     [rsp+110h+var_F0], 8
0x180005341  lea     r8, [rsp+110h+var_D8]
0x180005346  mov     [rsp+110h+var_E8], r13
0x18000534b  lea     rdx, [rbp+3Fh+var_60]
0x18000534f  mov     rcx, r14
0x180005352  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005357  mov     rcx, [rsp+110h+var_D0]; void *
0x18000535c  xor     r13d, r13d
0x18000535f  mov     rsi, rax
0x180005362  test    rcx, rcx
0x180005365  jz      short loc_18000536E
0x180005367  xor     edx, edx; struct std::nothrow_t *
0x180005369  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000536e  mov     rcx, [rsi]
0x180005371  mov     [rsp+110h+var_D8], rcx
0x180005376  mov     rcx, [rsi+8]
0x18000537a  mov     [rsi], r13
0x18000537d  mov     [rsp+110h+var_D0], rcx
0x180005382  mov     eax, [rsi+10h]
0x180005385  mov     [rsi+8], r13
0x180005389  mov     dword ptr [rsp+110h+var_C8], eax
0x18000538d  mov     dword ptr [rsi+10h], 0C0000001h
0x180005394  mov     rcx, [rbp+3Fh+var_58]; void *
0x180005398  test    rcx, rcx
0x18000539b  jz      short loc_1800053A4
0x18000539d  xor     edx, edx; struct std::nothrow_t *
0x18000539f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800053a4  mov     esi, dword ptr [rsp+110h+var_C8]
0x1800053a8  test    esi, esi
0x1800053aa  jns     short loc_1800053C6
0x1800053ac  mov     edx, esi; char *
0x1800053ae  lea     rcx, aKseq; "Kseq"
0x1800053b5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800053ba  mov     [rdi], r13
0x1800053bd  mov     [rdi+8], r13
0x1800053c1  jmp     loc_18000531A
0x1800053c6  lea     rax, [rbx+8]
0x1800053ca  mov     [rsp+110h+var_F0], 8
0x1800053d3  lea     r9, [rsp+110h+var_F0]
0x1800053d8  mov     [rsp+110h+var_E8], rax
0x1800053dd  lea     r8, [rsp+110h+var_D8]
0x1800053e2  mov     rcx, r14
0x1800053e5  lea     rdx, [rbp+3Fh+arg_0]
0x1800053e9  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x1800053ee  mov     rcx, [rsp+110h+var_D0]; void *
0x1800053f3  mov     rax, [rbp+3Fh+var_78]
0x1800053f7  mov     [rdi+10h], r15d
0x1800053fb  mov     [rdi], rax
0x1800053fe  mov     [rdi+8], rbx
0x180005402  test    rcx, rcx
0x180005405  jz      short loc_18000540E
0x180005407  xor     edx, edx; struct std::nothrow_t *
0x180005409  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000540e  xor     edx, edx; struct std::nothrow_t *
0x180005410  mov     rcx, r12; void *
0x180005413  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005418  mov     rcx, [rbp+3Fh+var_88]; void *
0x18000541c  test    rcx, rcx
0x18000541f  jz      short loc_180005428
0x180005421  xor     edx, edx; struct std::nothrow_t *
0x180005423  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005428  mov     rcx, [rbp+3Fh+var_A0]; void *
0x18000542c  test    rcx, rcx
0x18000542f  jz      short loc_180005438
0x180005431  xor     edx, edx; struct std::nothrow_t *
0x180005433  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005438  mov     rcx, [rbp+3Fh+var_B8]; void *
0x18000543c  test    rcx, rcx
0x18000543f  jz      short loc_180005448
0x180005441  xor     edx, edx; struct std::nothrow_t *
0x180005443  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005448  mov     rax, rdi
0x18000544b  add     rsp, 0D8h
0x180005452  pop     r15
0x180005454  pop     r14
0x180005456  pop     r13
0x180005458  pop     r12
0x18000545a  pop     rdi
0x18000545b  pop     rsi
0x18000545c  pop     rbx
0x18000545d  pop     rbp
0x18000545e  retn
0x18000545f  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x180005466  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
