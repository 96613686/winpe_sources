# XPerfCore::_SafeImageNtHeader

- ea: `0x18002758c`
- end: `0x1800275ef`
- name: `XPerfCore::_SafeImageNtHeader`
- size: `99`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180026888`

## callees

- `0x18002758c`

## pseudocode

```c
__int64 __fastcall XPerfCore::_SafeImageNtHeader(__int64 a1, unsigned int a2)
{
  __int64 v2; // rax
  unsigned int v3; // edx
  __int64 v4; // rcx
  __int64 result; // rax

  if ( !a1 )
    return 0;
  if ( a2 <= 0x40 )
    return 0;
  if ( *(_WORD *)a1 != 23117 )
    return 0;
  v2 = *(unsigned int *)(a1 + 60);
  if ( (v2 & 3) != 0 )
    return 0;
  if ( (unsigned int)v2 >= a2 )
    return 0;
  v3 = a2 - v2;
  if ( v3 < 0x1B )
    return 0;
  v4 = v2 + a1;
  if ( *(_DWORD *)v4 != 17744 )
    return 0;
  if ( *(_WORD *)(v4 + 24) != 267 )
  {
    if ( *(_WORD *)(v4 + 24) == 523 && v3 > 0x108 )
      return v4;
    return 0;
  }
  result = 0;
  if ( v3 > 0xF8 )
    return v4;
  return result;
}

```

## disassembly

```asm
0x18002758c  test    rcx, rcx
0x18002758f  jz      short loc_1800275EC
0x180027591  cmp     edx, 40h ; '@'
0x180027594  jbe     short loc_1800275EC
0x180027596  mov     eax, 5A4Dh
0x18002759b  cmp     [rcx], ax
0x18002759e  jnz     short loc_1800275EC
0x1800275a0  mov     eax, [rcx+3Ch]
0x1800275a3  test    al, 3
0x1800275a5  jnz     short loc_1800275EC
0x1800275a7  cmp     eax, edx
0x1800275a9  jnb     short loc_1800275EC
0x1800275ab  sub     edx, eax
0x1800275ad  cmp     edx, 1Bh
0x1800275b0  jb      short loc_1800275EC
0x1800275b2  add     rcx, rax
0x1800275b5  cmp     dword ptr [rcx], 4550h
0x1800275bb  jnz     short loc_1800275EC
0x1800275bd  mov     eax, 10Bh
0x1800275c2  cmp     [rcx+18h], ax
0x1800275c6  jz      short loc_1800275DF
0x1800275c8  mov     eax, 20Bh
0x1800275cd  cmp     [rcx+18h], ax
0x1800275d1  jnz     short loc_1800275EC
0x1800275d3  cmp     edx, 108h
0x1800275d9  jbe     short loc_1800275EC
0x1800275db  mov     rax, rcx
0x1800275de  retn
0x1800275df  xor     eax, eax
0x1800275e1  cmp     edx, 0F8h
0x1800275e7  cmova   rax, rcx
0x1800275eb  retn
0x1800275ec  xor     eax, eax
0x1800275ee  retn
```
