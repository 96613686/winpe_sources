# BfsQueryAccessOnly

- ea: `0x14000a4f4`
- end: `0x14000a51a`
- name: `BfsQueryAccessOnly`
- size: `38`
- prototype: `bool __fastcall(int, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005768`
- `0x14000dc70`

## callees

- `0x14000a4f4`

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
0x14000a4f4  mov     rax, [rdx+10h]
0x14000a4f8  mov     rdx, [rax+18h]
0x14000a4fc  mov     rax, [rdx+8]
0x14000a500  mov     edx, [rax+18h]
0x14000a503  cmp     ecx, 2
0x14000a506  jnz     short loc_14000A510
0x14000a508  test    edx, 0FFE1FF7Eh
0x14000a50e  jmp     short loc_14000A516
0x14000a510  test    edx, 0FFE1FF76h
0x14000a516  setz    al
0x14000a519  retn
```
