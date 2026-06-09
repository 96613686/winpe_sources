# _ValidateImageBase

- ea: `0x1400015d0`
- end: `0x1400015fb`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001580`

## callees

- `0x1400015d0`

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
0x1400015d0  mov     eax, 5A4Dh
0x1400015d5  cmp     [rcx], ax
0x1400015d8  jnz     short loc_1400015F8
0x1400015da  movsxd  rdx, dword ptr [rcx+3Ch]
0x1400015de  add     rdx, rcx
0x1400015e1  cmp     dword ptr [rdx], 4550h
0x1400015e7  jnz     short loc_1400015F8
0x1400015e9  xor     eax, eax
0x1400015eb  mov     ecx, 20Bh
0x1400015f0  cmp     [rdx+18h], cx
0x1400015f4  setz    al
0x1400015f7  retn
0x1400015f8  xor     eax, eax
0x1400015fa  retn
```
