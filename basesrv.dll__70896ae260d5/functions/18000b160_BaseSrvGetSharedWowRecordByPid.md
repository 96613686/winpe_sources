# BaseSrvGetSharedWowRecordByPid

- ea: `0x18000b160`
- end: `0x18000b183`
- name: `BaseSrvGetSharedWowRecordByPid`
- size: `35`
- prototype: `__int64 __fastcall(int, __int64 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083dc`
- `0x180009afc`
- `0x180009da4`

## callees

- `0x18000b160`

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
0x18000b160  mov     rax, cs:gWowHead
0x18000b167  jmp     short loc_18000B171
0x18000b169  cmp     [rax+18h], ecx
0x18000b16c  jz      short loc_18000B17D
0x18000b16e  mov     rax, [rax]
0x18000b171  test    rax, rax
0x18000b174  jnz     short loc_18000B169
0x18000b176  mov     eax, 0C0000225h
0x18000b17b  retn
0x18000b17d  mov     [rdx], rax
0x18000b180  xor     eax, eax
0x18000b182  retn
```
