# CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::AddRef(void)

- ea: `0x1800022a0`
- end: `0x1800022ad`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCTimeSyncTaskHandler@@$00@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x1800022a0  mov     eax, 1
0x1800022a5  lock xadd [rcx+8], eax
0x1800022aa  inc     eax
0x1800022ac  retn
```
