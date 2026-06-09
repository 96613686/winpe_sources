# std::_Syserror_map(int)

- ea: `0x140001930`
- end: `0x140001958`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001610`
- `0x140001790`
- `0x140001800`

## callees

- `0x140001930`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_140006590;
  if ( !"address family not supported" )
    return 0;
  while ( *(_DWORD *)v1 != a1 )
  {
    v1 += 2;
    if ( !v1[1] )
      return 0;
  }
  return (const char *)v1[1];
}

```

## disassembly

```asm
0x140001930  cmp     cs:off_140006598, 0; "address family not supported"
0x140001938  lea     rax, qword_140006590
0x14000193f  jz      short loc_140001950
0x140001941  cmp     [rax], ecx
0x140001943  jz      short loc_140001953
0x140001945  add     rax, 10h
0x140001949  cmp     qword ptr [rax+8], 0
0x14000194e  jnz     short loc_140001941
0x140001950  xor     eax, eax
0x140001952  retn
0x140001953  mov     rax, [rax+8]
0x140001957  retn
```
