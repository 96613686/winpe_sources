# _invalid_parameter_noinfo

- ea: `0x140006544`
- end: `0x140006562`
- name: `_invalid_parameter_noinfo`
- size: `30`
- prototype: `void __cdecl()`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x140004948`
- `0x1400051c4`
- `0x140005300`
- `0x140005380`
- `0x1400059a0`
- `0x1400065b0`
- `0x140006640`
- `0x1400069b4`
- `0x140006fe0`
- `0x1400083c0`
- `0x140008574`
- `0x140009c94`
- `0x14000aa1c`
- `0x14000aa50`
- `0x14000b1e0`
- `0x14000b490`
- `0x14000b5e8`
- `0x14000c3f0`

## callees

- `0x1400063f0`

## pseudocode

```c
void __cdecl invalid_parameter_noinfo()
{
  invalid_parameter(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x140006544  sub     rsp, 38h
0x140006548  and     [rsp+38h+var_18], 0
0x14000654e  xor     r9d, r9d; int
0x140006551  xor     r8d, r8d; int
0x140006554  xor     edx, edx; int
0x140006556  xor     ecx, ecx; int
0x140006558  call    _invalid_parameter
0x14000655d  add     rsp, 38h
0x140006561  retn
```
