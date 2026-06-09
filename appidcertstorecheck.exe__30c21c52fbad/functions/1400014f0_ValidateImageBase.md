# _ValidateImageBase

- ea: `0x1400014f0`
- end: `0x14000151b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x1400014f0`

## pseudocode

```c
_BOOL8 __fastcall ValidateImageBase(__int64 a1)
{
  __int64 v1; // rdx

  if ( *(_WORD *)a1 == 23117 && (v1 = a1 + *(int *)(a1 + 60), *(_DWORD *)v1 == 17744) )
    return *(_WORD *)(v1 + 24) == 523;
  else
    return 0;
}

```

## disassembly

```asm
0x1400014f0  mov     eax, 5A4Dh
0x1400014f5  cmp     [rcx], ax
0x1400014f8  jnz     short loc_140001518
0x1400014fa  movsxd  rdx, dword ptr [rcx+3Ch]
0x1400014fe  add     rdx, rcx
0x140001501  cmp     dword ptr [rdx], 4550h
0x140001507  jnz     short loc_140001518
0x140001509  xor     eax, eax
0x14000150b  mov     ecx, 20Bh
0x140001510  cmp     [rdx+18h], cx
0x140001514  setz    al
0x140001517  retn
0x140001518  xor     eax, eax
0x14000151a  retn
```
