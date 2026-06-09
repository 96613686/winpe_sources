# _ValidateImageBase

- ea: `0x180001590`
- end: `0x1800015bb`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001540`

## callees

- `0x180001590`

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
0x180001590  mov     eax, 5A4Dh
0x180001595  cmp     [rcx], ax
0x180001598  jnz     short loc_1800015B8
0x18000159a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000159e  add     rdx, rcx
0x1800015a1  cmp     dword ptr [rdx], 4550h
0x1800015a7  jnz     short loc_1800015B8
0x1800015a9  xor     eax, eax
0x1800015ab  mov     ecx, 20Bh
0x1800015b0  cmp     [rdx+18h], cx
0x1800015b4  setz    al
0x1800015b7  retn
0x1800015b8  xor     eax, eax
0x1800015ba  retn
```
