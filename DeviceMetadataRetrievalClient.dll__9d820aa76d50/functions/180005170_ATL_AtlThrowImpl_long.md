# ATL::AtlThrowImpl(long)

- ea: `0x180005170`
- end: `0x18000518f`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800050b4`
- `0x180005a38`
- `0x180005f04`
- `0x1800061c8`
- `0x18000b64c`
- `0x18000b954`

## callees

- `0x18000bcbc`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x18000518ELL);
}

```

## disassembly

```asm
0x180005170  sub     rsp, 28h
0x180005174  cmp     ecx, 8007000Eh
0x18000517a  mov     eax, 0C000001Dh
0x18000517f  mov     edx, 0C0000017h; unsigned int
0x180005184  cmovz   eax, edx
0x180005187  mov     ecx, eax; unsigned int
0x180005189  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
