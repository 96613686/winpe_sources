# wil::details::ResultStringSize(char const *)

- ea: `0x140004090`
- end: `0x1400040aa`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details *this, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002728`
- `0x1400042b8`

## callees

- `0x140004090`

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
0x140004090  test    rcx, rcx
0x140004093  jnz     short loc_140004099
0x140004095  lea     eax, [rcx+1]
0x140004098  retn
0x140004099  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000409d  inc     rax
0x1400040a0  cmp     byte ptr [rcx+rax], 0
0x1400040a4  jnz     short loc_14000409D
0x1400040a6  inc     rax
0x1400040a9  retn
```
