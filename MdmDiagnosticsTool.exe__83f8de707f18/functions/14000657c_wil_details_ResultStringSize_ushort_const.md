# wil::details::ResultStringSize(ushort const *)

- ea: `0x14000657c`
- end: `0x14000659e`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `34`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002d58`
- `0x14000667c`
- `0x1400067c8`

## callees

- `0x14000657c`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax

  if ( !this )
    return 2;
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)this + v3) );
  return 2 * v3 + 2;
}

```

## disassembly

```asm
0x14000657c  xor     edx, edx
0x14000657e  test    rcx, rcx
0x140006581  jnz     short loc_140006588
0x140006583  lea     eax, [rdx+2]
0x140006586  retn
0x140006588  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000658c  inc     rax
0x14000658f  cmp     [rcx+rax*2], dx
0x140006593  jnz     short loc_14000658C
0x140006595  lea     rax, ds:2[rax*2]
0x14000659d  retn
```
