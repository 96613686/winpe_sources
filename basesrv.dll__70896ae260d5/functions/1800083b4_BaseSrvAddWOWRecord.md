# BaseSrvAddWOWRecord

- ea: `0x1800083b4`
- end: `0x1800083d3`
- name: `BaseSrvAddWOWRecord`
- size: `31`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000821c`
- `0x180008d80`

## callees

- `0x1800083b4`

## pseudocode

```c
__int64 __fastcall BaseSrvAddWOWRecord(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  _QWORD *v3; // rcx

  result = *(_QWORD *)(a1 + 56);
  if ( result )
  {
    do
    {
      v3 = (_QWORD *)(result + 32);
      result = *(_QWORD *)(result + 32);
    }
    while ( result );
    *v3 = a2;
  }
  else
  {
    *(_QWORD *)(a1 + 56) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x1800083b4  mov     rax, [rcx+38h]
0x1800083b8  test    rax, rax
0x1800083bb  jnz     short loc_1800083C3
0x1800083bd  mov     [rcx+38h], rdx
0x1800083c1  retn
0x1800083c3  lea     rcx, [rax+20h]
0x1800083c7  mov     rax, [rcx]
0x1800083ca  test    rax, rax
0x1800083cd  jnz     short loc_1800083C3
0x1800083cf  mov     [rcx], rdx
0x1800083d2  retn
```
