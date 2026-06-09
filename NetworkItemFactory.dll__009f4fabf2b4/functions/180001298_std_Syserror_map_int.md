# std::_Syserror_map(int)

- ea: `0x180001298`
- end: `0x1800012c0`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002140`
- `0x1800022b0`
- `0x180002320`

## callees

- `0x180001298`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000C4D0;
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
0x180001298  cmp     cs:off_18000C4D8, 0; "address family not supported"
0x1800012a0  lea     rax, qword_18000C4D0
0x1800012a7  jz      short loc_1800012B8
0x1800012a9  cmp     [rax], ecx
0x1800012ab  jz      short loc_1800012BB
0x1800012ad  add     rax, 10h
0x1800012b1  cmp     qword ptr [rax+8], 0
0x1800012b6  jnz     short loc_1800012A9
0x1800012b8  xor     eax, eax
0x1800012ba  retn
0x1800012bb  mov     rax, [rax+8]
0x1800012bf  retn
```
