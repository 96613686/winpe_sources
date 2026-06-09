# sub_401CAC

- ea: `0x401cac`
- end: `0x401cfa`
- name: `sub_401CAC`
- size: `78`
- prototype: `_DWORD *__thiscall(_DWORD *this, void **)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x4019cc`
- `0x402e3c`
- `0x404994`
- `0x40672d`
- `0x40775a`
- `0x4078b3`
- `0x407abc`
- `0x409aee`
- `0x40a943`
- `0x40aa5c`
- `0x40ae70`
- `0x40af00`
- `0x40af30`
- `0x40af70`
- `0x40b2f0`
- `0x40b370`
- `0x40b7b5`
- `0x40bca4`

## callees

- `0x4015d2`
- `0x401cac`
- `0x401ef9`
- `0x402048`

## pseudocode

```c
_DWORD *__thiscall sub_401CAC(_DWORD *this, void **a2)
{
  int v3; // edi
  _DWORD *v4; // ecx
  int v5; // esi

  v3 = *this - 16;
  v4 = (char *)*a2 - 16;
  if ( v4 != (_DWORD *)v3 )
  {
    if ( *(int *)(v3 + 12) >= 0 && *v4 == *(_DWORD *)v3 )
    {
      v5 = sub_402048(v4);
      sub_4015D2((volatile signed __int32 *)v3);
      *this = v5 + 16;
    }
    else
    {
      sub_401EF9(*a2, *((_DWORD *)*a2 - 3));
    }
  }
  return this;
}

```

## disassembly

```asm
0x401cac  push    ebp
0x401cad  mov     ebp, esp
0x401caf  mov     eax, [ebp+arg_0]
0x401cb2  push    ebx
0x401cb3  mov     ebx, ecx
0x401cb5  push    edi
0x401cb6  mov     edx, [eax]
0x401cb8  mov     edi, [ebx]
0x401cba  sub     edi, 10h
0x401cbd  lea     ecx, [edx-10h]
0x401cc0  cmp     ecx, edi
0x401cc2  jz      short loc_401CF2
0x401cc4  cmp     dword ptr [edi+0Ch], 0
0x401cc8  jl      short loc_401CE7
0x401cca  mov     eax, [ecx]
0x401ccc  cmp     eax, [edi]
0x401cce  jnz     short loc_401CE7
0x401cd0  push    esi
0x401cd1  call    sub_402048
0x401cd6  mov     ecx, edi
0x401cd8  mov     esi, eax
0x401cda  call    sub_4015D2
0x401cdf  lea     eax, [esi+10h]
0x401ce2  mov     [ebx], eax
0x401ce4  pop     esi
0x401ce5  jmp     short loc_401CF2
0x401ce7  push    dword ptr [edx-0Ch]; int
0x401cea  mov     ecx, ebx
0x401cec  push    edx; Src
0x401ced  call    sub_401EF9
0x401cf2  pop     edi
0x401cf3  mov     eax, ebx
0x401cf5  pop     ebx
0x401cf6  pop     ebp
0x401cf7  retn    4
```
