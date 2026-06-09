# wil::details::ResultStringSize(ushort const *)

- ea: `0x140005efc`
- end: `0x140005f1d`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(wil::details *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400029c8`
- `0x140006070`
- `0x14000629c`

## callees

- `0x140005efc`

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
0x140005efc  xor     edx, edx
0x140005efe  test    rcx, rcx
0x140005f01  jnz     short loc_140005F07
0x140005f03  lea     eax, [rdx+2]
0x140005f06  retn
0x140005f07  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005f0b  inc     rax
0x140005f0e  cmp     [rcx+rax*2], dx
0x140005f12  jnz     short loc_140005F0B
0x140005f14  lea     rax, ds:2[rax*2]
0x140005f1c  retn
```
