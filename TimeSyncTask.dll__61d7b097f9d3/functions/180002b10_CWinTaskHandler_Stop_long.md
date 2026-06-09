# CWinTaskHandler::Stop(long *)

- ea: `0x180002b10`
- end: `0x180002b1c`
- name: `?Stop@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::Stop(CWinTaskHandler *this, int *a2)
{
  return (*(__int64 (__fastcall **)(CWinTaskHandler *, int *))(*(_QWORD *)this + 80LL))(this, a2);
}

```

## disassembly

```asm
0x180002b10  mov     rax, [rcx]
0x180002b13  mov     rax, [rax+50h]
0x180002b17  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
