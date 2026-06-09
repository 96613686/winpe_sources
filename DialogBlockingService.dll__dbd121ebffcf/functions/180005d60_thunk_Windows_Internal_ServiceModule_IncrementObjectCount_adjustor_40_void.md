# [thunk]:Windows::Internal::ServiceModule::IncrementObjectCount`adjustor{40}' (void)

- ea: `0x180005d60`
- end: `0x180005d69`
- name: `?IncrementObjectCount@ServiceModule@Internal@Windows@@WCI@EAAKXZ`
- size: `9`
- prototype: `ULONG()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005d50`

## pseudocode

```c
ULONG Windows::Internal::ServiceModule::IncrementObjectCount()
{
  return Windows::Internal::ServiceModule::IncrementObjectCount();
}

```

## disassembly

```asm
0x180005d60  sub     rcx, 28h ; '('
0x180005d64  jmp     ?IncrementObjectCount@ServiceModule@Internal@Windows@@UEAAKXZ; Windows::Internal::ServiceModule::IncrementObjectCount(void)
```
