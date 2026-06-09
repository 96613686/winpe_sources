# BfspGetBcdCopyFlags

- ea: `0x1400069e0`
- end: `0x140006a0b`
- name: `BfspGetBcdCopyFlags`
- size: `43`
- prototype: `int __fastcall(int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400052bc`
- `0x14000583c`
- `0x1400058e4`
- `0x140005ae8`
- `0x140005b98`
- `0x140005fc4`

## callees

- `0x1400069e0`

## pseudocode

```c
int __fastcall BfspGetBcdCopyFlags(int a1)
{
  int v1; // edx
  int result; // eax

  if ( (a1 & 0x40) != 0 )
    v1 = 24;
  else
    v1 = (a1 & 0x2000) != 0 ? 10 : 40;
  result = v1 | 0x80;
  if ( (a1 & 0x80000) == 0 )
    return v1;
  return result;
}

```

## disassembly

```asm
0x1400069e0  test    cl, 40h
0x1400069e3  jz      short loc_1400069EC
0x1400069e5  mov     edx, 18h
0x1400069ea  jmp     short loc_1400069FD
0x1400069ec  mov     eax, ecx
0x1400069ee  and     eax, 2000h
0x1400069f3  neg     eax
0x1400069f5  sbb     edx, edx
0x1400069f7  and     edx, 0FFFFFFE2h
0x1400069fa  add     edx, 28h ; '('
0x1400069fd  mov     eax, edx
0x1400069ff  bts     eax, 7
0x140006a03  bt      ecx, 13h
0x140006a07  cmovnb  eax, edx
0x140006a0a  retn
```
