# _ValidateImageBase

- ea: `0x180001600`
- end: `0x18000162b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015b0`

## callees

- `0x180001600`

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
0x180001600  mov     eax, 5A4Dh
0x180001605  cmp     [rcx], ax
0x180001608  jnz     short loc_180001628
0x18000160a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000160e  add     rdx, rcx
0x180001611  cmp     dword ptr [rdx], 4550h
0x180001617  jnz     short loc_180001628
0x180001619  xor     eax, eax
0x18000161b  mov     ecx, 20Bh
0x180001620  cmp     [rdx+18h], cx
0x180001624  setz    al
0x180001627  retn
0x180001628  xor     eax, eax
0x18000162a  retn
```
