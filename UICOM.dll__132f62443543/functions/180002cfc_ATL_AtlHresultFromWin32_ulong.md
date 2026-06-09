# ATL::AtlHresultFromWin32(ulong)

- ea: `0x180002cfc`
- end: `0x180002d0c`
- name: `?AtlHresultFromWin32@ATL@@YAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026a4`
- `0x1800041fc`

## callees

- `0x180002cfc`

## pseudocode

```c
__int64 __fastcall ATL::AtlHresultFromWin32(int a1)
{
  if ( a1 > 0 )
    return (unsigned __int16)a1 | 0x80070000;
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180002cfc  test    ecx, ecx
0x180002cfe  jle     short loc_180002D09
0x180002d00  movzx   ecx, cx
0x180002d03  or      ecx, 80070000h
0x180002d09  mov     eax, ecx
0x180002d0b  retn
```
