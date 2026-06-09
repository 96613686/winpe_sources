# std::_Syserror_map(int)

- ea: `0x180001b40`
- end: `0x180001b68`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001820`
- `0x1800019a0`
- `0x180001a10`

## callees

- `0x180001b40`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_180013590;
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
0x180001b40  cmp     cs:off_180013598, 0; "address family not supported"
0x180001b48  lea     rax, qword_180013590
0x180001b4f  jz      short loc_180001B60
0x180001b51  cmp     [rax], ecx
0x180001b53  jz      short loc_180001B63
0x180001b55  add     rax, 10h
0x180001b59  cmp     qword ptr [rax+8], 0
0x180001b5e  jnz     short loc_180001B51
0x180001b60  xor     eax, eax
0x180001b62  retn
0x180001b63  mov     rax, [rax+8]
0x180001b67  retn
```
