# std::_Syserror_map(int)

- ea: `0x1800020b8`
- end: `0x1800020e0`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006dc0`
- `0x180006fb0`
- `0x180007020`

## callees

- `0x1800020b8`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000D4D0;
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
0x1800020b8  cmp     cs:off_18000D4D8, 0; "address family not supported"
0x1800020c0  lea     rax, qword_18000D4D0
0x1800020c7  jz      short loc_1800020D8
0x1800020c9  cmp     [rax], ecx
0x1800020cb  jz      short loc_1800020DB
0x1800020cd  add     rax, 10h
0x1800020d1  cmp     qword ptr [rax+8], 0
0x1800020d6  jnz     short loc_1800020C9
0x1800020d8  xor     eax, eax
0x1800020da  retn
0x1800020db  mov     rax, [rax+8]
0x1800020df  retn
```
