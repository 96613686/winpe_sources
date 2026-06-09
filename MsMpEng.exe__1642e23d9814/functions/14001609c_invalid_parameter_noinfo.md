# _invalid_parameter_noinfo

- ea: `0x14001609c`
- end: `0x1400160ba`
- name: `_invalid_parameter_noinfo`
- size: `30`
- prototype: `void __cdecl()`
- caller_count: `41`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fbe0`
- `0x14000fca0`
- `0x1400101b0`
- `0x140010464`
- `0x140014b04`
- `0x1400154c8`
- `0x140016110`
- `0x14001667c`
- `0x1400168c0`
- `0x140016b80`
- `0x140016ec4`
- `0x140016fb8`
- `0x140017f08`
- `0x140018784`
- `0x1400187b4`
- `0x1400189d0`
- `0x140018a50`
- `0x1400191a0`
- `0x14001b044`
- `0x14001b8c4`
- `0x14001b988`
- `0x14001baa8`
- `0x14001c99c`
- `0x14001d490`
- `0x14001d520`
- `0x14001d684`
- `0x14001e3a8`
- `0x14001e75c`
- `0x14001f2d4`
- `0x1400206c8`
- `0x140020730`
- `0x1400208d4`
- `0x140020e40`
- `0x140022078`
- `0x1400223bc`
- `0x140022b90`
- `0x140022f30`
- `0x1400230d0`
- `0x1400231a0`
- `0x140023ffc`
- `0x14002411c`

## callees

- `0x140015f48`

## pseudocode

```c
void __cdecl invalid_parameter_noinfo()
{
  invalid_parameter(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x14001609c  sub     rsp, 38h
0x1400160a0  and     [rsp+38h+var_18], 0
0x1400160a6  xor     r9d, r9d; int
0x1400160a9  xor     r8d, r8d; int
0x1400160ac  xor     edx, edx; int
0x1400160ae  xor     ecx, ecx; int
0x1400160b0  call    _invalid_parameter
0x1400160b5  add     rsp, 38h
0x1400160b9  retn
```
