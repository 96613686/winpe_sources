# memcpy_s

- ea: `0x140007ea4`
- end: `0x140007f2d`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140004244`
- `0x1400042bc`
- `0x1400059d0`
- `0x14000c7b0`
- `0x140010e6c`
- `0x140011054`
- `0x14001147c`
- `0x1400114dc`

## callees

- `0x1400033ee`
- `0x14000349c`
- `0x140007ea4`
- `0x140018640`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007eca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f0b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007eca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f0b`

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
    v8 = (errno_t *)_o__errno();
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno();
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x140007ea4  mov     [rsp+arg_0], rbx
0x140007ea9  mov     [rsp+arg_8], rsi
0x140007eae  push    rdi
0x140007eaf  sub     rsp, 20h
0x140007eb3  mov     rbx, r9
0x140007eb6  mov     rsi, r8
0x140007eb9  mov     rdi, rdx
0x140007ebc  test    r9, r9
0x140007ebf  jnz     short loc_140007EC5
0x140007ec1  xor     eax, eax
0x140007ec3  jmp     short loc_140007F1D
0x140007ec5  test    rcx, rcx
0x140007ec8  jnz     short loc_140007EE0
0x140007eca  call    cs:__imp__o__errno
0x140007ed0  mov     ebx, 16h
0x140007ed5  mov     [rax], ebx
0x140007ed7  call    _invalid_parameter_noinfo
0x140007edc  mov     eax, ebx
0x140007ede  jmp     short loc_140007F1D
0x140007ee0  test    rsi, rsi
0x140007ee3  jz      short loc_140007EF7
0x140007ee5  cmp     rdi, rbx
0x140007ee8  jb      short loc_140007EF7
0x140007eea  mov     r8, rbx; Size
0x140007eed  mov     rdx, rsi; Src
0x140007ef0  call    memcpy_0
0x140007ef5  jmp     short loc_140007EC1
0x140007ef7  mov     r8, rdi; Size
0x140007efa  xor     edx, edx; Val
0x140007efc  call    memset_0
0x140007f01  test    rsi, rsi
0x140007f04  jz      short loc_140007ECA
0x140007f06  cmp     rdi, rbx
0x140007f09  jnb     short loc_140007F18
0x140007f0b  call    cs:__imp__o__errno
0x140007f11  mov     ebx, 22h ; '"'
0x140007f16  jmp     short loc_140007ED5
0x140007f18  mov     eax, 16h
0x140007f1d  mov     rbx, [rsp+28h+arg_0]
0x140007f22  mov     rsi, [rsp+28h+arg_8]
0x140007f27  add     rsp, 20h
0x140007f2b  pop     rdi
0x140007f2c  retn
```
