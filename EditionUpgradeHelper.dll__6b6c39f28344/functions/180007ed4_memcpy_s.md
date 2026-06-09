# memcpy_s

- ea: `0x180007ed4`
- end: `0x180007f5d`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180004d68`
- `0x180006bd8`
- `0x180007a3c`
- `0x180007bbc`

## callees

- `0x180002472`
- `0x1800024d4`
- `0x180007ed4`
- `0x18002664c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007efa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007f3b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007efa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007f3b`

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
0x180007ed4  mov     [rsp+arg_0], rbx
0x180007ed9  mov     [rsp+arg_8], rsi
0x180007ede  push    rdi
0x180007edf  sub     rsp, 20h
0x180007ee3  mov     rbx, r9
0x180007ee6  mov     rsi, r8
0x180007ee9  mov     rdi, rdx
0x180007eec  test    r9, r9
0x180007eef  jnz     short loc_180007EF5
0x180007ef1  xor     eax, eax
0x180007ef3  jmp     short loc_180007F4D
0x180007ef5  test    rcx, rcx
0x180007ef8  jnz     short loc_180007F10
0x180007efa  call    cs:__imp__o__errno
0x180007f00  mov     ebx, 16h
0x180007f05  mov     [rax], ebx
0x180007f07  call    _invalid_parameter_noinfo
0x180007f0c  mov     eax, ebx
0x180007f0e  jmp     short loc_180007F4D
0x180007f10  test    rsi, rsi
0x180007f13  jz      short loc_180007F27
0x180007f15  cmp     rdi, rbx
0x180007f18  jb      short loc_180007F27
0x180007f1a  mov     r8, rbx; Size
0x180007f1d  mov     rdx, rsi; Src
0x180007f20  call    memcpy_0
0x180007f25  jmp     short loc_180007EF1
0x180007f27  mov     r8, rdi; Size
0x180007f2a  xor     edx, edx; Val
0x180007f2c  call    memset_0
0x180007f31  test    rsi, rsi
0x180007f34  jz      short loc_180007EFA
0x180007f36  cmp     rdi, rbx
0x180007f39  jnb     short loc_180007F48
0x180007f3b  call    cs:__imp__o__errno
0x180007f41  mov     ebx, 22h ; '"'
0x180007f46  jmp     short loc_180007F05
0x180007f48  mov     eax, 16h
0x180007f4d  mov     rbx, [rsp+28h+arg_0]
0x180007f52  mov     rsi, [rsp+28h+arg_8]
0x180007f57  add     rsp, 20h
0x180007f5b  pop     rdi
0x180007f5c  retn
```
