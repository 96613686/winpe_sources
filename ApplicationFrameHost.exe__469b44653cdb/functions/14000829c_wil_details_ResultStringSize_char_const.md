# wil::details::ResultStringSize(char const *)

- ea: `0x14000829c`
- end: `0x1400082b6`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400049a0`
- `0x1400083f0`
- `0x140008608`

## callees

- `0x14000829c`

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
0x14000829c  test    rcx, rcx
0x14000829f  jnz     short loc_1400082A5
0x1400082a1  lea     eax, [rcx+1]
0x1400082a4  retn
0x1400082a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400082a9  inc     rax
0x1400082ac  cmp     byte ptr [rcx+rax], 0
0x1400082b0  jnz     short loc_1400082A9
0x1400082b2  inc     rax
0x1400082b5  retn
```
