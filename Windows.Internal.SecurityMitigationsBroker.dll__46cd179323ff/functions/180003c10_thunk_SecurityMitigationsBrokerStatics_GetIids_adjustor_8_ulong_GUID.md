# [thunk]:SecurityMitigationsBrokerStatics::GetIids`adjustor{8}' (ulong *,_GUID * *)

- ea: `0x180003c10`
- end: `0x180003c19`
- name: `?GetIids@SecurityMitigationsBrokerStatics@@W7EAAJPEAKPEAPEAU_GUID@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003ba0`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::GetIids(__int64 a1, unsigned int *a2, struct _GUID **a3)
{
  return SecurityMitigationsBrokerStatics::GetIids((SecurityMitigationsBrokerStatics *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180003c10  sub     rcx, 8; this
0x180003c14  jmp     ?GetIids@SecurityMitigationsBrokerStatics@@UEAAJPEAKPEAPEAU_GUID@@@Z; SecurityMitigationsBrokerStatics::GetIids(ulong *,_GUID * *)
```
