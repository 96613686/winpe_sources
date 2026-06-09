# av_strstart

- ea: `0x18002d9d0`
- end: `0x18002d9ff`
- name: `av_strstart`
- size: `47`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18004bfa0`
- `0x18004c080`
- `0x18004c100`
- `0x18004c180`
- `0x18004c200`
- `0x18004ce74`
- `0x180051400`
- `0x180051610`
- `0x180051660`
- `0x1800516f0`

## callees

- `0x18002d9d0`

## pseudocode

```c
bool __fastcall av_strstart(_BYTE *a1, char *a2, _QWORD *a3)
{
  char v3; // r9
  bool v4; // zf

  v3 = *a2;
  if ( !*a2 )
    goto LABEL_5;
  do
  {
    if ( v3 != *a1 )
      break;
    ++a2;
    ++a1;
    v3 = *a2;
  }
  while ( *a2 );
  v4 = *a2 == 0;
  if ( !*a2 )
  {
LABEL_5:
    if ( a3 )
      *a3 = a1;
    return *a2 == 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18002d9d0  mov     r9b, [rdx]
0x18002d9d3  xor     eax, eax
0x18002d9d5  test    r9b, r9b
0x18002d9d8  jz      short loc_18002D9F1
0x18002d9da  cmp     r9b, [rcx]
0x18002d9dd  jnz     short loc_18002D9ED
0x18002d9df  inc     rdx
0x18002d9e2  inc     rcx
0x18002d9e5  mov     r9b, [rdx]
0x18002d9e8  test    r9b, r9b
0x18002d9eb  jnz     short loc_18002D9DA
0x18002d9ed  cmp     [rdx], al
0x18002d9ef  jnz     short loc_18002D9FB
0x18002d9f1  test    r8, r8
0x18002d9f4  jz      short loc_18002D9F9
0x18002d9f6  mov     [r8], rcx
0x18002d9f9  cmp     [rdx], al
0x18002d9fb  setz    al
0x18002d9fe  retn
```
