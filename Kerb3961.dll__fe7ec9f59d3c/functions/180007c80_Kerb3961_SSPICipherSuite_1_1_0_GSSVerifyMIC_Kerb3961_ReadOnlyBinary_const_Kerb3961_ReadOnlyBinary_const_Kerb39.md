# Kerb3961::SSPICipherSuite<1,1,0>::GSSVerifyMIC(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180007c80`
- end: `0x180007cf9`
- name: `?GSSVerifyMIC@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_N1@Z`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002c64`
- `0x180007c80`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,0>::GSSVerifyMIC(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  char *v5; // rcx

  if ( *a3 <= 0xFFFFFFFFFFFF0000uLL )
  {
    if ( *a4 <= 0xFFFFFFFFFFFF0000uLL )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 336LL))(a1);
      return a2;
    }
    v5 = "inputSignature.length <= MessageLimit";
  }
  else
  {
    v5 = "inputMessage.length <= MessageLimit";
  }
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v5, (const char *)a2);
  *(_OWORD *)a2 = 0;
  *(_DWORD *)(a2 + 12) = -1073741675;
  return a2;
}

```

## disassembly

```asm
0x180007c80  push    rbx
0x180007c82  sub     rsp, 40h
0x180007c86  mov     rax, 0FFFFFFFFFFFF0000h
0x180007c8d  mov     rbx, rdx
0x180007c90  mov     r10, rcx
0x180007c93  cmp     [r8], rax
0x180007c96  jbe     short loc_180007CB3
0x180007c98  lea     rcx, aInputmessageLe_0; "inputMessage.length <= MessageLimit"
0x180007c9f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007ca4  xorps   xmm0, xmm0
0x180007ca7  movups  xmmword ptr [rbx], xmm0
0x180007caa  mov     dword ptr [rbx+0Ch], 0C0000095h
0x180007cb1  jmp     short loc_180007CF0
0x180007cb3  cmp     [r9], rax
0x180007cb6  jbe     short loc_180007CC1
0x180007cb8  lea     rcx, aInputsignature_1; "inputSignature.length <= MessageLimit"
0x180007cbf  jmp     short loc_180007C9F
0x180007cc1  mov     rax, [rcx]
0x180007cc4  mov     cl, [rsp+48h+arg_30]
0x180007ccb  mov     [rsp+48h+var_18], cl
0x180007ccf  mov     cl, [rsp+48h+arg_28]
0x180007cd3  mov     rax, [rax+150h]
0x180007cda  mov     [rsp+48h+var_20], cl
0x180007cde  mov     rcx, [rsp+48h+arg_20]
0x180007ce3  mov     [rsp+48h+var_28], rcx
0x180007ce8  mov     rcx, r10
0x180007ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf0  mov     rax, rbx
0x180007cf3  add     rsp, 40h
0x180007cf7  pop     rbx
0x180007cf8  retn
```
