# wil::details::ResultStringSize(char const *)

- ea: `0x1800073e0`
- end: `0x1800073fa`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details *this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fac`
- `0x180007570`
- `0x180007798`

## callees

- `0x1800073e0`

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
0x1800073e0  test    rcx, rcx
0x1800073e3  jnz     short loc_1800073E9
0x1800073e5  lea     eax, [rcx+1]
0x1800073e8  retn
0x1800073e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800073ed  inc     rax
0x1800073f0  cmp     byte ptr [rcx+rax], 0
0x1800073f4  jnz     short loc_1800073ED
0x1800073f6  inc     rax
0x1800073f9  retn
```
