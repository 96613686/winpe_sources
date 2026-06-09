# wil::details::ResultStringSize(ushort const *)

- ea: `0x18000b300`
- end: `0x18000b321`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008700`
- `0x18000b3cc`
- `0x18000b508`

## callees

- `0x18000b300`

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
0x18000b300  xor     edx, edx
0x18000b302  test    rcx, rcx
0x18000b305  jnz     short loc_18000B30B
0x18000b307  lea     eax, [rdx+2]
0x18000b30a  retn
0x18000b30b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b30f  inc     rax
0x18000b312  cmp     [rcx+rax*2], dx
0x18000b316  jnz     short loc_18000B30F
0x18000b318  lea     rax, ds:2[rax*2]
0x18000b320  retn
```
