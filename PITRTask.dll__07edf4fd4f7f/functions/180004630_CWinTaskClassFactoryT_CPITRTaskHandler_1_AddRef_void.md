# CWinTaskClassFactoryT<CPITRTaskHandler,1>::AddRef(void)

- ea: `0x180004630`
- end: `0x18000463d`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCPITRTaskHandler@@$00@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPITRTaskHandler,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x180004630  mov     eax, 1
0x180004635  lock xadd [rcx+8], eax
0x18000463a  inc     eax
0x18000463c  retn
```
