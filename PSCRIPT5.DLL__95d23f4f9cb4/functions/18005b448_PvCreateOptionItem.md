# PvCreateOptionItem

- ea: `0x18005b448`
- end: `0x18005b476`
- name: `PvCreateOptionItem`
- size: `46`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180058fa0`
- `0x1800594e0`
- `0x1800598f0`
- `0x180059b50`
- `0x18005a1b0`
- `0x18005aa50`
- `0x18005ab30`
- `0x18005ab90`
- `0x18005acb0`
- `0x18005af00`
- `0x18005b094`

## callees

- `0x18005b0e4`
- `0x18005b448`
- `0x18005b47c`

## pseudocode

```c
__int64 __fastcall PvCreateOptionItem(__int64 a1)
{
  __int64 result; // rax

  result = PCreateFeatureItem();
  if ( result )
    return PvCreateXlatedItem(a1, result + 88, *(unsigned int *)(result + 84));
  return result;
}

```

## disassembly

```asm
0x18005b448  push    rbx
0x18005b44a  sub     rsp, 20h
0x18005b44e  mov     rbx, rcx
0x18005b451  call    PCreateFeatureItem
0x18005b456  test    rax, rax
0x18005b459  jnz     short loc_18005B461
0x18005b45b  add     rsp, 20h
0x18005b45f  pop     rbx
0x18005b460  retn
0x18005b461  mov     r8d, [rax+54h]
0x18005b465  lea     rdx, [rax+58h]
0x18005b469  mov     rcx, rbx
0x18005b46c  add     rsp, 20h
0x18005b470  pop     rbx
0x18005b471  jmp     PvCreateXlatedItem
```
