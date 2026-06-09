# SecurityMitigationsBrokerStatics::InternalGetTrustLevelStatic(void)

- ea: `0x180003d70`
- end: `0x180003d76`
- name: `?InternalGetTrustLevelStatic@SecurityMitigationsBrokerStatics@@SA?AW4TrustLevel@@XZ`
- size: `6`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 SecurityMitigationsBrokerStatics::InternalGetTrustLevelStatic(void)
{
  return 1;
}

```

## disassembly

```asm
0x180003d70  mov     eax, 1
0x180003d75  retn
```
