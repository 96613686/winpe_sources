# wil::details::ResultStringSize(char const *)

- ea: `0x1800056d0`
- end: `0x1800056f3`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `35`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ab50`
- `0x18000c39c`
- `0x18000c4d8`

## callees

- `0x1800056d0`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const char *a2)
{
  __int64 v2; // rax

  if ( !this )
    return 1;
  v2 = -1;
  do
    ++v2;
  while ( *((_BYTE *)this + v2) );
  return v2 + 1;
}

```

## disassembly

```asm
0x1800056d0  test    rcx, rcx
0x1800056d3  jz      short loc_1800056ED
0x1800056d5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800056dc  nop     dword ptr [rax+00h]
0x1800056e0  inc     rax
0x1800056e3  cmp     byte ptr [rcx+rax], 0
0x1800056e7  jnz     short loc_1800056E0
0x1800056e9  inc     rax
0x1800056ec  retn
0x1800056ed  mov     eax, 1
0x1800056f2  retn
```
