# memcpy_s

- ea: `0x180009ce8`
- end: `0x180009d71`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x180004f28`
- `0x1800058a0`
- `0x18000691c`
- `0x1800089b0`
- `0x180008bd0`
- `0x18000c450`
- `0x18000c974`
- `0x18000d4d4`
- `0x18000d66c`
- `0x18000e220`
- `0x18000e4d0`
- `0x18000e520`
- `0x18000e950`
- `0x1800111c0`
- `0x180011290`

## callees

- `0x1800039a6`
- `0x180003a08`
- `0x180003a20`
- `0x180009ce8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d0e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d4f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d0e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d4f`

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
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source, SourceSize);
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source, SourceSize);
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x180009ce8  mov     [rsp+arg_0], rbx
0x180009ced  mov     [rsp+arg_8], rsi
0x180009cf2  push    rdi
0x180009cf3  sub     rsp, 20h
0x180009cf7  mov     rbx, r9
0x180009cfa  mov     rsi, r8
0x180009cfd  mov     rdi, rdx
0x180009d00  test    r9, r9
0x180009d03  jnz     short loc_180009D09
0x180009d05  xor     eax, eax
0x180009d07  jmp     short loc_180009D61
0x180009d09  test    rcx, rcx
0x180009d0c  jnz     short loc_180009D24
0x180009d0e  call    cs:__imp__o__errno
0x180009d14  mov     ebx, 16h
0x180009d19  mov     [rax], ebx
0x180009d1b  call    _invalid_parameter_noinfo
0x180009d20  mov     eax, ebx
0x180009d22  jmp     short loc_180009D61
0x180009d24  test    rsi, rsi
0x180009d27  jz      short loc_180009D3B
0x180009d29  cmp     rdi, rbx
0x180009d2c  jb      short loc_180009D3B
0x180009d2e  mov     r8, rbx; Size
0x180009d31  mov     rdx, rsi; Src
0x180009d34  call    memcpy_0
0x180009d39  jmp     short loc_180009D05
0x180009d3b  mov     r8, rdi; Size
0x180009d3e  xor     edx, edx; Val
0x180009d40  call    memset_0
0x180009d45  test    rsi, rsi
0x180009d48  jz      short loc_180009D0E
0x180009d4a  cmp     rdi, rbx
0x180009d4d  jnb     short loc_180009D5C
0x180009d4f  call    cs:__imp__o__errno
0x180009d55  mov     ebx, 22h ; '"'
0x180009d5a  jmp     short loc_180009D19
0x180009d5c  mov     eax, 16h
0x180009d61  mov     rbx, [rsp+28h+arg_0]
0x180009d66  mov     rsi, [rsp+28h+arg_8]
0x180009d6b  add     rsp, 20h
0x180009d6f  pop     rdi
0x180009d70  retn
```
