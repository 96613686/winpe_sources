# memcpy_s

- ea: `0x14000c1a4`
- end: `0x14000c22d`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x14000684c`
- `0x140006eb0`
- `0x140009994`
- `0x140009b4c`
- `0x140009e70`
- `0x14000b42c`
- `0x14000b92c`

## callees

- `0x1400020b2`
- `0x140002168`
- `0x14000c1a4`
- `0x140010dec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c1ca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c20b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c1ca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c20b`

## pseudocode

```c
errno_t __cdecl memcpy_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  errno_t *v8; // rax
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
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source);
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source);
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x14000c1a4  mov     [rsp+arg_0], rbx
0x14000c1a9  mov     [rsp+arg_8], rsi
0x14000c1ae  push    rdi
0x14000c1af  sub     rsp, 20h
0x14000c1b3  mov     rbx, r9
0x14000c1b6  mov     rsi, r8
0x14000c1b9  mov     rdi, rdx
0x14000c1bc  test    r9, r9
0x14000c1bf  jnz     short loc_14000C1C5
0x14000c1c1  xor     eax, eax
0x14000c1c3  jmp     short loc_14000C21D
0x14000c1c5  test    rcx, rcx
0x14000c1c8  jnz     short loc_14000C1E0
0x14000c1ca  call    cs:__imp__o__errno
0x14000c1d0  mov     ebx, 16h
0x14000c1d5  mov     [rax], ebx
0x14000c1d7  call    _invalid_parameter_noinfo
0x14000c1dc  mov     eax, ebx
0x14000c1de  jmp     short loc_14000C21D
0x14000c1e0  test    rsi, rsi
0x14000c1e3  jz      short loc_14000C1F7
0x14000c1e5  cmp     rdi, rbx
0x14000c1e8  jb      short loc_14000C1F7
0x14000c1ea  mov     r8, rbx; Size
0x14000c1ed  mov     rdx, rsi; Src
0x14000c1f0  call    memcpy_0
0x14000c1f5  jmp     short loc_14000C1C1
0x14000c1f7  mov     r8, rdi; Size
0x14000c1fa  xor     edx, edx; Val
0x14000c1fc  call    memset_0
0x14000c201  test    rsi, rsi
0x14000c204  jz      short loc_14000C1CA
0x14000c206  cmp     rdi, rbx
0x14000c209  jnb     short loc_14000C218
0x14000c20b  call    cs:__imp__o__errno
0x14000c211  mov     ebx, 22h ; '"'
0x14000c216  jmp     short loc_14000C1D5
0x14000c218  mov     eax, 16h
0x14000c21d  mov     rbx, [rsp+28h+arg_0]
0x14000c222  mov     rsi, [rsp+28h+arg_8]
0x14000c227  add     rsp, 20h
0x14000c22b  pop     rdi
0x14000c22c  retn
```
