# __invalid_parameter_noinfo_noreturn

- ea: `0x40de64`
- end: `0x40de81`
- name: `__invalid_parameter_noinfo_noreturn`
- size: `29`
- prototype: `void __cdecl __noreturn()`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x407fd4`
- `0x4086d2`
- `0x4087ac`
- `0x4098ae`
- `0x40a8af`
- `0x40a8db`

## callees

- `0x40ddf0`
- `0x40de81`

## pseudocode

```c
void __cdecl __noreturn _invalid_parameter_noinfo_noreturn()
{
  _invalid_parameter(0, 0, 0, 0, 0);
  _invoke_watson(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x40de64  mov     edi, edi
0x40de66  push    esi
0x40de67  xor     esi, esi
0x40de69  push    esi; Reserved
0x40de6a  push    esi; LineNo
0x40de6b  push    esi; FileName
0x40de6c  push    esi; FunctionName
0x40de6d  push    esi; Expression
0x40de6e  call    __invalid_parameter
0x40de73  add     esp, 14h
0x40de76  push    esi; Reserved
0x40de77  push    esi; LineNo
0x40de78  push    esi; FileName
0x40de79  push    esi; FunctionName
0x40de7a  push    esi; Expression
0x40de7b  call    __invoke_watson
```
