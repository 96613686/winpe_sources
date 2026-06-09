# wil::details::ResultStringSize(ushort const *)

- ea: `0x140004d18`
- end: `0x140004d39`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(wil::details *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f68`
- `0x140004ddc`
- `0x140004f18`

## callees

- `0x140004d18`

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
0x140004d18  xor     edx, edx
0x140004d1a  test    rcx, rcx
0x140004d1d  jnz     short loc_140004D23
0x140004d1f  lea     eax, [rdx+2]
0x140004d22  retn
0x140004d23  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004d27  inc     rax
0x140004d2a  cmp     [rcx+rax*2], dx
0x140004d2e  jnz     short loc_140004D27
0x140004d30  lea     rax, ds:2[rax*2]
0x140004d38  retn
```
