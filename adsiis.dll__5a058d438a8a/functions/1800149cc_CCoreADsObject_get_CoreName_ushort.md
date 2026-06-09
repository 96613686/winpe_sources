# CCoreADsObject::get_CoreName(ushort * *)

- ea: `0x1800149cc`
- end: `0x1800149e0`
- name: `?get_CoreName@CCoreADsObject@@QEAAJPEAPEAG@Z`
- size: `20`
- prototype: `__int64 __fastcall(CCoreADsObject *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002530`
- `0x1800039b0`

## callees

- `0x1800149cc`
- `0x18001beb8`

## pseudocode

```c
__int64 __fastcall CCoreADsObject::get_CoreName(CCoreADsObject *this, unsigned __int16 **a2)
{
  if ( a2 )
    return ADsAllocString(*((_QWORD *)this + 2), a2);
  else
    return 2147504136LL;
}

```

## disassembly

```asm
0x1800149cc  test    rdx, rdx
0x1800149cf  jnz     short loc_1800149D7
0x1800149d1  mov     eax, 80005008h
0x1800149d6  retn
0x1800149d7  mov     rcx, [rcx+10h]
0x1800149db  jmp     ADsAllocString
```
