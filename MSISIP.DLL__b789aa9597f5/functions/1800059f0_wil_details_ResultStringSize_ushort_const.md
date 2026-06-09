# wil::details::ResultStringSize(ushort const *)

- ea: `0x1800059f0`
- end: `0x180005a1b`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `43`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000abc8`
- `0x18000c39c`
- `0x18000c4d8`

## callees

- `0x1800059f0`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const unsigned __int16 *a2)
{
  __int64 v2; // rax

  if ( !this )
    return 2;
  v2 = -1;
  while ( *((_WORD *)this + ++v2) != 0 )
    ;
  return 2 * v2 + 2;
}

```

## disassembly

```asm
0x1800059f0  test    rcx, rcx
0x1800059f3  jz      short loc_180005A15
0x1800059f5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800059fc  nop     dword ptr [rax+00h]
0x180005a00  cmp     word ptr [rcx+rax*2+2], 0
0x180005a06  lea     rax, [rax+1]
0x180005a0a  jnz     short loc_180005A00
0x180005a0c  lea     rax, ds:2[rax*2]
0x180005a14  retn
0x180005a15  mov     eax, 2
0x180005a1a  retn
```
