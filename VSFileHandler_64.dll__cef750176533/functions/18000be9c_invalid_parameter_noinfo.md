# _invalid_parameter_noinfo

- ea: `0x18000be9c`
- end: `0x18000beba`
- name: `_invalid_parameter_noinfo`
- size: `30`
- prototype: `void __cdecl()`
- caller_count: `74`
- callee_count: `1`
- tags: ``

## callers

- `0x180003be8`
- `0x18000572c`
- `0x1800060c0`
- `0x180006918`
- `0x1800069b4`
- `0x180006b5c`
- `0x180006e34`
- `0x1800070d4`
- `0x18000baa0`
- `0x18000bb1c`
- `0x18000bb9c`
- `0x18000c07c`
- `0x18000c7fc`
- `0x18000ca68`
- `0x18000d23c`
- `0x18000d3c4`
- `0x18000dda0`
- `0x18000e820`
- `0x18000e8b8`
- `0x18000ebbc`
- `0x18000f264`
- `0x18000f554`
- `0x180010554`
- `0x180010818`
- `0x180010d58`
- `0x1800111c8`
- `0x180011764`
- `0x180011a9c`
- `0x180012448`
- `0x180012d28`
- `0x180014190`
- `0x180014f78`
- `0x18001550c`
- `0x180016750`
- `0x1800168e0`
- `0x180016ea0`
- `0x180017054`
- `0x1800170d0`
- `0x180017470`
- `0x1800179c0`
- `0x180017f64`
- `0x180018874`
- `0x180018960`
- `0x180018e24`
- `0x180019980`
- `0x180019a04`
- `0x180019aa8`
- `0x180019af0`
- `0x18001a3fc`
- `0x18001b548`

## callees

- `0x18000bdec`

## pseudocode

```c
void __cdecl invalid_parameter_noinfo()
{
  invalid_parameter(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x18000be9c  sub     rsp, 38h
0x18000bea0  and     [rsp+38h+var_18], 0
0x18000bea6  xor     r9d, r9d; LineNo
0x18000bea9  xor     r8d, r8d; FileName
0x18000beac  xor     edx, edx; FunctionName
0x18000beae  xor     ecx, ecx; Expression
0x18000beb0  call    _invalid_parameter
0x18000beb5  add     rsp, 38h
0x18000beb9  retn
```
