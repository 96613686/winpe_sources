# HampConnectionObjectCompareToMessage

- ea: `0x18000bc00`
- end: `0x18000bc1d`
- name: `HampConnectionObjectCompareToMessage`
- size: `29`
- prototype: `__int64 __fastcall(unsigned __int64 *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bc00`

## pseudocode

```c
__int64 __fastcall HampConnectionObjectCompareToMessage(unsigned __int64 *a1, __int64 a2)
{
  unsigned __int64 v2; // r8

  v2 = *(_QWORD *)(a2 + 48);
  if ( *a1 < v2 )
    return 0xFFFFFFFFLL;
  else
    return *a1 > v2;
}

```

## disassembly

```asm
0x18000bc00  mov     r8, [rdx+30h]
0x18000bc04  mov     rax, [rcx]
0x18000bc07  cmp     rax, r8
0x18000bc0a  jb      short loc_18000BC17
0x18000bc0c  xor     ecx, ecx
0x18000bc0e  cmp     rax, r8
0x18000bc11  setnbe  cl
0x18000bc14  mov     eax, ecx
0x18000bc16  retn
0x18000bc17  mov     eax, 0FFFFFFFFh
0x18000bc1c  retn
```
