# avio_enum_protocols

- ea: `0x180019870`
- end: `0x1800198ac`
- name: `avio_enum_protocols`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019870`

## pseudocode

```c
_QWORD *__fastcall avio_enum_protocols(__int64 *a1, int a2)
{
  __int64 i; // rcx
  _QWORD *result; // rax

  for ( i = *a1; ; ++i )
  {
    result = (_QWORD *)qword_180029598[i];
    if ( !result )
    {
      *a1 = 0;
      return result;
    }
    if ( !(a2 ? result[6] == 0 : result[5] == 0) )
      break;
  }
  *a1 = i + 1;
  return (_QWORD *)*result;
}

```

## disassembly

```asm
0x180019870  mov     r8, rcx
0x180019873  lea     r10, qword_180029598
0x18001987a  mov     rcx, [rcx]
0x18001987d  xor     r9d, r9d
0x180019880  jmp     short loc_180019895
0x180019882  test    edx, edx
0x180019884  jz      short loc_18001988C
0x180019886  cmp     [rax+30h], r9
0x18001988a  jmp     short loc_180019890
0x18001988c  cmp     [rax+28h], r9
0x180019890  jnz     short loc_1800198A2
0x180019892  inc     rcx
0x180019895  mov     rax, [r10+rcx*8]
0x180019899  test    rax, rax
0x18001989c  jnz     short loc_180019882
0x18001989e  mov     [r8], r9
0x1800198a1  retn
0x1800198a2  inc     rcx
0x1800198a5  mov     [r8], rcx
0x1800198a8  mov     rax, [rax]
0x1800198ab  retn
```
