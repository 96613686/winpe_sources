# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrap(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800112d0`
- end: `0x18001152a`
- name: `?CommonUnwrap@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_N1@Z`
- size: `602`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800112d0`
- `0x180011530`
- `0x18001190c`

## string_xrefs

- `0x180011327`: `header.tokenID == GSSAPITokenID::Wrap`
- `0x18001143c`: `result.outputMessage = CommonUnwrapConfidential(inputMessage, authData, protocolKey)`
- `0x1800114b6`: `result.outputMessage = CommonUnwrapIntegrity(inputMessage, authData, protocolKey)`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrap(
        int a1,
        __int64 a2,
        _QWORD *a3,
        int a4,
        __int64 a5,
        char a6,
        char a7)
{
  char *v8; // rcx
  __int64 v9; // r14
  char *v10; // rcx
  char v11; // si
  int v12; // r8d
  __int64 v13; // r15
  void *v14; // rcx
  int v15; // eax
  int v16; // r15d
  __int64 v17; // rsi
  int v18; // r8d
  void *v19; // rcx
  int v20; // eax
  int v21; // esi
  void *v22; // rcx
  unsigned __int64 v23; // rcx
  char v25; // [rsp+30h] [rbp-48h] BYREF
  void *v26; // [rsp+38h] [rbp-40h]
  __int64 v27; // [rsp+48h] [rbp-30h]
  void *v28; // [rsp+50h] [rbp-28h]
  _DWORD v29[5]; // [rsp+58h] [rbp-20h] BYREF
  int v30; // [rsp+6Ch] [rbp-Ch]

  if ( *a3 < 0x10u )
  {
    v8 = "inputMessage.length >= WrapHeaderSize";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v8, (const char *)a2);
    *(_QWORD *)(a2 + 20) = 0;
    *(_QWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 36) = 0;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -2146893048;
    return a2;
  }
  v9 = a3[1];
  if ( *(_WORD *)v9 != 1029 )
  {
    v8 = "header.tokenID == GSSAPITokenID::Wrap";
    goto LABEL_3;
  }
  if ( *(_BYTE *)(v9 + 3) != 0xFF )
  {
    v10 = "header.filler == header.FillerValue";
LABEL_8:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v10, (const char *)a2);
    *(_QWORD *)(a2 + 20) = 0;
    *(_QWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 36) = 0;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -2146893041;
    return a2;
  }
  v11 = 1;
  if ( (*(_BYTE *)(v9 + 2) & 1) != a6 )
  {
    v10 = "WI_IsFlagSet(header.flags, GSSAPIFlags::SentByAcceptor) == initiator";
    goto LABEL_8;
  }
  if ( ((*(_BYTE *)(v9 + 2) & 4) != 0) != a7 )
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
  v30 = 0;
  v27 = 0;
  v28 = 0;
  memset(v29, 0, sizeof(v29));
  if ( (*(_BYTE *)(v9 + 2) & 2) != 0 )
  {
    v13 = Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapConfidential(a1, (unsigned int)&v25, (_DWORD)a3, a4, a5);
    if ( v28 )
      operator delete(v28, 0);
    v27 = *(_QWORD *)v13;
    v14 = *(void **)(v13 + 8);
    *(_QWORD *)v13 = 0;
    v28 = v14;
    v15 = *(_DWORD *)(v13 + 16);
    *(_QWORD *)(v13 + 8) = 0;
    v29[0] = v15;
    *(_DWORD *)(v13 + 16) = -1073741823;
    v16 = v29[0];
    if ( v26 )
      operator delete(v26, 0);
    if ( v16 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"result.outputMessage = CommonUnwrapConfidential(inputMessage, authData, protocolKey)",
        (const char *)(unsigned int)v16,
        v12);
      *(_QWORD *)(a2 + 20) = 0;
      *(_QWORD *)(a2 + 28) = 0;
      *(_DWORD *)(a2 + 36) = 0;
      *(_DWORD *)(a2 + 16) = v16;
      goto LABEL_27;
    }
    LOBYTE(v30) = 1;
LABEL_30:
    v29[4] = 0;
    v23 = *(_QWORD *)(v9 + 8);
    *(_DWORD *)(a2 + 16) = v29[0];
    *(_QWORD *)a2 = v27;
    *(_QWORD *)(a2 + 8) = v28;
    *(_QWORD *)(a2 + 24) = _byteswap_uint64(v23);
    *(_DWORD *)(a2 + 32) = 0;
    *(_BYTE *)(a2 + 36) = v11;
    return a2;
  }
  v17 = Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapIntegrity(a1, (unsigned int)&v25, (_DWORD)a3, a4, a5);
  if ( v28 )
    operator delete(v28, 0);
  v27 = *(_QWORD *)v17;
  v19 = *(void **)(v17 + 8);
  *(_QWORD *)v17 = 0;
  v28 = v19;
  v20 = *(_DWORD *)(v17 + 16);
  *(_QWORD *)(v17 + 8) = 0;
  v29[0] = v20;
  *(_DWORD *)(v17 + 16) = -1073741823;
  v21 = v29[0];
  if ( v26 )
    operator delete(v26, 0);
  if ( v21 >= 0 )
  {
    v11 = 0;
    LOBYTE(v30) = 0;
    goto LABEL_30;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"result.outputMessage = CommonUnwrapIntegrity(inputMessage, authData, protocolKey)",
    (const char *)(unsigned int)v21,
    v18);
  *(_QWORD *)(a2 + 20) = 0;
  *(_QWORD *)(a2 + 28) = 0;
  *(_DWORD *)(a2 + 36) = 0;
  *(_DWORD *)(a2 + 16) = v21;
LABEL_27:
  v22 = v28;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)a2 = 0;
  if ( v22 )
    operator delete(v22, 0);
  return a2;
}

```

## disassembly

```asm
0x1800112d0  push    rbp
0x1800112d2  push    rbx
0x1800112d3  push    rsi
0x1800112d4  push    rdi
0x1800112d5  push    r14
0x1800112d7  push    r15
0x1800112d9  mov     rbp, rsp
0x1800112dc  sub     rsp, 78h
0x1800112e0  cmp     qword ptr [r8], 10h
0x1800112e4  mov     rbx, rdx
0x1800112e7  mov     r10, rcx
0x1800112ea  jnb     short loc_180011318
0x1800112ec  lea     rcx, aInputmessageLe; "inputMessage.length >= WrapHeaderSize"
0x1800112f3  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800112f8  xor     edi, edi
0x1800112fa  mov     [rbx+14h], rdi
0x1800112fe  mov     [rbx+1Ch], rdi
0x180011302  mov     [rbx+24h], edi
0x180011305  mov     [rbx], rdi
0x180011308  mov     [rbx+8], rdi
0x18001130c  mov     dword ptr [rbx+10h], 80090308h
0x180011313  jmp     loc_18001151A
0x180011318  mov     r14, [r8+8]
0x18001131c  mov     eax, 405h
0x180011321  cmp     [r14], ax
0x180011325  jz      short loc_180011330
0x180011327  lea     rcx, aHeaderTokenidG; "header.tokenID == GSSAPITokenID::Wrap"
0x18001132e  jmp     short loc_1800112F3
0x180011330  cmp     byte ptr [r14+3], 0FFh
0x180011335  jz      short loc_180011363
0x180011337  lea     rcx, aHeaderFillerHe_0; "header.filler == header.FillerValue"
0x18001133e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180011343  xor     edi, edi
0x180011345  mov     [rbx+14h], rdi
0x180011349  mov     [rbx+1Ch], rdi
0x18001134d  mov     [rbx+24h], edi
0x180011350  mov     [rbx], rdi
0x180011353  mov     [rbx+8], rdi
0x180011357  mov     dword ptr [rbx+10h], 8009030Fh
0x18001135e  jmp     loc_18001151A
0x180011363  mov     cl, [r14+2]
0x180011367  mov     sil, 1
0x18001136a  mov     al, cl
0x18001136c  and     al, sil
0x18001136f  cmp     al, [rbp+arg_28]
0x180011372  jz      short loc_18001137D
0x180011374  lea     rcx, aWiIsflagsetHea; "WI_IsFlagSet(header.flags, GSSAPIFlags:"...
0x18001137b  jmp     short loc_18001133E
0x18001137d  shr     cl, 2
0x180011380  and     cl, sil
0x180011383  cmp     cl, [rbp+arg_30]
0x180011386  jz      short loc_1800113B4
0x180011388  lea     rcx, aWiIsflagsetHea_0; "WI_IsFlagSet(header.flags, GSSAPIFlags:"...
0x18001138f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180011394  xor     edi, edi
0x180011396  mov     [rbx+14h], rdi
0x18001139a  mov     [rbx+1Ch], rdi
0x18001139e  mov     [rbx+24h], edi
0x1800113a1  mov     [rbx], rdi
0x1800113a4  mov     [rbx+8], rdi
0x1800113a8  mov     dword ptr [rbx+10h], 80090348h
0x1800113af  jmp     loc_18001151A
0x1800113b4  mov     rax, [rbp+arg_20]
0x1800113b8  lea     rdx, [rbp+var_48]
0x1800113bc  xor     edi, edi
0x1800113be  mov     [rsp+78h+var_58], rax
0x1800113c3  xorps   xmm0, xmm0
0x1800113c6  mov     [rbp+var_C], edi
0x1800113c9  movdqu  xmmword ptr [rbp+var_20+4], xmm0
0x1800113ce  mov     [rbp+var_30], rdi
0x1800113d2  mov     rcx, r10
0x1800113d5  mov     [rbp+var_28], rdi
0x1800113d9  mov     dword ptr [rbp+var_20], edi
0x1800113dc  test    byte ptr [r14+2], 2
0x1800113e1  jz      short loc_180011462
0x1800113e3  call    ?CommonUnwrapConfidential@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z; Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapConfidential(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800113e8  mov     rcx, [rbp+var_28]; void *
0x1800113ec  mov     r15, rax
0x1800113ef  test    rcx, rcx
0x1800113f2  jz      short loc_1800113FB
0x1800113f4  xor     edx, edx; struct std::nothrow_t *
0x1800113f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800113fb  mov     rcx, [r15]
0x1800113fe  mov     [rbp+var_30], rcx
0x180011402  mov     rcx, [r15+8]
0x180011406  mov     [r15], rdi
0x180011409  mov     [rbp+var_28], rcx
0x18001140d  mov     eax, [r15+10h]
0x180011411  mov     [r15+8], rdi
0x180011415  mov     dword ptr [rbp+var_20], eax
0x180011418  mov     dword ptr [r15+10h], 0C0000001h
0x180011420  mov     rcx, [rbp+var_40]; void *
0x180011424  mov     r15d, dword ptr [rbp+var_20]
0x180011428  test    rcx, rcx
0x18001142b  jz      short loc_180011434
0x18001142d  xor     edx, edx; struct std::nothrow_t *
0x18001142f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011434  test    r15d, r15d
0x180011437  jns     short loc_180011459
0x180011439  mov     edx, r15d; char *
0x18001143c  lea     rcx, aResultOutputme_2; "result.outputMessage = CommonUnwrapConf"...
0x180011443  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180011448  mov     [rbx+14h], rdi
0x18001144c  mov     [rbx+1Ch], rdi
0x180011450  mov     [rbx+24h], edi
0x180011453  mov     [rbx+10h], r15d
0x180011457  jmp     short loc_1800114D0
0x180011459  mov     byte ptr [rbp+var_C], sil
0x18001145d  jmp     loc_1800114F0
0x180011462  call    ?CommonUnwrapIntegrity@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z; Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapIntegrity(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180011467  mov     rcx, [rbp+var_28]; void *
0x18001146b  mov     rsi, rax
0x18001146e  test    rcx, rcx
0x180011471  jz      short loc_18001147A
0x180011473  xor     edx, edx; struct std::nothrow_t *
0x180011475  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001147a  mov     rcx, [rsi]
0x18001147d  mov     [rbp+var_30], rcx
0x180011481  mov     rcx, [rsi+8]
0x180011485  mov     [rsi], rdi
0x180011488  mov     [rbp+var_28], rcx
0x18001148c  mov     eax, [rsi+10h]
0x18001148f  mov     [rsi+8], rdi
0x180011493  mov     dword ptr [rbp+var_20], eax
0x180011496  mov     dword ptr [rsi+10h], 0C0000001h
0x18001149d  mov     rcx, [rbp+var_40]; void *
0x1800114a1  mov     esi, dword ptr [rbp+var_20]
0x1800114a4  test    rcx, rcx
0x1800114a7  jz      short loc_1800114B0
0x1800114a9  xor     edx, edx; struct std::nothrow_t *
0x1800114ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800114b0  test    esi, esi
0x1800114b2  jns     short loc_1800114E9
0x1800114b4  mov     edx, esi; char *
0x1800114b6  lea     rcx, aResultOutputme_0; "result.outputMessage = CommonUnwrapInte"...
0x1800114bd  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800114c2  mov     [rbx+14h], rdi
0x1800114c6  mov     [rbx+1Ch], rdi
0x1800114ca  mov     [rbx+24h], edi
0x1800114cd  mov     [rbx+10h], esi
0x1800114d0  mov     rcx, [rbp+var_28]; void *
0x1800114d4  mov     [rbx+8], rdi
0x1800114d8  mov     [rbx], rdi
0x1800114db  test    rcx, rcx
0x1800114de  jz      short loc_18001151A
0x1800114e0  xor     edx, edx; struct std::nothrow_t *
0x1800114e2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800114e7  jmp     short loc_18001151A
0x1800114e9  mov     sil, dil
0x1800114ec  mov     byte ptr [rbp+var_C], dil
0x1800114f0  mov     eax, dword ptr [rbp+var_20]
0x1800114f3  mov     dword ptr [rbp+var_20+10h], edi
0x1800114f6  mov     rcx, [r14+8]
0x1800114fa  mov     [rbx+10h], eax
0x1800114fd  mov     rax, [rbp+var_30]
0x180011501  mov     [rbx], rax
0x180011504  mov     rax, [rbp+var_28]
0x180011508  bswap   rcx
0x18001150b  mov     [rbx+8], rax
0x18001150f  mov     [rbx+18h], rcx
0x180011513  mov     [rbx+20h], edi
0x180011516  mov     [rbx+24h], sil
0x18001151a  mov     rax, rbx
0x18001151d  add     rsp, 78h
0x180011521  pop     r15
0x180011523  pop     r14
0x180011525  pop     rdi
0x180011526  pop     rsi
0x180011527  pop     rbx
0x180011528  pop     rbp
0x180011529  retn
```
