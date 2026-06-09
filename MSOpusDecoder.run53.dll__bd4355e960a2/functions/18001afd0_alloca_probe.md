# _alloca_probe

- ea: `0x18001afd0`
- end: `0x18001b01e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022f0`
- `0x180004890`
- `0x180005aa0`
- `0x180007410`
- `0x1800074a0`
- `0x180007b20`
- `0x180008400`
- `0x180009400`
- `0x18000b570`
- `0x18000b990`
- `0x18000d970`
- `0x18000e1c0`
- `0x18000e400`
- `0x180011220`
- `0x1800117c0`
- `0x180011a00`
- `0x180011e70`
- `0x180011fc0`
- `0x180013c90`
- `0x180015f70`
- `0x1800163a0`
- `0x180016590`
- `0x180017030`
- `0x180017d90`
- `0x180018750`
- `0x18001f49c`
- `0x180021098`
- `0x18002140c`
- `0x180021de8`

## callees

- `0x18001afd0`

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
0x18001afd0  sub     rsp, 10h
0x18001afd4  mov     [rsp+10h+var_10], r10
0x18001afd8  mov     [rsp+10h+var_8], r11
0x18001afdd  xor     r11, r11
0x18001afe0  lea     r10, [rsp+10h+arg_0]
0x18001afe5  sub     r10, rax
0x18001afe8  cmovb   r10, r11
0x18001afec  mov     r11, gs:10h
0x18001aff5  cmp     r10, r11
0x18001aff8  jnb     short cs20
0x18001affa  and     r10w, 0F000h
0x18001b000  lea     r11, [r11-1000h]
0x18001b007  mov     byte ptr [r11], 0
0x18001b00b  cmp     r10, r11
0x18001b00e  jnz     short cs10
0x18001b010  mov     r10, [rsp+10h+var_10]
0x18001b014  mov     r11, [rsp+10h+var_8]
0x18001b019  add     rsp, 10h
0x18001b01d  retn
```
