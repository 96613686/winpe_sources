# _alloca_probe

- ea: `0x140008990`
- end: `0x1400089de`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000227c`
- `0x1400024e4`
- `0x140002778`
- `0x1400056e0`
- `0x140007530`
- `0x1400083b4`

## callees

- `0x140008990`

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
0x140008990  sub     rsp, 10h
0x140008994  mov     [rsp+10h+var_10], r10
0x140008998  mov     [rsp+10h+var_8], r11
0x14000899d  xor     r11, r11
0x1400089a0  lea     r10, [rsp+10h+arg_0]
0x1400089a5  sub     r10, rax
0x1400089a8  cmovb   r10, r11
0x1400089ac  mov     r11, gs:10h
0x1400089b5  cmp     r10, r11
0x1400089b8  jnb     short loc_1400089D0
0x1400089ba  and     r10w, 0F000h
0x1400089c0  lea     r11, [r11-1000h]
0x1400089c7  mov     byte ptr [r11], 0
0x1400089cb  cmp     r10, r11
0x1400089ce  jnz     short loc_1400089C0
0x1400089d0  mov     r10, [rsp+10h+var_10]
0x1400089d4  mov     r11, [rsp+10h+var_8]
0x1400089d9  add     rsp, 10h
0x1400089dd  retn
```
