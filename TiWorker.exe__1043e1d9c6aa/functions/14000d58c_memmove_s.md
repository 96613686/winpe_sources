# memmove_s

- ea: `0x14000d58c`
- end: `0x14000d5df`
- name: `memmove_s`
- size: `83`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c0f8`

## callees

- `0x140002c2e`
- `0x14000d58c`
- `0x14002ad04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d59f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d5bf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d59f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d5bf`

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
0x14000d58c  push    rbx
0x14000d58e  sub     rsp, 20h
0x14000d592  mov     rax, r8
0x14000d595  test    r9, r9
0x14000d598  jz      short loc_14000D5D7
0x14000d59a  test    rcx, rcx
0x14000d59d  jnz     short loc_14000D5B5
0x14000d59f  call    cs:__imp__o__errno
0x14000d5a5  mov     ebx, 16h
0x14000d5aa  mov     [rax], ebx
0x14000d5ac  call    _invalid_parameter_noinfo
0x14000d5b1  mov     eax, ebx
0x14000d5b3  jmp     short loc_14000D5D9
0x14000d5b5  test    rax, rax
0x14000d5b8  jz      short loc_14000D59F
0x14000d5ba  cmp     rdx, r9
0x14000d5bd  jnb     short loc_14000D5CC
0x14000d5bf  call    cs:__imp__o__errno
0x14000d5c5  mov     ebx, 22h ; '"'
0x14000d5ca  jmp     short loc_14000D5AA
0x14000d5cc  mov     r8, r9; Size
0x14000d5cf  mov     rdx, rax; Src
0x14000d5d2  call    memmove_0
0x14000d5d7  xor     eax, eax
0x14000d5d9  add     rsp, 20h
0x14000d5dd  pop     rbx
0x14000d5de  retn
```
