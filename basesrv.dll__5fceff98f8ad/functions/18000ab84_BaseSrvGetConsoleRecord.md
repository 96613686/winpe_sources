# BaseSrvGetConsoleRecord

- ea: `0x18000ab84`
- end: `0x18000abad`
- name: `BaseSrvGetConsoleRecord`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180008938`
- `0x18000a194`
- `0x18000abe0`
- `0x18000b500`
- `0x18000b620`
- `0x18000c200`
- `0x18000c2d0`
- `0x18000c434`
- `0x18000c678`

## callees

- `0x18000ab84`

## pseudocode

```c
__int64 __fastcall BaseSrvGetConsoleRecord(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rax

  v2 = DOSHead;
  if ( a1 )
  {
    while ( v2 )
    {
      if ( v2[1] == a1 )
      {
        *a2 = v2;
        return 0;
      }
      v2 = (_QWORD *)*v2;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x18000ab84  mov     rax, cs:DOSHead
0x18000ab8b  test    rcx, rcx
0x18000ab8e  jz      short loc_18000ABA7
0x18000ab90  test    rax, rax
0x18000ab93  jz      short loc_18000ABA7
0x18000ab95  cmp     [rax+8], rcx
0x18000ab99  jz      short loc_18000ABA0
0x18000ab9b  mov     rax, [rax]
0x18000ab9e  jmp     short loc_18000AB90
0x18000aba0  mov     [rdx], rax
0x18000aba3  xor     eax, eax
0x18000aba5  retn
0x18000aba7  mov     eax, 0C000000Dh
0x18000abac  retn
```
