# [thunk]:SecurityMitigationsBrokerStatics::Release`adjustor{8}' (void)

- ea: `0x180003f80`
- end: `0x180003f89`
- name: `?Release@SecurityMitigationsBrokerStatics@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003f70`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::Release(__int64 a1, __int64 a2)
{
  return SecurityMitigationsBrokerStatics::Release(a1 - 8, a2);
}

```

## disassembly

```asm
0x180003f80  sub     rcx, 8; this
0x180003f84  jmp     ?Release@SecurityMitigationsBrokerStatics@@UEAAKXZ; SecurityMitigationsBrokerStatics::Release(void)
```
