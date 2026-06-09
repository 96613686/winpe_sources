# _tlgKeywordOn

- ea: `0x1400022ec`
- end: `0x140002312`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x1400050c8`
- `0x140008e10`
- `0x140009f40`
- `0x14000ac0c`
- `0x14000ad00`
- `0x14000adcc`
- `0x14000ae8c`
- `0x14000af4c`
- `0x14000b00c`
- `0x14000b5fc`
- `0x14000b6e4`
- `0x14000b93c`
- `0x14000bb94`
- `0x14000be40`
- `0x14000c070`
- `0x14000c2a0`
- `0x14000c4d0`
- `0x14000c700`
- `0x14000c930`
- `0x14000ef38`

## callees

- `0x1400022ec`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  bool result; // al

  result = 1;
  if ( a2 )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( (*(_QWORD *)(a1 + 16) & a2) == 0 || (a2 & v3) != v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400022ec  mov     rax, rcx
0x1400022ef  test    rdx, rdx
0x1400022f2  jz      short loc_14000230C
0x1400022f4  mov     rcx, [rcx+18h]
0x1400022f8  mov     rax, [rax+10h]
0x1400022fc  test    rdx, rax
0x1400022ff  jz      short loc_14000230F
0x140002301  mov     rax, rcx
0x140002304  and     rax, rdx
0x140002307  cmp     rax, rcx
0x14000230a  jnz     short loc_14000230F
0x14000230c  mov     al, 1
0x14000230e  retn
0x14000230f  xor     al, al
0x140002311  retn
```
