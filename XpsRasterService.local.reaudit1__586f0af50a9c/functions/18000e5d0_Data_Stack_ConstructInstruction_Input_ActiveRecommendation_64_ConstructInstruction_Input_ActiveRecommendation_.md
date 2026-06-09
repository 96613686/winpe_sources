# Data::Stack::ConstructInstruction<Input::ActiveRecommendation,64>::~ConstructInstruction<Input::ActiveRecommendation,64>(void)

- ea: `0x18000e5d0`
- end: `0x18000e5df`
- name: `??1?$ConstructInstruction@VActiveRecommendation@Input@@$0EA@@Stack@Data@@QEAA@XZ`
- size: `15`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800bfea0`
- `0x1800bff20`
- `0x1800c0320`
- `0x1800c03f0`
- `0x1800c0460`
- `0x1800c0510`
- `0x1800c06b0`
- `0x1800c0790`
- `0x1800c07e0`
- `0x1800c0800`
- `0x1800c0830`
- `0x1800c0880`

## callees

- `0x18000f850`

## pseudocode

```c
__int64 __fastcall Data::Stack::ConstructInstruction<Input::ActiveRecommendation,64>::~ConstructInstruction<Input::ActiveRecommendation,64>(
        __int64 *a1)
{
  return Data::Stack::ConstructInstruction<Binary::IntegratedSelection::DerivativeServer<1,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>,64>::CallComplexSkill(a1);
}

```

## disassembly

```asm
0x18000e5d0  sub     rsp, 28h
0x18000e5d4  call    ?CallComplexSkill@?$ConstructInstruction@V?$DerivativeServer@$00$03$02V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@$0EA@@Stack@Data@@AEAAXXZ; Data::Stack::ConstructInstruction<Binary::IntegratedSelection::DerivativeServer<1,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>,64>::CallComplexSkill(void)
0x18000e5d9  nop
0x18000e5da  add     rsp, 28h
0x18000e5de  retn
```
