# [thunk]:SecurityMitigationsBrokerStatics::GetRuntimeClassName`adjustor{8}' (HSTRING__ * *)

- ea: `0x180003cc0`
- end: `0x180003cc9`
- name: `?GetRuntimeClassName@SecurityMitigationsBrokerStatics@@W7EAAJPEAPEAUHSTRING__@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003ca0`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::GetRuntimeClassName(__int64 a1, HSTRING *a2)
{
  return SecurityMitigationsBrokerStatics::GetRuntimeClassName((SecurityMitigationsBrokerStatics *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x180003cc0  sub     rcx, 8; this
0x180003cc4  jmp     ?GetRuntimeClassName@SecurityMitigationsBrokerStatics@@UEAAJPEAPEAUHSTRING__@@@Z; SecurityMitigationsBrokerStatics::GetRuntimeClassName(HSTRING__ * *)
```
