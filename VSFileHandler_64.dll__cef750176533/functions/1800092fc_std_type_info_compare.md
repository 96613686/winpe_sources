# __std_type_info_compare

- ea: `0x1800092fc`
- end: `0x180009323`
- name: `__std_type_info_compare`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b2b0`

## callees

- `0x1800092fc`

## pseudocode

```c
__int64 __fastcall _std_type_info_compare(__int64 a1, __int64 a2)
{
  char *v2; // rax
  __int64 v3; // rdx
  char v4; // cl

  if ( a1 == a2 )
    return 0;
  v2 = (char *)(a1 + 9);
  v3 = a2 - a1;
  while ( 1 )
  {
    v4 = *v2;
    if ( *v2 != v2[v3] )
      break;
    ++v2;
    if ( !v4 )
      return 0;
  }
  return (unsigned __int8)*v2 < (unsigned __int8)v2[v3] ? -1 : 1;
}

```

## disassembly

```asm
0x1800092fc  cmp     rcx, rdx
0x1800092ff  jz      short loc_18000931A
0x180009301  add     rdx, 9
0x180009305  lea     rax, [rcx+9]
0x180009309  sub     rdx, rax
0x18000930c  mov     cl, [rax]
0x18000930e  cmp     cl, [rax+rdx]
0x180009311  jnz     short loc_18000931D
0x180009313  inc     rax
0x180009316  test    cl, cl
0x180009318  jnz     short loc_18000930C
0x18000931a  xor     eax, eax
0x18000931c  retn
0x18000931d  sbb     eax, eax
0x18000931f  or      eax, 1
0x180009322  retn
```
