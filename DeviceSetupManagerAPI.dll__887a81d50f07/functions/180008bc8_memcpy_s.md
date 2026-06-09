# memcpy_s

- ea: `0x180008bc8`
- end: `0x180008c51`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000526c`
- `0x1800070f4`
- `0x180007418`
- `0x18000853c`
- `0x18000877c`

## callees

- `0x1800024f6`
- `0x180002570`
- `0x180008bc8`
- `0x18000e458`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008bee`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008c2f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008bee`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008c2f`

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
0x180008bc8  mov     [rsp+arg_0], rbx
0x180008bcd  mov     [rsp+arg_8], rsi
0x180008bd2  push    rdi
0x180008bd3  sub     rsp, 20h
0x180008bd7  mov     rbx, r9
0x180008bda  mov     rsi, r8
0x180008bdd  mov     rdi, rdx
0x180008be0  test    r9, r9
0x180008be3  jnz     short loc_180008BE9
0x180008be5  xor     eax, eax
0x180008be7  jmp     short loc_180008C41
0x180008be9  test    rcx, rcx
0x180008bec  jnz     short loc_180008C04
0x180008bee  call    cs:__imp__o__errno
0x180008bf4  mov     ebx, 16h
0x180008bf9  mov     [rax], ebx
0x180008bfb  call    _invalid_parameter_noinfo
0x180008c00  mov     eax, ebx
0x180008c02  jmp     short loc_180008C41
0x180008c04  test    rsi, rsi
0x180008c07  jz      short loc_180008C1B
0x180008c09  cmp     rdi, rbx
0x180008c0c  jb      short loc_180008C1B
0x180008c0e  mov     r8, rbx; Size
0x180008c11  mov     rdx, rsi; Src
0x180008c14  call    memcpy_0
0x180008c19  jmp     short loc_180008BE5
0x180008c1b  mov     r8, rdi; Size
0x180008c1e  xor     edx, edx; Val
0x180008c20  call    memset_0
0x180008c25  test    rsi, rsi
0x180008c28  jz      short loc_180008BEE
0x180008c2a  cmp     rdi, rbx
0x180008c2d  jnb     short loc_180008C3C
0x180008c2f  call    cs:__imp__o__errno
0x180008c35  mov     ebx, 22h ; '"'
0x180008c3a  jmp     short loc_180008BF9
0x180008c3c  mov     eax, 16h
0x180008c41  mov     rbx, [rsp+28h+arg_0]
0x180008c46  mov     rsi, [rsp+28h+arg_8]
0x180008c4b  add     rsp, 20h
0x180008c4f  pop     rdi
0x180008c50  retn
```
