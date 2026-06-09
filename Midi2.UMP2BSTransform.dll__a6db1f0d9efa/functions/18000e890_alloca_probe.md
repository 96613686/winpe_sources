# _alloca_probe

- ea: `0x18000e890`
- end: `0x18000e8de`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c80`
- `0x180002ef0`
- `0x180003184`
- `0x1800040b0`
- `0x18000689c`
- `0x180006c0c`
- `0x180008020`
- `0x1800089e0`

## callees

- `0x18000e890`

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
0x18000e890  sub     rsp, 10h
0x18000e894  mov     [rsp+10h+var_10], r10
0x18000e898  mov     [rsp+10h+var_8], r11
0x18000e89d  xor     r11, r11
0x18000e8a0  lea     r10, [rsp+10h+arg_0]
0x18000e8a5  sub     r10, rax
0x18000e8a8  cmovb   r10, r11
0x18000e8ac  mov     r11, gs:10h
0x18000e8b5  cmp     r10, r11
0x18000e8b8  jnb     short cs20
0x18000e8ba  and     r10w, 0F000h
0x18000e8c0  lea     r11, [r11-1000h]
0x18000e8c7  mov     byte ptr [r11], 0
0x18000e8cb  cmp     r10, r11
0x18000e8ce  jnz     short cs10
0x18000e8d0  mov     r10, [rsp+10h+var_10]
0x18000e8d4  mov     r11, [rsp+10h+var_8]
0x18000e8d9  add     rsp, 10h
0x18000e8dd  retn
```
