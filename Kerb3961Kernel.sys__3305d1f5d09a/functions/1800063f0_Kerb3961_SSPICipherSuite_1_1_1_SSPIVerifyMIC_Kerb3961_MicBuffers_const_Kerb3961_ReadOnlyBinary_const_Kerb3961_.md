# Kerb3961::SSPICipherSuite<1,1,1>::SSPIVerifyMIC(Kerb3961::MicBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800063f0`
- end: `0x1800064da`
- name: `?SSPIVerifyMIC@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUMicBuffers@2@AEBUReadOnlyBinary@2@1_N2@Z`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002174`
- `0x1800063f0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x18000641e`: `combinedBuffer`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,1>::SSPIVerifyMIC(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        char a6,
        char a7)
{
  const char *v11; // rdx
  int v12; // r8d
  int v13; // edi
  _QWORD *v14; // r8
  char *v15; // rcx
  _BYTE v17[8]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v18; // [rsp+48h] [rbp-40h]
  char *v19; // [rsp+50h] [rbp-38h]

  Kerb3961::SSPICipherSuite<1,1,0>::CoalesceMICBuffers(v17, a3);
  v13 = (int)v19;
  if ( (int)v19 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"combinedBuffer",
      (const char *)(unsigned int)v19,
      v12);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = v13;
    goto LABEL_12;
  }
  if ( (_DWORD)v19 == 255 )
    v14 = *(_QWORD **)(a3 + 8);
  else
    v14 = v17;
  if ( *v14 > 0xFFFFFFFFFFFF0000uLL )
  {
    v15 = "effectiveInput.length <= MessageLimit";
LABEL_8:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v15, v11);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = -1073741675;
    goto LABEL_12;
  }
  if ( *a4 > 0xFFFFFFFFFFFF0000uLL )
  {
    v15 = "inputSignature.length <= MessageLimit";
    goto LABEL_8;
  }
  (*(void (__fastcall **)(__int64, __int64, _QWORD *, _QWORD *, __int64, char, char))(*(_QWORD *)a1 + 336LL))(
    a1,
    a2,
    v14,
    a4,
    a5,
    a6,
    a7);
LABEL_12:
  if ( v18 )
    Kerb3961Free(v18);
  return a2;
}

```

## disassembly

```asm
0x1800063f0  push    rbx
0x1800063f2  push    rbp
0x1800063f3  push    rsi
0x1800063f4  push    rdi
0x1800063f5  push    r14
0x1800063f7  sub     rsp, 60h
0x1800063fb  mov     rbx, rdx
0x1800063fe  mov     r14, rcx
0x180006401  mov     rdx, r8
0x180006404  lea     rcx, [rsp+88h+var_48]
0x180006409  mov     rbp, r9
0x18000640c  mov     rsi, r8
0x18000640f  call    ?CoalesceMICBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMicBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceMICBuffers(Kerb3961::MicBuffers const &)
0x180006414  mov     edi, dword ptr [rsp+88h+var_38]
0x180006418  test    edi, edi
0x18000641a  jns     short loc_180006438
0x18000641c  mov     edx, edi; char *
0x18000641e  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180006425  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000642a  xorps   xmm0, xmm0
0x18000642d  movups  xmmword ptr [rbx], xmm0
0x180006430  mov     [rbx+0Ch], edi
0x180006433  jmp     loc_1800064BC
0x180006438  cmp     edi, 0FFh
0x18000643e  jnz     short loc_180006446
0x180006440  mov     r8, [rsi+8]
0x180006444  jmp     short loc_18000644B
0x180006446  lea     r8, [rsp+88h+var_48]
0x18000644b  mov     rax, 0FFFFFFFFFFFF0000h
0x180006452  cmp     [r8], rax
0x180006455  jbe     short loc_180006472
0x180006457  lea     rcx, aEffectiveinput; "effectiveInput.length <= MessageLimit"
0x18000645e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180006463  xorps   xmm0, xmm0
0x180006466  movups  xmmword ptr [rbx], xmm0
0x180006469  mov     dword ptr [rbx+0Ch], 0C0000095h
0x180006470  jmp     short loc_1800064BC
0x180006472  cmp     [rbp+0], rax
0x180006476  jbe     short loc_180006481
0x180006478  lea     rcx, aInputsignature_1; "inputSignature.length <= MessageLimit"
0x18000647f  jmp     short loc_18000645E
0x180006481  mov     cl, [rsp+88h+arg_30]
0x180006488  mov     r9, rbp
0x18000648b  mov     rax, [r14]
0x18000648e  mov     rdx, rbx
0x180006491  mov     [rsp+88h+var_58], cl
0x180006495  mov     cl, [rsp+88h+arg_28]
0x18000649c  mov     [rsp+88h+var_60], cl
0x1800064a0  mov     rcx, [rsp+88h+arg_20]
0x1800064a8  mov     rax, [rax+150h]
0x1800064af  mov     [rsp+88h+var_68], rcx
0x1800064b4  mov     rcx, r14
0x1800064b7  call    _guard_dispatch_icall
0x1800064bc  mov     rcx, [rsp+88h+var_40]
0x1800064c1  test    rcx, rcx
0x1800064c4  jz      short loc_1800064CB
0x1800064c6  call    Kerb3961Free
0x1800064cb  mov     rax, rbx
0x1800064ce  add     rsp, 60h
0x1800064d2  pop     r14
0x1800064d4  pop     rdi
0x1800064d5  pop     rsi
0x1800064d6  pop     rbp
0x1800064d7  pop     rbx
0x1800064d8  retn
```
