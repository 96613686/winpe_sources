# int `Concurrency::details::_CancellationTokenState::_DeregisterCallback(details::_CancellationTokenState::_CancellationTokenRegistration *)'::`1'::dtor$1

- ea: `0x18002f05a`
- end: `0x18002f066`
- name: `?dtor$1@?0??_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003ef0`

## pseudocode

```c
__int64 __fastcall `Concurrency::details::_CancellationTokenState::_DeregisterCallback'::`1'::dtor$1(
        __int64 a1,
        __int64 a2)
{
  return sub_180003EF0((_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x18002f05a  lea     rcx, [rdx+60h]
0x18002f061  jmp     sub_180003EF0
```
