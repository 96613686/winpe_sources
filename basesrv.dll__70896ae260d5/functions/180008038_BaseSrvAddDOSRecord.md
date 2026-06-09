# BaseSrvAddDOSRecord

- ea: `0x180008038`
- end: `0x180008065`
- name: `BaseSrvAddDOSRecord`
- size: `45`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000806c`
- `0x180008644`

## callees

- `0x180008038`

## pseudocode

```c
_QWORD *__fastcall BaseSrvAddDOSRecord(__int64 a1, _QWORD *a2)
{
  _QWORD **v2; // r8
  _QWORD *v3; // rcx
  _QWORD *result; // rax

  *a2 = 0;
  v2 = *(_QWORD ***)(a1 + 72);
  if ( v2 )
  {
    v3 = *v2;
    if ( *v2 )
    {
      do
      {
        result = (_QWORD *)*v3;
        v2 = (_QWORD **)v3;
        v3 = result;
      }
      while ( result );
    }
    *v2 = a2;
  }
  else
  {
    *(_QWORD *)(a1 + 72) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x180008038  and     qword ptr [rdx], 0
0x18000803c  mov     r8, [rcx+48h]
0x180008040  test    r8, r8
0x180008043  jnz     short loc_18000804B
0x180008045  mov     [rcx+48h], rdx
0x180008049  retn
0x18000804b  mov     rcx, [r8]
0x18000804e  test    rcx, rcx
0x180008051  jz      short loc_180008061
0x180008053  mov     rax, [rcx]
0x180008056  mov     r8, rcx
0x180008059  mov     rcx, rax
0x18000805c  test    rax, rax
0x18000805f  jnz     short loc_180008053
0x180008061  mov     [r8], rdx
0x180008064  retn
```
