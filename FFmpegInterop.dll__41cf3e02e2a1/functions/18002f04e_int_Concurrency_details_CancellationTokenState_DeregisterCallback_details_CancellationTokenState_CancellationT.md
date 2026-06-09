# int `Concurrency::details::_CancellationTokenState::_DeregisterCallback(details::_CancellationTokenState::_CancellationTokenRegistration *)'::`1'::dtor$0

- ea: `0x18002f04e`
- end: `0x18002f05a`
- name: `?dtor$0@?0??_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002ea22`

## pseudocode

```c
volatile signed __int64 *__fastcall `Concurrency::details::_CancellationTokenState::_DeregisterCallback'::`1'::dtor$0(
        __int64 a1,
        __int64 a2)
{
  volatile signed __int64 *result; // rax

  result = *(volatile signed __int64 **)(a2 + 40);
  _InterlockedDecrement64(result);
  return result;
}

```

## disassembly

```asm
0x18002f04e  lea     rcx, [rdx+28h]
0x18002f055  jmp     loc_180006C24
0x180006c24  mov     rax, [rcx]
0x180006c27  lock dec qword ptr [rax]
0x180006c2b  retn
```
