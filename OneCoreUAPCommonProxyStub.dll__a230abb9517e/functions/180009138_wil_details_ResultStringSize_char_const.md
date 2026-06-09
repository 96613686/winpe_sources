# wil::details::ResultStringSize(char const *)

- ea: `0x180009138`
- end: `0x180009152`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800068a4`
- `0x18000923c`
- `0x180009378`

## callees

- `0x180009138`

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
0x180009138  test    rcx, rcx
0x18000913b  jnz     short loc_180009141
0x18000913d  lea     eax, [rcx+1]
0x180009140  retn
0x180009141  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009145  inc     rax
0x180009148  cmp     byte ptr [rcx+rax], 0
0x18000914c  jnz     short loc_180009145
0x18000914e  inc     rax
0x180009151  retn
```
