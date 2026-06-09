# CWinTaskHandler::Stop(long *)

- ea: `0x180005150`
- end: `0x18000515c`
- name: `?Stop@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180018010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::Stop(CWinTaskHandler *this, int *a2)
{
  return (*(__int64 (__fastcall **)(CWinTaskHandler *, int *))(*(_QWORD *)this + 80LL))(this, a2);
}

```

## disassembly

```asm
0x180005150  mov     rax, [rcx]
0x180005153  mov     rax, [rax+50h]
0x180005157  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
