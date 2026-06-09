# _ValidateImageBase

- ea: `0x180001620`
- end: `0x18000164b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015d0`

## callees

- `0x180001620`

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
0x180001620  mov     eax, 5A4Dh
0x180001625  cmp     [rcx], ax
0x180001628  jnz     short loc_180001648
0x18000162a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000162e  add     rdx, rcx
0x180001631  cmp     dword ptr [rdx], 4550h
0x180001637  jnz     short loc_180001648
0x180001639  xor     eax, eax
0x18000163b  mov     ecx, 20Bh
0x180001640  cmp     [rdx+18h], cx
0x180001644  setz    al
0x180001647  retn
0x180001648  xor     eax, eax
0x18000164a  retn
```
