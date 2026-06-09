# Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrap(Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800025e0`
- end: `0x1800028cc`
- name: `?CommonUnwrap@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z`
- size: `748`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800025e0`
- `0x1800028d4`
- `0x180002cc4`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x180002646`: `header.tokenID == GSSAPITokenID::Wrap`
- `0x18000275b`: `result.outputMessage = CommonUnwrapConfidential(inputMessage, authData, protocolKey)`
- `0x180002835`: `result.outputMessage = CommonUnwrapIntegrity(inputMessage, realAuthData, protocolKey)`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrap(
        int a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4,
        __int64 a5,
        char a6,
        char a7)
{
  int v8; // r15d
  char *v11; // rcx
  __int64 v12; // r14
  char *v13; // rcx
  char v14; // si
  int v15; // r8d
  __int64 v16; // r15
  __int64 v17; // rcx
  int v18; // eax
  int v19; // r15d
  __int64 v20; // rax
  int v21; // r8d
  int v22; // esi
  char *v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  __int64 v30; // [rsp+30h] [rbp-61h] BYREF
  __int64 v31; // [rsp+38h] [rbp-59h]
  _BYTE v32[8]; // [rsp+48h] [rbp-49h] BYREF
  __int64 v33; // [rsp+50h] [rbp-41h]
  char *v34; // [rsp+58h] [rbp-39h]
  __int64 v35; // [rsp+60h] [rbp-31h]
  __int64 v36; // [rsp+68h] [rbp-29h]
  _DWORD v37[5]; // [rsp+70h] [rbp-21h] BYREF
  int v38; // [rsp+84h] [rbp-Dh]

  v8 = (int)a3;
  if ( *a3 < 0x10u )
  {
    v11 = "inputMessage.length >= WrapHeaderSize";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v11, (const char *)a2);
    *(_QWORD *)(a2 + 20) = 0;
    *(_QWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 36) = 0;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -2146893048;
    return a2;
  }
  v12 = a3[1];
  if ( *(_WORD *)v12 != 1029 )
  {
    v11 = "header.tokenID == GSSAPITokenID::Wrap";
    goto LABEL_3;
  }
  if ( *(_BYTE *)(v12 + 3) != 0xFF )
  {
    v13 = "header.filler == header.FillerValue";
LABEL_8:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v13, (const char *)a2);
    *(_QWORD *)(a2 + 20) = 0;
    *(_QWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 36) = 0;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -2146893041;
    return a2;
  }
  v14 = 1;
  if ( (*(_BYTE *)(v12 + 2) & 1) != a6 )
  {
    v13 = "WI_IsFlagSet(header.flags, GSSAPIFlags::SentByAcceptor) == initiator";
    goto LABEL_8;
  }
  if ( ((*(_BYTE *)(v12 + 2) & 4) != 0) != a7 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"WI_IsFlagSet(header.flags, GSSAPIFlags::AcceptorSubkey) == acceptorSubkey",
      (const char *)a2);
    *(_QWORD *)(a2 + 20) = 0;
    *(_QWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 36) = 0;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -2146892984;
    return a2;
  }
  v38 = 0;
  v35 = 0;
  v36 = 0;
  memset(v37, 0, sizeof(v37));
  if ( (*(_BYTE *)(v12 + 2) & 2) == 0 )
  {
    v20 = *a4;
    v30 = 0;
    v31 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64 *))(v20 + 32))(a4) )
      __int2c();
    (*(void (__fastcall **)(__int64 *, _BYTE *, __int64 *))(*a4 + 24))(a4, v32, &v30);
    v22 = (int)v34;
    if ( (int)v34 >= 0 )
    {
      v24 = Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapIntegrity(
              a1,
              (unsigned int)&v30,
              v8,
              (unsigned int)v32,
              a5);
      if ( v36 )
        Kerb3961Free(v36);
      v35 = *(_QWORD *)v24;
      v25 = *(_QWORD *)(v24 + 8);
      *(_QWORD *)v24 = 0;
      v36 = v25;
      v26 = *(_DWORD *)(v24 + 16);
      *(_QWORD *)(v24 + 8) = 0;
      v37[0] = v26;
      *(_DWORD *)(v24 + 16) = -1073741823;
      v22 = v37[0];
      if ( v31 )
        Kerb3961Free(v31);
      if ( v22 >= 0 )
      {
        if ( v33 )
          Kerb3961Free(v33);
        v14 = 0;
        LOBYTE(v38) = 0;
        goto LABEL_38;
      }
      v23 = "result.outputMessage = CommonUnwrapIntegrity(inputMessage, realAuthData, protocolKey)";
    }
    else
    {
      v23 = "realAuthData";
    }
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v23, (const char *)(unsigned int)v22, v21);
    *(_QWORD *)(a2 + 20) = 0;
    *(_QWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 36) = 0;
    v27 = v33;
    *(_DWORD *)(a2 + 16) = v22;
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = 0;
    if ( v27 )
      Kerb3961Free(v27);
    goto LABEL_33;
  }
  v16 = Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrapConfidential(a1, (unsigned int)v32, (_DWORD)a3, (_DWORD)a4, a5);
  if ( v36 )
    Kerb3961Free(v36);
  v35 = *(_QWORD *)v16;
  v17 = *(_QWORD *)(v16 + 8);
  *(_QWORD *)v16 = 0;
  v36 = v17;
  v18 = *(_DWORD *)(v16 + 16);
  *(_QWORD *)(v16 + 8) = 0;
  v37[0] = v18;
  *(_DWORD *)(v16 + 16) = -1073741823;
  v19 = v37[0];
  if ( v33 )
    Kerb3961Free(v33);
  if ( v19 >= 0 )
  {
    LOBYTE(v38) = 1;
LABEL_38:
    v37[4] = 0;
    v28 = *(_QWORD *)(v12 + 8);
    *(_DWORD *)(a2 + 16) = v37[0];
    *(_QWORD *)a2 = v35;
    *(_QWORD *)(a2 + 8) = v36;
    *(_QWORD *)(a2 + 24) = _byteswap_uint64(v28);
    *(_DWORD *)(a2 + 32) = 0;
    *(_BYTE *)(a2 + 36) = v14;
    return a2;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"result.outputMessage = CommonUnwrapConfidential(inputMessage, authData, protocolKey)",
    (const char *)(unsigned int)v19,
    v15);
  *(_QWORD *)(a2 + 20) = 0;
  *(_QWORD *)(a2 + 28) = 0;
  *(_DWORD *)(a2 + 36) = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v19;
LABEL_33:
  if ( v36 )
    Kerb3961Free(v36);
  return a2;
}

```

## disassembly

```asm
0x1800025e0  push    rbp
0x1800025e2  push    rbx
0x1800025e3  push    rsi
0x1800025e4  push    rdi
0x1800025e5  push    r12
0x1800025e7  push    r13
0x1800025e9  push    r14
0x1800025eb  push    r15
0x1800025ed  lea     rbp, [rsp-7]
0x1800025f2  sub     rsp, 98h
0x1800025f9  cmp     qword ptr [r8], 10h
0x1800025fd  mov     r12, r9
0x180002600  mov     r15, r8
0x180002603  mov     rdi, rdx
0x180002606  mov     r13, rcx
0x180002609  jnb     short loc_180002637
0x18000260b  lea     rcx, aInputmessageLe; "inputMessage.length >= WrapHeaderSize"
0x180002612  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180002617  xor     ebx, ebx
0x180002619  mov     [rdi+14h], rbx
0x18000261d  mov     [rdi+1Ch], rbx
0x180002621  mov     [rdi+24h], ebx
0x180002624  mov     [rdi], rbx
0x180002627  mov     [rdi+8], rbx
0x18000262b  mov     dword ptr [rdi+10h], 80090308h
0x180002632  jmp     loc_1800028B4
0x180002637  mov     r14, [r8+8]
0x18000263b  mov     eax, 405h
0x180002640  cmp     [r14], ax
0x180002644  jz      short loc_18000264F
0x180002646  lea     rcx, aHeaderTokenidG; "header.tokenID == GSSAPITokenID::Wrap"
0x18000264d  jmp     short loc_180002612
0x18000264f  cmp     byte ptr [r14+3], 0FFh
0x180002654  jz      short loc_180002682
0x180002656  lea     rcx, aHeaderFillerHe_0; "header.filler == header.FillerValue"
0x18000265d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180002662  xor     ebx, ebx
0x180002664  mov     [rdi+14h], rbx
0x180002668  mov     [rdi+1Ch], rbx
0x18000266c  mov     [rdi+24h], ebx
0x18000266f  mov     [rdi], rbx
0x180002672  mov     [rdi+8], rbx
0x180002676  mov     dword ptr [rdi+10h], 8009030Fh
0x18000267d  jmp     loc_1800028B4
0x180002682  mov     cl, [r14+2]
0x180002686  mov     sil, 1
0x180002689  mov     al, cl
0x18000268b  and     al, sil
0x18000268e  cmp     al, [rbp+3Fh+arg_28]
0x180002691  jz      short loc_18000269C
0x180002693  lea     rcx, aWiIsflagsetHea; "WI_IsFlagSet(header.flags, GSSAPIFlags:"...
0x18000269a  jmp     short loc_18000265D
0x18000269c  shr     cl, 2
0x18000269f  and     cl, sil
0x1800026a2  cmp     cl, [rbp+3Fh+arg_30]
0x1800026a5  jz      short loc_1800026D3
0x1800026a7  lea     rcx, aWiIsflagsetHea_0; "WI_IsFlagSet(header.flags, GSSAPIFlags:"...
0x1800026ae  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800026b3  xor     ebx, ebx
0x1800026b5  mov     [rdi+14h], rbx
0x1800026b9  mov     [rdi+1Ch], rbx
0x1800026bd  mov     [rdi+24h], ebx
0x1800026c0  mov     [rdi], rbx
0x1800026c3  mov     [rdi+8], rbx
0x1800026c7  mov     dword ptr [rdi+10h], 80090348h
0x1800026ce  jmp     loc_1800028B4
0x1800026d3  xor     ebx, ebx
0x1800026d5  xorps   xmm0, xmm0
0x1800026d8  movdqu  xmmword ptr [rbp+3Fh+var_60+4], xmm0
0x1800026dd  mov     [rbp+3Fh+var_4C], ebx
0x1800026e0  mov     [rbp+3Fh+var_70], rbx
0x1800026e4  mov     [rbp+3Fh+var_68], rbx
0x1800026e8  mov     dword ptr [rbp+3Fh+var_60], ebx
0x1800026eb  test    byte ptr [r14+2], 2
0x1800026f0  jz      loc_18000278B
0x1800026f6  mov     rax, [rbp+3Fh+arg_20]
0x1800026fa  lea     rdx, [rbp+3Fh+var_88]
0x1800026fe  mov     rcx, r13
0x180002701  mov     [rsp+0D0h+var_B0], rax
0x180002706  call    ?CommonUnwrapConfidential@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0@Z; Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrapConfidential(Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,Kerb3961::ReadOnlyBinary const &)
0x18000270b  mov     rcx, [rbp+3Fh+var_68]
0x18000270f  mov     r15, rax
0x180002712  test    rcx, rcx
0x180002715  jz      short loc_18000271C
0x180002717  call    Kerb3961Free
0x18000271c  mov     rcx, [r15]
0x18000271f  mov     [rbp+3Fh+var_70], rcx
0x180002723  mov     rcx, [r15+8]
0x180002727  mov     [r15], rbx
0x18000272a  mov     [rbp+3Fh+var_68], rcx
0x18000272e  mov     eax, [r15+10h]
0x180002732  mov     [r15+8], rbx
0x180002736  mov     dword ptr [rbp+3Fh+var_60], eax
0x180002739  mov     dword ptr [r15+10h], 0C0000001h
0x180002741  mov     rcx, [rbp+3Fh+var_80]
0x180002745  mov     r15d, dword ptr [rbp+3Fh+var_60]
0x180002749  test    rcx, rcx
0x18000274c  jz      short loc_180002753
0x18000274e  call    Kerb3961Free
0x180002753  test    r15d, r15d
0x180002756  jns     short loc_180002782
0x180002758  mov     edx, r15d; char *
0x18000275b  lea     rcx, aResultOutputme_2; "result.outputMessage = CommonUnwrapConf"...
0x180002762  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180002767  mov     [rdi+14h], rbx
0x18000276b  mov     [rdi+1Ch], rbx
0x18000276f  mov     [rdi+24h], ebx
0x180002772  mov     [rdi], rbx
0x180002775  mov     [rdi+8], rbx
0x180002779  mov     [rdi+10h], r15d
0x18000277d  jmp     loc_180002866
0x180002782  mov     byte ptr [rbp+3Fh+var_4C], sil
0x180002786  jmp     loc_18000288A
0x18000278b  mov     rax, [r9]
0x18000278e  mov     rcx, r12
0x180002791  mov     [rbp+3Fh+var_A0], rbx
0x180002795  mov     [rbp+3Fh+var_98], rbx
0x180002799  mov     rax, [rax+20h]
0x18000279d  call    _guard_dispatch_icall
0x1800027a2  test    al, al
0x1800027a4  jnz     short loc_1800027A8
0x1800027a6  int     2Ch; Windows NT - assertion failure
0x1800027a8  mov     rax, [r12]
0x1800027ac  lea     r8, [rbp+3Fh+var_A0]
0x1800027b0  lea     rdx, [rbp+3Fh+var_88]
0x1800027b4  mov     rcx, r12
0x1800027b7  mov     rax, [rax+18h]
0x1800027bb  call    _guard_dispatch_icall
0x1800027c0  mov     esi, dword ptr [rbp+3Fh+var_78]
0x1800027c3  test    esi, esi
0x1800027c5  jns     short loc_1800027D0
0x1800027c7  lea     rcx, aRealauthdata; "realAuthData"
0x1800027ce  jmp     short loc_18000283C
0x1800027d0  mov     rax, [rbp+3Fh+arg_20]
0x1800027d4  lea     r9, [rbp+3Fh+var_88]
0x1800027d8  mov     r8, r15
0x1800027db  mov     [rsp+0D0h+var_B0], rax
0x1800027e0  lea     rdx, [rbp+3Fh+var_A0]
0x1800027e4  mov     rcx, r13
0x1800027e7  call    ?CommonUnwrapIntegrity@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z; Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapIntegrity(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800027ec  mov     rcx, [rbp+3Fh+var_68]
0x1800027f0  mov     rsi, rax
0x1800027f3  test    rcx, rcx
0x1800027f6  jz      short loc_1800027FD
0x1800027f8  call    Kerb3961Free
0x1800027fd  mov     rcx, [rsi]
0x180002800  mov     [rbp+3Fh+var_70], rcx
0x180002804  mov     rcx, [rsi+8]
0x180002808  mov     [rsi], rbx
0x18000280b  mov     [rbp+3Fh+var_68], rcx
0x18000280f  mov     eax, [rsi+10h]
0x180002812  mov     [rsi+8], rbx
0x180002816  mov     dword ptr [rbp+3Fh+var_60], eax
0x180002819  mov     dword ptr [rsi+10h], 0C0000001h
0x180002820  mov     rcx, [rbp+3Fh+var_98]
0x180002824  mov     esi, dword ptr [rbp+3Fh+var_60]
0x180002827  test    rcx, rcx
0x18000282a  jz      short loc_180002831
0x18000282c  call    Kerb3961Free
0x180002831  test    esi, esi
0x180002833  jns     short loc_180002876
0x180002835  lea     rcx, aResultOutputme_1; "result.outputMessage = CommonUnwrapInte"...
0x18000283c  mov     edx, esi; char *
0x18000283e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180002843  mov     [rdi+14h], rbx
0x180002847  mov     [rdi+1Ch], rbx
0x18000284b  mov     [rdi+24h], ebx
0x18000284e  mov     rcx, [rbp+3Fh+var_80]
0x180002852  mov     [rdi+10h], esi
0x180002855  mov     [rdi+8], rbx
0x180002859  mov     [rdi], rbx
0x18000285c  test    rcx, rcx
0x18000285f  jz      short loc_180002866
0x180002861  call    Kerb3961Free
0x180002866  mov     rcx, [rbp+3Fh+var_68]
0x18000286a  test    rcx, rcx
0x18000286d  jz      short loc_1800028B4
0x18000286f  call    Kerb3961Free
0x180002874  jmp     short loc_1800028B4
0x180002876  mov     rcx, [rbp+3Fh+var_80]
0x18000287a  test    rcx, rcx
0x18000287d  jz      short loc_180002884
0x18000287f  call    Kerb3961Free
0x180002884  mov     sil, bl
0x180002887  mov     byte ptr [rbp+3Fh+var_4C], bl
0x18000288a  mov     eax, dword ptr [rbp+3Fh+var_60]
0x18000288d  mov     dword ptr [rbp+3Fh+var_60+10h], ebx
0x180002890  mov     rcx, [r14+8]
0x180002894  mov     [rdi+10h], eax
0x180002897  mov     rax, [rbp+3Fh+var_70]
0x18000289b  mov     [rdi], rax
0x18000289e  mov     rax, [rbp+3Fh+var_68]
0x1800028a2  bswap   rcx
0x1800028a5  mov     [rdi+8], rax
0x1800028a9  mov     [rdi+18h], rcx
0x1800028ad  mov     [rdi+20h], ebx
0x1800028b0  mov     [rdi+24h], sil
0x1800028b4  mov     rax, rdi
0x1800028b7  add     rsp, 98h
0x1800028be  pop     r15
0x1800028c0  pop     r14
0x1800028c2  pop     r13
0x1800028c4  pop     r12
0x1800028c6  pop     rdi
0x1800028c7  pop     rsi
0x1800028c8  pop     rbx
0x1800028c9  pop     rbp
0x1800028ca  retn
```
