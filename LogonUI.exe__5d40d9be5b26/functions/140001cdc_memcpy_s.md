# memcpy_s

- ea: `0x140001cdc`
- end: `0x140001d65`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140001988`
- `0x1400039c8`
- `0x140004ca0`
- `0x1400059c0`
- `0x140006254`
- `0x140006bc8`
- `0x140006e7c`
- `0x14000715c`

## callees

- `0x140001cdc`
- `0x14000322e`
- `0x1400032d0`
- `0x14000793c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140001d02`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140001d43`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140001d02`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140001d43`

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
0x140001cdc  mov     [rsp+arg_0], rbx
0x140001ce1  mov     [rsp+arg_8], rsi
0x140001ce6  push    rdi
0x140001ce7  sub     rsp, 20h
0x140001ceb  mov     rbx, r9
0x140001cee  mov     rsi, r8
0x140001cf1  mov     rdi, rdx
0x140001cf4  test    r9, r9
0x140001cf7  jnz     short loc_140001CFD
0x140001cf9  xor     eax, eax
0x140001cfb  jmp     short loc_140001D55
0x140001cfd  test    rcx, rcx
0x140001d00  jnz     short loc_140001D18
0x140001d02  call    cs:__imp__o__errno
0x140001d08  mov     ebx, 16h
0x140001d0d  mov     [rax], ebx
0x140001d0f  call    _invalid_parameter_noinfo
0x140001d14  mov     eax, ebx
0x140001d16  jmp     short loc_140001D55
0x140001d18  test    rsi, rsi
0x140001d1b  jz      short loc_140001D2F
0x140001d1d  cmp     rdi, rbx
0x140001d20  jb      short loc_140001D2F
0x140001d22  mov     r8, rbx; Size
0x140001d25  mov     rdx, rsi; Src
0x140001d28  call    memcpy_0
0x140001d2d  jmp     short loc_140001CF9
0x140001d2f  mov     r8, rdi; Size
0x140001d32  xor     edx, edx; Val
0x140001d34  call    memset_0
0x140001d39  test    rsi, rsi
0x140001d3c  jz      short loc_140001D02
0x140001d3e  cmp     rdi, rbx
0x140001d41  jnb     short loc_140001D50
0x140001d43  call    cs:__imp__o__errno
0x140001d49  mov     ebx, 22h ; '"'
0x140001d4e  jmp     short loc_140001D0D
0x140001d50  mov     eax, 16h
0x140001d55  mov     rbx, [rsp+28h+arg_0]
0x140001d5a  mov     rsi, [rsp+28h+arg_8]
0x140001d5f  add     rsp, 20h
0x140001d63  pop     rdi
0x140001d64  retn
```
