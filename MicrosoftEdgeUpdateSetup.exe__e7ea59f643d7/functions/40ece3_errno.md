# __errno

- ea: `0x40ece3`
- end: `0x40ecf6`
- name: `__errno`
- size: `19`
- prototype: `int *__cdecl()`
- caller_count: `75`
- callee_count: `2`
- tags: ``

## callers

- `0x40111b`
- `0x4039b7`
- `0x403c95`
- `0x403e90`
- `0x404d09`
- `0x40539c`
- `0x4061f3`
- `0x40b2d7`
- `0x40bb92`
- `0x40bc97`
- `0x40bd00`
- `0x40c1f0`
- `0x40c2b1`
- `0x40c35a`
- `0x40c4e1`
- `0x40c668`
- `0x40c713`
- `0x40c790`
- `0x40cc85`
- `0x40ccfb`
- `0x40ce23`
- `0x40cf7c`
- `0x40cfdd`
- `0x40d693`
- `0x40d7e8`
- `0x40d94d`
- `0x40d968`
- `0x40db46`
- `0x40dd69`
- `0x40e371`
- `0x40e39a`
- `0x40ecad`
- `0x40ecf6`
- `0x40ed53`
- `0x40eda8`
- `0x40ee5a`
- `0x40ef46`
- `0x40f5c2`
- `0x40f689`
- `0x40fac9`
- `0x40fece`
- `0x410359`
- `0x41043d`
- `0x4104ce`
- `0x4109f3`
- `0x411621`
- `0x4118fe`
- `0x412467`
- `0x412722`
- `0x412ad9`

## callees

- `0x40e970`
- `0x40ece3`

## pseudocode

```c
int *__cdecl _errno()
{
  char *v0; // eax

  v0 = (char *)__acrt_getptd_noexit();
  if ( v0 )
    return (int *)(v0 + 16);
  else
    return &dword_426054;
}

```

## disassembly

```asm
0x40ece3  call    ___acrt_getptd_noexit
0x40ece8  test    eax, eax
0x40ecea  jnz     short loc_40ECF2
0x40ecec  mov     eax, offset dword_426054
0x40ecf1  retn
0x40ecf2  add     eax, 10h
0x40ecf5  retn
```
