# _ValidateImageBase

- ea: `0x180002f80`
- end: `0x180002fab`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f30`

## callees

- `0x180002f80`

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
0x180002f80  mov     eax, 5A4Dh
0x180002f85  cmp     [rcx], ax
0x180002f88  jnz     short loc_180002FA8
0x180002f8a  movsxd  rdx, dword ptr [rcx+3Ch]
0x180002f8e  add     rdx, rcx
0x180002f91  cmp     dword ptr [rdx], 4550h
0x180002f97  jnz     short loc_180002FA8
0x180002f99  xor     eax, eax
0x180002f9b  mov     ecx, 20Bh
0x180002fa0  cmp     [rdx+18h], cx
0x180002fa4  setz    al
0x180002fa7  retn
0x180002fa8  xor     eax, eax
0x180002faa  retn
```
