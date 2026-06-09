# CCoreADsObject::get_CoreGUID(ushort * *)

- ea: `0x1800149b0`
- end: `0x1800149c4`
- name: `?get_CoreGUID@CCoreADsObject@@QEAAJPEAPEAG@Z`
- size: `20`
- prototype: `__int64 __fastcall(CCoreADsObject *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002520`
- `0x1800039a0`

## callees

- `0x1800149b0`
- `0x18001beb8`

## pseudocode

```c
__int64 __fastcall CCoreADsObject::get_CoreGUID(CCoreADsObject *this, unsigned __int16 **a2)
{
  if ( a2 )
    return ADsAllocString(*((_QWORD *)this + 6), a2);
  else
    return 2147504136LL;
}

```

## disassembly

```asm
0x1800149b0  test    rdx, rdx
0x1800149b3  jnz     short loc_1800149BB
0x1800149b5  mov     eax, 80005008h
0x1800149ba  retn
0x1800149bb  mov     rcx, [rcx+30h]
0x1800149bf  jmp     ADsAllocString
```
