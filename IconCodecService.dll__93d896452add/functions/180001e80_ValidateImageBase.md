# _ValidateImageBase

- ea: `0x180001e80`
- end: `0x180001eab`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e30`

## callees

- `0x180001e80`

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
0x180001e80  mov     eax, 5A4Dh
0x180001e85  cmp     [rcx], ax
0x180001e88  jnz     short loc_180001EA8
0x180001e8a  movsxd  rdx, dword ptr [rcx+3Ch]
0x180001e8e  add     rdx, rcx
0x180001e91  cmp     dword ptr [rdx], 4550h
0x180001e97  jnz     short loc_180001EA8
0x180001e99  xor     eax, eax
0x180001e9b  mov     ecx, 20Bh
0x180001ea0  cmp     [rdx+18h], cx
0x180001ea4  setz    al
0x180001ea7  retn
0x180001ea8  xor     eax, eax
0x180001eaa  retn
```
