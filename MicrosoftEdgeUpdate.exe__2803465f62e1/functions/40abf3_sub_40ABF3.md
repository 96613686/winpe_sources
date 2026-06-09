# sub_40ABF3

- ea: `0x40abf3`
- end: `0x40ac17`
- name: `sub_40ABF3`
- size: `36`
- prototype: `int __cdecl(void *Src, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x408b7c`
- `0x408c21`
- `0x408f3a`
- `0x4090e0`
- `0x409375`
- `0x40a37e`
- `0x40a3b9`

## callees

- `0x40a05f`

## pseudocode

```c
int __cdecl sub_40ABF3(void *Src, unsigned int a2)
{
  int v2; // ecx
  int v3; // esi

  v3 = v2;
  *(_DWORD *)v2 = 0;
  *(_DWORD *)(v2 + 16) = 0;
  *(_DWORD *)(v2 + 20) = 7;
  sub_40A05F((void **)v2, Src, a2);
  return v3;
}

```

## disassembly

```asm
0x40abf3  push    ebp
0x40abf4  mov     ebp, esp
0x40abf6  push    esi
0x40abf7  push    [ebp+arg_4]; int
0x40abfa  mov     esi, ecx
0x40abfc  push    [ebp+Src]; Src
0x40abff  and     dword ptr [esi], 0
0x40ac02  and     dword ptr [esi+10h], 0
0x40ac06  mov     dword ptr [esi+14h], 7
0x40ac0d  call    sub_40A05F
0x40ac12  mov     eax, esi
0x40ac14  pop     esi
0x40ac15  pop     ebp
0x40ac16  retn
```
