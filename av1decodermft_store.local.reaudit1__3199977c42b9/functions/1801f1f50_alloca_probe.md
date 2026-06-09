# __alloca_probe

- ea: `0x1801f1f50`
- end: `0x1801f1f9e`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `37`
- callee_count: `1`
- tags: ``

## callers

- `0x180125020`
- `0x180133134`
- `0x1801333c8`
- `0x180135cb0`
- `0x180135dd8`
- `0x18016b5f8`
- `0x180185b20`
- `0x180186320`
- `0x1801a1330`
- `0x1801b0f30`
- `0x1801b5ac0`
- `0x1801b93e0`
- `0x1801bb9e0`
- `0x1801bc1e0`
- `0x1801bd690`
- `0x1801becf0`
- `0x1801bfa40`
- `0x1801c0260`
- `0x1801c15a0`
- `0x1801c1710`
- `0x1801c2d50`
- `0x1801c5280`
- `0x1801c59a0`
- `0x1801c6100`
- `0x1801c6630`
- `0x1801c6a60`
- `0x1801c71b0`
- `0x1801c7990`
- `0x1801c7f50`
- `0x1801cb030`
- `0x1801cbb50`
- `0x1801cc350`
- `0x1801cc9d0`
- `0x1801cce40`
- `0x1801cd9b0`
- `0x1801ce300`
- `0x1801cea40`

## callees

- `0x1801f1f50`

## pseudocode

```c
unsigned __int64 __fastcall _alloca_probe()
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
0x1801f1f50  sub     rsp, 10h
0x1801f1f54  mov     [rsp+10h+var_10], r10
0x1801f1f58  mov     [rsp+10h+var_8], r11
0x1801f1f5d  xor     r11, r11
0x1801f1f60  lea     r10, [rsp+10h+arg_0]
0x1801f1f65  sub     r10, rax
0x1801f1f68  cmovb   r10, r11
0x1801f1f6c  mov     r11, gs:10h
0x1801f1f75  cmp     r10, r11
0x1801f1f78  jnb     short cs20
0x1801f1f7a  and     r10w, 0F000h
0x1801f1f80  lea     r11, [r11-1000h]
0x1801f1f87  mov     byte ptr [r11], 0
0x1801f1f8b  cmp     r10, r11
0x1801f1f8e  jnz     short cs10
0x1801f1f90  mov     r10, [rsp+10h+var_10]
0x1801f1f94  mov     r11, [rsp+10h+var_8]
0x1801f1f99  add     rsp, 10h
0x1801f1f9d  retn
```
