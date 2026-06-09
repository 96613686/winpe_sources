# Kerb3961::RFC4121CipherSuite<1,1,2>::CommonVerifyMIC(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180003020`
- end: `0x18000323a`
- name: `?CommonVerifyMIC@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_N1@Z`
- size: `538`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800018e8`
- `0x180003020`
- `0x180003910`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x180003072`: `resultToken.tokenID == GSSAPITokenID::MIC`
- `0x180003081`: `resultToken.filler == MICToken::FillerValue`
- `0x1800030a5`: `resultToken.filler2 == MICToken::Filler2Value`
- `0x1800030b6`: `WI_IsFlagSet(resultToken.flags, GSSAPIFlags::Sealed) == false`
- `0x1800030c8`: `WI_IsFlagSet(resultToken.flags, GSSAPIFlags::SentByAcceptor) == initiator`
- `0x1800030dc`: `WI_IsFlagSet(resultToken.flags, GSSAPIFlags::AcceptorSubkey) == acceptorSubkey`
- `0x180003199`: `combinedInput`
- `0x1800031ea`: `this->VerifyMic(specificKey, combinedInput, {micLength, reinterpret_cast<const uint8_t*>(&resultToken.data)})`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,2>::CommonVerifyMIC(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        unsigned __int8 a6,
        char a7)
{
  char *v11; // rcx
  __int64 v12; // rdi
  char *v13; // rcx
  char v14; // cl
  int v15; // r8d
  int v16; // esi
  unsigned __int64 v17; // r12
  unsigned __int64 v18; // rax
  int v19; // r8d
  int v20; // esi
  char *v21; // rcx
  __int64 v23; // [rsp+30h] [rbp-48h] BYREF
  __int64 v24; // [rsp+38h] [rbp-40h]
  char *v25[2]; // [rsp+40h] [rbp-38h] BYREF
  char *v26; // [rsp+50h] [rbp-28h]
  _BYTE v27[8]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v28; // [rsp+60h] [rbp-18h]
  char *v29; // [rsp+68h] [rbp-10h]
  char v30; // [rsp+D8h] [rbp+60h] BYREF

  if ( *a4 < 0x10u )
  {
    v11 = "inputSignature.length >= MICHeaderSize";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v11, (const char *)a2);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = -2146893048;
    return a2;
  }
  v12 = a4[1];
  if ( *(_WORD *)v12 != 1028 )
  {
    v11 = "resultToken.tokenID == GSSAPITokenID::MIC";
    goto LABEL_3;
  }
  if ( *(_BYTE *)(v12 + 3) != 0xFF )
  {
    v13 = "resultToken.filler == MICToken::FillerValue";
LABEL_8:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v13, (const char *)a2);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = -2146893041;
    return a2;
  }
  if ( *(_DWORD *)(v12 + 4) != -1 )
  {
    v13 = "resultToken.filler2 == MICToken::Filler2Value";
    goto LABEL_8;
  }
  v14 = *(_BYTE *)(v12 + 2);
  if ( (v14 & 2) != 0 )
  {
    v13 = "WI_IsFlagSet(resultToken.flags, GSSAPIFlags::Sealed) == false";
    goto LABEL_8;
  }
  if ( (v14 & 1) != a6 )
  {
    v13 = "WI_IsFlagSet(resultToken.flags, GSSAPIFlags::SentByAcceptor) == initiator";
    goto LABEL_8;
  }
  if ( ((v14 & 4) != 0) != a7 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"WI_IsFlagSet(resultToken.flags, GSSAPIFlags::AcceptorSubkey) == acceptorSubkey",
      (const char *)a2);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = -2146892984;
    return a2;
  }
  (*(void (__fastcall **)(_QWORD *, char **, __int64, __int64, int))(*a1 + 168LL))(a1, v25, a5, 2 * (a6 ^ 1LL) + 23, 2);
  v16 = (int)v26;
  if ( (int)v26 >= 0 )
  {
    v17 = *a4 - 16LL;
    v18 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 128LL))(a1 + 1);
    v23 = 16;
    if ( v17 > v18 )
      v17 = v18;
    v24 = a4[1];
    Kerb3961::Concatenate(v27, a3, &v23);
    v20 = (int)v29;
    if ( (int)v29 >= 0 )
    {
      v23 = v17;
      v24 = v12 + 16;
      v20 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, char *, char **, _BYTE *, __int64 *))(a1[1] + 96LL))(
                         a1 + 1,
                         &v30,
                         v25,
                         v27,
                         &v23);
      if ( v20 >= 0 )
      {
        *(_QWORD *)a2 = _byteswap_uint64(*(_QWORD *)(v12 + 8));
        *(_QWORD *)(a2 + 8) = 0;
LABEL_27:
        if ( v28 )
          Kerb3961Free(v28);
        goto LABEL_29;
      }
      v21 = "this->VerifyMic(specificKey, combinedInput, {micLength, reinterpret_cast<const uint8_t*>(&resultToken.data)})";
    }
    else
    {
      v21 = "combinedInput";
    }
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v21, (const char *)(unsigned int)v20, v19);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = v20;
    goto LABEL_27;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"specificKey",
    (const char *)(unsigned int)v26,
    v15);
  *(_OWORD *)a2 = 0;
  *(_DWORD *)(a2 + 12) = v16;
LABEL_29:
  if ( v25[1] )
     Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v25[0]);
  return a2;
}

```

## disassembly

```asm
0x180003020  push    rbp
0x180003022  push    rbx
0x180003023  push    rsi
0x180003024  push    rdi
0x180003025  push    r12
0x180003027  push    r13
0x180003029  push    r14
0x18000302b  push    r15
0x18000302d  mov     rbp, rsp
0x180003030  sub     rsp, 78h
0x180003034  cmp     qword ptr [r9], 10h
0x180003038  mov     r14, r9
0x18000303b  mov     r13, r8
0x18000303e  mov     rbx, rdx
0x180003041  mov     r15, rcx
0x180003044  jnb     short loc_180003064
0x180003046  lea     rcx, aInputsignature; "inputSignature.length >= MICHeaderSize"
0x18000304d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180003052  xorps   xmm0, xmm0
0x180003055  movups  xmmword ptr [rbx], xmm0
0x180003058  mov     dword ptr [rbx+0Ch], 80090308h
0x18000305f  jmp     loc_180003225
0x180003064  mov     rdi, [r9+8]
0x180003068  mov     eax, 404h
0x18000306d  cmp     [rdi], ax
0x180003070  jz      short loc_18000307B
0x180003072  lea     rcx, aResulttokenTok; "resultToken.tokenID == GSSAPITokenID::M"...
0x180003079  jmp     short loc_18000304D
0x18000307b  cmp     byte ptr [rdi+3], 0FFh
0x18000307f  jz      short loc_18000309F
0x180003081  lea     rcx, aResulttokenFil_0; "resultToken.filler == MICToken::FillerV"...
0x180003088  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000308d  xorps   xmm0, xmm0
0x180003090  movups  xmmword ptr [rbx], xmm0
0x180003093  mov     dword ptr [rbx+0Ch], 8009030Fh
0x18000309a  jmp     loc_180003225
0x18000309f  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x1800030a3  jz      short loc_1800030AE
0x1800030a5  lea     rcx, aResulttokenFil; "resultToken.filler2 == MICToken::Filler"...
0x1800030ac  jmp     short loc_180003088
0x1800030ae  mov     cl, [rdi+2]
0x1800030b1  test    cl, 2
0x1800030b4  jz      short loc_1800030BF
0x1800030b6  lea     rcx, aWiIsflagsetRes_0; "WI_IsFlagSet(resultToken.flags, GSSAPIF"...
0x1800030bd  jmp     short loc_180003088
0x1800030bf  mov     al, cl
0x1800030c1  and     al, 1
0x1800030c3  cmp     al, [rbp+arg_28]
0x1800030c6  jz      short loc_1800030D1
0x1800030c8  lea     rcx, aWiIsflagsetRes; "WI_IsFlagSet(resultToken.flags, GSSAPIF"...
0x1800030cf  jmp     short loc_180003088
0x1800030d1  shr     cl, 2
0x1800030d4  and     cl, 1
0x1800030d7  cmp     cl, [rbp+arg_30]
0x1800030da  jz      short loc_1800030FA
0x1800030dc  lea     rcx, aWiIsflagsetRes_1; "WI_IsFlagSet(resultToken.flags, GSSAPIF"...
0x1800030e3  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800030e8  xorps   xmm0, xmm0
0x1800030eb  movups  xmmword ptr [rbx], xmm0
0x1800030ee  mov     dword ptr [rbx+0Ch], 80090348h
0x1800030f5  jmp     loc_180003225
0x1800030fa  mov     rax, [r15]
0x1800030fd  lea     rdx, [rbp+var_38]
0x180003101  movzx   r9d, [rbp+arg_28]
0x180003106  mov     rcx, r15
0x180003109  mov     r8, [rbp+arg_20]
0x18000310d  xor     r9, 1
0x180003111  mov     dword ptr [rsp+78h+var_58], 2
0x180003119  mov     rax, [rax+0A8h]
0x180003120  lea     r9, ds:17h[r9*2]
0x180003128  call    _guard_dispatch_icall
0x18000312d  mov     esi, dword ptr [rbp+var_28]
0x180003130  test    esi, esi
0x180003132  jns     short loc_180003150
0x180003134  mov     edx, esi; char *
0x180003136  lea     rcx, aSpecifickey; "specificKey"
0x18000313d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180003142  xorps   xmm0, xmm0
0x180003145  movups  xmmword ptr [rbx], xmm0
0x180003148  mov     [rbx+0Ch], esi
0x18000314b  jmp     loc_180003213
0x180003150  mov     rax, [r15+8]
0x180003154  lea     rcx, [r15+8]
0x180003158  mov     r12, [r14]
0x18000315b  add     r12, 0FFFFFFFFFFFFFFF0h
0x18000315f  mov     rax, [rax+80h]
0x180003166  call    _guard_dispatch_icall
0x18000316b  cmp     r12, rax
0x18000316e  mov     [rbp+var_48], 10h
0x180003176  lea     r8, [rbp+var_48]
0x18000317a  mov     rdx, r13
0x18000317d  cmova   r12, rax
0x180003181  lea     rcx, [rbp+var_20]
0x180003185  mov     rax, [r14+8]
0x180003189  mov     [rbp+var_40], rax
0x18000318d  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180003192  mov     esi, dword ptr [rbp+var_10]
0x180003195  test    esi, esi
0x180003197  jns     short loc_1800031B2
0x180003199  lea     rcx, aCombinedinput; "combinedInput"
0x1800031a0  mov     edx, esi; char *
0x1800031a2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800031a7  xorps   xmm0, xmm0
0x1800031aa  movups  xmmword ptr [rbx], xmm0
0x1800031ad  mov     [rbx+0Ch], esi
0x1800031b0  jmp     short loc_180003205
0x1800031b2  lea     rax, [rdi+10h]
0x1800031b6  mov     [rbp+var_48], r12
0x1800031ba  mov     [rbp+var_40], rax
0x1800031be  lea     rcx, [rbp+var_48]
0x1800031c2  mov     rax, [r15+8]
0x1800031c6  lea     r9, [rbp+var_20]
0x1800031ca  mov     [rsp+78h+var_58], rcx
0x1800031cf  lea     r8, [rbp+var_38]
0x1800031d3  lea     rdx, [rbp+arg_18]
0x1800031d7  lea     rcx, [r15+8]
0x1800031db  mov     rax, [rax+60h]
0x1800031df  call    _guard_dispatch_icall
0x1800031e4  mov     esi, [rax]
0x1800031e6  test    esi, esi
0x1800031e8  jns     short loc_1800031F3
0x1800031ea  lea     rcx, aThisVerifymicS_0; "this->VerifyMic(specificKey, combinedIn"...
0x1800031f1  jmp     short loc_1800031A0
0x1800031f3  mov     rax, [rdi+8]
0x1800031f7  bswap   rax
0x1800031fa  mov     [rbx], rax
0x1800031fd  mov     qword ptr [rbx+8], 0
0x180003205  mov     rcx, [rbp+var_18]
0x180003209  test    rcx, rcx
0x18000320c  jz      short loc_180003213
0x18000320e  call    Kerb3961Free
0x180003213  mov     rdx, [rbp+var_30]
0x180003217  test    rdx, rdx
0x18000321a  jz      short loc_180003225
0x18000321c  mov     rcx, [rbp+var_38]
0x180003220  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180003225  mov     rax, rbx
0x180003228  add     rsp, 78h
0x18000322c  pop     r15
0x18000322e  pop     r14
0x180003230  pop     r13
0x180003232  pop     r12
0x180003234  pop     rdi
0x180003235  pop     rsi
0x180003236  pop     rbx
0x180003237  pop     rbp
0x180003238  retn
```
