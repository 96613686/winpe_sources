# memcpy_s

- ea: `0x14000cad8`
- end: `0x14000cb62`
- name: `memcpy_s`
- size: `138`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140009aa8`
- `0x14000b284`
- `0x14000b5a8`
- `0x14000c530`

## callees

- `0x14000202c`
- `0x14000cad8`
- `0x1400121e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000cb0b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000cb0b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000cafe`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000cb40`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000cafe`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000cb40`

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
0x14000cad8  mov     [rsp+arg_0], rbx
0x14000cadd  mov     [rsp+arg_8], rsi
0x14000cae2  push    rdi
0x14000cae3  sub     rsp, 20h
0x14000cae7  mov     rbx, r9
0x14000caea  mov     rsi, r8
0x14000caed  mov     rdi, rdx
0x14000caf0  test    r9, r9
0x14000caf3  jnz     short loc_14000CAF9
0x14000caf5  xor     eax, eax
0x14000caf7  jmp     short loc_14000CB52
0x14000caf9  test    rcx, rcx
0x14000cafc  jnz     short loc_14000CB15
0x14000cafe  call    cs:__imp__errno
0x14000cb04  mov     ebx, 16h
0x14000cb09  mov     [rax], ebx
0x14000cb0b  call    cs:__imp__invalid_parameter_noinfo
0x14000cb11  mov     eax, ebx
0x14000cb13  jmp     short loc_14000CB52
0x14000cb15  test    rsi, rsi
0x14000cb18  jz      short loc_14000CB2C
0x14000cb1a  cmp     rdi, rbx
0x14000cb1d  jb      short loc_14000CB2C
0x14000cb1f  mov     r8, rbx; Size
0x14000cb22  mov     rdx, rsi; Src
0x14000cb25  call    memcpy_0
0x14000cb2a  jmp     short loc_14000CAF5
0x14000cb2c  mov     r8, rdi; Size
0x14000cb2f  xor     edx, edx; Val
0x14000cb31  call    memset_0
0x14000cb36  test    rsi, rsi
0x14000cb39  jz      short loc_14000CAFE
0x14000cb3b  cmp     rdi, rbx
0x14000cb3e  jnb     short loc_14000CB4D
0x14000cb40  call    cs:__imp__errno
0x14000cb46  mov     ebx, 22h ; '"'
0x14000cb4b  jmp     short loc_14000CB09
0x14000cb4d  mov     eax, 16h
0x14000cb52  mov     rbx, [rsp+28h+arg_0]
0x14000cb57  mov     rsi, [rsp+28h+arg_8]
0x14000cb5c  add     rsp, 20h
0x14000cb60  pop     rdi
0x14000cb61  retn
```
