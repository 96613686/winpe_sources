# IN6_IS_ADDR_LOOPBACK

- ea: `0x180004460`
- end: `0x1800044a1`
- name: `IN6_IS_ADDR_LOOPBACK`
- size: `65`
- prototype: `BOOLEAN __stdcall(const IN6_ADDR *a)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019b0`
- `0x180002e00`

## callees

- `0x180004460`

## pseudocode

```c
BOOLEAN __stdcall IN6_IS_ADDR_LOOPBACK(const IN6_ADDR *a)
{
  return !a->u.Word[0]
      && !a->u.Word[1]
      && !a->u.Word[2]
      && !a->u.Word[3]
      && !a->u.Word[4]
      && !a->u.Word[5]
      && !a->u.Word[6]
      && a->u.Word[7] == 256;
}

```

## disassembly

```asm
0x180004460  cmp     word ptr [rcx], 0
0x180004464  jnz     short loc_18000449E
0x180004466  cmp     word ptr [rcx+2], 0
0x18000446b  jnz     short loc_18000449E
0x18000446d  cmp     word ptr [rcx+4], 0
0x180004472  jnz     short loc_18000449E
0x180004474  cmp     word ptr [rcx+6], 0
0x180004479  jnz     short loc_18000449E
0x18000447b  cmp     word ptr [rcx+8], 0
0x180004480  jnz     short loc_18000449E
0x180004482  cmp     word ptr [rcx+0Ah], 0
0x180004487  jnz     short loc_18000449E
0x180004489  cmp     word ptr [rcx+0Ch], 0
0x18000448e  jnz     short loc_18000449E
0x180004490  mov     eax, 100h
0x180004495  cmp     [rcx+0Eh], ax
0x180004499  jnz     short loc_18000449E
0x18000449b  mov     al, 1
0x18000449d  retn
0x18000449e  xor     al, al
0x1800044a0  retn
```
