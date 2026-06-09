# CWinTaskHandler::AddRef(void)

- ea: `0x1800022c0`
- end: `0x1800022cd`
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
0x1800022c0  mov     eax, 1
0x1800022c5  lock xadd [rcx+20h], eax
0x1800022ca  inc     eax
0x1800022cc  retn
```
