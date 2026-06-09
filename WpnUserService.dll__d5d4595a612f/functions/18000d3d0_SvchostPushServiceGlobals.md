# SvchostPushServiceGlobals

- ea: `0x18000d3d0`
- end: `0x18000d3d8`
- name: `SvchostPushServiceGlobals`
- size: `8`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(__int64 a1)
{
  *(_QWORD *)&xmmword_180019240 = a1;
}

```

## disassembly

```asm
0x18000d3d0  mov     qword ptr cs:xmmword_180019240, rcx
0x18000d3d7  retn
```
