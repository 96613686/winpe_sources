# BaseSrvGetConsoleRecordByPid

- ea: `0x18000a92c`
- end: `0x18000a94f`
- name: `BaseSrvGetConsoleRecordByPid`
- size: `35`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083dc`
- `0x180009afc`
- `0x180009da4`

## callees

- `0x18000a92c`

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
0x18000a92c  mov     rax, cs:DOSHead
0x18000a933  test    rax, rax
0x18000a936  jz      short loc_18000A949
0x18000a938  cmp     [rax+38h], ecx
0x18000a93b  jz      short loc_18000A942
0x18000a93d  mov     rax, [rax]
0x18000a940  jmp     short loc_18000A933
0x18000a942  mov     [rdx], rax
0x18000a945  xor     eax, eax
0x18000a947  retn
0x18000a949  mov     eax, 0C0000225h
0x18000a94e  retn
```
