# memmove_s

- ea: `0x18000b4cc`
- end: `0x18000b51f`
- name: `memmove_s`
- size: `83`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008428`

## callees

- `0x18000281a`
- `0x18000b4cc`
- `0x18001007c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b4df`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b4ff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b4df`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b4ff`

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
0x18000b4cc  push    rbx
0x18000b4ce  sub     rsp, 20h
0x18000b4d2  mov     rax, r8
0x18000b4d5  test    r9, r9
0x18000b4d8  jz      short loc_18000B517
0x18000b4da  test    rcx, rcx
0x18000b4dd  jnz     short loc_18000B4F5
0x18000b4df  call    cs:__imp__o__errno
0x18000b4e5  mov     ebx, 16h
0x18000b4ea  mov     [rax], ebx
0x18000b4ec  call    _invalid_parameter_noinfo
0x18000b4f1  mov     eax, ebx
0x18000b4f3  jmp     short loc_18000B519
0x18000b4f5  test    rax, rax
0x18000b4f8  jz      short loc_18000B4DF
0x18000b4fa  cmp     rdx, r9
0x18000b4fd  jnb     short loc_18000B50C
0x18000b4ff  call    cs:__imp__o__errno
0x18000b505  mov     ebx, 22h ; '"'
0x18000b50a  jmp     short loc_18000B4EA
0x18000b50c  mov     r8, r9; Size
0x18000b50f  mov     rdx, rax; Src
0x18000b512  call    memmove_0
0x18000b517  xor     eax, eax
0x18000b519  add     rsp, 20h
0x18000b51d  pop     rbx
0x18000b51e  retn
```
