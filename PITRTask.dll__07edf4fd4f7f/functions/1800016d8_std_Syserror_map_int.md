# std::_Syserror_map(int)

- ea: `0x1800016d8`
- end: `0x180001700`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bef0`
- `0x18000c150`
- `0x18000c1c0`

## callees

- `0x1800016d8`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1800134D0;
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
0x1800016d8  cmp     cs:off_1800134D8, 0; "address family not supported"
0x1800016e0  lea     rax, qword_1800134D0
0x1800016e7  jz      short loc_1800016F8
0x1800016e9  cmp     [rax], ecx
0x1800016eb  jz      short loc_1800016FB
0x1800016ed  add     rax, 10h
0x1800016f1  cmp     qword ptr [rax+8], 0
0x1800016f6  jnz     short loc_1800016E9
0x1800016f8  xor     eax, eax
0x1800016fa  retn
0x1800016fb  mov     rax, [rax+8]
0x1800016ff  retn
```
