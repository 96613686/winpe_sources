# wil::details::ResultStringSize(ushort const *)

- ea: `0x1400082bc`
- end: `0x1400082dd`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004a18`
- `0x1400083f0`
- `0x140008608`

## callees

- `0x1400082bc`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax

  if ( !this )
    return 2;
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)this + v3) );
  return 2 * v3 + 2;
}

```

## disassembly

```asm
0x1400082bc  xor     edx, edx
0x1400082be  test    rcx, rcx
0x1400082c1  jnz     short loc_1400082C7
0x1400082c3  lea     eax, [rdx+2]
0x1400082c6  retn
0x1400082c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400082cb  inc     rax
0x1400082ce  cmp     [rcx+rax*2], dx
0x1400082d2  jnz     short loc_1400082CB
0x1400082d4  lea     rax, ds:2[rax*2]
0x1400082dc  retn
```
