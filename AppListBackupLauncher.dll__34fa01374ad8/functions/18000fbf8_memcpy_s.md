# memcpy_s

- ea: `0x18000fbf8`
- end: `0x18000fc81`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180005314`
- `0x180008bb0`
- `0x18000c0a4`
- `0x18000c3c8`
- `0x18000e714`
- `0x18000eb4c`
- `0x18000ed6c`

## callees

- `0x180002d6a`
- `0x180002dc8`
- `0x180002de0`
- `0x18000fbf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fc1e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fc5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fc1e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fc5f`

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
0x18000fbf8  mov     [rsp+arg_0], rbx
0x18000fbfd  mov     [rsp+arg_8], rsi
0x18000fc02  push    rdi
0x18000fc03  sub     rsp, 20h
0x18000fc07  mov     rbx, r9
0x18000fc0a  mov     rsi, r8
0x18000fc0d  mov     rdi, rdx
0x18000fc10  test    r9, r9
0x18000fc13  jnz     short loc_18000FC19
0x18000fc15  xor     eax, eax
0x18000fc17  jmp     short loc_18000FC71
0x18000fc19  test    rcx, rcx
0x18000fc1c  jnz     short loc_18000FC34
0x18000fc1e  call    cs:__imp__o__errno
0x18000fc24  mov     ebx, 16h
0x18000fc29  mov     [rax], ebx
0x18000fc2b  call    _invalid_parameter_noinfo
0x18000fc30  mov     eax, ebx
0x18000fc32  jmp     short loc_18000FC71
0x18000fc34  test    rsi, rsi
0x18000fc37  jz      short loc_18000FC4B
0x18000fc39  cmp     rdi, rbx
0x18000fc3c  jb      short loc_18000FC4B
0x18000fc3e  mov     r8, rbx; Size
0x18000fc41  mov     rdx, rsi; Src
0x18000fc44  call    memcpy_0
0x18000fc49  jmp     short loc_18000FC15
0x18000fc4b  mov     r8, rdi; Size
0x18000fc4e  xor     edx, edx; Val
0x18000fc50  call    memset_0
0x18000fc55  test    rsi, rsi
0x18000fc58  jz      short loc_18000FC1E
0x18000fc5a  cmp     rdi, rbx
0x18000fc5d  jnb     short loc_18000FC6C
0x18000fc5f  call    cs:__imp__o__errno
0x18000fc65  mov     ebx, 22h ; '"'
0x18000fc6a  jmp     short loc_18000FC29
0x18000fc6c  mov     eax, 16h
0x18000fc71  mov     rbx, [rsp+28h+arg_0]
0x18000fc76  mov     rsi, [rsp+28h+arg_8]
0x18000fc7b  add     rsp, 20h
0x18000fc7f  pop     rdi
0x18000fc80  retn
```
