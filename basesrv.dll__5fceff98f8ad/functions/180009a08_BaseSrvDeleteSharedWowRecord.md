# BaseSrvDeleteSharedWowRecord

- ea: `0x180009a08`
- end: `0x180009a57`
- name: `BaseSrvDeleteSharedWowRecord`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ed0`
- `0x18000a388`
- `0x18000c000`
- `0x18000c678`
- `0x18000c820`

## callees

- `0x180009a08`
- `0x18000a8f8`

## pseudocode

```c
__int64 __fastcall BaseSrvDeleteSharedWowRecord(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rcx

  if ( a2 )
  {
    v2 = (_QWORD *)gWowHead;
    v3 = 0;
    while ( v2 )
    {
      if ( v2 == a2 )
      {
        if ( v3 )
          *v3 = *a2;
        else
          gWowHead = *a2;
        BaseSrvFreeSharedWowRecord(a2);
        return 0;
      }
      v3 = v2;
      v2 = (_QWORD *)*v2;
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x180009a08  sub     rsp, 28h
0x180009a0c  test    rdx, rdx
0x180009a0f  jz      short loc_180009A2C
0x180009a11  mov     rax, cs:gWowHead
0x180009a18  xor     ecx, ecx
0x180009a1a  jmp     short loc_180009A27
0x180009a1c  cmp     rax, rdx
0x180009a1f  jz      short loc_180009A37
0x180009a21  mov     rcx, rax
0x180009a24  mov     rax, [rax]
0x180009a27  test    rax, rax
0x180009a2a  jnz     short loc_180009A1C
0x180009a2c  mov     eax, 0C0000225h
0x180009a31  add     rsp, 28h
0x180009a35  retn
0x180009a37  mov     rax, [rdx]
0x180009a3a  test    rcx, rcx
0x180009a3d  jnz     short loc_180009A48
0x180009a3f  mov     cs:gWowHead, rax
0x180009a46  jmp     short loc_180009A4B
0x180009a48  mov     [rcx], rax
0x180009a4b  mov     rcx, rdx
0x180009a4e  call    BaseSrvFreeSharedWowRecord
0x180009a53  xor     eax, eax
0x180009a55  jmp     short loc_180009A31
```
