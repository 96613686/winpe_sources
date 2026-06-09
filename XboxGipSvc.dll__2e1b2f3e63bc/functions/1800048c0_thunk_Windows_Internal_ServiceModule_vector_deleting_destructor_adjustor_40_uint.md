# [thunk]:Windows::Internal::ServiceModule::`vector deleting destructor'`adjustor{40}' (uint)

- ea: `0x1800048c0`
- end: `0x1800048c9`
- name: `??_EServiceModule@Internal@Windows@@WCI@EAAPEAXI@Z`
- size: `9`
- prototype: `Windows::Internal::ServiceModule *__fastcall(__int64, __int64, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180004b74`

## pseudocode

```c
Windows::Internal::ServiceModule *__fastcall Windows::Internal::ServiceModule::`vector deleting destructor'(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  return Windows::Internal::ServiceModule::`vector deleting destructor'(
           (Windows::Internal::ServiceModule *)(a1 - 40),
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x1800048c0  sub     rcx, 28h ; '('; this
0x1800048c4  jmp     ??_EServiceModule@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::ServiceModule::`vector deleting destructor'(uint)
```
