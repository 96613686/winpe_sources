# ATL::AtlThrowImpl(long)

- ea: `0x140004e44`
- end: `0x140004e63`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140005bb8`
- `0x140005c44`
- `0x1400073c4`
- `0x1400074ec`
- `0x140008700`
- `0x140008828`
- `0x140008950`
- `0x1400089b8`
- `0x140008aa0`
- `0x140008b50`
- `0x14000b960`
- `0x1400106d8`
- `0x1400126b0`
- `0x140014e28`
- `0x1400166f4`
- `0x140016a44`

## callees

- `0x1400047bc`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x140004E62LL);
}

```

## disassembly

```asm
0x140004e44  sub     rsp, 28h
0x140004e48  cmp     ecx, 8007000Eh
0x140004e4e  mov     eax, 0C000001Dh
0x140004e53  mov     edx, 0C0000017h; unsigned int
0x140004e58  cmovz   eax, edx
0x140004e5b  mov     ecx, eax; unsigned int
0x140004e5d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
