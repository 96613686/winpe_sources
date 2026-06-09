# DdcTaskStateHandlerDesktop::AddRef(void)

- ea: `0x1800022d0`
- end: `0x1800022dd`
- name: `?AddRef@DdcTaskStateHandlerDesktop@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(DdcTaskStateHandlerDesktop *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall DdcTaskStateHandlerDesktop::AddRef(DdcTaskStateHandlerDesktop *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x1800022d0  mov     eax, 1
0x1800022d5  lock xadd [rcx+8], eax
0x1800022da  inc     eax
0x1800022dc  retn
```
