# ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)

- ea: `0x18000bf30`
- end: `0x18000bf3f`
- name: `?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ`
- size: `15`
- prototype: `void __noreturn()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a6c0`
- `0x18000acf0`
- `0x18000ad7c`
- `0x18000b754`
- `0x18000bd68`

## callees

- `0x180006a80`

## pseudocode

```c
void __noreturn ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException()
{
  ATL::AtlThrowImpl(-2147024882);
}

```

## disassembly

```asm
0x18000bf30  sub     rsp, 28h
0x18000bf34  mov     ecx, 8007000Eh; int
0x18000bf39  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
