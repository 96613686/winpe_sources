# memcpy_s

- ea: `0x14000bfd0`
- end: `0x14000c05a`
- name: `memcpy_s`
- size: `138`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140008cf0`
- `0x14000a5c4`
- `0x14000a8e8`
- `0x14000b960`
- `0x14000bb9c`

## callees

- `0x1400022ec`
- `0x14000bfd0`
- `0x14000fa80`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000c003`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000c003`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000bff6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000c038`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000bff6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000c038`

## pseudocode

```c
errno_t __cdecl memcpy_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  int *v8; // rax
  errno_t v9; // ebx

  if ( !SourceSize )
    return 0;
  if ( !Destination )
    goto LABEL_4;
  if ( Source && DestinationSize >= SourceSize )
  {
    memcpy_0(Destination, Source, SourceSize);
    return 0;
  }
  memset_0(Destination, 0, DestinationSize);
  if ( !Source )
  {
LABEL_4:
    v8 = _errno();
    v9 = 22;
LABEL_5:
    *v8 = v9;
    _invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = _errno();
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x14000bfd0  mov     [rsp+arg_0], rbx
0x14000bfd5  mov     [rsp+arg_8], rsi
0x14000bfda  push    rdi
0x14000bfdb  sub     rsp, 20h
0x14000bfdf  mov     rbx, r9
0x14000bfe2  mov     rsi, r8
0x14000bfe5  mov     rdi, rdx
0x14000bfe8  test    r9, r9
0x14000bfeb  jnz     short loc_14000BFF1
0x14000bfed  xor     eax, eax
0x14000bfef  jmp     short loc_14000C04A
0x14000bff1  test    rcx, rcx
0x14000bff4  jnz     short loc_14000C00D
0x14000bff6  call    cs:__imp__errno
0x14000bffc  mov     ebx, 16h
0x14000c001  mov     [rax], ebx
0x14000c003  call    cs:__imp__invalid_parameter_noinfo
0x14000c009  mov     eax, ebx
0x14000c00b  jmp     short loc_14000C04A
0x14000c00d  test    rsi, rsi
0x14000c010  jz      short loc_14000C024
0x14000c012  cmp     rdi, rbx
0x14000c015  jb      short loc_14000C024
0x14000c017  mov     r8, rbx; Size
0x14000c01a  mov     rdx, rsi; Src
0x14000c01d  call    memcpy_0
0x14000c022  jmp     short loc_14000BFED
0x14000c024  mov     r8, rdi; Size
0x14000c027  xor     edx, edx; Val
0x14000c029  call    memset_0
0x14000c02e  test    rsi, rsi
0x14000c031  jz      short loc_14000BFF6
0x14000c033  cmp     rdi, rbx
0x14000c036  jnb     short loc_14000C045
0x14000c038  call    cs:__imp__errno
0x14000c03e  mov     ebx, 22h ; '"'
0x14000c043  jmp     short loc_14000C001
0x14000c045  mov     eax, 16h
0x14000c04a  mov     rbx, [rsp+28h+arg_0]
0x14000c04f  mov     rsi, [rsp+28h+arg_8]
0x14000c054  add     rsp, 20h
0x14000c058  pop     rdi
0x14000c059  retn
```
