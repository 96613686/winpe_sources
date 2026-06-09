# memmove_s

- ea: `0x1800116e4`
- end: `0x180011744`
- name: `memmove_s`
- size: `96`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180008a74`
- `0x18000b994`
- `0x18000ba70`
- `0x18000c124`
- `0x18000c49c`
- `0x18001d958`
- `0x1800215a8`
- `0x180021e30`
- `0x1800222b4`
- `0x1800225b0`

## callees

- `0x1800116e4`
- `0x1800173a6`
- `0x180027754`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800116f7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001171d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800116f7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001171d`

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
0x1800116e4  push    rbx
0x1800116e6  sub     rsp, 20h
0x1800116ea  mov     rax, r8
0x1800116ed  test    r9, r9
0x1800116f0  jz      short loc_18001173B
0x1800116f2  test    rcx, rcx
0x1800116f5  jnz     short loc_180011713
0x1800116f7  call    cs:__imp__o__errno
0x1800116fe  nop     dword ptr [rax+rax+00h]
0x180011703  mov     ebx, 16h
0x180011708  mov     [rax], ebx
0x18001170a  call    _invalid_parameter_noinfo
0x18001170f  mov     eax, ebx
0x180011711  jmp     short loc_18001173D
0x180011713  test    rax, rax
0x180011716  jz      short loc_1800116F7
0x180011718  cmp     rdx, r9
0x18001171b  jnb     short loc_180011730
0x18001171d  call    cs:__imp__o__errno
0x180011724  nop     dword ptr [rax+rax+00h]
0x180011729  mov     ebx, 22h ; '"'
0x18001172e  jmp     short loc_180011708
0x180011730  mov     r8, r9; Size
0x180011733  mov     rdx, rax; Src
0x180011736  call    memmove_0
0x18001173b  xor     eax, eax
0x18001173d  add     rsp, 20h
0x180011741  pop     rbx
0x180011742  retn
```
