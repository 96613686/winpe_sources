# BfpPathTreeEmpty

- ea: `0x140017bb8`
- end: `0x140017bde`
- name: `BfpPathTreeEmpty`
- size: `38`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f230`
- `0x14000f308`
- `0x14000f3d0`
- `0x14000f544`
- `0x140011264`
- `0x140017f00`
- `0x140019c44`
- `0x14001b280`

## callees

- `0x140017bb8`

## pseudocode

```c
bool __fastcall BfpPathTreeEmpty(__int64 a1)
{
  __int64 v1; // rax

  if ( !a1 )
    return 1;
  v1 = *(_QWORD *)a1;
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
  {
    if ( v1 )
      v1 ^= a1;
  }
  return v1 == 0;
}

```

## disassembly

```asm
0x140017bb8  test    rcx, rcx
0x140017bbb  jz      short loc_140017BCE
0x140017bbd  test    byte ptr [rcx+8], 1
0x140017bc1  mov     rax, [rcx]
0x140017bc4  jnz     short loc_140017BD2
0x140017bc6  test    rax, rax
0x140017bc9  setz    al
0x140017bcc  retn
0x140017bce  mov     al, 1
0x140017bd0  retn
0x140017bd2  test    rax, rax
0x140017bd5  jz      short loc_140017BDC
0x140017bd7  xor     rax, rcx
0x140017bda  jmp     short loc_140017BC6
0x140017bdc  jmp     short loc_140017BC6
```
