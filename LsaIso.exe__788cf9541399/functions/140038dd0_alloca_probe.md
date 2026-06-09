# _alloca_probe

- ea: `0x140038dd0`
- end: `0x140038e1d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x140004810`
- `0x1400070cc`
- `0x14000717c`
- `0x14000726c`
- `0x14000bb58`
- `0x14000dd10`
- `0x14000dea0`
- `0x1400145ac`
- `0x140018880`
- `0x14001c194`
- `0x14001c4a8`
- `0x14001c788`
- `0x14001ca30`
- `0x140036e5c`

## callees

- `0x140038dd0`

## pseudocode

```c
unsigned __int64 __fastcall alloca_probe()
{
  unsigned __int64 result; // rax
  char *v1; // r10
  char *StackLimit; // r11
  char v3; // [rsp+18h] [rbp+8h] BYREF

  v1 = &v3 - result;
  if ( (unsigned __int64)&v3 < result )
    v1 = 0;
  StackLimit = (char *)NtCurrentTeb()->NtTib.StackLimit;
  if ( v1 < StackLimit )
  {
    LOWORD(v1) = (unsigned __int16)v1 & 0xF000;
    do
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x140038dd0  sub     rsp, 10h
0x140038dd4  mov     [rsp+10h+var_10], r10
0x140038dd8  mov     [rsp+10h+var_8], r11
0x140038ddd  xor     r11, r11
0x140038de0  lea     r10, [rsp+10h+arg_0]
0x140038de5  sub     r10, rax
0x140038de8  cmovb   r10, r11
0x140038dec  mov     r11, gs:10h
0x140038df5  cmp     r10, r11
0x140038df8  jnb     short loc_140038E0F
0x140038dfa  and     r10w, 0F000h
0x140038e00  lea     r11, [r11-1000h]
0x140038e07  test    [r11], r11b
0x140038e0a  cmp     r10, r11
0x140038e0d  jb      short loc_140038E00
0x140038e0f  mov     r10, [rsp+10h+var_10]
0x140038e13  mov     r11, [rsp+10h+var_8]
0x140038e18  add     rsp, 10h
0x140038e1c  retn
```
