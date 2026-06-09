# std::_Syserror_map(int)

- ea: `0x180002030`
- end: `0x180002058`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d10`
- `0x180001e90`
- `0x180001f00`

## callees

- `0x180002030`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000D590;
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
0x180002030  cmp     cs:off_18000D598, 0; "address family not supported"
0x180002038  lea     rax, qword_18000D590
0x18000203f  jz      short loc_180002050
0x180002041  cmp     [rax], ecx
0x180002043  jz      short loc_180002053
0x180002045  add     rax, 10h
0x180002049  cmp     qword ptr [rax+8], 0
0x18000204e  jnz     short loc_180002041
0x180002050  xor     eax, eax
0x180002052  retn
0x180002053  mov     rax, [rax+8]
0x180002057  retn
```
