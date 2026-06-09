# std::_Syserror_map(int)

- ea: `0x180002450`
- end: `0x180002478`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002130`
- `0x1800022b0`
- `0x180002320`

## callees

- `0x180002450`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  _QWORD *v1; // rax

  v1 = &unk_1800095A0;
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
0x180002450  cmp     cs:off_1800095A8, 0; "address family not supported"
0x180002458  lea     rax, unk_1800095A0
0x18000245f  jz      short loc_180002470
0x180002461  cmp     [rax], ecx
0x180002463  jz      short loc_180002473
0x180002465  add     rax, 10h
0x180002469  cmp     qword ptr [rax+8], 0
0x18000246e  jnz     short loc_180002461
0x180002470  xor     eax, eax
0x180002472  retn
0x180002473  mov     rax, [rax+8]
0x180002477  retn
```
