# memmove_s

- ea: `0x14000d6d8`
- end: `0x14000d72b`
- name: `memmove_s`
- size: `83`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c830`
- `0x14000cbd0`

## callees

- `0x140002cd6`
- `0x14000d6d8`
- `0x140029c00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d6eb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d70b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d6eb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d70b`

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
0x14000d6d8  push    rbx
0x14000d6da  sub     rsp, 20h
0x14000d6de  mov     rax, r8
0x14000d6e1  test    r9, r9
0x14000d6e4  jz      short loc_14000D723
0x14000d6e6  test    rcx, rcx
0x14000d6e9  jnz     short loc_14000D701
0x14000d6eb  call    cs:__imp__o__errno
0x14000d6f1  mov     ebx, 16h
0x14000d6f6  mov     [rax], ebx
0x14000d6f8  call    _invalid_parameter_noinfo
0x14000d6fd  mov     eax, ebx
0x14000d6ff  jmp     short loc_14000D725
0x14000d701  test    rax, rax
0x14000d704  jz      short loc_14000D6EB
0x14000d706  cmp     rdx, r9
0x14000d709  jnb     short loc_14000D718
0x14000d70b  call    cs:__imp__o__errno
0x14000d711  mov     ebx, 22h ; '"'
0x14000d716  jmp     short loc_14000D6F6
0x14000d718  mov     r8, r9; Size
0x14000d71b  mov     rdx, rax; Src
0x14000d71e  call    memmove_0
0x14000d723  xor     eax, eax
0x14000d725  add     rsp, 20h
0x14000d729  pop     rbx
0x14000d72a  retn
```
