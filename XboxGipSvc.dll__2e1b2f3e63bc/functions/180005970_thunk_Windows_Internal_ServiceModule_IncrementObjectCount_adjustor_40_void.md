# [thunk]:Windows::Internal::ServiceModule::IncrementObjectCount`adjustor{40}' (void)

- ea: `0x180005970`
- end: `0x180005979`
- name: `?IncrementObjectCount@ServiceModule@Internal@Windows@@WCI@EAAKXZ`
- size: `9`
- prototype: `ULONG()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005960`

## pseudocode

```c
ULONG Windows::Internal::ServiceModule::IncrementObjectCount()
{
  return Windows::Internal::ServiceModule::IncrementObjectCount();
}

```

## disassembly

```asm
0x180005970  sub     rcx, 28h ; '('
0x180005974  jmp     ?IncrementObjectCount@ServiceModule@Internal@Windows@@UEAAKXZ; Windows::Internal::ServiceModule::IncrementObjectCount(void)
```
