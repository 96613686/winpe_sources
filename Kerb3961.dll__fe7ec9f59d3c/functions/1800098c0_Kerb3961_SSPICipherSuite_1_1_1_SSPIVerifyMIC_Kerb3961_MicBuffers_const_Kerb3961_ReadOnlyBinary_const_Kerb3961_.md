# Kerb3961::SSPICipherSuite<1,1,1>::SSPIVerifyMIC(Kerb3961::MicBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800098c0`
- end: `0x1800099ab`
- name: `?SSPIVerifyMIC@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUMicBuffers@2@AEBUReadOnlyBinary@2@1_N2@Z`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x180004e74`
- `0x1800098c0`
- `0x18001e010`

## string_xrefs

- `0x1800098ee`: `combinedBuffer`

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
  void *v18; // [rsp+48h] [rbp-40h]
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
    operator delete(v18, 0);
  return a2;
}

```

## disassembly

```asm
0x1800098c0  push    rbx
0x1800098c2  push    rbp
0x1800098c3  push    rsi
0x1800098c4  push    rdi
0x1800098c5  push    r14
0x1800098c7  sub     rsp, 60h
0x1800098cb  mov     rbx, rdx
0x1800098ce  mov     r14, rcx
0x1800098d1  mov     rdx, r8
0x1800098d4  lea     rcx, [rsp+88h+var_48]
0x1800098d9  mov     rbp, r9
0x1800098dc  mov     rsi, r8
0x1800098df  call    ?CoalesceMICBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMicBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceMICBuffers(Kerb3961::MicBuffers const &)
0x1800098e4  mov     edi, dword ptr [rsp+88h+var_38]
0x1800098e8  test    edi, edi
0x1800098ea  jns     short loc_180009908
0x1800098ec  mov     edx, edi; char *
0x1800098ee  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x1800098f5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800098fa  xorps   xmm0, xmm0
0x1800098fd  movups  xmmword ptr [rbx], xmm0
0x180009900  mov     [rbx+0Ch], edi
0x180009903  jmp     loc_18000998C
0x180009908  cmp     edi, 0FFh
0x18000990e  jnz     short loc_180009916
0x180009910  mov     r8, [rsi+8]
0x180009914  jmp     short loc_18000991B
0x180009916  lea     r8, [rsp+88h+var_48]
0x18000991b  mov     rax, 0FFFFFFFFFFFF0000h
0x180009922  cmp     [r8], rax
0x180009925  jbe     short loc_180009942
0x180009927  lea     rcx, aEffectiveinput; "effectiveInput.length <= MessageLimit"
0x18000992e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009933  xorps   xmm0, xmm0
0x180009936  movups  xmmword ptr [rbx], xmm0
0x180009939  mov     dword ptr [rbx+0Ch], 0C0000095h
0x180009940  jmp     short loc_18000998C
0x180009942  cmp     [rbp+0], rax
0x180009946  jbe     short loc_180009951
0x180009948  lea     rcx, aInputsignature_1; "inputSignature.length <= MessageLimit"
0x18000994f  jmp     short loc_18000992E
0x180009951  mov     cl, [rsp+88h+arg_30]
0x180009958  mov     r9, rbp
0x18000995b  mov     rax, [r14]
0x18000995e  mov     rdx, rbx
0x180009961  mov     [rsp+88h+var_58], cl
0x180009965  mov     cl, [rsp+88h+arg_28]
0x18000996c  mov     [rsp+88h+var_60], cl
0x180009970  mov     rcx, [rsp+88h+arg_20]
0x180009978  mov     rax, [rax+150h]
0x18000997f  mov     [rsp+88h+var_68], rcx
0x180009984  mov     rcx, r14
0x180009987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998c  mov     rcx, [rsp+88h+var_40]; void *
0x180009991  test    rcx, rcx
0x180009994  jz      short loc_18000999D
0x180009996  xor     edx, edx; struct std::nothrow_t *
0x180009998  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000999d  mov     rax, rbx
0x1800099a0  add     rsp, 60h
0x1800099a4  pop     r14
0x1800099a6  pop     rdi
0x1800099a7  pop     rsi
0x1800099a8  pop     rbp
0x1800099a9  pop     rbx
0x1800099aa  retn
```
