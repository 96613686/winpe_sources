# wil::details::ResultStringSize(ushort const *)

- ea: `0x180004d7c`
- end: `0x180004d9e`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `34`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bc0`
- `0x180004e6c`
- `0x180004fb8`

## callees

- `0x180004d7c`

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
0x180004d7c  xor     edx, edx
0x180004d7e  test    rcx, rcx
0x180004d81  jnz     short loc_180004D88
0x180004d83  lea     eax, [rdx+2]
0x180004d86  retn
0x180004d88  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d8c  inc     rax
0x180004d8f  cmp     [rcx+rax*2], dx
0x180004d93  jnz     short loc_180004D8C
0x180004d95  lea     rax, ds:2[rax*2]
0x180004d9d  retn
```
