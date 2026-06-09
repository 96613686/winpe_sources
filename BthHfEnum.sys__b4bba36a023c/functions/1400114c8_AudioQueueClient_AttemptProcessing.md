# AudioQueueClient_AttemptProcessing

- ea: `0x1400114c8`
- end: `0x1400114d7`
- name: `AudioQueueClient_AttemptProcessing`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002d280`
- `0x14002d320`

## callees

- `0x140010eb0`

## pseudocode

```c
void __fastcall AudioQueueClient_AttemptProcessing(struct WDFQUEUE__ *a1)
{
  ScoStreamProcessDataQueue(a1);
}

```

## disassembly

```asm
0x1400114c8  sub     rsp, 28h
0x1400114cc  call    ?ScoStreamProcessDataQueue@@YAXPEAUWDFQUEUE__@@@Z; ScoStreamProcessDataQueue(WDFQUEUE__ *)
0x1400114d1  add     rsp, 28h
0x1400114d5  retn
```
