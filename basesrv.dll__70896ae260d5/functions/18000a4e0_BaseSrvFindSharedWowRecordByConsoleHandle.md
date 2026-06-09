# BaseSrvFindSharedWowRecordByConsoleHandle

- ea: `0x18000a4e0`
- end: `0x18000a504`
- name: `BaseSrvFindSharedWowRecordByConsoleHandle`
- size: `36`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a0a0`
- `0x18000a960`
- `0x18000bd20`
- `0x18000c2a4`

## callees

- `0x18000a4e0`

## pseudocode

```c
__int64 __fastcall BaseSrvFindSharedWowRecordByConsoleHandle(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *i; // rax

  for ( i = (_QWORD *)gWowHead; i; i = (_QWORD *)*i )
  {
    if ( i[1] == a2 )
    {
      *a3 = i;
      return 0;
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x18000a4e0  mov     rax, cs:gWowHead
0x18000a4e7  test    rax, rax
0x18000a4ea  jz      short loc_18000A4FE
0x18000a4ec  cmp     [rax+8], rdx
0x18000a4f0  jz      short loc_18000A4F7
0x18000a4f2  mov     rax, [rax]
0x18000a4f5  jmp     short loc_18000A4E7
0x18000a4f7  mov     [r8], rax
0x18000a4fa  xor     eax, eax
0x18000a4fc  retn
0x18000a4fe  mov     eax, 0C0000225h
0x18000a503  retn
```
