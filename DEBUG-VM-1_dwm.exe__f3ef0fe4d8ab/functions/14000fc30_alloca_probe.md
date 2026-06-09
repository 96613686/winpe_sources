# _alloca_probe

- ea: `0x14000fc30`
- end: `0x14000fc7e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140006e90`
- `0x140006f40`
- `0x1400071d4`
- `0x14000a1b0`
- `0x14000bcec`

## callees

- `0x14000fc30`

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
0x14000fc30  sub     rsp, 10h
0x14000fc34  mov     [rsp+10h+var_10], r10
0x14000fc38  mov     [rsp+10h+var_8], r11
0x14000fc3d  xor     r11, r11
0x14000fc40  lea     r10, [rsp+10h+arg_0]
0x14000fc45  sub     r10, rax
0x14000fc48  cmovb   r10, r11
0x14000fc4c  mov     r11, gs:10h
0x14000fc55  cmp     r10, r11
0x14000fc58  jnb     short loc_14000FC70
0x14000fc5a  and     r10w, 0F000h
0x14000fc60  lea     r11, [r11-1000h]
0x14000fc67  mov     byte ptr [r11], 0
0x14000fc6b  cmp     r10, r11
0x14000fc6e  jnz     short loc_14000FC60
0x14000fc70  mov     r10, [rsp+10h+var_10]
0x14000fc74  mov     r11, [rsp+10h+var_8]
0x14000fc79  add     rsp, 10h
0x14000fc7d  retn
```
