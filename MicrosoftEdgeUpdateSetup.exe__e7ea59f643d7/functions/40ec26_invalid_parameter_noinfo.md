# __invalid_parameter_noinfo

- ea: `0x40ec26`
- end: `0x40ec36`
- name: `__invalid_parameter_noinfo`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `52`
- callee_count: `1`
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
- `0x40ef46`
- `0x40fece`
- `0x410359`
- `0x4104ce`
- `0x4118fe`
- `0x412722`
- `0x412ad9`
- `0x412fd0`
- `0x41312c`
- `0x4132a0`
- `0x41378e`
- `0x4138a7`
- `0x413c4a`
- `0x413d88`
- `0x414580`
- `0x414672`
- `0x414937`
- `0x414da1`
- `0x41692a`
- `0x4169a1`
- `0x417638`
- `0x41b167`

## callees

- `0x40ebc2`

## pseudocode

```c
void __cdecl _invalid_parameter_noinfo()
{
  _invalid_parameter(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x40ec26  xor     eax, eax
0x40ec28  push    eax; Reserved
0x40ec29  push    eax; LineNo
0x40ec2a  push    eax; FileName
0x40ec2b  push    eax; FunctionName
0x40ec2c  push    eax; Expression
0x40ec2d  call    __invalid_parameter
0x40ec32  add     esp, 14h
0x40ec35  retn
```
