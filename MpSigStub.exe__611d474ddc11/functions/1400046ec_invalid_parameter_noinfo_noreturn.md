# _invalid_parameter_noinfo_noreturn

- ea: `0x1400046ec`
- end: `0x14000471b`
- name: `_invalid_parameter_noinfo_noreturn`
- size: `47`
- prototype: `void __cdecl __noreturn()`
- caller_count: `50`
- callee_count: `2`
- tags: ``

## callers

- `0x1400251e8`
- `0x140025810`
- `0x140025874`
- `0x14002595c`
- `0x1400259b8`
- `0x140026868`
- `0x140026df0`
- `0x1400320b4`
- `0x14003221c`
- `0x140032378`
- `0x1400325b4`
- `0x1400327fc`
- `0x140032860`
- `0x1400328ec`
- `0x140032998`
- `0x140032a0c`
- `0x140034314`
- `0x1400343d8`
- `0x14003441c`
- `0x140034460`
- `0x140035ad0`
- `0x140037108`
- `0x140043d0c`
- `0x140043ec0`
- `0x14004418c`
- `0x1400443b8`
- `0x1400464e8`
- `0x140046618`
- `0x140046670`
- `0x140046ad4`
- `0x140046d50`
- `0x140046e3c`
- `0x140047254`
- `0x140047558`
- `0x14004792c`
- `0x140047d5c`
- `0x140048054`
- `0x140048628`
- `0x1400489fc`
- `0x1400499b0`
- `0x140049ce8`
- `0x14004a1bc`
- `0x14004ab84`
- `0x14004acf0`
- `0x14004afc0`
- `0x14004b7f8`
- `0x14004b968`
- `0x14004d864`
- `0x1400a30d0`
- `0x1400a4200`

## callees

- `0x140004578`
- `0x14000471c`

## pseudocode

```c
void __cdecl __noreturn invalid_parameter_noinfo_noreturn()
{
  invalid_parameter(0, 0, 0, 0, 0);
  invoke_watson(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x1400046ec  sub     rsp, 38h
0x1400046f0  and     [rsp+38h+var_18], 0
0x1400046f6  xor     r9d, r9d; int
0x1400046f9  xor     r8d, r8d; int
0x1400046fc  xor     edx, edx; int
0x1400046fe  xor     ecx, ecx; int
0x140004700  call    _invalid_parameter
0x140004705  and     [rsp+38h+var_18], 0
0x14000470b  xor     r9d, r9d; LineNo
0x14000470e  xor     r8d, r8d; FileName
0x140004711  xor     edx, edx; FunctionName
0x140004713  xor     ecx, ecx; Expression
0x140004715  call    _invoke_watson
```
