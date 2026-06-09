# ATL::AtlHresultFromWin32(ulong)

- ea: `0x180004e28`
- end: `0x180004e38`
- name: `?AtlHresultFromWin32@ATL@@YAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000462c`
- `0x18000607c`

## callees

- `0x180004e28`

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
0x180004e28  test    ecx, ecx
0x180004e2a  jle     short loc_180004E35
0x180004e2c  movzx   ecx, cx
0x180004e2f  or      ecx, 80070000h
0x180004e35  mov     eax, ecx
0x180004e37  retn
```
