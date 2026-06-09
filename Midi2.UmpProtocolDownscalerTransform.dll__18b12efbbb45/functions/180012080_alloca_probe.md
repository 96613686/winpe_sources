# _alloca_probe

- ea: `0x180012080`
- end: `0x1800120ce`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e68`
- `0x1800040d8`
- `0x18000436c`
- `0x180005290`
- `0x180007a7c`
- `0x180007dec`
- `0x180009200`
- `0x180009bc0`

## callees

- `0x180012080`

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
0x180012080  sub     rsp, 10h
0x180012084  mov     [rsp+10h+var_10], r10
0x180012088  mov     [rsp+10h+var_8], r11
0x18001208d  xor     r11, r11
0x180012090  lea     r10, [rsp+10h+arg_0]
0x180012095  sub     r10, rax
0x180012098  cmovb   r10, r11
0x18001209c  mov     r11, gs:10h
0x1800120a5  cmp     r10, r11
0x1800120a8  jnb     short cs20
0x1800120aa  and     r10w, 0F000h
0x1800120b0  lea     r11, [r11-1000h]
0x1800120b7  mov     byte ptr [r11], 0
0x1800120bb  cmp     r10, r11
0x1800120be  jnz     short cs10
0x1800120c0  mov     r10, [rsp+10h+var_10]
0x1800120c4  mov     r11, [rsp+10h+var_8]
0x1800120c9  add     rsp, 10h
0x1800120cd  retn
```
