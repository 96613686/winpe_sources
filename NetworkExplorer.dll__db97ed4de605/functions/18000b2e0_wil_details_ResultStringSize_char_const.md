# wil::details::ResultStringSize(char const *)

- ea: `0x18000b2e0`
- end: `0x18000b2fa`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008688`
- `0x18000b3cc`
- `0x18000b508`

## callees

- `0x18000b2e0`

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
0x18000b2e0  test    rcx, rcx
0x18000b2e3  jnz     short loc_18000B2E9
0x18000b2e5  lea     eax, [rcx+1]
0x18000b2e8  retn
0x18000b2e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b2ed  inc     rax
0x18000b2f0  cmp     byte ptr [rcx+rax], 0
0x18000b2f4  jnz     short loc_18000B2ED
0x18000b2f6  inc     rax
0x18000b2f9  retn
```
