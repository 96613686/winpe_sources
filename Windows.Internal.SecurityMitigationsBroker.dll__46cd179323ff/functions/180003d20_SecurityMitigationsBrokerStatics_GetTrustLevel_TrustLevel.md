# SecurityMitigationsBrokerStatics::GetTrustLevel(TrustLevel *)

- ea: `0x180003d20`
- end: `0x180003d29`
- name: `?GetTrustLevel@SecurityMitigationsBrokerStatics@@UEAAJPEAW4TrustLevel@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(SecurityMitigationsBrokerStatics *__hidden this, enum TrustLevel *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003d30`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::GetTrustLevel(
        SecurityMitigationsBrokerStatics *this,
        enum TrustLevel *a2)
{
  *a2 = PartialTrust;
  return 0;
}

```

## disassembly

```asm
0x180003d20  mov     dword ptr [rdx], 1
0x180003d26  xor     eax, eax
0x180003d28  retn
```
