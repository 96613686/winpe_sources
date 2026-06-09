# CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::AddRef(void)

- ea: `0x18000d990`
- end: `0x18000d99d`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCDrvRecoveryOnRebootHandler@@$00@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x18000d990  mov     eax, 1
0x18000d995  lock xadd [rcx+8], eax
0x18000d99a  inc     eax
0x18000d99c  retn
```
