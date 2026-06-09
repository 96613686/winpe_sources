# memmove_s

- ea: `0x180010eac`
- end: `0x180010eff`
- name: `memmove_s`
- size: `83`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180007734`
- `0x18000b440`
- `0x18000b518`
- `0x18000bb94`
- `0x18000bef4`
- `0x18001cbc4`
- `0x180020564`
- `0x180020db4`
- `0x180021204`
- `0x1800214e0`

## callees

- `0x180010eac`
- `0x180016956`
- `0x1800264a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010ebf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010edf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010ebf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010edf`

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
      v4 = (errno_t *)_o__errno(Destination, DestinationSize, Source, SourceSize);
      v5 = 22;
LABEL_4:
      *v4 = v5;
      invalid_parameter_noinfo();
      return v5;
    }
    if ( DestinationSize < SourceSize )
    {
      v4 = (errno_t *)_o__errno(Destination, DestinationSize, Source, SourceSize);
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
0x180010eac  push    rbx
0x180010eae  sub     rsp, 20h
0x180010eb2  mov     rax, r8
0x180010eb5  test    r9, r9
0x180010eb8  jz      short loc_180010EF7
0x180010eba  test    rcx, rcx
0x180010ebd  jnz     short loc_180010ED5
0x180010ebf  call    cs:__imp__o__errno
0x180010ec5  mov     ebx, 16h
0x180010eca  mov     [rax], ebx
0x180010ecc  call    _invalid_parameter_noinfo
0x180010ed1  mov     eax, ebx
0x180010ed3  jmp     short loc_180010EF9
0x180010ed5  test    rax, rax
0x180010ed8  jz      short loc_180010EBF
0x180010eda  cmp     rdx, r9
0x180010edd  jnb     short loc_180010EEC
0x180010edf  call    cs:__imp__o__errno
0x180010ee5  mov     ebx, 22h ; '"'
0x180010eea  jmp     short loc_180010ECA
0x180010eec  mov     r8, r9; Size
0x180010eef  mov     rdx, rax; Src
0x180010ef2  call    memmove_0
0x180010ef7  xor     eax, eax
0x180010ef9  add     rsp, 20h
0x180010efd  pop     rbx
0x180010efe  retn
```
