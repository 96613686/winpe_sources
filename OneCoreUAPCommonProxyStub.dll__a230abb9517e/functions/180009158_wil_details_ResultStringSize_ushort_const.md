# wil::details::ResultStringSize(ushort const *)

- ea: `0x180009158`
- end: `0x180009179`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000691c`
- `0x18000923c`
- `0x180009378`

## callees

- `0x180009158`

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
0x180009158  xor     edx, edx
0x18000915a  test    rcx, rcx
0x18000915d  jnz     short loc_180009163
0x18000915f  lea     eax, [rdx+2]
0x180009162  retn
0x180009163  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009167  inc     rax
0x18000916a  cmp     [rcx+rax*2], dx
0x18000916e  jnz     short loc_180009167
0x180009170  lea     rax, ds:2[rax*2]
0x180009178  retn
```
