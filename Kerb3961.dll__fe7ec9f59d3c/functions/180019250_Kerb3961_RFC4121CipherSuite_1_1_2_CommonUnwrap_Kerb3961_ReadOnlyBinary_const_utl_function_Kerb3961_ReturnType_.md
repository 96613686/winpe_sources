# Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrap(Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180019250`
- end: `0x180019549`
- name: `?CommonUnwrap@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z`
- size: `761`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18001190c`
- `0x180019250`
- `0x180019550`
- `0x18001e010`

## string_xrefs

- `0x1800192b6`: `header.tokenID == GSSAPITokenID::Wrap`
- `0x1800193cf`: `result.outputMessage = CommonUnwrapConfidential(inputMessage, authData, protocolKey)`
- `0x1800194ad`: `result.outputMessage = CommonUnwrapIntegrity(inputMessage, realAuthData, protocolKey)`

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
  void *v17; // rcx
  int v18; // eax
  int v19; // r15d
  __int64 v20; // rax
  int v21; // r8d
  int v22; // esi
  char *v23; // rcx
  __int64 v24; // rsi
  void *v25; // rcx
  int v26; // eax
  void *v27; // rcx
  unsigned __int64 v28; // rcx
  __int64 v30; // [rsp+30h] [rbp-61h] BYREF
  void *v31; // [rsp+38h] [rbp-59h]
  _BYTE v32[8]; // [rsp+48h] [rbp-49h] BYREF
  void *v33; // [rsp+50h] [rbp-41h]
  char *v34; // [rsp+58h] [rbp-39h]
  __int64 v35; // [rsp+60h] [rbp-31h]
  void *v36; // [rsp+68h] [rbp-29h]
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
        operator delete(v36, 0);
      v35 = *(_QWORD *)v24;
      v25 = *(void **)(v24 + 8);
      *(_QWORD *)v24 = 0;
      v36 = v25;
      v26 = *(_DWORD *)(v24 + 16);
      *(_QWORD *)(v24 + 8) = 0;
      v37[0] = v26;
      *(_DWORD *)(v24 + 16) = -1073741823;
      v22 = v37[0];
      if ( v31 )
        operator delete(v31, 0);
      if ( v22 >= 0 )
      {
        if ( v33 )
          operator delete(v33, 0);
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
      operator delete(v27, 0);
    goto LABEL_33;
  }
  v16 = Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrapConfidential(a1, (unsigned int)v32, (_DWORD)a3, (_DWORD)a4, a5);
  if ( v36 )
    operator delete(v36, 0);
  v35 = *(_QWORD *)v16;
  v17 = *(void **)(v16 + 8);
  *(_QWORD *)v16 = 0;
  v36 = v17;
  v18 = *(_DWORD *)(v16 + 16);
  *(_QWORD *)(v16 + 8) = 0;
  v37[0] = v18;
  *(_DWORD *)(v16 + 16) = -1073741823;
  v19 = v37[0];
  if ( v33 )
    operator delete(v33, 0);
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
    operator delete(v36, 0);
  return a2;
}

```

## disassembly

```asm
0x180019250  push    rbp
0x180019252  push    rbx
0x180019253  push    rsi
0x180019254  push    rdi
0x180019255  push    r12
0x180019257  push    r13
0x180019259  push    r14
0x18001925b  push    r15
0x18001925d  lea     rbp, [rsp-7]
0x180019262  sub     rsp, 98h
0x180019269  cmp     qword ptr [r8], 10h
0x18001926d  mov     r12, r9
0x180019270  mov     r15, r8
0x180019273  mov     rdi, rdx
0x180019276  mov     r13, rcx
0x180019279  jnb     short loc_1800192A7
0x18001927b  lea     rcx, aInputmessageLe; "inputMessage.length >= WrapHeaderSize"
0x180019282  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180019287  xor     ebx, ebx
0x180019289  mov     [rdi+14h], rbx
0x18001928d  mov     [rdi+1Ch], rbx
0x180019291  mov     [rdi+24h], ebx
0x180019294  mov     [rdi], rbx
0x180019297  mov     [rdi+8], rbx
0x18001929b  mov     dword ptr [rdi+10h], 80090308h
0x1800192a2  jmp     loc_180019532
0x1800192a7  mov     r14, [r8+8]
0x1800192ab  mov     eax, 405h
0x1800192b0  cmp     [r14], ax
0x1800192b4  jz      short loc_1800192BF
0x1800192b6  lea     rcx, aHeaderTokenidG; "header.tokenID == GSSAPITokenID::Wrap"
0x1800192bd  jmp     short loc_180019282
0x1800192bf  cmp     byte ptr [r14+3], 0FFh
0x1800192c4  jz      short loc_1800192F2
0x1800192c6  lea     rcx, aHeaderFillerHe_0; "header.filler == header.FillerValue"
0x1800192cd  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800192d2  xor     ebx, ebx
0x1800192d4  mov     [rdi+14h], rbx
0x1800192d8  mov     [rdi+1Ch], rbx
0x1800192dc  mov     [rdi+24h], ebx
0x1800192df  mov     [rdi], rbx
0x1800192e2  mov     [rdi+8], rbx
0x1800192e6  mov     dword ptr [rdi+10h], 8009030Fh
0x1800192ed  jmp     loc_180019532
0x1800192f2  mov     cl, [r14+2]
0x1800192f6  mov     sil, 1
0x1800192f9  mov     al, cl
0x1800192fb  and     al, sil
0x1800192fe  cmp     al, [rbp+3Fh+arg_28]
0x180019301  jz      short loc_18001930C
0x180019303  lea     rcx, aWiIsflagsetHea; "WI_IsFlagSet(header.flags, GSSAPIFlags:"...
0x18001930a  jmp     short loc_1800192CD
0x18001930c  shr     cl, 2
0x18001930f  and     cl, sil
0x180019312  cmp     cl, [rbp+3Fh+arg_30]
0x180019315  jz      short loc_180019343
0x180019317  lea     rcx, aWiIsflagsetHea_0; "WI_IsFlagSet(header.flags, GSSAPIFlags:"...
0x18001931e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180019323  xor     ebx, ebx
0x180019325  mov     [rdi+14h], rbx
0x180019329  mov     [rdi+1Ch], rbx
0x18001932d  mov     [rdi+24h], ebx
0x180019330  mov     [rdi], rbx
0x180019333  mov     [rdi+8], rbx
0x180019337  mov     dword ptr [rdi+10h], 80090348h
0x18001933e  jmp     loc_180019532
0x180019343  xor     ebx, ebx
0x180019345  xorps   xmm0, xmm0
0x180019348  movdqu  xmmword ptr [rbp+3Fh+var_60+4], xmm0
0x18001934d  mov     [rbp+3Fh+var_4C], ebx
0x180019350  mov     [rbp+3Fh+var_70], rbx
0x180019354  mov     [rbp+3Fh+var_68], rbx
0x180019358  mov     dword ptr [rbp+3Fh+var_60], ebx
0x18001935b  test    byte ptr [r14+2], 2
0x180019360  jz      loc_1800193FF
0x180019366  mov     rax, [rbp+3Fh+arg_20]
0x18001936a  lea     rdx, [rbp+3Fh+var_88]
0x18001936e  mov     rcx, r13
0x180019371  mov     [rsp+0D0h+var_B0], rax
0x180019376  call    ?CommonUnwrapConfidential@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0@Z; Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrapConfidential(Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,Kerb3961::ReadOnlyBinary const &)
0x18001937b  mov     rcx, [rbp+3Fh+var_68]; void *
0x18001937f  mov     r15, rax
0x180019382  test    rcx, rcx
0x180019385  jz      short loc_18001938E
0x180019387  xor     edx, edx; struct std::nothrow_t *
0x180019389  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001938e  mov     rcx, [r15]
0x180019391  mov     [rbp+3Fh+var_70], rcx
0x180019395  mov     rcx, [r15+8]
0x180019399  mov     [r15], rbx
0x18001939c  mov     [rbp+3Fh+var_68], rcx
0x1800193a0  mov     eax, [r15+10h]
0x1800193a4  mov     [r15+8], rbx
0x1800193a8  mov     dword ptr [rbp+3Fh+var_60], eax
0x1800193ab  mov     dword ptr [r15+10h], 0C0000001h
0x1800193b3  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800193b7  mov     r15d, dword ptr [rbp+3Fh+var_60]
0x1800193bb  test    rcx, rcx
0x1800193be  jz      short loc_1800193C7
0x1800193c0  xor     edx, edx; struct std::nothrow_t *
0x1800193c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800193c7  test    r15d, r15d
0x1800193ca  jns     short loc_1800193F6
0x1800193cc  mov     edx, r15d; char *
0x1800193cf  lea     rcx, aResultOutputme_2; "result.outputMessage = CommonUnwrapConf"...
0x1800193d6  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800193db  mov     [rdi+14h], rbx
0x1800193df  mov     [rdi+1Ch], rbx
0x1800193e3  mov     [rdi+24h], ebx
0x1800193e6  mov     [rdi], rbx
0x1800193e9  mov     [rdi+8], rbx
0x1800193ed  mov     [rdi+10h], r15d
0x1800193f1  jmp     loc_1800194E0
0x1800193f6  mov     byte ptr [rbp+3Fh+var_4C], sil
0x1800193fa  jmp     loc_180019508
0x1800193ff  mov     rax, [r9]
0x180019402  mov     rcx, r12
0x180019405  mov     [rbp+3Fh+var_A0], rbx
0x180019409  mov     [rbp+3Fh+var_98], rbx
0x18001940d  mov     rax, [rax+20h]
0x180019411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019416  test    al, al
0x180019418  jnz     short loc_18001941C
0x18001941a  int     2Ch; Windows NT - assertion failure
0x18001941c  mov     rax, [r12]
0x180019420  lea     r8, [rbp+3Fh+var_A0]
0x180019424  lea     rdx, [rbp+3Fh+var_88]
0x180019428  mov     rcx, r12
0x18001942b  mov     rax, [rax+18h]
0x18001942f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019434  mov     esi, dword ptr [rbp+3Fh+var_78]
0x180019437  test    esi, esi
0x180019439  jns     short loc_180019444
0x18001943b  lea     rcx, aRealauthdata; "realAuthData"
0x180019442  jmp     short loc_1800194B4
0x180019444  mov     rax, [rbp+3Fh+arg_20]
0x180019448  lea     r9, [rbp+3Fh+var_88]
0x18001944c  mov     r8, r15
0x18001944f  mov     [rsp+0D0h+var_B0], rax
0x180019454  lea     rdx, [rbp+3Fh+var_A0]
0x180019458  mov     rcx, r13
0x18001945b  call    ?CommonUnwrapIntegrity@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z; Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapIntegrity(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180019460  mov     rcx, [rbp+3Fh+var_68]; void *
0x180019464  mov     rsi, rax
0x180019467  test    rcx, rcx
0x18001946a  jz      short loc_180019473
0x18001946c  xor     edx, edx; struct std::nothrow_t *
0x18001946e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019473  mov     rcx, [rsi]
0x180019476  mov     [rbp+3Fh+var_70], rcx
0x18001947a  mov     rcx, [rsi+8]
0x18001947e  mov     [rsi], rbx
0x180019481  mov     [rbp+3Fh+var_68], rcx
0x180019485  mov     eax, [rsi+10h]
0x180019488  mov     [rsi+8], rbx
0x18001948c  mov     dword ptr [rbp+3Fh+var_60], eax
0x18001948f  mov     dword ptr [rsi+10h], 0C0000001h
0x180019496  mov     rcx, [rbp+3Fh+var_98]; void *
0x18001949a  mov     esi, dword ptr [rbp+3Fh+var_60]
0x18001949d  test    rcx, rcx
0x1800194a0  jz      short loc_1800194A9
0x1800194a2  xor     edx, edx; struct std::nothrow_t *
0x1800194a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800194a9  test    esi, esi
0x1800194ab  jns     short loc_1800194F2
0x1800194ad  lea     rcx, aResultOutputme_1; "result.outputMessage = CommonUnwrapInte"...
0x1800194b4  mov     edx, esi; char *
0x1800194b6  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800194bb  mov     [rdi+14h], rbx
0x1800194bf  mov     [rdi+1Ch], rbx
0x1800194c3  mov     [rdi+24h], ebx
0x1800194c6  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800194ca  mov     [rdi+10h], esi
0x1800194cd  mov     [rdi+8], rbx
0x1800194d1  mov     [rdi], rbx
0x1800194d4  test    rcx, rcx
0x1800194d7  jz      short loc_1800194E0
0x1800194d9  xor     edx, edx; struct std::nothrow_t *
0x1800194db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800194e0  mov     rcx, [rbp+3Fh+var_68]; void *
0x1800194e4  test    rcx, rcx
0x1800194e7  jz      short loc_180019532
0x1800194e9  xor     edx, edx; struct std::nothrow_t *
0x1800194eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800194f0  jmp     short loc_180019532
0x1800194f2  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800194f6  test    rcx, rcx
0x1800194f9  jz      short loc_180019502
0x1800194fb  xor     edx, edx; struct std::nothrow_t *
0x1800194fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019502  mov     sil, bl
0x180019505  mov     byte ptr [rbp+3Fh+var_4C], bl
0x180019508  mov     eax, dword ptr [rbp+3Fh+var_60]
0x18001950b  mov     dword ptr [rbp+3Fh+var_60+10h], ebx
0x18001950e  mov     rcx, [r14+8]
0x180019512  mov     [rdi+10h], eax
0x180019515  mov     rax, [rbp+3Fh+var_70]
0x180019519  mov     [rdi], rax
0x18001951c  mov     rax, [rbp+3Fh+var_68]
0x180019520  bswap   rcx
0x180019523  mov     [rdi+8], rax
0x180019527  mov     [rdi+18h], rcx
0x18001952b  mov     [rdi+20h], ebx
0x18001952e  mov     [rdi+24h], sil
0x180019532  mov     rax, rdi
0x180019535  add     rsp, 98h
0x18001953c  pop     r15
0x18001953e  pop     r14
0x180019540  pop     r13
0x180019542  pop     r12
0x180019544  pop     rdi
0x180019545  pop     rsi
0x180019546  pop     rbx
0x180019547  pop     rbp
0x180019548  retn
```
