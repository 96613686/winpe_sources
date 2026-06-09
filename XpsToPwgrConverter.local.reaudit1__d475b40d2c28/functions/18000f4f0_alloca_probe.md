# _alloca_probe

- ea: `0x18000f4f0`
- end: `0x18000f53e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026dc`
- `0x18000295c`
- `0x180002c08`
- `0x18000659c`
- `0x180008630`
- `0x180008758`
- `0x180008f08`
- `0x18000a6dc`
- `0x18000dc08`
- `0x18000eb64`

## callees

- `0x18000f4f0`

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
0x18000f4f0  sub     rsp, 10h
0x18000f4f4  mov     [rsp+10h+var_10], r10
0x18000f4f8  mov     [rsp+10h+var_8], r11
0x18000f4fd  xor     r11, r11
0x18000f500  lea     r10, [rsp+10h+arg_0]
0x18000f505  sub     r10, rax
0x18000f508  cmovb   r10, r11
0x18000f50c  mov     r11, gs:10h
0x18000f515  cmp     r10, r11
0x18000f518  jnb     short cs20
0x18000f51a  and     r10w, 0F000h
0x18000f520  lea     r11, [r11-1000h]
0x18000f527  mov     byte ptr [r11], 0
0x18000f52b  cmp     r10, r11
0x18000f52e  jnz     short cs10
0x18000f530  mov     r10, [rsp+10h+var_10]
0x18000f534  mov     r11, [rsp+10h+var_8]
0x18000f539  add     rsp, 10h
0x18000f53d  retn
```
