# _alloca_probe

- ea: `0x140010d80`
- end: `0x140010dce`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002744`
- `0x1400029ac`
- `0x140002c48`
- `0x140008e4c`
- `0x14000ba10`
- `0x14000bb38`
- `0x14000f45c`

## callees

- `0x140010d80`

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
    {
      StackLimit -= 4096;
      *StackLimit = 0;
    }
    while ( v1 != StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x140010d80  sub     rsp, 10h
0x140010d84  mov     [rsp+10h+var_10], r10
0x140010d88  mov     [rsp+10h+var_8], r11
0x140010d8d  xor     r11, r11
0x140010d90  lea     r10, [rsp+10h+arg_0]
0x140010d95  sub     r10, rax
0x140010d98  cmovb   r10, r11
0x140010d9c  mov     r11, gs:10h
0x140010da5  cmp     r10, r11
0x140010da8  jnb     short loc_140010DC0
0x140010daa  and     r10w, 0F000h
0x140010db0  lea     r11, [r11-1000h]
0x140010db7  mov     byte ptr [r11], 0
0x140010dbb  cmp     r10, r11
0x140010dbe  jnz     short loc_140010DB0
0x140010dc0  mov     r10, [rsp+10h+var_10]
0x140010dc4  mov     r11, [rsp+10h+var_8]
0x140010dc9  add     rsp, 10h
0x140010dcd  retn
```
