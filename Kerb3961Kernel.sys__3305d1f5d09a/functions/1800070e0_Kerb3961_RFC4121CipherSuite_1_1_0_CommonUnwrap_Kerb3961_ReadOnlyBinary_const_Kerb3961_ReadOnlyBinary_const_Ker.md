# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrap(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800070e0`
- end: `0x180007331`
- name: `?CommonUnwrap@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_N1@Z`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002cc4`
- `0x1800070e0`
- `0x180007338`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`

## string_xrefs

- `0x180007137`: `header.tokenID == GSSAPITokenID::Wrap`
- `0x180007248`: `result.outputMessage = CommonUnwrapConfidential(inputMessage, authData, protocolKey)`
- `0x1800072be`: `result.outputMessage = CommonUnwrapIntegrity(inputMessage, authData, protocolKey)`

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
  __int64 v14; // rcx
  int v15; // eax
  int v16; // r15d
  __int64 v17; // rsi
  int v18; // r8d
  __int64 v19; // rcx
  int v20; // eax
  int v21; // esi
  __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  char v25; // [rsp+30h] [rbp-48h] BYREF
  __int64 v26; // [rsp+38h] [rbp-40h]
  __int64 v27; // [rsp+48h] [rbp-30h]
  __int64 v28; // [rsp+50h] [rbp-28h]
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
      Kerb3961Free(v28);
    v27 = *(_QWORD *)v13;
    v14 = *(_QWORD *)(v13 + 8);
    *(_QWORD *)v13 = 0;
    v28 = v14;
    v15 = *(_DWORD *)(v13 + 16);
    *(_QWORD *)(v13 + 8) = 0;
    v29[0] = v15;
    *(_DWORD *)(v13 + 16) = -1073741823;
    v16 = v29[0];
    if ( v26 )
      Kerb3961Free(v26);
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
    Kerb3961Free(v28);
  v27 = *(_QWORD *)v17;
  v19 = *(_QWORD *)(v17 + 8);
  *(_QWORD *)v17 = 0;
  v28 = v19;
  v20 = *(_DWORD *)(v17 + 16);
  *(_QWORD *)(v17 + 8) = 0;
  v29[0] = v20;
  *(_DWORD *)(v17 + 16) = -1073741823;
  v21 = v29[0];
  if ( v26 )
    Kerb3961Free(v26);
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
    Kerb3961Free(v22);
  return a2;
}

```

## disassembly

```asm
0x1800070e0  push    rbp
0x1800070e2  push    rbx
0x1800070e3  push    rsi
0x1800070e4  push    rdi
0x1800070e5  push    r14
0x1800070e7  push    r15
0x1800070e9  mov     rbp, rsp
0x1800070ec  sub     rsp, 78h
0x1800070f0  cmp     qword ptr [r8], 10h
0x1800070f4  mov     rbx, rdx
0x1800070f7  mov     r10, rcx
0x1800070fa  jnb     short loc_180007128
0x1800070fc  lea     rcx, aInputmessageLe; "inputMessage.length >= WrapHeaderSize"
0x180007103  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007108  xor     edi, edi
0x18000710a  mov     [rbx+14h], rdi
0x18000710e  mov     [rbx+1Ch], rdi
0x180007112  mov     [rbx+24h], edi
0x180007115  mov     [rbx], rdi
0x180007118  mov     [rbx+8], rdi
0x18000711c  mov     dword ptr [rbx+10h], 80090308h
0x180007123  jmp     loc_180007320
0x180007128  mov     r14, [r8+8]
0x18000712c  mov     eax, 405h
0x180007131  cmp     [r14], ax
0x180007135  jz      short loc_180007140
0x180007137  lea     rcx, aHeaderTokenidG; "header.tokenID == GSSAPITokenID::Wrap"
0x18000713e  jmp     short loc_180007103
0x180007140  cmp     byte ptr [r14+3], 0FFh
0x180007145  jz      short loc_180007173
0x180007147  lea     rcx, aHeaderFillerHe_0; "header.filler == header.FillerValue"
0x18000714e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007153  xor     edi, edi
0x180007155  mov     [rbx+14h], rdi
0x180007159  mov     [rbx+1Ch], rdi
0x18000715d  mov     [rbx+24h], edi
0x180007160  mov     [rbx], rdi
0x180007163  mov     [rbx+8], rdi
0x180007167  mov     dword ptr [rbx+10h], 8009030Fh
0x18000716e  jmp     loc_180007320
0x180007173  mov     cl, [r14+2]
0x180007177  mov     sil, 1
0x18000717a  mov     al, cl
0x18000717c  and     al, sil
0x18000717f  cmp     al, [rbp+arg_28]
0x180007182  jz      short loc_18000718D
0x180007184  lea     rcx, aWiIsflagsetHea; "WI_IsFlagSet(header.flags, GSSAPIFlags:"...
0x18000718b  jmp     short loc_18000714E
0x18000718d  shr     cl, 2
0x180007190  and     cl, sil
0x180007193  cmp     cl, [rbp+arg_30]
0x180007196  jz      short loc_1800071C4
0x180007198  lea     rcx, aWiIsflagsetHea_0; "WI_IsFlagSet(header.flags, GSSAPIFlags:"...
0x18000719f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800071a4  xor     edi, edi
0x1800071a6  mov     [rbx+14h], rdi
0x1800071aa  mov     [rbx+1Ch], rdi
0x1800071ae  mov     [rbx+24h], edi
0x1800071b1  mov     [rbx], rdi
0x1800071b4  mov     [rbx+8], rdi
0x1800071b8  mov     dword ptr [rbx+10h], 80090348h
0x1800071bf  jmp     loc_180007320
0x1800071c4  mov     rax, [rbp+arg_20]
0x1800071c8  lea     rdx, [rbp+var_48]
0x1800071cc  xor     edi, edi
0x1800071ce  mov     [rsp+78h+var_58], rax
0x1800071d3  xorps   xmm0, xmm0
0x1800071d6  mov     [rbp+var_C], edi
0x1800071d9  movdqu  xmmword ptr [rbp+var_20+4], xmm0
0x1800071de  mov     [rbp+var_30], rdi
0x1800071e2  mov     rcx, r10
0x1800071e5  mov     [rbp+var_28], rdi
0x1800071e9  mov     dword ptr [rbp+var_20], edi
0x1800071ec  test    byte ptr [r14+2], 2
0x1800071f1  jz      short loc_18000726E
0x1800071f3  call    ?CommonUnwrapConfidential@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z; Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapConfidential(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800071f8  mov     rcx, [rbp+var_28]
0x1800071fc  mov     r15, rax
0x1800071ff  test    rcx, rcx
0x180007202  jz      short loc_180007209
0x180007204  call    Kerb3961Free
0x180007209  mov     rcx, [r15]
0x18000720c  mov     [rbp+var_30], rcx
0x180007210  mov     rcx, [r15+8]
0x180007214  mov     [r15], rdi
0x180007217  mov     [rbp+var_28], rcx
0x18000721b  mov     eax, [r15+10h]
0x18000721f  mov     [r15+8], rdi
0x180007223  mov     dword ptr [rbp+var_20], eax
0x180007226  mov     dword ptr [r15+10h], 0C0000001h
0x18000722e  mov     rcx, [rbp+var_40]
0x180007232  mov     r15d, dword ptr [rbp+var_20]
0x180007236  test    rcx, rcx
0x180007239  jz      short loc_180007240
0x18000723b  call    Kerb3961Free
0x180007240  test    r15d, r15d
0x180007243  jns     short loc_180007265
0x180007245  mov     edx, r15d; char *
0x180007248  lea     rcx, aResultOutputme_2; "result.outputMessage = CommonUnwrapConf"...
0x18000724f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007254  mov     [rbx+14h], rdi
0x180007258  mov     [rbx+1Ch], rdi
0x18000725c  mov     [rbx+24h], edi
0x18000725f  mov     [rbx+10h], r15d
0x180007263  jmp     short loc_1800072D8
0x180007265  mov     byte ptr [rbp+var_C], sil
0x180007269  jmp     loc_1800072F6
0x18000726e  call    ?CommonUnwrapIntegrity@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z; Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapIntegrity(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180007273  mov     rcx, [rbp+var_28]
0x180007277  mov     rsi, rax
0x18000727a  test    rcx, rcx
0x18000727d  jz      short loc_180007284
0x18000727f  call    Kerb3961Free
0x180007284  mov     rcx, [rsi]
0x180007287  mov     [rbp+var_30], rcx
0x18000728b  mov     rcx, [rsi+8]
0x18000728f  mov     [rsi], rdi
0x180007292  mov     [rbp+var_28], rcx
0x180007296  mov     eax, [rsi+10h]
0x180007299  mov     [rsi+8], rdi
0x18000729d  mov     dword ptr [rbp+var_20], eax
0x1800072a0  mov     dword ptr [rsi+10h], 0C0000001h
0x1800072a7  mov     rcx, [rbp+var_40]
0x1800072ab  mov     esi, dword ptr [rbp+var_20]
0x1800072ae  test    rcx, rcx
0x1800072b1  jz      short loc_1800072B8
0x1800072b3  call    Kerb3961Free
0x1800072b8  test    esi, esi
0x1800072ba  jns     short loc_1800072EF
0x1800072bc  mov     edx, esi; char *
0x1800072be  lea     rcx, aResultOutputme_0; "result.outputMessage = CommonUnwrapInte"...
0x1800072c5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800072ca  mov     [rbx+14h], rdi
0x1800072ce  mov     [rbx+1Ch], rdi
0x1800072d2  mov     [rbx+24h], edi
0x1800072d5  mov     [rbx+10h], esi
0x1800072d8  mov     rcx, [rbp+var_28]
0x1800072dc  mov     [rbx+8], rdi
0x1800072e0  mov     [rbx], rdi
0x1800072e3  test    rcx, rcx
0x1800072e6  jz      short loc_180007320
0x1800072e8  call    Kerb3961Free
0x1800072ed  jmp     short loc_180007320
0x1800072ef  mov     sil, dil
0x1800072f2  mov     byte ptr [rbp+var_C], dil
0x1800072f6  mov     eax, dword ptr [rbp+var_20]
0x1800072f9  mov     dword ptr [rbp+var_20+10h], edi
0x1800072fc  mov     rcx, [r14+8]
0x180007300  mov     [rbx+10h], eax
0x180007303  mov     rax, [rbp+var_30]
0x180007307  mov     [rbx], rax
0x18000730a  mov     rax, [rbp+var_28]
0x18000730e  bswap   rcx
0x180007311  mov     [rbx+8], rax
0x180007315  mov     [rbx+18h], rcx
0x180007319  mov     [rbx+20h], edi
0x18000731c  mov     [rbx+24h], sil
0x180007320  mov     rax, rbx
0x180007323  add     rsp, 78h
0x180007327  pop     r15
0x180007329  pop     r14
0x18000732b  pop     rdi
0x18000732c  pop     rsi
0x18000732d  pop     rbx
0x18000732e  pop     rbp
0x18000732f  retn
```
