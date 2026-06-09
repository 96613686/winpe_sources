# BfsQueryAccessOnly

- ea: `0x14000a364`
- end: `0x14000a38a`
- name: `BfsQueryAccessOnly`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400055d8`
- `0x14000dadc`

## callees

- `0x14000a364`

## pseudocode

```c
bool __fastcall BfsQueryAccessOnly(int a1, __int64 a2)
{
  int v2; // edx

  v2 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) + 8LL) + 24LL);
  if ( a1 == 2 )
    return (v2 & 0xFFE1FF7E) == 0;
  else
    return (v2 & 0xFFE1FF76) == 0;
}

```

## disassembly

```asm
0x14000a364  mov     rax, [rdx+10h]
0x14000a368  mov     rdx, [rax+18h]
0x14000a36c  mov     rax, [rdx+8]
0x14000a370  mov     edx, [rax+18h]
0x14000a373  cmp     ecx, 2
0x14000a376  jnz     short loc_14000A380
0x14000a378  test    edx, 0FFE1FF7Eh
0x14000a37e  jmp     short loc_14000A386
0x14000a380  test    edx, 0FFE1FF76h
0x14000a386  setz    al
0x14000a389  retn
```
