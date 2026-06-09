# wil::details::ResultStringSize(ushort const *)

- ea: `0x1400061e8`
- end: `0x140006209`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(wil::details *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002cdc`
- `0x1400062cc`
- `0x140006408`

## callees

- `0x1400061e8`

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
0x1400061e8  xor     edx, edx
0x1400061ea  test    rcx, rcx
0x1400061ed  jnz     short loc_1400061F3
0x1400061ef  lea     eax, [rdx+2]
0x1400061f2  retn
0x1400061f3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400061f7  inc     rax
0x1400061fa  cmp     [rcx+rax*2], dx
0x1400061fe  jnz     short loc_1400061F7
0x140006200  lea     rax, ds:2[rax*2]
0x140006208  retn
```
