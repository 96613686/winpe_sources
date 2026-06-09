# GetConsoleRecordDosSesId

- ea: `0x18000c5e4`
- end: `0x18000c612`
- name: `GetConsoleRecordDosSesId`
- size: `46`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000a960`
- `0x18000c088`
- `0x18000c2a4`

## callees

- `0x18000c5e4`

## pseudocode

```c
__int64 __fastcall GetConsoleRecordDosSesId(int a1, _QWORD *a2)
{
  _QWORD *i; // rax

  if ( a1 )
  {
    for ( i = DOSHead; i; i = (_QWORD *)*i )
    {
      if ( !i[1] && *((_DWORD *)i + 13) == a1 )
      {
        *a2 = i;
        return 0;
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x18000c5e4  test    ecx, ecx
0x18000c5e6  jz      short loc_18000C60C
0x18000c5e8  mov     rax, cs:DOSHead
0x18000c5ef  test    rax, rax
0x18000c5f2  jz      short loc_18000C60C
0x18000c5f4  cmp     qword ptr [rax+8], 0
0x18000c5f9  jnz     short loc_18000C600
0x18000c5fb  cmp     [rax+34h], ecx
0x18000c5fe  jz      short loc_18000C605
0x18000c600  mov     rax, [rax]
0x18000c603  jmp     short loc_18000C5EF
0x18000c605  mov     [rdx], rax
0x18000c608  xor     eax, eax
0x18000c60a  retn
0x18000c60c  mov     eax, 0C000000Dh
0x18000c611  retn
```
