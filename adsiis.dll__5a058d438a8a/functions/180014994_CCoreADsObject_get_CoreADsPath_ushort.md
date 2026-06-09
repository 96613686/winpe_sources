# CCoreADsObject::get_CoreADsPath(ushort * *)

- ea: `0x180014994`
- end: `0x1800149a8`
- name: `?get_CoreADsPath@CCoreADsObject@@QEAAJPEAPEAG@Z`
- size: `20`
- prototype: `__int64 __fastcall(CCoreADsObject *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002500`
- `0x180003910`

## callees

- `0x180014994`
- `0x18001beb8`

## pseudocode

```c
__int64 __fastcall CCoreADsObject::get_CoreADsPath(CCoreADsObject *this, unsigned __int16 **a2)
{
  if ( a2 )
    return ADsAllocString(*((_QWORD *)this + 3), a2);
  else
    return 2147504136LL;
}

```

## disassembly

```asm
0x180014994  test    rdx, rdx
0x180014997  jnz     short loc_18001499F
0x180014999  mov     eax, 80005008h
0x18001499e  retn
0x18001499f  mov     rcx, [rcx+18h]
0x1800149a3  jmp     ADsAllocString
```
