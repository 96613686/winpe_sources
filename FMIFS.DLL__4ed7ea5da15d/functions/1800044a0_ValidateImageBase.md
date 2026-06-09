# _ValidateImageBase

- ea: `0x1800044a0`
- end: `0x1800044cb`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004450`

## callees

- `0x1800044a0`

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
0x1800044a0  mov     eax, 5A4Dh
0x1800044a5  cmp     [rcx], ax
0x1800044a8  jnz     short loc_1800044C8
0x1800044aa  movsxd  rdx, dword ptr [rcx+3Ch]
0x1800044ae  add     rdx, rcx
0x1800044b1  cmp     dword ptr [rdx], 4550h
0x1800044b7  jnz     short loc_1800044C8
0x1800044b9  xor     eax, eax
0x1800044bb  mov     ecx, 20Bh
0x1800044c0  cmp     [rdx+18h], cx
0x1800044c4  setz    al
0x1800044c7  retn
0x1800044c8  xor     eax, eax
0x1800044ca  retn
```
