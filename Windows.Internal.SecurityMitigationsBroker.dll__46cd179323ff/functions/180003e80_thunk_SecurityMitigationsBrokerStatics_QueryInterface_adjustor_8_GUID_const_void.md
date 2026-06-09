# [thunk]:SecurityMitigationsBrokerStatics::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180003e80`
- end: `0x180003e89`
- name: `?QueryInterface@SecurityMitigationsBrokerStatics@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003e70`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::QueryInterface(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  return SecurityMitigationsBrokerStatics::QueryInterface(a1 - 8, a2, a3);
}

```

## disassembly

```asm
0x180003e80  sub     rcx, 8; this
0x180003e84  jmp     ?QueryInterface@SecurityMitigationsBrokerStatics@@UEAAJAEBU_GUID@@PEAPEAX@Z; SecurityMitigationsBrokerStatics::QueryInterface(_GUID const &,void * *)
```
