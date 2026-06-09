# _tlgKeywordOn

- ea: `0x14000258c`
- end: `0x1400025b2`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140007ebc`
- `0x14000811c`
- `0x14000a070`
- `0x14000a5c8`
- `0x14000ab00`
- `0x14000abc0`
- `0x14000ad14`
- `0x14000afd4`
- `0x14000b2e0`
- `0x14000b510`
- `0x14000ba4c`

## callees

- `0x14000258c`

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
0x14000258c  mov     rax, rcx
0x14000258f  test    rdx, rdx
0x140002592  jz      short loc_1400025AC
0x140002594  mov     rcx, [rcx+18h]
0x140002598  mov     rax, [rax+10h]
0x14000259c  test    rdx, rax
0x14000259f  jz      short loc_1400025AF
0x1400025a1  mov     rax, rcx
0x1400025a4  and     rax, rdx
0x1400025a7  cmp     rax, rcx
0x1400025aa  jnz     short loc_1400025AF
0x1400025ac  mov     al, 1
0x1400025ae  retn
0x1400025af  xor     al, al
0x1400025b1  retn
```
