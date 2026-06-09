# memmove_s

- ea: `0x18001484c`
- end: `0x18001489f`
- name: `memmove_s`
- size: `83`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dd5c`

## callees

- `0x18000f48e`
- `0x18001484c`
- `0x180028408`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001485f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001487f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001485f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001487f`

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
0x18001484c  push    rbx
0x18001484e  sub     rsp, 20h
0x180014852  mov     rax, r8
0x180014855  test    r9, r9
0x180014858  jz      short loc_180014897
0x18001485a  test    rcx, rcx
0x18001485d  jnz     short loc_180014875
0x18001485f  call    cs:__imp__o__errno
0x180014865  mov     ebx, 16h
0x18001486a  mov     [rax], ebx
0x18001486c  call    _invalid_parameter_noinfo
0x180014871  mov     eax, ebx
0x180014873  jmp     short loc_180014899
0x180014875  test    rax, rax
0x180014878  jz      short loc_18001485F
0x18001487a  cmp     rdx, r9
0x18001487d  jnb     short loc_18001488C
0x18001487f  call    cs:__imp__o__errno
0x180014885  mov     ebx, 22h ; '"'
0x18001488a  jmp     short loc_18001486A
0x18001488c  mov     r8, r9; Size
0x18001488f  mov     rdx, rax; Src
0x180014892  call    memmove_0
0x180014897  xor     eax, eax
0x180014899  add     rsp, 20h
0x18001489d  pop     rbx
0x18001489e  retn
```
