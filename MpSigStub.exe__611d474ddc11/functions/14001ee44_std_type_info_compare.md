# __std_type_info_compare

- ea: `0x14001ee44`
- end: `0x14001ee6b`
- name: `__std_type_info_compare`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140021f08`

## callees

- `0x14001ee44`

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
0x14001ee44  cmp     rcx, rdx
0x14001ee47  jz      short loc_14001EE62
0x14001ee49  add     rdx, 9
0x14001ee4d  lea     rax, [rcx+9]
0x14001ee51  sub     rdx, rax
0x14001ee54  mov     cl, [rax]
0x14001ee56  cmp     cl, [rax+rdx]
0x14001ee59  jnz     short loc_14001EE65
0x14001ee5b  inc     rax
0x14001ee5e  test    cl, cl
0x14001ee60  jnz     short loc_14001EE54
0x14001ee62  xor     eax, eax
0x14001ee64  retn
0x14001ee65  sbb     eax, eax
0x14001ee67  or      eax, 1
0x14001ee6a  retn
```
