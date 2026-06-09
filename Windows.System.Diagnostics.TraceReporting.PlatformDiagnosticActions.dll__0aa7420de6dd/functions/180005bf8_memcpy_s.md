# memcpy_s

- ea: `0x180005bf8`
- end: `0x180005c81`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003dfc`
- `0x180004c50`
- `0x180004e70`

## callees

- `0x180001ffa`
- `0x180002058`
- `0x180005bf8`
- `0x180009f74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005c1e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005c5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005c1e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005c5f`

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
0x180005bf8  mov     [rsp+arg_0], rbx
0x180005bfd  mov     [rsp+arg_8], rsi
0x180005c02  push    rdi
0x180005c03  sub     rsp, 20h
0x180005c07  mov     rbx, r9
0x180005c0a  mov     rsi, r8
0x180005c0d  mov     rdi, rdx
0x180005c10  test    r9, r9
0x180005c13  jnz     short loc_180005C19
0x180005c15  xor     eax, eax
0x180005c17  jmp     short loc_180005C71
0x180005c19  test    rcx, rcx
0x180005c1c  jnz     short loc_180005C34
0x180005c1e  call    cs:__imp__o__errno
0x180005c24  mov     ebx, 16h
0x180005c29  mov     [rax], ebx
0x180005c2b  call    _invalid_parameter_noinfo
0x180005c30  mov     eax, ebx
0x180005c32  jmp     short loc_180005C71
0x180005c34  test    rsi, rsi
0x180005c37  jz      short loc_180005C4B
0x180005c39  cmp     rdi, rbx
0x180005c3c  jb      short loc_180005C4B
0x180005c3e  mov     r8, rbx; Size
0x180005c41  mov     rdx, rsi; Src
0x180005c44  call    memcpy_0
0x180005c49  jmp     short loc_180005C15
0x180005c4b  mov     r8, rdi; Size
0x180005c4e  xor     edx, edx; Val
0x180005c50  call    memset_0
0x180005c55  test    rsi, rsi
0x180005c58  jz      short loc_180005C1E
0x180005c5a  cmp     rdi, rbx
0x180005c5d  jnb     short loc_180005C6C
0x180005c5f  call    cs:__imp__o__errno
0x180005c65  mov     ebx, 22h ; '"'
0x180005c6a  jmp     short loc_180005C29
0x180005c6c  mov     eax, 16h
0x180005c71  mov     rbx, [rsp+28h+arg_0]
0x180005c76  mov     rsi, [rsp+28h+arg_8]
0x180005c7b  add     rsp, 20h
0x180005c7f  pop     rdi
0x180005c80  retn
```
