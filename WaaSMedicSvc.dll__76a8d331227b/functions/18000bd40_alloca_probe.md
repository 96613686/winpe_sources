# _alloca_probe

- ea: `0x18000bd40`
- end: `0x18000bd8e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032fc`
- `0x18000357c`
- `0x180003828`
- `0x1800068d0`
- `0x180007074`
- `0x1800071c8`
- `0x18000749c`
- `0x18000750c`
- `0x18000a36c`

## callees

- `0x18000bd40`

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
0x18000bd40  sub     rsp, 10h
0x18000bd44  mov     [rsp+10h+var_10], r10
0x18000bd48  mov     [rsp+10h+var_8], r11
0x18000bd4d  xor     r11, r11
0x18000bd50  lea     r10, [rsp+10h+arg_0]
0x18000bd55  sub     r10, rax
0x18000bd58  cmovb   r10, r11
0x18000bd5c  mov     r11, gs:10h
0x18000bd65  cmp     r10, r11
0x18000bd68  jnb     short cs20
0x18000bd6a  and     r10w, 0F000h
0x18000bd70  lea     r11, [r11-1000h]
0x18000bd77  mov     byte ptr [r11], 0
0x18000bd7b  cmp     r10, r11
0x18000bd7e  jnz     short cs10
0x18000bd80  mov     r10, [rsp+10h+var_10]
0x18000bd84  mov     r11, [rsp+10h+var_8]
0x18000bd89  add     rsp, 10h
0x18000bd8d  retn
```
