# __invalid_parameter_noinfo

- ea: `0x40de54`
- end: `0x40de64`
- name: `__invalid_parameter_noinfo`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x40e4a7`
- `0x40eda9`
- `0x40ee87`
- `0x40eef0`
- `0x40f400`
- `0x40f4c0`
- `0x40fdf6`
- `0x40fe5a`
- `0x410078`
- `0x410cee`
- `0x411024`
- `0x411199`
- `0x4121f6`
- `0x412f99`
- `0x412fe0`
- `0x4135ea`
- `0x413728`
- `0x413f20`
- `0x414012`
- `0x4142d7`
- `0x4146bc`
- `0x414733`
- `0x414d28`

## callees

- `0x40ddf0`

## pseudocode

```c
void __cdecl _invalid_parameter_noinfo()
{
  _invalid_parameter(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x40de54  xor     eax, eax
0x40de56  push    eax; Reserved
0x40de57  push    eax; LineNo
0x40de58  push    eax; FileName
0x40de59  push    eax; FunctionName
0x40de5a  push    eax; Expression
0x40de5b  call    __invalid_parameter
0x40de60  add     esp, 14h
0x40de63  retn
```
