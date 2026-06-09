# ATL::CSimpleStringT<char,0>::ThrowMemoryException(void)

- ea: `0x180006b4c`
- end: `0x180006b5b`
- name: `?ThrowMemoryException@?$CSimpleStringT@D$0A@@ATL@@KAXXZ`
- size: `15`
- prototype: `void __noreturn()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800060c0`
- `0x180006918`
- `0x180006dec`
- `0x180006e34`
- `0x18000708c`
- `0x1800070d4`

## callees

- `0x180002238`

## pseudocode

```c
void __noreturn ATL::CSimpleStringT<char,0>::ThrowMemoryException()
{
  ATL::AtlThrowImpl(-2147024882);
}

```

## disassembly

```asm
0x180006b4c  sub     rsp, 28h
0x180006b50  mov     ecx, 8007000Eh; int
0x180006b55  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
