# Kerb3961::CipherPolicyImpl::CheckKeyUsage(Kerb3961::KeyUsage &)

- ea: `0x18000ba20`
- end: `0x18000baa5`
- name: `?CheckKeyUsage@CipherPolicyImpl@Kerb3961@@SA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEAW4KeyUsage@2@@Z`
- size: `133`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c580`
- `0x18000c710`
- `0x18000cbd0`
- `0x18000cd60`

## callees

- `0x180003a38`
- `0x18000a798`
- `0x18000ba20`
- `0x180011760`

## string_xrefs

- `0x18000ba98`: `Non test code is attempting to bypass policy`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::CipherPolicyImpl::CheckKeyUsage(_DWORD *a1, _QWORD *a2)
{
  const char *v3; // rdx
  _QWORD *v4; // r11
  char *v5; // rcx
  char v7; // [rsp+38h] [rbp+10h] BYREF
  char v8; // [rsp+39h] [rbp+11h]
  char v9; // [rsp+3Dh] [rbp+15h]

  if ( *a2 == 0x8000000000000000uLL && !Kerb3961::g_allowPolicyBypass )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"Non test code is attempting to bypass policy",
      (const unsigned __int16 *)0x8000000000000000LL);
  Kerb3961::GetScenarioForKeyUsage(&v7);
  if ( v9 )
  {
    if ( v8 == 6 )
    {
      *v4 = 0x8000000000000000uLL;
      *a1 = 0;
      return a1;
    }
    v5 = "keyScenario.usageOperations == KeyPolicyOperation::GssApi";
  }
  else
  {
    v5 = "scenarioOpt.has_value()";
  }
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v5, v3);
  *a1 = -1073741811;
  return a1;
}

```

## disassembly

```asm
0x18000ba20  mov     [rsp+arg_0], rbx
0x18000ba25  push    rsi
0x18000ba26  sub     rsp, 20h
0x18000ba2a  mov     r11, rdx
0x18000ba2d  mov     rsi, 8000000000000000h
0x18000ba37  mov     rdx, [rdx]; unsigned __int16 *
0x18000ba3a  mov     rbx, rcx
0x18000ba3d  cmp     rdx, rsi
0x18000ba40  jnz     short loc_18000BA4B
0x18000ba42  cmp     cs:?g_allowPolicyBypass@Kerb3961@@3_NA, 0; bool Kerb3961::g_allowPolicyBypass
0x18000ba49  jz      short loc_18000BA98
0x18000ba4b  lea     rcx, [rsp+28h+arg_8]
0x18000ba50  call    ?GetScenarioForKeyUsage@Kerb3961@@YA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@1@@Z; Kerb3961::GetScenarioForKeyUsage(Kerb3961::KeyUsage)
0x18000ba55  cmp     [rsp+28h+arg_D], 0
0x18000ba5a  jnz     short loc_18000BA70
0x18000ba5c  lea     rcx, aScenariooptHas; "scenarioOpt.has_value()"
0x18000ba63  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ba68  mov     dword ptr [rbx], 0C000000Dh
0x18000ba6e  jmp     short loc_18000BA89
0x18000ba70  cmp     [rsp+28h+arg_9], 6
0x18000ba75  jz      short loc_18000BA80
0x18000ba77  lea     rcx, aKeyscenarioUsa; "keyScenario.usageOperations == KeyPolic"...
0x18000ba7e  jmp     short loc_18000BA63
0x18000ba80  mov     [r11], rsi
0x18000ba83  mov     dword ptr [rbx], 0
0x18000ba89  mov     rax, rbx
0x18000ba8c  mov     rbx, [rsp+28h+arg_0]
0x18000ba91  add     rsp, 20h
0x18000ba95  pop     rsi
0x18000ba96  retn
0x18000ba98  lea     rcx, aNonTestCodeIsA; "Non test code is attempting to bypass p"...
0x18000ba9f  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
