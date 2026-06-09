# ATL::AtlThrowImpl(long)

- ea: `0x180006df4`
- end: `0x180006e13`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180006468`
- `0x180006784`
- `0x180006c88`
- `0x180006cbc`
- `0x180008ecc`
- `0x1800096c8`
- `0x180009884`

## callees

- `0x18000b5c4`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x180006E12LL);
}

```

## disassembly

```asm
0x180006df4  sub     rsp, 28h
0x180006df8  cmp     ecx, 8007000Eh
0x180006dfe  mov     eax, 0C000001Dh
0x180006e03  mov     edx, 0C0000017h; unsigned int
0x180006e08  cmovz   eax, edx
0x180006e0b  mov     ecx, eax; unsigned int
0x180006e0d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
