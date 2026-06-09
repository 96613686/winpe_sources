# _ValidateImageBase

- ea: `0x140001500`
- end: `0x14000152b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014b0`

## callees

- `0x140001500`

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
0x140001500  mov     eax, 5A4Dh
0x140001505  cmp     [rcx], ax
0x140001508  jnz     short loc_140001528
0x14000150a  movsxd  rdx, dword ptr [rcx+3Ch]
0x14000150e  add     rdx, rcx
0x140001511  cmp     dword ptr [rdx], 4550h
0x140001517  jnz     short loc_140001528
0x140001519  xor     eax, eax
0x14000151b  mov     ecx, 20Bh
0x140001520  cmp     [rdx+18h], cx
0x140001524  setz    al
0x140001527  retn
0x140001528  xor     eax, eax
0x14000152a  retn
```
