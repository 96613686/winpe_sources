# _ValidateImageBase

- ea: `0x180004eb0`
- end: `0x180004edb`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e60`

## callees

- `0x180004eb0`

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
0x180004eb0  mov     eax, 5A4Dh
0x180004eb5  cmp     [rcx], ax
0x180004eb8  jnz     short loc_180004ED8
0x180004eba  movsxd  rdx, dword ptr [rcx+3Ch]
0x180004ebe  add     rdx, rcx
0x180004ec1  cmp     dword ptr [rdx], 4550h
0x180004ec7  jnz     short loc_180004ED8
0x180004ec9  xor     eax, eax
0x180004ecb  mov     ecx, 20Bh
0x180004ed0  cmp     [rdx+18h], cx
0x180004ed4  setz    al
0x180004ed7  retn
0x180004ed8  xor     eax, eax
0x180004eda  retn
```
