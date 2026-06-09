# wil::details::ResultStringSize(ushort const *)

- ea: `0x180007400`
- end: `0x180007421`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(wil::details *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003024`
- `0x180007570`
- `0x180007798`

## callees

- `0x180007400`

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
0x180007400  xor     edx, edx
0x180007402  test    rcx, rcx
0x180007405  jnz     short loc_18000740B
0x180007407  lea     eax, [rdx+2]
0x18000740a  retn
0x18000740b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000740f  inc     rax
0x180007412  cmp     [rcx+rax*2], dx
0x180007416  jnz     short loc_18000740F
0x180007418  lea     rax, ds:2[rax*2]
0x180007420  retn
```
