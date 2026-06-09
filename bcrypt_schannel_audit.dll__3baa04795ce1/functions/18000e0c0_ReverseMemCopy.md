# ReverseMemCopy

- ea: `0x18000e0c0`
- end: `0x18000e0dc`
- name: `ReverseMemCopy`
- size: `28`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ddd4`
- `0x18000df40`
- `0x180012318`
- `0x180017828`
- `0x180017980`
- `0x180017abc`
- `0x180017c5c`
- `0x180017dd0`
- `0x180017f48`
- `0x1800180d8`
- `0x180018270`
- `0x180018460`

## callees

- `0x18000e0c0`

## pseudocode

```c
char __fastcall ReverseMemCopy(unsigned __int64 a1, char *a2, unsigned int a3)
{
  _BYTE *i; // r8
  char result; // al

  for ( i = (_BYTE *)(a1 + a3 - 1LL); (unsigned __int64)i >= a1; --i )
  {
    result = *a2;
    *i = *a2++;
  }
  return result;
}

```

## disassembly

```asm
0x18000e0c0  mov     r8d, r8d
0x18000e0c3  dec     r8
0x18000e0c6  add     r8, rcx
0x18000e0c9  jmp     short loc_18000E0D6
0x18000e0cb  mov     al, [rdx]
0x18000e0cd  mov     [r8], al
0x18000e0d0  dec     r8
0x18000e0d3  inc     rdx
0x18000e0d6  cmp     r8, rcx
0x18000e0d9  jnb     short loc_18000E0CB
0x18000e0db  retn
```
