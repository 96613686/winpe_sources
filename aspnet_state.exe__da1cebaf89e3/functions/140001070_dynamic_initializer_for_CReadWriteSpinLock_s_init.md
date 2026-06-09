# _dynamic_initializer_for__CReadWriteSpinLock::s_init__

- ea: `0x140001070`
- end: `0x140001084`
- name: `_dynamic_initializer_for__CReadWriteSpinLock::s_init__`
- size: `20`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005394`

## pseudocode

```c
__int64 dynamic_initializer_for__CReadWriteSpinLock::s_init__()
{
  __int64 result; // rax

  result = CReadWriteSpinLock::StaticInit();
  CReadWriteSpinLock::s_init = result;
  return result;
}

```

## disassembly

```asm
0x140001070  sub     rsp, 28h
0x140001074  call    ?StaticInit@CReadWriteSpinLock@@SAHXZ; CReadWriteSpinLock::StaticInit(void)
0x140001079  mov     cs:?s_init@CReadWriteSpinLock@@0HA, eax; int CReadWriteSpinLock::s_init
0x14000107f  add     rsp, 28h
0x140001083  retn
```
