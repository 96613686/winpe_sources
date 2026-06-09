# AllocAndCopy(ushort *,ushort * *)

- ea: `0x180006e18`
- end: `0x180006e86`
- name: `?AllocAndCopy@@YAJPEAGPEAPEAG@Z`
- size: `110`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006d4c`
- `0x18000d4b8`
- `0x18000d650`

## callees

- `0x180004120`
- `0x180006e18`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006e66`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006e66`

## pseudocode

```c
__int64 __fastcall AllocAndCopy(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax

  v4 = -2147217407;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  if ( (int)v5 > 0 )
  {
    v7 = (int)v5 + 2;
    v8 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v7, 2u));
    *a2 = v8;
    if ( v8 )
      return (unsigned int)StringCchCopyW(v8, v7, a1);
  }
  return v4;
}

```

## disassembly

```asm
0x180006e18  push    rbx
0x180006e1a  push    rbp
0x180006e1b  push    rsi
0x180006e1c  push    rdi
0x180006e1d  push    r14
0x180006e1f  sub     rsp, 20h
0x180006e23  mov     rdi, rcx
0x180006e26  mov     r14, rdx
0x180006e29  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006e2d  mov     ebx, 80041001h
0x180006e32  mov     rax, rcx
0x180006e35  xor     ebp, ebp
0x180006e37  inc     rax
0x180006e3a  cmp     [rdi+rax*2], bp
0x180006e3e  jnz     short loc_180006E37
0x180006e40  test    eax, eax
0x180006e42  jg      short loc_180006E51
0x180006e44  mov     eax, ebx
0x180006e46  add     rsp, 20h
0x180006e4a  pop     r14
0x180006e4c  pop     rdi
0x180006e4d  pop     rsi
0x180006e4e  pop     rbp
0x180006e4f  pop     rbx
0x180006e50  retn
0x180006e51  add     eax, 2
0x180006e54  movsxd  rsi, eax
0x180006e57  mov     eax, 2
0x180006e5c  mul     rsi
0x180006e5f  cmovb   rax, rcx
0x180006e63  mov     rcx, rax
0x180006e66  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180006e6c  mov     [r14], rax
0x180006e6f  test    rax, rax
0x180006e72  jz      short loc_180006E44
0x180006e74  mov     r8, rdi; unsigned __int16 *
0x180006e77  mov     rdx, rsi; unsigned __int64
0x180006e7a  mov     rcx, rax; unsigned __int16 *
0x180006e7d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006e82  mov     ebx, eax
0x180006e84  jmp     short loc_180006E44
```
