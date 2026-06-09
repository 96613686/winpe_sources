# GetConsoleRecordDosSesId

- ea: `0x18000c9c0`
- end: `0x18000c9ee`
- name: `GetConsoleRecordDosSesId`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000abe0`
- `0x18000c434`
- `0x18000c678`

## callees

- `0x18000c9c0`

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
0x18000c9c0  test    ecx, ecx
0x18000c9c2  jz      short loc_18000C9E8
0x18000c9c4  mov     rax, cs:DOSHead
0x18000c9cb  test    rax, rax
0x18000c9ce  jz      short loc_18000C9E8
0x18000c9d0  cmp     qword ptr [rax+8], 0
0x18000c9d5  jnz     short loc_18000C9DC
0x18000c9d7  cmp     [rax+34h], ecx
0x18000c9da  jz      short loc_18000C9E1
0x18000c9dc  mov     rax, [rax]
0x18000c9df  jmp     short loc_18000C9CB
0x18000c9e1  mov     [rdx], rax
0x18000c9e4  xor     eax, eax
0x18000c9e6  retn
0x18000c9e8  mov     eax, 0C000000Dh
0x18000c9ed  retn
```
