# memmove_s

- ea: `0x140011c44`
- end: `0x140011c97`
- name: `memmove_s`
- size: `83`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cca8`

## callees

- `0x1400033ee`
- `0x140011c44`
- `0x14001864c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140011c57`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140011c77`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140011c57`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140011c77`

## pseudocode

```c
errno_t __cdecl memmove_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  errno_t *v4; // rax
  errno_t v5; // ebx

  if ( SourceSize )
  {
    if ( !Destination || !Source )
    {
      v4 = (errno_t *)_o__errno(Destination, DestinationSize);
      v5 = 22;
LABEL_4:
      *v4 = v5;
      invalid_parameter_noinfo();
      return v5;
    }
    if ( DestinationSize < SourceSize )
    {
      v4 = (errno_t *)((__int64 (*)(void))_o__errno)();
      v5 = 34;
      goto LABEL_4;
    }
    memmove_0(Destination, Source, SourceSize);
  }
  return 0;
}

```

## disassembly

```asm
0x140011c44  push    rbx
0x140011c46  sub     rsp, 20h
0x140011c4a  mov     rax, r8
0x140011c4d  test    r9, r9
0x140011c50  jz      short loc_140011C8F
0x140011c52  test    rcx, rcx
0x140011c55  jnz     short loc_140011C6D
0x140011c57  call    cs:__imp__o__errno
0x140011c5d  mov     ebx, 16h
0x140011c62  mov     [rax], ebx
0x140011c64  call    _invalid_parameter_noinfo
0x140011c69  mov     eax, ebx
0x140011c6b  jmp     short loc_140011C91
0x140011c6d  test    rax, rax
0x140011c70  jz      short loc_140011C57
0x140011c72  cmp     rdx, r9
0x140011c75  jnb     short loc_140011C84
0x140011c77  call    cs:__imp__o__errno
0x140011c7d  mov     ebx, 22h ; '"'
0x140011c82  jmp     short loc_140011C62
0x140011c84  mov     r8, r9; Size
0x140011c87  mov     rdx, rax; Src
0x140011c8a  call    memmove_0
0x140011c8f  xor     eax, eax
0x140011c91  add     rsp, 20h
0x140011c95  pop     rbx
0x140011c96  retn
```
