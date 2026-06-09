# Kerb3961::RC4_4757::CommonGetMIC(Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x18000d580`
- end: `0x18000d8f5`
- name: `?CommonGetMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_KI0_N2@Z`
- size: `885`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800037e0`
- `0x180003a38`
- `0x180005b1c`
- `0x18000d580`
- `0x18000fd70`
- `0x18000fe44`
- `0x180010290`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::CommonGetMIC(
        _QWORD *a1,
        __int64 a2,
        __int128 *a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        char a7)
{
  int v11; // ebx
  const unsigned __int16 *v12; // rdx
  int v13; // r8d
  int v14; // r15d
  __int64 v15; // rcx
  __int64 v16; // rbx
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
  __int64 v27; // rcx
  __int64 v28; // r12
  __int64 v29; // r8
  int v30; // r8d
  int v31; // esi
  __int64 v32; // rcx
  __int64 v33; // rsi
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int128 v39; // [rsp+20h] [rbp-B1h] BYREF
  char *v40; // [rsp+30h] [rbp-A1h]
  __int64 v41; // [rsp+38h] [rbp-99h] BYREF
  __int64 v42; // [rsp+40h] [rbp-91h]
  char *v43; // [rsp+48h] [rbp-89h]
  _BYTE v44[8]; // [rsp+50h] [rbp-81h] BYREF
  __int64 v45; // [rsp+58h] [rbp-79h]
  char *v46; // [rsp+60h] [rbp-71h]
  _BYTE v47[8]; // [rsp+68h] [rbp-69h] BYREF
  __int64 v48; // [rsp+70h] [rbp-61h]
  char *v49; // [rsp+78h] [rbp-59h]
  _BYTE v50[8]; // [rsp+80h] [rbp-51h] BYREF
  __int64 v51; // [rsp+88h] [rbp-49h]
  char *v52; // [rsp+90h] [rbp-41h]
  __int64 v53; // [rsp+98h] [rbp-39h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-31h]
  char *v55; // [rsp+A8h] [rbp-29h]
  _BYTE v56[8]; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-19h]
  char v58; // [rsp+120h] [rbp+4Fh] BYREF

  v11 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v11 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v12);
  Kerb3961::MakeBuffer(&v53);
  v14 = (int)v55;
  if ( (int)v55 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"headerBuffer",
      (const char *)(unsigned int)v55,
      v13);
    v15 = v54;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v14;
    goto LABEL_37;
  }
  v16 = v54;
  v17 = a6;
  v18 = a7 != 0;
  a7 = -a7;
  *(_QWORD *)(v54 + 16) = 0;
  *(_DWORD *)(v16 + 4) = -1;
  *(_DWORD *)v16 = 1114369;
  *(_DWORD *)(v16 + 12) = v18 - 1;
  *(_DWORD *)(v16 + 8) = _byteswap_ulong(a4);
  Kerb3961::RC4_4757::HmacData(
    a1,
    v44,
    v17,
    &__S336__1__CommonGetMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__KI0_N2_Z_4U53_B);
  v20 = (int)v46;
  if ( (int)v46 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v46, v19);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v20;
    goto LABEL_6;
  }
  *(_QWORD *)&v39 = 8;
  *((_QWORD *)&v39 + 1) = v16;
  Kerb3961::Concatenate(
    (__int64)v47,
    &__S337__1__CommonGetMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__KI0_N2_Z_4U53_B,
    &v39,
    a3);
  v22 = (int)v49;
  if ( (int)v49 >= 0 )
  {
    Kerb3961::RC4_4757::HashData(a1, v50, v47);
    v24 = (int)v52;
    if ( (int)v52 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hash", (const char *)(unsigned int)v52, v23);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v24;
      goto LABEL_16;
    }
    Kerb3961::RC4_4757::HmacData(a1, &v39, v44, v50);
    v26 = (int)v40;
    if ( (int)v40 >= 0 )
    {
      v28 = *((_QWORD *)&v39 + 1);
      v29 = a6;
      *(_QWORD *)(v16 + 16) = **((_QWORD **)&v39 + 1);
      Kerb3961::RC4_4757::HmacData(
        a1,
        &v41,
        v29,
        &__S339__1__CommonGetMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__KI0_N2_Z_4U53_B);
      v31 = (int)v43;
      if ( (int)v43 >= 0 )
      {
        *(_QWORD *)&v39 = 8;
        *((_QWORD *)&v39 + 1) = v16 + 16;
        v33 = Kerb3961::RC4_4757::HmacData(a1, v56, &v41, &v39);
        if ( v42 )
          Kerb3961Free(v42);
        v41 = *(_QWORD *)v33;
        v34 = *(_QWORD *)(v33 + 8);
        *(_QWORD *)v33 = 0;
        v42 = v34;
        v35 = *(_DWORD *)(v33 + 16);
        *(_QWORD *)(v33 + 8) = 0;
        LODWORD(v43) = v35;
        *(_DWORD *)(v33 + 16) = -1073741823;
        if ( v57 )
          Kerb3961Free(v57);
        v31 = (int)v43;
        if ( (int)v43 >= 0 )
        {
          *(_QWORD *)&v39 = 8;
          *((_QWORD *)&v39 + 1) = v16 + 8;
          Kerb3961::RC4_4757::RC4Data(a1, &v58, &v41, &v39);
          v36 = v42;
          v37 = v53;
          *(_DWORD *)(a2 + 16) = v14;
          *(_QWORD *)a2 = v37;
          *(_QWORD *)(a2 + 8) = v16;
          if ( v36 )
            Kerb3961Free(v36);
          Kerb3961Free(v28);
          if ( v51 )
            Kerb3961Free(v51);
          if ( v48 )
            Kerb3961Free(v48);
          v15 = v45;
LABEL_37:
          if ( v15 )
            goto LABEL_38;
          return a2;
        }
      }
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Kseq", (const char *)(unsigned int)v43, v30);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      v32 = v42;
      *(_DWORD *)(a2 + 16) = v31;
      if ( v32 )
        Kerb3961Free(v32);
      v27 = v28;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"checksum",
        (const char *)(unsigned int)v40,
        v25);
      v27 = *((_QWORD *)&v39 + 1);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v26;
      if ( !v27 )
        goto LABEL_16;
    }
    Kerb3961Free(v27);
LABEL_16:
    if ( v51 )
      Kerb3961Free(v51);
    goto LABEL_12;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"signBuffer",
    (const char *)(unsigned int)v49,
    v21);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v22;
LABEL_12:
  if ( v48 )
    Kerb3961Free(v48);
LABEL_6:
  if ( v45 )
    Kerb3961Free(v45);
  if ( v16 )
  {
    v15 = v16;
LABEL_38:
    Kerb3961Free(v15);
  }
  return a2;
}

```

## disassembly

```asm
0x18000d580  push    rbp
0x18000d582  push    rbx
0x18000d583  push    rsi
0x18000d584  push    rdi
0x18000d585  push    r12
0x18000d587  push    r13
0x18000d589  push    r14
0x18000d58b  push    r15
0x18000d58d  lea     rbp, [rsp-7]
0x18000d592  sub     rsp, 0D8h
0x18000d599  mov     r14, rcx
0x18000d59c  mov     rsi, r9
0x18000d59f  add     rcx, 8
0x18000d5a3  mov     r12, r8
0x18000d5a6  mov     rdi, rdx
0x18000d5a9  mov     rax, [rcx]
0x18000d5ac  mov     rax, [rax+68h]
0x18000d5b0  call    _guard_dispatch_icall
0x18000d5b5  mov     r10, [r14]
0x18000d5b8  mov     ebx, eax
0x18000d5ba  mov     rcx, r14
0x18000d5bd  mov     rax, [r10+0E0h]
0x18000d5c4  call    _guard_dispatch_icall
0x18000d5c9  cmp     ebx, eax
0x18000d5cb  jnz     loc_18000D8E8
0x18000d5d1  mov     edx, 18h
0x18000d5d6  lea     rcx, [rbp+3Fh+var_78]
0x18000d5da  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000d5df  mov     r15, [rbp+3Fh+var_68]
0x18000d5e3  xor     r13d, r13d
0x18000d5e6  test    r15d, r15d
0x18000d5e9  jns     short loc_18000D60E
0x18000d5eb  mov     edx, r15d; char *
0x18000d5ee  lea     rcx, aHeaderbuffer; "headerBuffer"
0x18000d5f5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d5fa  mov     rcx, [rbp+3Fh+var_70]
0x18000d5fe  mov     [rdi], r13
0x18000d601  mov     [rdi+8], r13
0x18000d605  mov     [rdi+10h], r15d
0x18000d609  jmp     loc_18000D8C6
0x18000d60e  mov     rbx, [rbp+3Fh+var_70]
0x18000d612  lea     r9, ?$S336@?1??CommonGetMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_KI0_N2@Z@4U53@B
0x18000d619  mov     r8, [rbp+3Fh+arg_28]
0x18000d61d  or      edx, 0FFFFFFFFh
0x18000d620  neg     [rbp+3Fh+arg_30]
0x18000d623  mov     rcx, r14
0x18000d626  bswap   esi
0x18000d628  mov     [rbx+10h], r13
0x18000d62c  sbb     eax, eax
0x18000d62e  mov     [rbx+4], edx
0x18000d631  not     eax
0x18000d633  and     eax, edx
0x18000d635  mov     dword ptr [rbx], 110101h
0x18000d63b  mov     [rbx+0Ch], eax
0x18000d63e  lea     rdx, [rsp+110h+var_C0]
0x18000d643  mov     [rbx+8], esi
0x18000d646  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000d64b  mov     esi, dword ptr [rbp+3Fh+var_B0]
0x18000d64e  test    esi, esi
0x18000d650  jns     short loc_18000D689
0x18000d652  mov     edx, esi; char *
0x18000d654  lea     rcx, aKsign; "Ksign"
0x18000d65b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d660  mov     [rdi], r13
0x18000d663  mov     [rdi+8], r13
0x18000d667  mov     [rdi+10h], esi
0x18000d66a  mov     rcx, [rbp+3Fh+var_B8]
0x18000d66e  test    rcx, rcx
0x18000d671  jz      short loc_18000D678
0x18000d673  call    Kerb3961Free
0x18000d678  test    rbx, rbx
0x18000d67b  jz      loc_18000D8D0
0x18000d681  mov     rcx, rbx
0x18000d684  jmp     loc_18000D8CB
0x18000d689  mov     r9, r12
0x18000d68c  mov     [rsp+110h+var_F0], 8
0x18000d695  lea     r8, [rsp+110h+var_F0]
0x18000d69a  mov     [rsp+110h+var_E8], rbx
0x18000d69f  lea     rdx, ?$S337@?1??CommonGetMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_KI0_N2@Z@4U53@B
0x18000d6a6  lea     rcx, [rbp+3Fh+var_A8]
0x18000d6aa  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000d6af  mov     esi, dword ptr [rbp+3Fh+var_98]
0x18000d6b2  test    esi, esi
0x18000d6b4  jns     short loc_18000D6DE
0x18000d6b6  mov     edx, esi; char *
0x18000d6b8  lea     rcx, aSignbuffer; "signBuffer"
0x18000d6bf  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d6c4  mov     [rdi], r13
0x18000d6c7  mov     [rdi+8], r13
0x18000d6cb  mov     [rdi+10h], esi
0x18000d6ce  mov     rcx, [rbp+3Fh+var_A0]
0x18000d6d2  test    rcx, rcx
0x18000d6d5  jz      short loc_18000D66A
0x18000d6d7  call    Kerb3961Free
0x18000d6dc  jmp     short loc_18000D66A
0x18000d6de  lea     r8, [rbp+3Fh+var_A8]
0x18000d6e2  mov     rcx, r14
0x18000d6e5  lea     rdx, [rbp+3Fh+var_90]
0x18000d6e9  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x18000d6ee  mov     esi, dword ptr [rbp+3Fh+var_80]
0x18000d6f1  test    esi, esi
0x18000d6f3  jns     short loc_18000D71D
0x18000d6f5  mov     edx, esi; char *
0x18000d6f7  lea     rcx, aHash; "hash"
0x18000d6fe  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d703  mov     [rdi], r13
0x18000d706  mov     [rdi+8], r13
0x18000d70a  mov     [rdi+10h], esi
0x18000d70d  mov     rcx, [rbp+3Fh+var_88]
0x18000d711  test    rcx, rcx
0x18000d714  jz      short loc_18000D6CE
0x18000d716  call    Kerb3961Free
0x18000d71b  jmp     short loc_18000D6CE
0x18000d71d  lea     r9, [rbp+3Fh+var_90]
0x18000d721  mov     rcx, r14
0x18000d724  lea     r8, [rsp+110h+var_C0]
0x18000d729  lea     rdx, [rsp+110h+var_F0]
0x18000d72e  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000d733  mov     esi, dword ptr [rsp+110h+var_E0]
0x18000d737  test    esi, esi
0x18000d739  jns     short loc_18000D764
0x18000d73b  mov     edx, esi; char *
0x18000d73d  lea     rcx, aChecksum; "checksum"
0x18000d744  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d749  mov     rcx, [rsp+110h+var_E8]
0x18000d74e  mov     [rdi], r13
0x18000d751  mov     [rdi+8], r13
0x18000d755  mov     [rdi+10h], esi
0x18000d758  test    rcx, rcx
0x18000d75b  jz      short loc_18000D70D
0x18000d75d  call    Kerb3961Free
0x18000d762  jmp     short loc_18000D70D
0x18000d764  mov     r12, [rsp+110h+var_E8]
0x18000d769  lea     r13, [rbx+10h]
0x18000d76d  mov     r8, [rbp+3Fh+arg_28]
0x18000d771  lea     r9, ?$S339@?1??CommonGetMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_KI0_N2@Z@4U53@B
0x18000d778  lea     rdx, [rsp+110h+var_D8]
0x18000d77d  mov     rcx, r14
0x18000d780  mov     rax, [r12]
0x18000d784  mov     [r13+0], rax
0x18000d788  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000d78d  mov     esi, dword ptr [rsp+110h+var_C8]
0x18000d791  test    esi, esi
0x18000d793  jns     short loc_18000D7C9
0x18000d795  mov     edx, esi; char *
0x18000d797  lea     rcx, aKseq; "Kseq"
0x18000d79e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d7a3  mov     qword ptr [rdi], 0
0x18000d7aa  mov     qword ptr [rdi+8], 0
0x18000d7b2  mov     rcx, [rsp+110h+var_D0]
0x18000d7b7  mov     [rdi+10h], esi
0x18000d7ba  test    rcx, rcx
0x18000d7bd  jz      short loc_18000D7C4
0x18000d7bf  call    Kerb3961Free
0x18000d7c4  mov     rcx, r12
0x18000d7c7  jmp     short loc_18000D75D
0x18000d7c9  lea     r9, [rsp+110h+var_F0]
0x18000d7ce  mov     [rsp+110h+var_F0], 8
0x18000d7d7  lea     r8, [rsp+110h+var_D8]
0x18000d7dc  mov     [rsp+110h+var_E8], r13
0x18000d7e1  lea     rdx, [rbp+3Fh+var_60]
0x18000d7e5  mov     rcx, r14
0x18000d7e8  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000d7ed  mov     rcx, [rsp+110h+var_D0]
0x18000d7f2  xor     r13d, r13d
0x18000d7f5  mov     rsi, rax
0x18000d7f8  test    rcx, rcx
0x18000d7fb  jz      short loc_18000D802
0x18000d7fd  call    Kerb3961Free
0x18000d802  mov     rcx, [rsi]
0x18000d805  mov     [rsp+110h+var_D8], rcx
0x18000d80a  mov     rcx, [rsi+8]
0x18000d80e  mov     [rsi], r13
0x18000d811  mov     [rsp+110h+var_D0], rcx
0x18000d816  mov     eax, [rsi+10h]
0x18000d819  mov     [rsi+8], r13
0x18000d81d  mov     dword ptr [rsp+110h+var_C8], eax
0x18000d821  mov     dword ptr [rsi+10h], 0C0000001h
0x18000d828  mov     rcx, [rbp+3Fh+var_58]
0x18000d82c  test    rcx, rcx
0x18000d82f  jz      short loc_18000D836
0x18000d831  call    Kerb3961Free
0x18000d836  mov     esi, dword ptr [rsp+110h+var_C8]
0x18000d83a  test    esi, esi
0x18000d83c  jns     short loc_18000D858
0x18000d83e  mov     edx, esi; char *
0x18000d840  lea     rcx, aKseq; "Kseq"
0x18000d847  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000d84c  mov     [rdi], r13
0x18000d84f  mov     [rdi+8], r13
0x18000d853  jmp     loc_18000D7B2
0x18000d858  lea     rax, [rbx+8]
0x18000d85c  mov     [rsp+110h+var_F0], 8
0x18000d865  lea     r9, [rsp+110h+var_F0]
0x18000d86a  mov     [rsp+110h+var_E8], rax
0x18000d86f  lea     r8, [rsp+110h+var_D8]
0x18000d874  mov     rcx, r14
0x18000d877  lea     rdx, [rbp+3Fh+arg_0]
0x18000d87b  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x18000d880  mov     rcx, [rsp+110h+var_D0]
0x18000d885  mov     rax, [rbp+3Fh+var_78]
0x18000d889  mov     [rdi+10h], r15d
0x18000d88d  mov     [rdi], rax
0x18000d890  mov     [rdi+8], rbx
0x18000d894  test    rcx, rcx
0x18000d897  jz      short loc_18000D89E
0x18000d899  call    Kerb3961Free
0x18000d89e  mov     rcx, r12
0x18000d8a1  call    Kerb3961Free
0x18000d8a6  mov     rcx, [rbp+3Fh+var_88]
0x18000d8aa  test    rcx, rcx
0x18000d8ad  jz      short loc_18000D8B4
0x18000d8af  call    Kerb3961Free
0x18000d8b4  mov     rcx, [rbp+3Fh+var_A0]
0x18000d8b8  test    rcx, rcx
0x18000d8bb  jz      short loc_18000D8C2
0x18000d8bd  call    Kerb3961Free
0x18000d8c2  mov     rcx, [rbp+3Fh+var_B8]
0x18000d8c6  test    rcx, rcx
0x18000d8c9  jz      short loc_18000D8D0
0x18000d8cb  call    Kerb3961Free
0x18000d8d0  mov     rax, rdi
0x18000d8d3  add     rsp, 0D8h
0x18000d8da  pop     r15
0x18000d8dc  pop     r14
0x18000d8de  pop     r13
0x18000d8e0  pop     r12
0x18000d8e2  pop     rdi
0x18000d8e3  pop     rsi
0x18000d8e4  pop     rbx
0x18000d8e5  pop     rbp
0x18000d8e6  retn
0x18000d8e8  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x18000d8ef  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
