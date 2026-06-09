# Kerb3961::RC4_4757::CommonVerifyMIC(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180005ed0`
- end: `0x180006268`
- name: `?CommonVerifyMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_N1@Z`
- size: `920`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180005ed0`
- `0x180006ee0`
- `0x180008500`
- `0x1800085cc`
- `0x180009190`
- `0x18001e010`

## string_xrefs

- `0x180005f2c`: `inputSignature.length == sizeof(MICToken)`
- `0x1800061d4`: `seqCopy.Direction == expectedDirection`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::CommonVerifyMIC(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
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
  void *v22; // rcx
  void *v23; // rbx
  char v24; // r8
  __int64 i; // rdx
  char v26; // cl
  char v27; // al
  int v28; // r8d
  unsigned int v29; // r14d
  __int64 v30; // r14
  void *v31; // rcx
  int v32; // eax
  const char *v33; // rdx
  bool v34; // cf
  __int64 v36; // [rsp+20h] [rbp-81h] BYREF
  __int64 v37; // [rsp+28h] [rbp-79h] BYREF
  void *v38; // [rsp+30h] [rbp-71h]
  char *v39; // [rsp+38h] [rbp-69h]
  __int64 v40; // [rsp+40h] [rbp-61h] BYREF
  void *v41; // [rsp+48h] [rbp-59h]
  char *v42; // [rsp+50h] [rbp-51h]
  _BYTE v43[8]; // [rsp+58h] [rbp-49h] BYREF
  void *v44; // [rsp+60h] [rbp-41h]
  char *v45; // [rsp+68h] [rbp-39h]
  _BYTE v46[8]; // [rsp+70h] [rbp-31h] BYREF
  void *v47; // [rsp+78h] [rbp-29h]
  char *v48; // [rsp+80h] [rbp-21h]
  _BYTE v49[8]; // [rsp+88h] [rbp-19h] BYREF
  void *v50; // [rsp+90h] [rbp-11h]
  char *v51; // [rsp+98h] [rbp-9h]
  _BYTE v52[8]; // [rsp+A0h] [rbp-1h] BYREF
  void *v53; // [rsp+A8h] [rbp+7h]
  char v54; // [rsp+F0h] [rbp+4Fh] BYREF

  v10 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v10 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v11);
  if ( *(_QWORD *)a4 != 24 )
  {
    v12 = "inputSignature.length == sizeof(MICToken)";
LABEL_4:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v12, (const char *)v11);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = -2146893041;
    return a2;
  }
  v13 = *(_QWORD *)(a4 + 8);
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
    &__S18__1__CommonVerifyMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_00_N1_Z_4U53_B);
  v15 = (int)v45;
  if ( (int)v45 >= 0 )
  {
    v38 = *(void **)(a4 + 8);
    v37 = 8;
    Kerb3961::Concatenate(
      v46,
      &__S19__1__CommonVerifyMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_00_N1_Z_4U53_B,
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
        operator delete(v47, 0);
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
        v26 = *((_BYTE *)v38 + i);
        v27 = *(_BYTE *)(i + v13 + 16);
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
          &__S21__1__CommonVerifyMIC_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_00_N1_Z_4U53_B);
        v29 = (unsigned int)v42;
        if ( (int)v42 < 0 )
          goto LABEL_25;
        v37 = 8;
        v38 = (void *)(v13 + 16);
        v30 = Kerb3961::RC4_4757::HmacData(a1, v52, &v40, &v37);
        if ( v41 )
          operator delete(v41, 0);
        v40 = *(_QWORD *)v30;
        v31 = *(void **)(v30 + 8);
        *(_QWORD *)v30 = 0;
        v41 = v31;
        v32 = *(_DWORD *)(v30 + 16);
        *(_QWORD *)(v30 + 8) = 0;
        LODWORD(v42) = v32;
        *(_DWORD *)(v30 + 16) = -1073741823;
        if ( v53 )
          operator delete(v53, 0);
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
          operator delete(v41, 0);
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
    operator delete(v22, 0);
LABEL_39:
    if ( v50 )
      operator delete(v50, 0);
    goto LABEL_41;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v45, v14);
  *(_OWORD *)a2 = 0;
  *(_DWORD *)(a2 + 12) = v15;
LABEL_43:
  if ( v44 )
    operator delete(v44, 0);
  return a2;
}

```

## disassembly

```asm
0x180005ed0  mov     [rsp-8+arg_8], rbx
0x180005ed5  mov     [rsp-8+arg_10], rsi
0x180005eda  push    rbp
0x180005edb  push    rdi
0x180005edc  push    r12
0x180005ede  push    r14
0x180005ee0  push    r15
0x180005ee2  lea     rbp, [rsp-1Fh]
0x180005ee7  sub     rsp, 0C0h
0x180005eee  mov     r15, rcx
0x180005ef1  mov     r14, r9
0x180005ef4  add     rcx, 8
0x180005ef8  mov     r12, r8
0x180005efb  mov     rdi, rdx
0x180005efe  mov     rax, [rcx]
0x180005f01  mov     rax, [rax+68h]
0x180005f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f0a  mov     r10, [r15]
0x180005f0d  mov     ebx, eax
0x180005f0f  mov     rcx, r15
0x180005f12  mov     rax, [r10+0E0h]
0x180005f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1e  cmp     ebx, eax
0x180005f20  jnz     loc_18000625B
0x180005f26  cmp     qword ptr [r14], 18h
0x180005f2a  jz      short loc_180005F4A
0x180005f2c  lea     rcx, aInputsignature_0; "inputSignature.length == sizeof(MICToke"...
0x180005f33  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180005f38  xorps   xmm0, xmm0
0x180005f3b  movups  xmmword ptr [rdi], xmm0
0x180005f3e  mov     dword ptr [rdi+0Ch], 8009030Fh
0x180005f45  jmp     loc_18000623C
0x180005f4a  mov     rsi, [r14+8]
0x180005f4e  mov     eax, 101h
0x180005f53  cmp     [rsi], ax
0x180005f56  jz      short loc_180005F61
0x180005f58  lea     rcx, aHeaderTokIdHea; "header.TOK_ID == header.ID"
0x180005f5f  jmp     short loc_180005F33
0x180005f61  cmp     word ptr [rsi+2], 11h
0x180005f66  jz      short loc_180005F71
0x180005f68  lea     rcx, aHeaderSgnAlgHe; "header.SGN_ALG == header.SignAlgorithm"
0x180005f6f  jmp     short loc_180005F33
0x180005f71  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x180005f75  jz      short loc_180005F80
0x180005f77  lea     rcx, aHeaderFillerHe; "header.Filler == header.FillerBytes"
0x180005f7e  jmp     short loc_180005F33
0x180005f80  mov     r8, [rbp+3Fh+arg_20]
0x180005f84  lea     r9, ?$S18@?1??CommonVerifyMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@00_N1@Z@4U53@B
0x180005f8b  lea     rdx, [rbp+3Fh+var_88]
0x180005f8f  mov     rcx, r15
0x180005f92  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005f97  mov     ebx, dword ptr [rbp+3Fh+var_78]
0x180005f9a  test    ebx, ebx
0x180005f9c  jns     short loc_180005FBA
0x180005f9e  mov     edx, ebx; char *
0x180005fa0  lea     rcx, aKsign; "Ksign"
0x180005fa7  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005fac  xorps   xmm0, xmm0
0x180005faf  movups  xmmword ptr [rdi], xmm0
0x180005fb2  mov     [rdi+0Ch], ebx
0x180005fb5  jmp     loc_18000622C
0x180005fba  mov     rax, [r14+8]
0x180005fbe  lea     r8, [rbp+3Fh+var_B8]
0x180005fc2  mov     r9, r12
0x180005fc5  mov     [rbp+3Fh+var_B0], rax
0x180005fc9  lea     rdx, ?$S19@?1??CommonVerifyMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@00_N1@Z@4U53@B
0x180005fd0  mov     [rbp+3Fh+var_B8], 8
0x180005fd8  lea     rcx, [rbp+3Fh+var_70]
0x180005fdc  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005fe1  mov     ebx, dword ptr [rbp+3Fh+var_60]
0x180005fe4  test    ebx, ebx
0x180005fe6  jns     short loc_180006004
0x180005fe8  mov     edx, ebx; char *
0x180005fea  lea     rcx, aSignbuffer; "signBuffer"
0x180005ff1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005ff6  xorps   xmm0, xmm0
0x180005ff9  movups  xmmword ptr [rdi], xmm0
0x180005ffc  mov     [rdi+0Ch], ebx
0x180005fff  jmp     loc_18000621C
0x180006004  lea     r8, [rbp+3Fh+var_70]
0x180006008  mov     rcx, r15
0x18000600b  lea     rdx, [rbp+3Fh+var_58]
0x18000600f  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x180006014  mov     ebx, dword ptr [rbp+3Fh+var_48]
0x180006017  test    ebx, ebx
0x180006019  jns     short loc_180006037
0x18000601b  mov     edx, ebx; char *
0x18000601d  lea     rcx, aHash; "hash"
0x180006024  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006029  xorps   xmm0, xmm0
0x18000602c  movups  xmmword ptr [rdi], xmm0
0x18000602f  mov     [rdi+0Ch], ebx
0x180006032  jmp     loc_18000620C
0x180006037  lea     r9, [rbp+3Fh+var_58]
0x18000603b  mov     rcx, r15
0x18000603e  lea     r8, [rbp+3Fh+var_88]
0x180006042  lea     rdx, [rbp+3Fh+var_B8]
0x180006046  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000604b  mov     ebx, dword ptr [rbp+3Fh+var_A8]
0x18000604e  test    ebx, ebx
0x180006050  jns     short loc_18000607B
0x180006052  mov     edx, ebx; char *
0x180006054  lea     rcx, aChecksum; "checksum"
0x18000605b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006060  mov     rcx, [rbp+3Fh+var_B0]
0x180006064  xorps   xmm0, xmm0
0x180006067  movups  xmmword ptr [rdi], xmm0
0x18000606a  mov     [rdi+0Ch], ebx
0x18000606d  test    rcx, rcx
0x180006070  jz      loc_18000620C
0x180006076  jmp     loc_180006205
0x18000607b  mov     rbx, [rbp+3Fh+var_B0]
0x18000607f  lea     r12, [rsi+10h]
0x180006083  xor     r8b, r8b
0x180006086  xor     edx, edx
0x180006088  mov     cl, [rdx+rbx]
0x18000608b  mov     al, [rdx+r12]
0x18000608f  inc     rdx; char *
0x180006092  xor     cl, al
0x180006094  or      r8b, cl
0x180006097  cmp     rdx, 8
0x18000609b  jnz     short loc_180006088
0x18000609d  test    r8b, r8b
0x1800060a0  jz      short loc_1800060C0
0x1800060a2  lea     rcx, aSecureequalbuf_1; "SecureEqualBuffer(checksum, reinterpret"...
0x1800060a9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800060ae  xorps   xmm0, xmm0
0x1800060b1  movups  xmmword ptr [rdi], xmm0
0x1800060b4  mov     dword ptr [rdi+0Ch], 8009030Fh
0x1800060bb  jmp     loc_1800061FD
0x1800060c0  mov     r8, [rbp+3Fh+arg_20]
0x1800060c4  lea     r9, ?$S21@?1??CommonVerifyMIC@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@00_N1@Z@4U53@B
0x1800060cb  lea     rdx, [rbp+3Fh+var_A0]
0x1800060cf  mov     rcx, r15
0x1800060d2  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800060d7  mov     r14d, dword ptr [rbp+3Fh+var_90]
0x1800060db  test    r14d, r14d
0x1800060de  jns     short loc_1800060FE
0x1800060e0  mov     edx, r14d; char *
0x1800060e3  lea     rcx, aKseq; "Kseq"
0x1800060ea  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800060ef  xorps   xmm0, xmm0
0x1800060f2  movups  xmmword ptr [rdi], xmm0
0x1800060f5  mov     [rdi+0Ch], r14d
0x1800060f9  jmp     loc_1800061ED
0x1800060fe  lea     r9, [rbp+3Fh+var_B8]
0x180006102  mov     [rbp+3Fh+var_B8], 8
0x18000610a  lea     r8, [rbp+3Fh+var_A0]
0x18000610e  mov     [rbp+3Fh+var_B0], r12
0x180006112  lea     rdx, [rbp+3Fh+var_40]
0x180006116  mov     rcx, r15
0x180006119  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000611e  mov     rcx, [rbp+3Fh+var_98]; void *
0x180006122  mov     r14, rax
0x180006125  test    rcx, rcx
0x180006128  jz      short loc_180006131
0x18000612a  xor     edx, edx; struct std::nothrow_t *
0x18000612c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006131  mov     rcx, [r14]
0x180006134  mov     r12d, 0C0000001h
0x18000613a  mov     [rbp+3Fh+var_A0], rcx
0x18000613e  mov     rcx, [r14+8]
0x180006142  mov     qword ptr [r14], 0
0x180006149  mov     [rbp+3Fh+var_98], rcx
0x18000614d  mov     eax, [r14+10h]
0x180006151  mov     qword ptr [r14+8], 0
0x180006159  mov     dword ptr [rbp+3Fh+var_90], eax
0x18000615c  mov     [r14+10h], r12d
0x180006160  mov     rcx, [rbp+3Fh+var_38]; void *
0x180006164  test    rcx, rcx
0x180006167  jz      short loc_180006170
0x180006169  xor     edx, edx; struct std::nothrow_t *
0x18000616b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006170  mov     r14d, dword ptr [rbp+3Fh+var_90]
0x180006174  test    r14d, r14d
0x180006177  js      loc_1800060E0
0x18000617d  mov     rax, [rsi+8]
0x180006181  lea     r9, [rbp+3Fh+var_B8]
0x180006185  mov     [rsp+0E0h+var_C0], rax
0x18000618a  lea     r8, [rbp+3Fh+var_A0]
0x18000618e  lea     rax, [rsp+0E0h+var_C0]
0x180006193  mov     [rbp+3Fh+var_B8], 8
0x18000619b  lea     rdx, [rbp+3Fh+arg_0]
0x18000619f  mov     [rbp+3Fh+var_B0], rax
0x1800061a3  mov     rcx, r15
0x1800061a6  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x1800061ab  neg     [rbp+3Fh+arg_28]
0x1800061ae  sbb     eax, eax
0x1800061b0  cmp     dword ptr [rbp+3Fh+var_C0+4], eax
0x1800061b3  jnz     short loc_1800061D4
0x1800061b5  mov     ecx, dword ptr [rsp+0E0h+var_C0]
0x1800061b9  bswap   ecx
0x1800061bb  mov     ecx, ecx
0x1800061bd  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x1800061c1  mov     [rdi], rcx
0x1800061c4  mov     dword ptr [rdi+8], 0
0x1800061cb  mov     dword ptr [rdi+0Ch], 0
0x1800061d2  jmp     short loc_1800061ED
0x1800061d4  lea     rcx, aSeqcopyDirecti; "seqCopy.Direction == expectedDirection"
0x1800061db  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800061e0  xorps   xmm0, xmm0
0x1800061e3  movups  xmmword ptr [rdi], xmm0
0x1800061e6  mov     dword ptr [rdi+0Ch], 8009030Fh
0x1800061ed  mov     rcx, [rbp+3Fh+var_98]; void *
0x1800061f1  test    rcx, rcx
0x1800061f4  jz      short loc_1800061FD
0x1800061f6  xor     edx, edx; struct std::nothrow_t *
0x1800061f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800061fd  test    rbx, rbx
0x180006200  jz      short loc_18000620C
0x180006202  mov     rcx, rbx; void *
0x180006205  xor     edx, edx; struct std::nothrow_t *
0x180006207  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000620c  mov     rcx, [rbp+3Fh+var_50]; void *
0x180006210  test    rcx, rcx
0x180006213  jz      short loc_18000621C
0x180006215  xor     edx, edx; struct std::nothrow_t *
0x180006217  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000621c  mov     rcx, [rbp+3Fh+var_68]; void *
0x180006220  test    rcx, rcx
0x180006223  jz      short loc_18000622C
0x180006225  xor     edx, edx; struct std::nothrow_t *
0x180006227  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000622c  mov     rcx, [rbp+3Fh+var_80]; void *
0x180006230  test    rcx, rcx
0x180006233  jz      short loc_18000623C
0x180006235  xor     edx, edx; struct std::nothrow_t *
0x180006237  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000623c  lea     r11, [rsp+0E0h+var_20]
0x180006244  mov     rax, rdi
0x180006247  mov     rbx, [r11+38h]
0x18000624b  mov     rsi, [r11+40h]
0x18000624f  mov     rsp, r11
0x180006252  pop     r15
0x180006254  pop     r14
0x180006256  pop     r12
0x180006258  pop     rdi
0x180006259  pop     rbp
0x18000625a  retn
0x18000625b  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x180006262  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
