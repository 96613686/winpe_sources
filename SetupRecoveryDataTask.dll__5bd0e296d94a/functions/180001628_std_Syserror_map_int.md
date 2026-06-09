# std::_Syserror_map(int)

- ea: `0x180001628`
- end: `0x180001650`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000af20`
- `0x18000b180`
- `0x18000b1f0`

## callees

- `0x180001628`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000E4D0;
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
0x180001628  cmp     cs:off_18000E4D8, 0; "address family not supported"
0x180001630  lea     rax, qword_18000E4D0
0x180001637  jz      short loc_180001648
0x180001639  cmp     [rax], ecx
0x18000163b  jz      short loc_18000164B
0x18000163d  add     rax, 10h
0x180001641  cmp     qword ptr [rax+8], 0
0x180001646  jnz     short loc_180001639
0x180001648  xor     eax, eax
0x18000164a  retn
0x18000164b  mov     rax, [rax+8]
0x18000164f  retn
```
