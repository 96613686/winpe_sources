# wil::details::ResultStringSize(char const *)

- ea: `0x140006558`
- end: `0x140006573`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `27`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002cd8`
- `0x14000667c`
- `0x1400067c8`

## callees

- `0x140006558`

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
0x140006558  test    rcx, rcx
0x14000655b  jnz     short loc_140006562
0x14000655d  lea     eax, [rcx+1]
0x140006560  retn
0x140006562  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006566  inc     rax
0x140006569  cmp     byte ptr [rcx+rax], 0
0x14000656d  jnz     short loc_140006566
0x14000656f  inc     rax
0x140006572  retn
```
