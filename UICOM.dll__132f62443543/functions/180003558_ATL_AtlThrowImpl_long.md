# ATL::AtlThrowImpl(long)

- ea: `0x180003558`
- end: `0x180003577`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180002448`
- `0x1800026a4`
- `0x180002ba8`
- `0x180002bdc`
- `0x180002d14`
- `0x180002ebc`
- `0x180003378`
- `0x180003a94`
- `0x180004038`
- `0x1800041fc`

## callees

- `0x180004e44`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x180003576LL);
}

```

## disassembly

```asm
0x180003558  sub     rsp, 28h
0x18000355c  cmp     ecx, 8007000Eh
0x180003562  mov     eax, 0C000001Dh
0x180003567  mov     edx, 0C0000017h; unsigned int
0x18000356c  cmovz   eax, edx
0x18000356f  mov     ecx, eax; unsigned int
0x180003571  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
