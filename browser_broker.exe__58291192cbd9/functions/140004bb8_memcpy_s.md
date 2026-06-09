# memcpy_s

- ea: `0x140004bb8`
- end: `0x140004c41`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140002728`
- `0x140003434`
- `0x1400042b8`

## callees

- `0x140001f1e`
- `0x140001fa2`
- `0x140004bb8`
- `0x140005a84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004bde`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004c1f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004bde`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004c1f`

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
0x140004bb8  mov     [rsp+arg_0], rbx
0x140004bbd  mov     [rsp+arg_8], rsi
0x140004bc2  push    rdi
0x140004bc3  sub     rsp, 20h
0x140004bc7  mov     rbx, r9
0x140004bca  mov     rsi, r8
0x140004bcd  mov     rdi, rdx
0x140004bd0  test    r9, r9
0x140004bd3  jnz     short loc_140004BD9
0x140004bd5  xor     eax, eax
0x140004bd7  jmp     short loc_140004C31
0x140004bd9  test    rcx, rcx
0x140004bdc  jnz     short loc_140004BF4
0x140004bde  call    cs:__imp__o__errno
0x140004be4  mov     ebx, 16h
0x140004be9  mov     [rax], ebx
0x140004beb  call    _invalid_parameter_noinfo
0x140004bf0  mov     eax, ebx
0x140004bf2  jmp     short loc_140004C31
0x140004bf4  test    rsi, rsi
0x140004bf7  jz      short loc_140004C0B
0x140004bf9  cmp     rdi, rbx
0x140004bfc  jb      short loc_140004C0B
0x140004bfe  mov     r8, rbx; Size
0x140004c01  mov     rdx, rsi; Src
0x140004c04  call    memcpy_0
0x140004c09  jmp     short loc_140004BD5
0x140004c0b  mov     r8, rdi; Size
0x140004c0e  xor     edx, edx; Val
0x140004c10  call    memset_0
0x140004c15  test    rsi, rsi
0x140004c18  jz      short loc_140004BDE
0x140004c1a  cmp     rdi, rbx
0x140004c1d  jnb     short loc_140004C2C
0x140004c1f  call    cs:__imp__o__errno
0x140004c25  mov     ebx, 22h ; '"'
0x140004c2a  jmp     short loc_140004BE9
0x140004c2c  mov     eax, 16h
0x140004c31  mov     rbx, [rsp+28h+arg_0]
0x140004c36  mov     rsi, [rsp+28h+arg_8]
0x140004c3b  add     rsp, 20h
0x140004c3f  pop     rdi
0x140004c40  retn
```
