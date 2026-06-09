# [thunk]:SecurityMitigationsBrokerStatics::GetTrustLevel`adjustor{8}' (TrustLevel *)

- ea: `0x180003d30`
- end: `0x180003d39`
- name: `?GetTrustLevel@SecurityMitigationsBrokerStatics@@W7EAAJPEAW4TrustLevel@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003d20`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::GetTrustLevel(__int64 a1, enum TrustLevel *a2)
{
  return SecurityMitigationsBrokerStatics::GetTrustLevel((SecurityMitigationsBrokerStatics *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x180003d30  sub     rcx, 8; this
0x180003d34  jmp     ?GetTrustLevel@SecurityMitigationsBrokerStatics@@UEAAJPEAW4TrustLevel@@@Z; SecurityMitigationsBrokerStatics::GetTrustLevel(TrustLevel *)
```
