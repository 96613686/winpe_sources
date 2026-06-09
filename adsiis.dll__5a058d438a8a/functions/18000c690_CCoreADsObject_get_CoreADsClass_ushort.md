# CCoreADsObject::get_CoreADsClass(ushort * *)

- ea: `0x18000c690`
- end: `0x18000c6a4`
- name: `?get_CoreADsClass@CCoreADsObject@@QEAAJPEAPEAG@Z`
- size: `20`
- prototype: `__int64 __fastcall(CCoreADsObject *__hidden this, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180002510`
- `0x180003920`
- `0x180005a90`
- `0x180005e40`
- `0x180006090`
- `0x180006f60`
- `0x180007300`
- `0x1800102e0`

## callees

- `0x18000c690`
- `0x18001beb8`

## pseudocode

```c
__int64 __fastcall CCoreADsObject::get_CoreADsClass(CCoreADsObject *this, unsigned __int16 **a2)
{
  if ( a2 )
    return ADsAllocString(*((_QWORD *)this + 5), a2);
  else
    return 2147504136LL;
}

```

## disassembly

```asm
0x18000c690  test    rdx, rdx
0x18000c693  jnz     short loc_18000C69B
0x18000c695  mov     eax, 80005008h
0x18000c69a  retn
0x18000c69b  mov     rcx, [rcx+28h]
0x18000c69f  jmp     ADsAllocString
```
