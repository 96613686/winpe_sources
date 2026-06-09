# CWinTaskHandler::Stop(long *)

- ea: `0x180009590`
- end: `0x18000959c`
- name: `?Stop@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::Stop(CWinTaskHandler *this, int *a2)
{
  return (*(__int64 (__fastcall **)(CWinTaskHandler *, int *))(*(_QWORD *)this + 80LL))(this, a2);
}

```

## disassembly

```asm
0x180009590  mov     rax, [rcx]
0x180009593  mov     rax, [rax+50h]
0x180009597  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
