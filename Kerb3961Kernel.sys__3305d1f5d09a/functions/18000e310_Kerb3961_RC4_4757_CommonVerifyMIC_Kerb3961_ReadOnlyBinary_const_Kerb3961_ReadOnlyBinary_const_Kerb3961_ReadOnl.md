# Kerb3961::RC4_4757::CommonVerifyMIC(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x18000e310`
- end: `0x18000e69b`
- name: `?CommonVerifyMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_N1@Z`
- size: `907`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800037e0`
- `0x180003a38`
- `0x18000e310`
- `0x18000fd70`
- `0x18000fe44`
- `0x180010290`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x18000e36c`: `inputSignature.length == sizeof(MICToken)`
- `0x18000e610`: `seqCopy.Direction == expectedDirection`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::CommonVerifyMIC(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        char a6)
{
  int v10; // ebx
  const unsigned __int16 *v11; // rdx
  char *v12; // rcx
  __int64 v13; // rsi
  int v14; // r8d
  int v15; // ebx
  int v16; // r8d
  int v17; // ebx
  int v18; // r8d
  int v19; // ebx
  int v20; // r8d
  int v21; // ebx
  __int64 *v22; // rcx
  __int64 *v23; // rbx
  char v24; // r8
  __int64 i; // rdx
  char v26; // cl
  char v27; // al
  int v28; // r8d
  unsigned int v29; // r14d
  __int64 v30; // r14
  __int64 v31; // rcx
  int v32; // eax
  const char *v33; // rdx
  bool v34; // cf
  __int64 v36; // [rsp+20h] [rbp-81h] BYREF
  __int64 v37; // [rsp+28h] [rbp-79h] BYREF
  __int64 *v38; // [rsp+30h] [rbp-71h]
  char *v39; // [rsp+38h] [rbp-69h]
  __int64 v40; // [rsp+40h] [rbp-61h] BYREF
  __int64 v41; // [rsp+48h] [rbp-59h]
  char *v42; // [rsp+50h] [rbp-51h]
  _BYTE v43[8]; // [rsp+58h] [rbp-49h] BYREF
  __int64 v44; // [rsp+60h] [rbp-41h]
  char *v45; // [rsp+68h] [rbp-39h]
  _BYTE v46[8]; // [rsp+70h] [rbp-31h] BYREF
  __int64 v47; // [rsp+78h] [rbp-29h]
  char *v48; // [rsp+80h] [rbp-21h]
  _BYTE v49[8]; // [rsp+88h] [rbp-19h] BYREF
  __int64 v50; // [rsp+90h] [rbp-11h]
  char *v51; // [rsp+98h] [rbp-9h]
  _BYTE v52[8]; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v53; // [rsp+A8h] [rbp+7h]
  char v54; // [rsp+F0h] [rbp+4Fh] BYREF

  v10 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v10 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v11);
  if ( *a4 != 24 )
  {
    v12 = "inputSignature.length == sizeof(MICToken)";
LABEL_4:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v12, (const char *)v11);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = -2146893041;
    return a2;
  }
  v13 = a4[1];
  if ( *(_WORD *)v13 != 257 )
  {
    v12 = "header.TOK_ID == header.ID";
    goto LABEL_4;
  }
  if ( *(_WORD *)(v13 + 2) != 17 )
  {
    v12 = "header.SGN_ALG == header.SignAlgorithm";
    goto LABEL_4;
  }
  if ( *(_DWORD *)(v13 + 4) != -1 )
  {
    v12 = "header.Filler == header.FillerBytes";
    goto LABEL_4;
  }
  Kerb3961::RC4_4757::HmacData(
    a1,
    v43,
    a5,
    &__S340__1__CommonVerifyMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_00_N1_Z_4U53_B);
  v15 = (int)v45;
  if ( (int)v45 >= 0 )
  {
    v38 = (__int64 *)a4[1];
    v37 = 8;
    Kerb3961::Concatenate(
      v46,
      &__S341__1__CommonVerifyMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_00_N1_Z_4U53_B,
      &v37,
      a3);
    v17 = (int)v48;
    if ( (int)v48 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"signBuffer",
        (const char *)(unsigned int)v48,
        v16);
      *(_OWORD *)a2 = 0;
      *(_DWORD *)(a2 + 12) = v17;
LABEL_41:
      if ( v47 )
        Kerb3961Free(v47);
      goto LABEL_43;
    }
    Kerb3961::RC4_4757::HashData(a1, v49, v46);
    v19 = (int)v51;
    if ( (int)v51 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hash", (const char *)(unsigned int)v51, v18);
      *(_OWORD *)a2 = 0;
      *(_DWORD *)(a2 + 12) = v19;
      goto LABEL_39;
    }
    Kerb3961::RC4_4757::HmacData(a1, &v37, v43, v49);
    v21 = (int)v39;
    if ( (int)v39 >= 0 )
    {
      v23 = v38;
      v24 = 0;
      for ( i = 0; i != 8; ++i )
      {
        v26 = *(_BYTE *)(i + v13 + 16);
        v27 = *((_BYTE *)v38 + i);
        v24 |= v27 ^ v26;
      }
      if ( v24 )
      {
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"SecureEqualBuffer(checksum, reinterpret_cast<const uint8_t*>(&header.SGN_CKSUM), "
                                       "sizeof(header.SGN_CKSUM))",
          (const char *)8);
        *(_OWORD *)a2 = 0;
        *(_DWORD *)(a2 + 12) = -2146893041;
      }
      else
      {
        Kerb3961::RC4_4757::HmacData(
          a1,
          &v40,
          a5,
          &__S343__1__CommonVerifyMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_00_N1_Z_4U53_B);
        v29 = (unsigned int)v42;
        if ( (int)v42 < 0 )
          goto LABEL_25;
        v37 = 8;
        v38 = (__int64 *)(v13 + 16);
        v30 = Kerb3961::RC4_4757::HmacData(a1, v52, &v40, &v37);
        if ( v41 )
          Kerb3961Free(v41);
        v40 = *(_QWORD *)v30;
        v31 = *(_QWORD *)(v30 + 8);
        *(_QWORD *)v30 = 0;
        v41 = v31;
        v32 = *(_DWORD *)(v30 + 16);
        *(_QWORD *)(v30 + 8) = 0;
        LODWORD(v42) = v32;
        *(_DWORD *)(v30 + 16) = -1073741823;
        if ( v53 )
          Kerb3961Free(v53);
        v29 = (unsigned int)v42;
        if ( (int)v42 < 0 )
        {
LABEL_25:
          Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Kseq", (const char *)v29, v28);
          *(_OWORD *)a2 = 0;
          *(_DWORD *)(a2 + 12) = v29;
        }
        else
        {
          v36 = *(_QWORD *)(v13 + 8);
          v37 = 8;
          v38 = &v36;
          Kerb3961::RC4_4757::RC4Data(a1, &v54, &v40, &v37);
          v34 = a6 != 0;
          a6 = -a6;
          if ( HIDWORD(v36) == -v34 )
          {
            LODWORD(v36) = _byteswap_ulong(v36);
            *(_QWORD *)a2 = (unsigned int)v36;
            *(_DWORD *)(a2 + 8) = 0;
            *(_DWORD *)(a2 + 12) = 0;
          }
          else
          {
            Kerb3961::Logging::Verify::ConditionFailed(
              (Kerb3961::Logging::Verify *)"seqCopy.Direction == expectedDirection",
              v33);
            *(_OWORD *)a2 = 0;
            *(_DWORD *)(a2 + 12) = -2146893041;
          }
        }
        if ( v41 )
          Kerb3961Free(v41);
      }
      if ( !v23 )
        goto LABEL_39;
      v22 = v23;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"checksum",
        (const char *)(unsigned int)v39,
        v20);
      v22 = v38;
      *(_OWORD *)a2 = 0;
      *(_DWORD *)(a2 + 12) = v21;
      if ( !v22 )
        goto LABEL_39;
    }
    Kerb3961Free(v22);
LABEL_39:
    if ( v50 )
      Kerb3961Free(v50);
    goto LABEL_41;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v45, v14);
  *(_OWORD *)a2 = 0;
  *(_DWORD *)(a2 + 12) = v15;
LABEL_43:
  if ( v44 )
    Kerb3961Free(v44);
  return a2;
}

```

## disassembly

```asm
0x18000e310  mov     [rsp-8+arg_8], rbx
0x18000e315  mov     [rsp-8+arg_10], rsi
0x18000e31a  push    rbp
0x18000e31b  push    rdi
0x18000e31c  push    r12
0x18000e31e  push    r14
0x18000e320  push    r15
0x18000e322  lea     rbp, [rsp-1Fh]
0x18000e327  sub     rsp, 0C0h
0x18000e32e  mov     r15, rcx
0x18000e331  mov     r14, r9
0x18000e334  add     rcx, 8
0x18000e338  mov     r12, r8
0x18000e33b  mov     rdi, rdx
0x18000e33e  mov     rax, [rcx]
0x18000e341  mov     rax, [rax+68h]
0x18000e345  call    _guard_dispatch_icall
0x18000e34a  mov     r10, [r15]
0x18000e34d  mov     ebx, eax
0x18000e34f  mov     rcx, r15
0x18000e352  mov     rax, [r10+0E0h]
0x18000e359  call    _guard_dispatch_icall
0x18000e35e  cmp     ebx, eax
0x18000e360  jnz     loc_18000E68E
0x18000e366  cmp     qword ptr [r14], 18h
0x18000e36a  jz      short loc_18000E38A
0x18000e36c  lea     rcx, aInputsignature_0; "inputSignature.length == sizeof(MICToke"...
0x18000e373  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000e378  xorps   xmm0, xmm0
0x18000e37b  movups  xmmword ptr [rdi], xmm0
0x18000e37e  mov     dword ptr [rdi+0Ch], 8009030Fh
0x18000e385  jmp     loc_18000E66E
0x18000e38a  mov     rsi, [r14+8]
0x18000e38e  mov     eax, 101h
0x18000e393  cmp     [rsi], ax
0x18000e396  jz      short loc_18000E3A1
0x18000e398  lea     rcx, aHeaderTokIdHea; "header.TOK_ID == header.ID"
0x18000e39f  jmp     short loc_18000E373
0x18000e3a1  cmp     word ptr [rsi+2], 11h
0x18000e3a6  jz      short loc_18000E3B1
0x18000e3a8  lea     rcx, aHeaderSgnAlgHe; "header.SGN_ALG == header.SignAlgorithm"
0x18000e3af  jmp     short loc_18000E373
0x18000e3b1  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x18000e3b5  jz      short loc_18000E3C0
0x18000e3b7  lea     rcx, aHeaderFillerHe; "header.Filler == header.FillerBytes"
0x18000e3be  jmp     short loc_18000E373
0x18000e3c0  mov     r8, [rbp+3Fh+arg_20]
0x18000e3c4  lea     r9, ?$S340@?1??CommonVerifyMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@00_N1@Z@4U53@B
0x18000e3cb  lea     rdx, [rbp+3Fh+var_88]
0x18000e3cf  mov     rcx, r15
0x18000e3d2  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000e3d7  mov     ebx, dword ptr [rbp+3Fh+var_78]
0x18000e3da  test    ebx, ebx
0x18000e3dc  jns     short loc_18000E3FA
0x18000e3de  mov     edx, ebx; char *
0x18000e3e0  lea     rcx, aKsign; "Ksign"
0x18000e3e7  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e3ec  xorps   xmm0, xmm0
0x18000e3ef  movups  xmmword ptr [rdi], xmm0
0x18000e3f2  mov     [rdi+0Ch], ebx
0x18000e3f5  jmp     loc_18000E660
0x18000e3fa  mov     rax, [r14+8]
0x18000e3fe  lea     r8, [rbp+3Fh+var_B8]
0x18000e402  mov     r9, r12
0x18000e405  mov     [rbp+3Fh+var_B0], rax
0x18000e409  lea     rdx, ?$S341@?1??CommonVerifyMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@00_N1@Z@4U53@B
0x18000e410  mov     [rbp+3Fh+var_B8], 8
0x18000e418  lea     rcx, [rbp+3Fh+var_70]
0x18000e41c  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000e421  mov     ebx, dword ptr [rbp+3Fh+var_60]
0x18000e424  test    ebx, ebx
0x18000e426  jns     short loc_18000E444
0x18000e428  mov     edx, ebx; char *
0x18000e42a  lea     rcx, aSignbuffer; "signBuffer"
0x18000e431  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e436  xorps   xmm0, xmm0
0x18000e439  movups  xmmword ptr [rdi], xmm0
0x18000e43c  mov     [rdi+0Ch], ebx
0x18000e43f  jmp     loc_18000E652
0x18000e444  lea     r8, [rbp+3Fh+var_70]
0x18000e448  mov     rcx, r15
0x18000e44b  lea     rdx, [rbp+3Fh+var_58]
0x18000e44f  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x18000e454  mov     ebx, dword ptr [rbp+3Fh+var_48]
0x18000e457  test    ebx, ebx
0x18000e459  jns     short loc_18000E477
0x18000e45b  mov     edx, ebx; char *
0x18000e45d  lea     rcx, aHash; "hash"
0x18000e464  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e469  xorps   xmm0, xmm0
0x18000e46c  movups  xmmword ptr [rdi], xmm0
0x18000e46f  mov     [rdi+0Ch], ebx
0x18000e472  jmp     loc_18000E644
0x18000e477  lea     r9, [rbp+3Fh+var_58]
0x18000e47b  mov     rcx, r15
0x18000e47e  lea     r8, [rbp+3Fh+var_88]
0x18000e482  lea     rdx, [rbp+3Fh+var_B8]
0x18000e486  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000e48b  mov     ebx, dword ptr [rbp+3Fh+var_A8]
0x18000e48e  test    ebx, ebx
0x18000e490  jns     short loc_18000E4BB
0x18000e492  mov     edx, ebx; char *
0x18000e494  lea     rcx, aChecksum; "checksum"
0x18000e49b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e4a0  mov     rcx, [rbp+3Fh+var_B0]
0x18000e4a4  xorps   xmm0, xmm0
0x18000e4a7  movups  xmmword ptr [rdi], xmm0
0x18000e4aa  mov     [rdi+0Ch], ebx
0x18000e4ad  test    rcx, rcx
0x18000e4b0  jz      loc_18000E644
0x18000e4b6  jmp     loc_18000E63F
0x18000e4bb  mov     rbx, [rbp+3Fh+var_B0]
0x18000e4bf  lea     r12, [rsi+10h]
0x18000e4c3  xor     r8b, r8b
0x18000e4c6  xor     edx, edx
0x18000e4c8  mov     cl, [rdx+r12]
0x18000e4cc  mov     al, [rdx+rbx]
0x18000e4cf  inc     rdx; char *
0x18000e4d2  xor     cl, al
0x18000e4d4  or      r8b, cl
0x18000e4d7  cmp     rdx, 8
0x18000e4db  jnz     short loc_18000E4C8
0x18000e4dd  test    r8b, r8b
0x18000e4e0  jz      short loc_18000E500
0x18000e4e2  lea     rcx, aSecureequalbuf_1; "SecureEqualBuffer(checksum, reinterpret"...
0x18000e4e9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000e4ee  xorps   xmm0, xmm0
0x18000e4f1  movups  xmmword ptr [rdi], xmm0
0x18000e4f4  mov     dword ptr [rdi+0Ch], 8009030Fh
0x18000e4fb  jmp     loc_18000E637
0x18000e500  mov     r8, [rbp+3Fh+arg_20]
0x18000e504  lea     r9, ?$S343@?1??CommonVerifyMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@00_N1@Z@4U53@B
0x18000e50b  lea     rdx, [rbp+3Fh+var_A0]
0x18000e50f  mov     rcx, r15
0x18000e512  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000e517  mov     r14d, dword ptr [rbp+3Fh+var_90]
0x18000e51b  test    r14d, r14d
0x18000e51e  jns     short loc_18000E53E
0x18000e520  mov     edx, r14d; char *
0x18000e523  lea     rcx, aKseq; "Kseq"
0x18000e52a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e52f  xorps   xmm0, xmm0
0x18000e532  movups  xmmword ptr [rdi], xmm0
0x18000e535  mov     [rdi+0Ch], r14d
0x18000e539  jmp     loc_18000E629
0x18000e53e  lea     r9, [rbp+3Fh+var_B8]
0x18000e542  mov     [rbp+3Fh+var_B8], 8
0x18000e54a  lea     r8, [rbp+3Fh+var_A0]
0x18000e54e  mov     [rbp+3Fh+var_B0], r12
0x18000e552  lea     rdx, [rbp+3Fh+var_40]
0x18000e556  mov     rcx, r15
0x18000e559  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000e55e  mov     rcx, [rbp+3Fh+var_98]
0x18000e562  mov     r14, rax
0x18000e565  test    rcx, rcx
0x18000e568  jz      short loc_18000E56F
0x18000e56a  call    Kerb3961Free
0x18000e56f  mov     rcx, [r14]
0x18000e572  mov     r12d, 0C0000001h
0x18000e578  mov     [rbp+3Fh+var_A0], rcx
0x18000e57c  mov     rcx, [r14+8]
0x18000e580  mov     qword ptr [r14], 0
0x18000e587  mov     [rbp+3Fh+var_98], rcx
0x18000e58b  mov     eax, [r14+10h]
0x18000e58f  mov     qword ptr [r14+8], 0
0x18000e597  mov     dword ptr [rbp+3Fh+var_90], eax
0x18000e59a  mov     [r14+10h], r12d
0x18000e59e  mov     rcx, [rbp+3Fh+var_38]
0x18000e5a2  test    rcx, rcx
0x18000e5a5  jz      short loc_18000E5AC
0x18000e5a7  call    Kerb3961Free
0x18000e5ac  mov     r14d, dword ptr [rbp+3Fh+var_90]
0x18000e5b0  test    r14d, r14d
0x18000e5b3  js      loc_18000E520
0x18000e5b9  mov     rax, [rsi+8]
0x18000e5bd  lea     r9, [rbp+3Fh+var_B8]
0x18000e5c1  mov     [rsp+0E0h+var_C0], rax
0x18000e5c6  lea     r8, [rbp+3Fh+var_A0]
0x18000e5ca  lea     rax, [rsp+0E0h+var_C0]
0x18000e5cf  mov     [rbp+3Fh+var_B8], 8
0x18000e5d7  lea     rdx, [rbp+3Fh+arg_0]
0x18000e5db  mov     [rbp+3Fh+var_B0], rax
0x18000e5df  mov     rcx, r15
0x18000e5e2  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x18000e5e7  neg     [rbp+3Fh+arg_28]
0x18000e5ea  sbb     eax, eax
0x18000e5ec  cmp     dword ptr [rbp+3Fh+var_C0+4], eax
0x18000e5ef  jnz     short loc_18000E610
0x18000e5f1  mov     ecx, dword ptr [rsp+0E0h+var_C0]
0x18000e5f5  bswap   ecx
0x18000e5f7  mov     ecx, ecx
0x18000e5f9  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x18000e5fd  mov     [rdi], rcx
0x18000e600  mov     dword ptr [rdi+8], 0
0x18000e607  mov     dword ptr [rdi+0Ch], 0
0x18000e60e  jmp     short loc_18000E629
0x18000e610  lea     rcx, aSeqcopyDirecti; "seqCopy.Direction == expectedDirection"
0x18000e617  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000e61c  xorps   xmm0, xmm0
0x18000e61f  movups  xmmword ptr [rdi], xmm0
0x18000e622  mov     dword ptr [rdi+0Ch], 8009030Fh
0x18000e629  mov     rcx, [rbp+3Fh+var_98]
0x18000e62d  test    rcx, rcx
0x18000e630  jz      short loc_18000E637
0x18000e632  call    Kerb3961Free
0x18000e637  test    rbx, rbx
0x18000e63a  jz      short loc_18000E644
0x18000e63c  mov     rcx, rbx
0x18000e63f  call    Kerb3961Free
0x18000e644  mov     rcx, [rbp+3Fh+var_50]
0x18000e648  test    rcx, rcx
0x18000e64b  jz      short loc_18000E652
0x18000e64d  call    Kerb3961Free
0x18000e652  mov     rcx, [rbp+3Fh+var_68]
0x18000e656  test    rcx, rcx
0x18000e659  jz      short loc_18000E660
0x18000e65b  call    Kerb3961Free
0x18000e660  mov     rcx, [rbp+3Fh+var_80]
0x18000e664  test    rcx, rcx
0x18000e667  jz      short loc_18000E66E
0x18000e669  call    Kerb3961Free
0x18000e66e  lea     r11, [rsp+0E0h+var_20]
0x18000e676  mov     rax, rdi
0x18000e679  mov     rbx, [r11+38h]
0x18000e67d  mov     rsi, [r11+40h]
0x18000e681  mov     rsp, r11
0x18000e684  pop     r15
0x18000e686  pop     r14
0x18000e688  pop     r12
0x18000e68a  pop     rdi
0x18000e68b  pop     rbp
0x18000e68c  retn
0x18000e68e  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x18000e695  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
