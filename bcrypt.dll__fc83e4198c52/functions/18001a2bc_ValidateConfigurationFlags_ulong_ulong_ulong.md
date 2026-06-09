# ValidateConfigurationFlags(ulong,ulong,ulong)

- ea: `0x18001a2bc`
- end: `0x18001a2f3`
- name: `?ValidateConfigurationFlags@@YAHKKK@Z`
- size: `55`
- prototype: `_BOOL8 __fastcall(int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000283c`

## callees

- `0x18001a2bc`

## pseudocode

```c
_BOOL8 __fastcall ValidateConfigurationFlags(int a1, int a2, int a3)
{
  int v3; // eax

  if ( a1 == 65552 )
  {
    v3 = 65537;
    if ( a2 != 2 )
      v3 = 1;
  }
  else
  {
    v3 = a1 == 65584;
  }
  return (~v3 & a3) == 0;
}

```

## disassembly

```asm
0x18001a2bc  mov     r9d, ecx
0x18001a2bf  cmp     ecx, 10010h
0x18001a2c5  mov     ecx, 1
0x18001a2ca  jnz     short loc_18001A2D9
0x18001a2cc  cmp     edx, 2
0x18001a2cf  mov     eax, 10001h
0x18001a2d4  cmovnz  eax, ecx
0x18001a2d7  jmp     short loc_18001A2E5
0x18001a2d9  xor     eax, eax
0x18001a2db  cmp     r9d, 10030h
0x18001a2e2  cmovz   eax, ecx
0x18001a2e5  not     eax
0x18001a2e7  test    r8d, eax
0x18001a2ea  mov     eax, 0
0x18001a2ef  setz    al
0x18001a2f2  retn
```
