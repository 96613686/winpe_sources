# BaseSrvGetSharedWowRecordByPid

- ea: `0x18000b400`
- end: `0x18000b423`
- name: `BaseSrvGetSharedWowRecordByPid`
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

- `0x18000b400`

## pseudocode

```c
__int64 __fastcall BaseSrvGetSharedWowRecordByPid(int a1, __int64 *a2)
{
  __int64 i; // rax

  for ( i = gWowHead; ; i = *(_QWORD *)i )
  {
    if ( !i )
      return 3221226021LL;
    if ( *(_DWORD *)(i + 24) == a1 )
      break;
  }
  *a2 = i;
  return 0;
}

```

## disassembly

```asm
0x18000b400  mov     rax, cs:gWowHead
0x18000b407  jmp     short loc_18000B411
0x18000b409  cmp     [rax+18h], ecx
0x18000b40c  jz      short loc_18000B41D
0x18000b40e  mov     rax, [rax]
0x18000b411  test    rax, rax
0x18000b414  jnz     short loc_18000B409
0x18000b416  mov     eax, 0C0000225h
0x18000b41b  retn
0x18000b41d  mov     [rdx], rax
0x18000b420  xor     eax, eax
0x18000b422  retn
```
