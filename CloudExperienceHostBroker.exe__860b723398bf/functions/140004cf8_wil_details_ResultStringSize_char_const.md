# wil::details::ResultStringSize(char const *)

- ea: `0x140004cf8`
- end: `0x140004d12`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details *this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002ef0`
- `0x140004ddc`
- `0x140004f18`

## callees

- `0x140004cf8`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const char *a2)
{
  __int64 v3; // rax

  if ( !this )
    return 1;
  v3 = -1;
  do
    ++v3;
  while ( *((_BYTE *)this + v3) );
  return v3 + 1;
}

```

## disassembly

```asm
0x140004cf8  test    rcx, rcx
0x140004cfb  jnz     short loc_140004D01
0x140004cfd  lea     eax, [rcx+1]
0x140004d00  retn
0x140004d01  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004d05  inc     rax
0x140004d08  cmp     byte ptr [rcx+rax], 0
0x140004d0c  jnz     short loc_140004D05
0x140004d0e  inc     rax
0x140004d11  retn
```
