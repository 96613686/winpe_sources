# STRW::Append(ushort const *)

- ea: `0x180009578`
- end: `0x18000959f`
- name: `?Append@STRW@@QEAAJPEBG@Z`
- size: `39`
- prototype: `__int64 __fastcall(STRW *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180009834`
- `0x18000a220`
- `0x1800120c8`

## callees

- `0x180009578`
- `0x180011f30`

## pseudocode

```c
int __fastcall STRW::Append(STRW *this, const unsigned __int16 *a2)
{
  int result; // eax
  unsigned __int64 v3; // r8

  result = 0;
  if ( a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
    return STRW::Append(this, a2, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180009578  sub     rsp, 28h
0x18000957c  xor     r9d, r9d
0x18000957f  mov     eax, r9d
0x180009582  test    rdx, rdx
0x180009585  jz      short loc_18000959A
0x180009587  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000958b  inc     r8; unsigned __int64
0x18000958e  cmp     [rdx+r8*2], r9w
0x180009593  jnz     short loc_18000958B
0x180009595  call    ?Append@STRW@@QEAAJPEBG_K@Z; STRW::Append(ushort const *,unsigned __int64)
0x18000959a  add     rsp, 28h
0x18000959e  retn
```
