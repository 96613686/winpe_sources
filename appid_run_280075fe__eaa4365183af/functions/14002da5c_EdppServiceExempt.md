# EdppServiceExempt

- ea: `0x14002da5c`
- end: `0x14002da92`
- name: `EdppServiceExempt`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140003ec0`

## callees

- `0x14002da5c`
- `0x140032e40`

## pseudocode

```c
__int64 __fastcall EdppServiceExempt(__int64 a1, BOOLEAN *a2)
{
  _QWORD *v2; // r8
  __int64 result; // rax

  v2 = *(_QWORD **)(a1 + 72);
  *a2 = 0;
  result = *v2 - 0x4896EF1A58125A50LL;
  if ( *v2 == 0x4896EF1A58125A50LL )
    result = v2[1] - 0x6CCAB39AC6D657BALL;
  if ( result )
    return SrpIsTokenService(*(void **)(a1 + 48), a2);
  return result;
}

```

## disassembly

```asm
0x14002da5c  sub     rsp, 28h
0x14002da60  mov     r8, [rcx+48h]
0x14002da64  mov     byte ptr [rdx], 0
0x14002da67  mov     rax, [r8]
0x14002da6a  sub     rax, cs:qword_14000DFF0
0x14002da71  jnz     short loc_14002DA7E
0x14002da73  mov     rax, [r8+8]
0x14002da77  sub     rax, cs:qword_14000DFF8
0x14002da7e  test    rax, rax
0x14002da81  jz      short loc_14002DA8C
0x14002da83  mov     rcx, [rcx+30h]
0x14002da87  call    SrpIsTokenService
0x14002da8c  add     rsp, 28h
0x14002da90  retn
```
