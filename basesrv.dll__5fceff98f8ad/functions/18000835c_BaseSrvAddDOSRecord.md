# BaseSrvAddDOSRecord

- ea: `0x18000835c`
- end: `0x18000838c`
- name: `BaseSrvAddDOSRecord`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008394`
- `0x180008938`

## callees

- `0x18000835c`

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
0x18000835c  mov     qword ptr [rdx], 0
0x180008363  mov     r8, [rcx+48h]
0x180008367  test    r8, r8
0x18000836a  jnz     short loc_180008372
0x18000836c  mov     [rcx+48h], rdx
0x180008370  retn
0x180008372  mov     rcx, [r8]
0x180008375  test    rcx, rcx
0x180008378  jz      short loc_180008388
0x18000837a  mov     rax, [rcx]
0x18000837d  mov     r8, rcx
0x180008380  mov     rcx, rax
0x180008383  test    rax, rax
0x180008386  jnz     short loc_18000837A
0x180008388  mov     [r8], rdx
0x18000838b  retn
```
