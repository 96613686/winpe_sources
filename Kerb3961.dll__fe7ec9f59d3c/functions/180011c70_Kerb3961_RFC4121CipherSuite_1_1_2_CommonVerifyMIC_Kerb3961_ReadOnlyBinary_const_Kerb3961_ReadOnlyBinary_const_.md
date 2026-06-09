# Kerb3961::RFC4121CipherSuite<1,1,2>::CommonVerifyMIC(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180011c70`
- end: `0x180011e8b`
- name: `?CommonVerifyMIC@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_N1@Z`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c34`
- `0x180002c64`
- `0x180002fc0`
- `0x18000700c`
- `0x180011c70`
- `0x18001e010`

## string_xrefs

- `0x180011cc2`: `resultToken.tokenID == GSSAPITokenID::MIC`
- `0x180011cd1`: `resultToken.filler == MICToken::FillerValue`
- `0x180011cf5`: `resultToken.filler2 == MICToken::Filler2Value`
- `0x180011d06`: `WI_IsFlagSet(resultToken.flags, GSSAPIFlags::Sealed) == false`
- `0x180011d18`: `WI_IsFlagSet(resultToken.flags, GSSAPIFlags::SentByAcceptor) == initiator`
- `0x180011d2c`: `WI_IsFlagSet(resultToken.flags, GSSAPIFlags::AcceptorSubkey) == acceptorSubkey`
- `0x180011de9`: `combinedInput`
- `0x180011e3a`: `this->VerifyMic(specificKey, combinedInput, {micLength, reinterpret_cast<const uint8_t*>(&resultToken.data)})`

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
  void *v28; // [rsp+60h] [rbp-18h]
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
          operator delete(v28, 0);
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
0x180011c70  push    rbp
0x180011c72  push    rbx
0x180011c73  push    rsi
0x180011c74  push    rdi
0x180011c75  push    r12
0x180011c77  push    r13
0x180011c79  push    r14
0x180011c7b  push    r15
0x180011c7d  mov     rbp, rsp
0x180011c80  sub     rsp, 78h
0x180011c84  cmp     qword ptr [r9], 10h
0x180011c88  mov     r14, r9
0x180011c8b  mov     r13, r8
0x180011c8e  mov     rbx, rdx
0x180011c91  mov     r15, rcx
0x180011c94  jnb     short loc_180011CB4
0x180011c96  lea     rcx, aInputsignature; "inputSignature.length >= MICHeaderSize"
0x180011c9d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180011ca2  xorps   xmm0, xmm0
0x180011ca5  movups  xmmword ptr [rbx], xmm0
0x180011ca8  mov     dword ptr [rbx+0Ch], 80090308h
0x180011caf  jmp     loc_180011E77
0x180011cb4  mov     rdi, [r9+8]
0x180011cb8  mov     eax, 404h
0x180011cbd  cmp     [rdi], ax
0x180011cc0  jz      short loc_180011CCB
0x180011cc2  lea     rcx, aResulttokenTok; "resultToken.tokenID == GSSAPITokenID::M"...
0x180011cc9  jmp     short loc_180011C9D
0x180011ccb  cmp     byte ptr [rdi+3], 0FFh
0x180011ccf  jz      short loc_180011CEF
0x180011cd1  lea     rcx, aResulttokenFil_0; "resultToken.filler == MICToken::FillerV"...
0x180011cd8  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180011cdd  xorps   xmm0, xmm0
0x180011ce0  movups  xmmword ptr [rbx], xmm0
0x180011ce3  mov     dword ptr [rbx+0Ch], 8009030Fh
0x180011cea  jmp     loc_180011E77
0x180011cef  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x180011cf3  jz      short loc_180011CFE
0x180011cf5  lea     rcx, aResulttokenFil; "resultToken.filler2 == MICToken::Filler"...
0x180011cfc  jmp     short loc_180011CD8
0x180011cfe  mov     cl, [rdi+2]
0x180011d01  test    cl, 2
0x180011d04  jz      short loc_180011D0F
0x180011d06  lea     rcx, aWiIsflagsetRes_0; "WI_IsFlagSet(resultToken.flags, GSSAPIF"...
0x180011d0d  jmp     short loc_180011CD8
0x180011d0f  mov     al, cl
0x180011d11  and     al, 1
0x180011d13  cmp     al, [rbp+arg_28]
0x180011d16  jz      short loc_180011D21
0x180011d18  lea     rcx, aWiIsflagsetRes; "WI_IsFlagSet(resultToken.flags, GSSAPIF"...
0x180011d1f  jmp     short loc_180011CD8
0x180011d21  shr     cl, 2
0x180011d24  and     cl, 1
0x180011d27  cmp     cl, [rbp+arg_30]
0x180011d2a  jz      short loc_180011D4A
0x180011d2c  lea     rcx, aWiIsflagsetRes_1; "WI_IsFlagSet(resultToken.flags, GSSAPIF"...
0x180011d33  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180011d38  xorps   xmm0, xmm0
0x180011d3b  movups  xmmword ptr [rbx], xmm0
0x180011d3e  mov     dword ptr [rbx+0Ch], 80090348h
0x180011d45  jmp     loc_180011E77
0x180011d4a  mov     rax, [r15]
0x180011d4d  lea     rdx, [rbp+var_38]
0x180011d51  movzx   r9d, [rbp+arg_28]
0x180011d56  mov     rcx, r15
0x180011d59  mov     r8, [rbp+arg_20]
0x180011d5d  xor     r9, 1
0x180011d61  mov     dword ptr [rsp+78h+var_58], 2
0x180011d69  mov     rax, [rax+0A8h]
0x180011d70  lea     r9, ds:17h[r9*2]
0x180011d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d7d  mov     esi, dword ptr [rbp+var_28]
0x180011d80  test    esi, esi
0x180011d82  jns     short loc_180011DA0
0x180011d84  mov     edx, esi; char *
0x180011d86  lea     rcx, aSpecifickey; "specificKey"
0x180011d8d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180011d92  xorps   xmm0, xmm0
0x180011d95  movups  xmmword ptr [rbx], xmm0
0x180011d98  mov     [rbx+0Ch], esi
0x180011d9b  jmp     loc_180011E65
0x180011da0  mov     rax, [r15+8]
0x180011da4  lea     rcx, [r15+8]
0x180011da8  mov     r12, [r14]
0x180011dab  add     r12, 0FFFFFFFFFFFFFFF0h
0x180011daf  mov     rax, [rax+80h]
0x180011db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dbb  cmp     r12, rax
0x180011dbe  mov     [rbp+var_48], 10h
0x180011dc6  lea     r8, [rbp+var_48]
0x180011dca  mov     rdx, r13
0x180011dcd  cmova   r12, rax
0x180011dd1  lea     rcx, [rbp+var_20]
0x180011dd5  mov     rax, [r14+8]
0x180011dd9  mov     [rbp+var_40], rax
0x180011ddd  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180011de2  mov     esi, dword ptr [rbp+var_10]
0x180011de5  test    esi, esi
0x180011de7  jns     short loc_180011E02
0x180011de9  lea     rcx, aCombinedinput; "combinedInput"
0x180011df0  mov     edx, esi; char *
0x180011df2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180011df7  xorps   xmm0, xmm0
0x180011dfa  movups  xmmword ptr [rbx], xmm0
0x180011dfd  mov     [rbx+0Ch], esi
0x180011e00  jmp     short loc_180011E55
0x180011e02  lea     rax, [rdi+10h]
0x180011e06  mov     [rbp+var_48], r12
0x180011e0a  mov     [rbp+var_40], rax
0x180011e0e  lea     rcx, [rbp+var_48]
0x180011e12  mov     rax, [r15+8]
0x180011e16  lea     r9, [rbp+var_20]
0x180011e1a  mov     [rsp+78h+var_58], rcx
0x180011e1f  lea     r8, [rbp+var_38]
0x180011e23  lea     rdx, [rbp+arg_18]
0x180011e27  lea     rcx, [r15+8]
0x180011e2b  mov     rax, [rax+60h]
0x180011e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e34  mov     esi, [rax]
0x180011e36  test    esi, esi
0x180011e38  jns     short loc_180011E43
0x180011e3a  lea     rcx, aThisVerifymicS_0; "this->VerifyMic(specificKey, combinedIn"...
0x180011e41  jmp     short loc_180011DF0
0x180011e43  mov     rax, [rdi+8]
0x180011e47  bswap   rax
0x180011e4a  mov     [rbx], rax
0x180011e4d  mov     qword ptr [rbx+8], 0
0x180011e55  mov     rcx, [rbp+var_18]; void *
0x180011e59  test    rcx, rcx
0x180011e5c  jz      short loc_180011E65
0x180011e5e  xor     edx, edx; struct std::nothrow_t *
0x180011e60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011e65  mov     rdx, [rbp+var_30]
0x180011e69  test    rdx, rdx
0x180011e6c  jz      short loc_180011E77
0x180011e6e  mov     rcx, [rbp+var_38]
0x180011e72  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180011e77  mov     rax, rbx
0x180011e7a  add     rsp, 78h
0x180011e7e  pop     r15
0x180011e80  pop     r14
0x180011e82  pop     r13
0x180011e84  pop     r12
0x180011e86  pop     rdi
0x180011e87  pop     rsi
0x180011e88  pop     rbx
0x180011e89  pop     rbp
0x180011e8a  retn
```
