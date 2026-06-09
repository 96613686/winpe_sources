# std::_Syserror_map(int)

- ea: `0x140002440`
- end: `0x140002468`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002120`
- `0x1400022a0`
- `0x140002310`

## callees

- `0x140002440`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1400075A0;
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
0x140002440  cmp     cs:off_1400075A8, 0; "address family not supported"
0x140002448  lea     rax, qword_1400075A0
0x14000244f  jz      short loc_140002460
0x140002451  cmp     [rax], ecx
0x140002453  jz      short loc_140002463
0x140002455  add     rax, 10h
0x140002459  cmp     qword ptr [rax+8], 0
0x14000245e  jnz     short loc_140002451
0x140002460  xor     eax, eax
0x140002462  retn
0x140002463  mov     rax, [rax+8]
0x140002467  retn
```
