# CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::AddRef(void)

- ea: `0x1800040c0`
- end: `0x1800040cd`
- name: `?AddRef@?$CWinTaskClassFactoryT@VSetupRecoveryTaskHandler@@$00@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x1800040c0  mov     eax, 1
0x1800040c5  lock xadd [rcx+8], eax
0x1800040ca  inc     eax
0x1800040cc  retn
```
