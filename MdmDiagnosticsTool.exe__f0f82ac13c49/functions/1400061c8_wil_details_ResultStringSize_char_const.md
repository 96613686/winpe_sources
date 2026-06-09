# wil::details::ResultStringSize(char const *)

- ea: `0x1400061c8`
- end: `0x1400061e2`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details *this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002c64`
- `0x1400062cc`
- `0x140006408`

## callees

- `0x1400061c8`

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
0x1400061c8  test    rcx, rcx
0x1400061cb  jnz     short loc_1400061D1
0x1400061cd  lea     eax, [rcx+1]
0x1400061d0  retn
0x1400061d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400061d5  inc     rax
0x1400061d8  cmp     byte ptr [rcx+rax], 0
0x1400061dc  jnz     short loc_1400061D5
0x1400061de  inc     rax
0x1400061e1  retn
```
