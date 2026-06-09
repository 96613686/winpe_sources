# _alloca_probe

- ea: `0x180010290`
- end: `0x1800102de`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003698`
- `0x180003a3c`
- `0x180003cbc`
- `0x180003f78`
- `0x180004224`
- `0x18000afdc`
- `0x18000f570`
- `0x18000f698`

## callees

- `0x180010290`

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
0x180010290  sub     rsp, 10h
0x180010294  mov     [rsp+10h+var_10], r10
0x180010298  mov     [rsp+10h+var_8], r11
0x18001029d  xor     r11, r11
0x1800102a0  lea     r10, [rsp+10h+arg_0]
0x1800102a5  sub     r10, rax
0x1800102a8  cmovb   r10, r11
0x1800102ac  mov     r11, gs:10h
0x1800102b5  cmp     r10, r11
0x1800102b8  jnb     short cs20
0x1800102ba  and     r10w, 0F000h
0x1800102c0  lea     r11, [r11-1000h]
0x1800102c7  mov     byte ptr [r11], 0
0x1800102cb  cmp     r10, r11
0x1800102ce  jnz     short cs10
0x1800102d0  mov     r10, [rsp+10h+var_10]
0x1800102d4  mov     r11, [rsp+10h+var_8]
0x1800102d9  add     rsp, 10h
0x1800102dd  retn
```
