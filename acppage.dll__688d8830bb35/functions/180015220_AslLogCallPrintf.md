# AslLogCallPrintf

- ea: `0x180015220`
- end: `0x180015251`
- name: `AslLogCallPrintf`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d10`
- `0x18001101c`
- `0x18001123c`
- `0x180011640`
- `0x1800119a0`
- `0x180011b28`
- `0x180011c84`
- `0x180011d60`
- `0x180011e94`
- `0x18001207c`
- `0x180012224`
- `0x1800137e0`
- `0x180014b84`
- `0x180014d54`
- `0x180014f6c`
- `0x18001551c`
- `0x1800156e8`
- `0x18001590c`
- `0x1800159a4`
- `0x180015a4c`
- `0x180015ce0`

## callees

- `0x180015220`
- `0x180017010`

## pseudocode

```c
__int64 (__fastcall *__fastcall AslLogCallPrintf(__int64 a1))(_QWORD)
{
  __int64 (__fastcall *result)(_QWORD); // rax

  result = g_AslLogPfnVPrintf;
  if ( g_AslLogPfnVPrintf )
    return (__int64 (__fastcall *)(_QWORD))g_AslLogPfnVPrintf(a1);
  return result;
}

```

## disassembly

```asm
0x180015220  mov     r11, rsp
0x180015223  mov     [r11+20h], r9
0x180015227  sub     rsp, 48h
0x18001522b  mov     rax, cs:g_AslLogPfnVPrintf
0x180015232  mov     qword ptr [r11-18h], 0
0x18001523a  test    rax, rax
0x18001523d  jz      short loc_18001524C
0x18001523f  lea     r10, [r11+28h]
0x180015243  mov     [r11-28h], r10
0x180015247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001524c  add     rsp, 48h
0x180015250  retn
```
