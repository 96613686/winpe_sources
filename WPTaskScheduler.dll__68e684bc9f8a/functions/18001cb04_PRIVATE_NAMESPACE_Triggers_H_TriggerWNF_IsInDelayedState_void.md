# PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::IsInDelayedState(void)

- ea: `0x18001cb04`
- end: `0x18001cb23`
- name: `?IsInDelayedState@TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@AEAAHXZ`
- size: `31`
- prototype: `BOOL __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerWNF *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009360`

## callees

- `0x18001cb04`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001cb19`

## pseudocode

```c
BOOL __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::IsInDelayedState(
        PRIVATE_NAMESPACE_Triggers_H::TriggerWNF *this)
{
  struct _TP_TIMER *v1; // rcx

  return *((_DWORD *)this + 58) && (v1 = (struct _TP_TIMER *)*((_QWORD *)this + 32)) != 0 && IsThreadpoolTimerSet(v1);
}

```

## disassembly

```asm
0x18001cb04  cmp     dword ptr [rcx+0E8h], 0
0x18001cb0b  jbe     short loc_18001CB20
0x18001cb0d  mov     rcx, [rcx+100h]
0x18001cb14  test    rcx, rcx
0x18001cb17  jz      short loc_18001CB20
0x18001cb19  jmp     cs:__imp_IsThreadpoolTimerSet
0x18001cb20  xor     eax, eax
0x18001cb22  retn
```
