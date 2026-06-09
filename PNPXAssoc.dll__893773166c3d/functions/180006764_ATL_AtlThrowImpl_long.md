# ATL::AtlThrowImpl(long)

- ea: `0x180006764`
- end: `0x180006783`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800056c8`
- `0x180005b14`
- `0x180006018`
- `0x18000604c`
- `0x1800062a8`
- `0x18000729c`
- `0x180007a88`
- `0x180007c4c`

## callees

- `0x180008f7c`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x180006782LL);
}

```

## disassembly

```asm
0x180006764  sub     rsp, 28h
0x180006768  cmp     ecx, 8007000Eh
0x18000676e  mov     eax, 0C000001Dh
0x180006773  mov     edx, 0C0000017h; unsigned int
0x180006778  cmovz   eax, edx
0x18000677b  mov     ecx, eax; unsigned int
0x18000677d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
