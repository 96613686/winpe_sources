# CWinTaskHandler::AddRef(void)

- ea: `0x180004650`
- end: `0x18000465d`
- name: `?AddRef@CWinTaskHandler@@MEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::AddRef(CWinTaskHandler *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 8);
}

```

## disassembly

```asm
0x180004650  mov     eax, 1
0x180004655  lock xadd [rcx+20h], eax
0x18000465a  inc     eax
0x18000465c  retn
```
