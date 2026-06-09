# wil::details::ResultStringSize(char const *)

- ea: `0x140005edc`
- end: `0x140005ef6`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details *this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002950`
- `0x140006070`
- `0x14000629c`

## callees

- `0x140005edc`

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
0x140005edc  test    rcx, rcx
0x140005edf  jnz     short loc_140005EE5
0x140005ee1  lea     eax, [rcx+1]
0x140005ee4  retn
0x140005ee5  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005ee9  inc     rax
0x140005eec  cmp     byte ptr [rcx+rax], 0
0x140005ef0  jnz     short loc_140005EE9
0x140005ef2  inc     rax
0x140005ef5  retn
```
