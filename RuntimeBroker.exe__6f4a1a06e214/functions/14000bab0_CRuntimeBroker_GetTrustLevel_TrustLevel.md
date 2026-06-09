# CRuntimeBroker::GetTrustLevel(TrustLevel *)

- ea: `0x14000bab0`
- end: `0x14000bab9`
- name: `?GetTrustLevel@CRuntimeBroker@@UEAAJPEAW4TrustLevel@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(CRuntimeBroker *__hidden this, enum TrustLevel *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::GetTrustLevel(CRuntimeBroker *this, enum TrustLevel *a2)
{
  *a2 = PartialTrust;
  return 0;
}

```

## disassembly

```asm
0x14000bab0  mov     dword ptr [rdx], 1
0x14000bab6  xor     eax, eax
0x14000bab8  retn
```
