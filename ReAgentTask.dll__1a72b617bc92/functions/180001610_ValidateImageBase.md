# _ValidateImageBase

- ea: `0x180001610`
- end: `0x18000163b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015c0`

## callees

- `0x180001610`

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
0x180001610  mov     eax, 5A4Dh
0x180001615  cmp     [rcx], ax
0x180001618  jnz     short loc_180001638
0x18000161a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000161e  add     rdx, rcx
0x180001621  cmp     dword ptr [rdx], 4550h
0x180001627  jnz     short loc_180001638
0x180001629  xor     eax, eax
0x18000162b  mov     ecx, 20Bh
0x180001630  cmp     [rdx+18h], cx
0x180001634  setz    al
0x180001637  retn
0x180001638  xor     eax, eax
0x18000163a  retn
```
