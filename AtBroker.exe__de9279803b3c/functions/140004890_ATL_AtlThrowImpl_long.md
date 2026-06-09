# ATL::AtlThrowImpl(long)

- ea: `0x140004890`
- end: `0x1400048af`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ea0`
- `0x140006d0c`
- `0x140009e84`
- `0x14000bf04`
- `0x14000c108`
- `0x14000c340`
- `0x14000c7e0`
- `0x14000c864`
- `0x14000c8b4`
- `0x14000cb50`
- `0x14000ced0`
- `0x14000d118`
- `0x14000e538`
- `0x14000ea38`
- `0x14000f5dc`
- `0x14000f9c0`
- `0x140010c6c`
- `0x140010e44`
- `0x140011204`
- `0x1400116c4`

## callees

- `0x14000a74c`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x1400048AELL);
}

```

## disassembly

```asm
0x140004890  sub     rsp, 28h
0x140004894  cmp     ecx, 8007000Eh
0x14000489a  mov     eax, 0C000001Dh
0x14000489f  mov     edx, 0C0000017h; unsigned int
0x1400048a4  cmovz   eax, edx
0x1400048a7  mov     ecx, eax; unsigned int
0x1400048a9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
