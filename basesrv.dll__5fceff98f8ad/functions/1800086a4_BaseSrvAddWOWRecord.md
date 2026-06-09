# BaseSrvAddWOWRecord

- ea: `0x1800086a4`
- end: `0x1800086c3`
- name: `BaseSrvAddWOWRecord`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008528`
- `0x18000905c`

## callees

- `0x1800086a4`

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
0x1800086a4  mov     rax, [rcx+38h]
0x1800086a8  test    rax, rax
0x1800086ab  jnz     short loc_1800086B3
0x1800086ad  mov     [rcx+38h], rdx
0x1800086b1  retn
0x1800086b3  lea     rcx, [rax+20h]
0x1800086b7  mov     rax, [rcx]
0x1800086ba  test    rax, rax
0x1800086bd  jnz     short loc_1800086B3
0x1800086bf  mov     [rcx], rdx
0x1800086c2  retn
```
