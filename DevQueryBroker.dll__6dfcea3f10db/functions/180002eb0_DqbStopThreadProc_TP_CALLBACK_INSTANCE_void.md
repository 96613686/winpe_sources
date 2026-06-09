# DqbStopThreadProc(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180002eb0`
- end: `0x180002eb5`
- name: `?DqbStopThreadProc@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `5`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002c20`

## pseudocode

```c
// attributes: thunk
void __fastcall DqbStopThreadProc(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  DqbServiceStop();
}

```

## disassembly

```asm
0x180002eb0  jmp     ?DqbServiceStop@@YAXXZ; DqbServiceStop(void)
```
