# std::_Syserror_map(int)

- ea: `0x180002c80`
- end: `0x180002ca8`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009fb0`
- `0x18000a120`
- `0x18000a190`

## callees

- `0x180002c80`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_180011500;
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
0x180002c80  cmp     cs:off_180011508, 0; "address family not supported"
0x180002c88  lea     rax, qword_180011500
0x180002c8f  jz      short loc_180002CA0
0x180002c91  cmp     [rax], ecx
0x180002c93  jz      short loc_180002CA3
0x180002c95  add     rax, 10h
0x180002c99  cmp     qword ptr [rax+8], 0
0x180002c9e  jnz     short loc_180002C91
0x180002ca0  xor     eax, eax
0x180002ca2  retn
0x180002ca3  mov     rax, [rax+8]
0x180002ca7  retn
```
