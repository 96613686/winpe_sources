# _tlgKeywordOn

- ea: `0x1800019ac`
- end: `0x1800019d2`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180008798`
- `0x18000a820`
- `0x18000aff0`
- `0x18000b8c4`
- `0x18000baa4`
- `0x18000bb90`

## callees

- `0x1800019ac`

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
0x1800019ac  mov     rax, rcx
0x1800019af  test    rdx, rdx
0x1800019b2  jz      short loc_1800019CC
0x1800019b4  mov     rcx, [rcx+18h]
0x1800019b8  mov     rax, [rax+10h]
0x1800019bc  test    rdx, rax
0x1800019bf  jz      short loc_1800019CF
0x1800019c1  mov     rax, rcx
0x1800019c4  and     rax, rdx
0x1800019c7  cmp     rax, rcx
0x1800019ca  jnz     short loc_1800019CF
0x1800019cc  mov     al, 1
0x1800019ce  retn
0x1800019cf  xor     al, al
0x1800019d1  retn
```
