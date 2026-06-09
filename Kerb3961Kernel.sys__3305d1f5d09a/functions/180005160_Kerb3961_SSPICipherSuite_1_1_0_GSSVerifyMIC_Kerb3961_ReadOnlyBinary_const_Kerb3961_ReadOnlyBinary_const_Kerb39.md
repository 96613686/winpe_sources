# Kerb3961::SSPICipherSuite<1,1,0>::GSSVerifyMIC(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180005160`
- end: `0x1800051da`
- name: `?GSSVerifyMIC@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_N1@Z`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005160`
- `0x180011760`
- `0x180012240`

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
0x180005160  push    rbx
0x180005162  sub     rsp, 40h
0x180005166  mov     rax, 0FFFFFFFFFFFF0000h
0x18000516d  mov     rbx, rdx
0x180005170  mov     r10, rcx
0x180005173  cmp     [r8], rax
0x180005176  jbe     short loc_180005193
0x180005178  lea     rcx, aInputmessageLe_0; "inputMessage.length <= MessageLimit"
0x18000517f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180005184  xorps   xmm0, xmm0
0x180005187  movups  xmmword ptr [rbx], xmm0
0x18000518a  mov     dword ptr [rbx+0Ch], 0C0000095h
0x180005191  jmp     short loc_1800051D0
0x180005193  cmp     [r9], rax
0x180005196  jbe     short loc_1800051A1
0x180005198  lea     rcx, aInputsignature_1; "inputSignature.length <= MessageLimit"
0x18000519f  jmp     short loc_18000517F
0x1800051a1  mov     rax, [rcx]
0x1800051a4  mov     cl, [rsp+48h+arg_30]
0x1800051ab  mov     [rsp+48h+var_18], cl
0x1800051af  mov     cl, [rsp+48h+arg_28]
0x1800051b3  mov     rax, [rax+150h]
0x1800051ba  mov     [rsp+48h+var_20], cl
0x1800051be  mov     rcx, [rsp+48h+arg_20]
0x1800051c3  mov     [rsp+48h+var_28], rcx
0x1800051c8  mov     rcx, r10
0x1800051cb  call    _guard_dispatch_icall
0x1800051d0  mov     rax, rbx
0x1800051d3  add     rsp, 40h
0x1800051d7  pop     rbx
0x1800051d8  retn
```
