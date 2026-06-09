# std::_Syserror_map(int)

- ea: `0x140002068`
- end: `0x140002090`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400065c0`
- `0x140006730`
- `0x1400067a0`

## callees

- `0x140002068`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1400114D0;
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
0x140002068  cmp     cs:off_1400114D8, 0; "address family not supported"
0x140002070  lea     rax, qword_1400114D0
0x140002077  jz      short loc_140002088
0x140002079  cmp     [rax], ecx
0x14000207b  jz      short loc_14000208B
0x14000207d  add     rax, 10h
0x140002081  cmp     qword ptr [rax+8], 0
0x140002086  jnz     short loc_140002079
0x140002088  xor     eax, eax
0x14000208a  retn
0x14000208b  mov     rax, [rax+8]
0x14000208f  retn
```
