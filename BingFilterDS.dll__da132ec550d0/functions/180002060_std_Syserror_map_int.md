# std::_Syserror_map(int)

- ea: `0x180002060`
- end: `0x180002088`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007470`
- `0x1800075e0`
- `0x180007650`

## callees

- `0x180002060`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000F4E0;
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
0x180002060  cmp     cs:off_18000F4E8, 0; "address family not supported"
0x180002068  lea     rax, qword_18000F4E0
0x18000206f  jz      short loc_180002080
0x180002071  cmp     [rax], ecx
0x180002073  jz      short loc_180002083
0x180002075  add     rax, 10h
0x180002079  cmp     qword ptr [rax+8], 0
0x18000207e  jnz     short loc_180002071
0x180002080  xor     eax, eax
0x180002082  retn
0x180002083  mov     rax, [rax+8]
0x180002087  retn
```
