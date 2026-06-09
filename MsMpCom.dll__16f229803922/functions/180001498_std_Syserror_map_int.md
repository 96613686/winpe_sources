# std::_Syserror_map(int)

- ea: `0x180001498`
- end: `0x1800014c0`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800085c0`
- `0x180008730`
- `0x1800087a0`

## callees

- `0x180001498`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000B4D0;
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
0x180001498  cmp     cs:off_18000B4D8, 0; "address family not supported"
0x1800014a0  lea     rax, qword_18000B4D0
0x1800014a7  jz      short loc_1800014B8
0x1800014a9  cmp     [rax], ecx
0x1800014ab  jz      short loc_1800014BB
0x1800014ad  add     rax, 10h
0x1800014b1  cmp     qword ptr [rax+8], 0
0x1800014b6  jnz     short loc_1800014A9
0x1800014b8  xor     eax, eax
0x1800014ba  retn
0x1800014bb  mov     rax, [rax+8]
0x1800014bf  retn
```
