# BaseSrvGetConsoleRecordByPid

- ea: `0x18000abb4`
- end: `0x18000abd7`
- name: `BaseSrvGetConsoleRecordByPid`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800086cc`
- `0x180009de8`
- `0x18000a090`

## callees

- `0x18000abb4`

## pseudocode

```c
__int64 __fastcall BaseSrvGetConsoleRecordByPid(int a1, _QWORD *a2)
{
  _DWORD *i; // rax

  for ( i = DOSHead; i; i = *(_DWORD **)i )
  {
    if ( i[14] == a1 )
    {
      *a2 = i;
      return 0;
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x18000abb4  mov     rax, cs:DOSHead
0x18000abbb  test    rax, rax
0x18000abbe  jz      short loc_18000ABD1
0x18000abc0  cmp     [rax+38h], ecx
0x18000abc3  jz      short loc_18000ABCA
0x18000abc5  mov     rax, [rax]
0x18000abc8  jmp     short loc_18000ABBB
0x18000abca  mov     [rdx], rax
0x18000abcd  xor     eax, eax
0x18000abcf  retn
0x18000abd1  mov     eax, 0C0000225h
0x18000abd6  retn
```
