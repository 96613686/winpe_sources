# BaseSrvGetConsoleRecord

- ea: `0x18000a8fc`
- end: `0x18000a925`
- name: `BaseSrvGetConsoleRecord`
- size: `41`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180008644`
- `0x180009e9c`
- `0x18000a960`
- `0x18000b260`
- `0x18000b380`
- `0x18000be80`
- `0x18000bf40`
- `0x18000c088`
- `0x18000c2a4`

## callees

- `0x18000a8fc`

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
0x18000a8fc  mov     rax, cs:DOSHead
0x18000a903  test    rcx, rcx
0x18000a906  jz      short loc_18000A91F
0x18000a908  test    rax, rax
0x18000a90b  jz      short loc_18000A91F
0x18000a90d  cmp     [rax+8], rcx
0x18000a911  jz      short loc_18000A918
0x18000a913  mov     rax, [rax]
0x18000a916  jmp     short loc_18000A908
0x18000a918  mov     [rdx], rax
0x18000a91b  xor     eax, eax
0x18000a91d  retn
0x18000a91f  mov     eax, 0C000000Dh
0x18000a924  retn
```
