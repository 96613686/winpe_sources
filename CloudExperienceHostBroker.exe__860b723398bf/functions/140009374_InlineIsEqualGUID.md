# InlineIsEqualGUID

- ea: `0x140009374`
- end: `0x14000939b`
- name: `InlineIsEqualGUID`
- size: `39`
- prototype: `_BOOL8 __fastcall(_DWORD *, _DWORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400062e8`
- `0x140006680`
- `0x140007980`
- `0x140008290`
- `0x140008300`
- `0x140008360`

## callees

- `0x140009374`

## pseudocode

```c
_BOOL8 __fastcall InlineIsEqualGUID(_DWORD *a1, _DWORD *a2)
{
  return *a1 == *a2 && a1[1] == a2[1] && a1[2] == a2[2] && a1[3] == a2[3];
}

```

## disassembly

```asm
0x140009374  mov     eax, [rdx]
0x140009376  cmp     [rcx], eax
0x140009378  jnz     short loc_140009398
0x14000937a  mov     eax, [rdx+4]
0x14000937d  cmp     [rcx+4], eax
0x140009380  jnz     short loc_140009398
0x140009382  mov     eax, [rdx+8]
0x140009385  cmp     [rcx+8], eax
0x140009388  jnz     short loc_140009398
0x14000938a  mov     eax, [rdx+0Ch]
0x14000938d  cmp     [rcx+0Ch], eax
0x140009390  jnz     short loc_140009398
0x140009392  mov     eax, 1
0x140009397  retn
0x140009398  xor     eax, eax
0x14000939a  retn
```
