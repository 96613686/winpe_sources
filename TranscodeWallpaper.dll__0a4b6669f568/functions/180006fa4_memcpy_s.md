# memcpy_s

- ea: `0x180006fa4`
- end: `0x18000702d`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180004d1c`
- `0x180005bc4`
- `0x180005de4`
- `0x180006a74`
- `0x18000a924`
- `0x18000aa84`
- `0x18000c720`

## callees

- `0x180002c4a`
- `0x180002cb4`
- `0x180006fa4`
- `0x18000dd60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006fca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000700b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006fca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000700b`

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
0x180006fa4  mov     [rsp+arg_0], rbx
0x180006fa9  mov     [rsp+arg_8], rsi
0x180006fae  push    rdi
0x180006faf  sub     rsp, 20h
0x180006fb3  mov     rbx, r9
0x180006fb6  mov     rsi, r8
0x180006fb9  mov     rdi, rdx
0x180006fbc  test    r9, r9
0x180006fbf  jnz     short loc_180006FC5
0x180006fc1  xor     eax, eax
0x180006fc3  jmp     short loc_18000701D
0x180006fc5  test    rcx, rcx
0x180006fc8  jnz     short loc_180006FE0
0x180006fca  call    cs:__imp__o__errno
0x180006fd0  mov     ebx, 16h
0x180006fd5  mov     [rax], ebx
0x180006fd7  call    _invalid_parameter_noinfo
0x180006fdc  mov     eax, ebx
0x180006fde  jmp     short loc_18000701D
0x180006fe0  test    rsi, rsi
0x180006fe3  jz      short loc_180006FF7
0x180006fe5  cmp     rdi, rbx
0x180006fe8  jb      short loc_180006FF7
0x180006fea  mov     r8, rbx; Size
0x180006fed  mov     rdx, rsi; Src
0x180006ff0  call    memcpy_0
0x180006ff5  jmp     short loc_180006FC1
0x180006ff7  mov     r8, rdi; Size
0x180006ffa  xor     edx, edx; Val
0x180006ffc  call    memset_0
0x180007001  test    rsi, rsi
0x180007004  jz      short loc_180006FCA
0x180007006  cmp     rdi, rbx
0x180007009  jnb     short loc_180007018
0x18000700b  call    cs:__imp__o__errno
0x180007011  mov     ebx, 22h ; '"'
0x180007016  jmp     short loc_180006FD5
0x180007018  mov     eax, 16h
0x18000701d  mov     rbx, [rsp+28h+arg_0]
0x180007022  mov     rsi, [rsp+28h+arg_8]
0x180007027  add     rsp, 20h
0x18000702b  pop     rdi
0x18000702c  retn
```
