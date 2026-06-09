# wil::details::ResultStringSize(char const *)

- ea: `0x180004d58`
- end: `0x180004d73`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `27`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b40`
- `0x180004e6c`
- `0x180004fb8`

## callees

- `0x180004d58`

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
0x180004d58  test    rcx, rcx
0x180004d5b  jnz     short loc_180004D62
0x180004d5d  lea     eax, [rcx+1]
0x180004d60  retn
0x180004d62  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d66  inc     rax
0x180004d69  cmp     byte ptr [rcx+rax], 0
0x180004d6d  jnz     short loc_180004D66
0x180004d6f  inc     rax
0x180004d72  retn
```
