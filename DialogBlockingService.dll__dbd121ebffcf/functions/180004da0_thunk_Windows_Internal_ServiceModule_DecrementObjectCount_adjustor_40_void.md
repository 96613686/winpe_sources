# [thunk]:Windows::Internal::ServiceModule::DecrementObjectCount`adjustor{40}' (void)

- ea: `0x180004da0`
- end: `0x180004da9`
- name: `?DecrementObjectCount@ServiceModule@Internal@Windows@@WCI@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180004d50`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModule::DecrementObjectCount(__int64 a1)
{
  return Windows::Internal::ServiceModule::DecrementObjectCount((Windows::Internal::ServiceModule *)(a1 - 40));
}

```

## disassembly

```asm
0x180004da0  sub     rcx, 28h ; '('; this
0x180004da4  jmp     ?DecrementObjectCount@ServiceModule@Internal@Windows@@UEAAKXZ; Windows::Internal::ServiceModule::DecrementObjectCount(void)
```
