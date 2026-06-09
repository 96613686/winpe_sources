# __memset_repmovs

- ea: `0x140001c80`
- end: `0x140001cc3`
- name: `__memset_repmovs`
- size: `67`
- prototype: `__int64 __fastcall(_OWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b40`

## callees

- `0x140001c80`
- `0x140001d00`

## pseudocode

```c
__int64 __fastcall _memset_repmovs(_OWORD *a1, __int64 a2, __int64 a3)
{
  __int128 v3; // xmm0
  __int64 result; // rax

  if ( (_isa_info & 1) == 0 )
    _memset_query();
  *a1 = v3;
  a1[1] = v3;
  a1[2] = v3;
  a1[3] = v3;
  memset(
    (void *)((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL),
    v3,
    (unsigned __int64)a1 + a3 - ((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL));
  return result;
}

```

## disassembly

```asm
0x140001c80  push    rdi
0x140001c81  test    cs:__isa_info, 1
0x140001c88  jz      short loc_140001CBC
0x140001c8a  mov     rdi, rcx
0x140001c8d  add     r8, rcx
0x140001c90  movups  xmmword ptr [rcx], xmm0
0x140001c93  add     rdi, 40h ; '@'
0x140001c97  movups  xmmword ptr [rcx+10h], xmm0
0x140001c9b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140001c9f  movups  xmmword ptr [rcx+20h], xmm0
0x140001ca3  sub     r8, rdi
0x140001ca6  movups  xmmword ptr [rcx+30h], xmm0
0x140001caa  mov     rcx, r8
0x140001cad  mov     r9, rax
0x140001cb0  movq    rax, xmm0
0x140001cb5  rep stosb
0x140001cb7  mov     rax, r9
0x140001cba  pop     rdi
0x140001cbb  retn
0x140001cbc  call    __memset_query
0x140001cc1  jmp     short loc_140001C8A
```
