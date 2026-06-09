# std::_Syserror_map(int)

- ea: `0x180001a70`
- end: `0x180001a98`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001750`
- `0x1800018d0`
- `0x180001940`

## callees

- `0x180001a70`

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
0x180001a70  cmp     cs:off_18000D598, 0; "address family not supported"
0x180001a78  lea     rax, qword_18000D590
0x180001a7f  jz      short loc_180001A90
0x180001a81  cmp     [rax], ecx
0x180001a83  jz      short loc_180001A93
0x180001a85  add     rax, 10h
0x180001a89  cmp     qword ptr [rax+8], 0
0x180001a8e  jnz     short loc_180001A81
0x180001a90  xor     eax, eax
0x180001a92  retn
0x180001a93  mov     rax, [rax+8]
0x180001a97  retn
```
