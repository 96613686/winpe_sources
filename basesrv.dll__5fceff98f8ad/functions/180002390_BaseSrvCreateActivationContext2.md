# BaseSrvCreateActivationContext2

- ea: `0x180002390`
- end: `0x1800023ad`
- name: `BaseSrvCreateActivationContext2`
- size: `29`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d90`

## callees

- `0x180002390`
- `0x18000e010`

## pseudocode

```c
__int64 BaseSrvCreateActivationContext2()
{
  if ( sxsFunctions )
    return (*(__int64 (**)(void))sxsFunctions)();
  else
    return 3221225659LL;
}

```

## disassembly

```asm
0x180002390  mov     rax, cs:sxsFunctions
0x180002397  test    rax, rax
0x18000239a  jz      short loc_1800023A6
0x18000239c  mov     rax, [rax]
0x18000239f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a4  retn
0x1800023a6  mov     eax, 0C00000BBh
0x1800023ab  jmp     short locret_1800023A4
```
