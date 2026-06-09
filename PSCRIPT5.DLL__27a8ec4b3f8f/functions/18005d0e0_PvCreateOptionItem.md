# PvCreateOptionItem

- ea: `0x18005d0e0`
- end: `0x18005d10f`
- name: `PvCreateOptionItem`
- size: `47`
- prototype: `_QWORD *__fastcall(__int64, int)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18005abc0`
- `0x18005b120`
- `0x18005b550`
- `0x18005b7b0`
- `0x18005be10`
- `0x18005c6c0`
- `0x18005c7a0`
- `0x18005c800`
- `0x18005c920`
- `0x18005cb70`
- `0x18005cd14`

## callees

- `0x18005cd68`
- `0x18005d0e0`
- `0x18005d118`

## pseudocode

```c
_QWORD *__fastcall PvCreateOptionItem(__int64 a1, int a2)
{
  _QWORD *result; // rax

  result = PCreateFeatureItem(a1, a2);
  if ( result )
    return PvCreateXlatedItem(a1, result + 11, *((_DWORD *)result + 21));
  return result;
}

```

## disassembly

```asm
0x18005d0e0  push    rbx
0x18005d0e2  sub     rsp, 20h
0x18005d0e6  mov     rbx, rcx
0x18005d0e9  call    PCreateFeatureItem
0x18005d0ee  test    rax, rax
0x18005d0f1  jnz     short loc_18005D0FA
0x18005d0f3  add     rsp, 20h
0x18005d0f7  pop     rbx
0x18005d0f8  retn
0x18005d0fa  mov     r8d, [rax+54h]
0x18005d0fe  lea     rdx, [rax+58h]
0x18005d102  mov     rcx, rbx
0x18005d105  add     rsp, 20h
0x18005d109  pop     rbx
0x18005d10a  jmp     PvCreateXlatedItem
```
