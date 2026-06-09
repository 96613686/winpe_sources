# CMimeType::get_Extension(ushort * *)

- ea: `0x18000dfe0`
- end: `0x18000dff4`
- name: `?get_Extension@CMimeType@@UEAAJPEAPEAG@Z`
- size: `20`
- prototype: `__int64 __fastcall(CMimeType *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000dfe0`
- `0x18001beb8`

## pseudocode

```c
__int64 __fastcall CMimeType::get_Extension(CMimeType *this, unsigned __int16 **a2)
{
  if ( a2 )
    return ADsAllocString(*((_QWORD *)this + 4), a2);
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x18000dfe0  test    rdx, rdx
0x18000dfe3  jnz     short loc_18000DFEB
0x18000dfe5  mov     eax, 80004003h
0x18000dfea  retn
0x18000dfeb  mov     rcx, [rcx+20h]
0x18000dfef  jmp     ADsAllocString
```
