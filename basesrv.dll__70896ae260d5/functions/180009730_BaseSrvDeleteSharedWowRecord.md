# BaseSrvDeleteSharedWowRecord

- ea: `0x180009730`
- end: `0x18000977f`
- name: `BaseSrvDeleteSharedWowRecord`
- size: `79`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005c70`
- `0x18000a0a0`
- `0x18000bd20`
- `0x18000c2a4`
- `0x18000c454`

## callees

- `0x180009730`
- `0x18000a674`

## pseudocode

```c
__int64 __fastcall BaseSrvDeleteSharedWowRecord(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rcx
  _QWORD *i; // rax

  v2 = 0;
  if ( a2 )
  {
    for ( i = (_QWORD *)gWowHead; i; i = (_QWORD *)*i )
    {
      if ( i == a2 )
      {
        if ( v2 )
          *v2 = *a2;
        else
          gWowHead = *a2;
        BaseSrvFreeSharedWowRecord(a2);
        return 0;
      }
      v2 = i;
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x180009730  sub     rsp, 28h
0x180009734  xor     ecx, ecx
0x180009736  test    rdx, rdx
0x180009739  jz      short loc_180009754
0x18000973b  mov     rax, cs:gWowHead
0x180009742  jmp     short loc_18000974F
0x180009744  cmp     rax, rdx
0x180009747  jz      short loc_18000975F
0x180009749  mov     rcx, rax
0x18000974c  mov     rax, [rax]
0x18000974f  test    rax, rax
0x180009752  jnz     short loc_180009744
0x180009754  mov     eax, 0C0000225h
0x180009759  add     rsp, 28h
0x18000975d  retn
0x18000975f  mov     rax, [rdx]
0x180009762  test    rcx, rcx
0x180009765  jnz     short loc_180009770
0x180009767  mov     cs:gWowHead, rax
0x18000976e  jmp     short loc_180009773
0x180009770  mov     [rcx], rax
0x180009773  mov     rcx, rdx
0x180009776  call    BaseSrvFreeSharedWowRecord
0x18000977b  xor     eax, eax
0x18000977d  jmp     short loc_180009759
```
