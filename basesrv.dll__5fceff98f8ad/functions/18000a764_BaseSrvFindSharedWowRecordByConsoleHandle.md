# BaseSrvFindSharedWowRecordByConsoleHandle

- ea: `0x18000a764`
- end: `0x18000a788`
- name: `BaseSrvFindSharedWowRecordByConsoleHandle`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a388`
- `0x18000abe0`
- `0x18000c000`
- `0x18000c678`

## callees

- `0x18000a764`

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
0x18000a764  mov     rax, cs:gWowHead
0x18000a76b  test    rax, rax
0x18000a76e  jz      short loc_18000A782
0x18000a770  cmp     [rax+8], rdx
0x18000a774  jz      short loc_18000A77B
0x18000a776  mov     rax, [rax]
0x18000a779  jmp     short loc_18000A76B
0x18000a77b  mov     [r8], rax
0x18000a77e  xor     eax, eax
0x18000a780  retn
0x18000a782  mov     eax, 0C0000225h
0x18000a787  retn
```
