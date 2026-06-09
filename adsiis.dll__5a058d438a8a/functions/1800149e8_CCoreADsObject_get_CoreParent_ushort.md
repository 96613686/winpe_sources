# CCoreADsObject::get_CoreParent(ushort * *)

- ea: `0x1800149e8`
- end: `0x1800149fc`
- name: `?get_CoreParent@CCoreADsObject@@QEAAJPEAPEAG@Z`
- size: `20`
- prototype: `__int64 __fastcall(CCoreADsObject *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002540`
- `0x1800039c0`

## callees

- `0x1800149e8`
- `0x18001beb8`

## pseudocode

```c
__int64 __fastcall CCoreADsObject::get_CoreParent(CCoreADsObject *this, unsigned __int16 **a2)
{
  if ( a2 )
    return ADsAllocString(*((_QWORD *)this + 4), a2);
  else
    return 2147504136LL;
}

```

## disassembly

```asm
0x1800149e8  test    rdx, rdx
0x1800149eb  jnz     short loc_1800149F3
0x1800149ed  mov     eax, 80005008h
0x1800149f2  retn
0x1800149f3  mov     rcx, [rcx+20h]
0x1800149f7  jmp     ADsAllocString
```
