# DpspGetScenarioExecutionLevel

- ea: `0x1800086d0`
- end: `0x1800086df`
- name: `DpspGetScenarioExecutionLevel`
- size: `15`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001830`
- `0x180002510`
- `0x180004de4`
- `0x18000c21c`
- `0x1800145f0`

## callees

- `0x1800086d0`

## pseudocode

```c
__int64 __fastcall DpspGetScenarioExecutionLevel(__int64 a1)
{
  if ( a1 )
    return (unsigned int)_InterlockedExchange((volatile __int32 *)(a1 + 40), *(_DWORD *)(a1 + 40));
  else
    return 0;
}

```

## disassembly

```asm
0x1800086d0  test    rcx, rcx
0x1800086d3  jz      short loc_1800086DC
0x1800086d5  mov     eax, [rcx+28h]
0x1800086d8  xchg    eax, [rcx+28h]
0x1800086db  retn
0x1800086dc  xor     eax, eax
0x1800086de  retn
```
