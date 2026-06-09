# memcpy_s

- ea: `0x18000dbd8`
- end: `0x18000dc61`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d884`
- `0x1800101a4`
- `0x180011688`
- `0x180012884`
- `0x1800131a4`
- `0x180013d3c`
- `0x1800140f4`
- `0x18001433c`

## callees

- `0x18000dbd8`
- `0x18000f48e`
- `0x18000f4dc`
- `0x1800283fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000dbfe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000dc3f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000dbfe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000dc3f`

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
    v8 = (errno_t *)_o__errno(Destination, DestinationSize);
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno(Destination, DestinationSize);
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x18000dbd8  mov     [rsp+arg_0], rbx
0x18000dbdd  mov     [rsp+arg_8], rsi
0x18000dbe2  push    rdi
0x18000dbe3  sub     rsp, 20h
0x18000dbe7  mov     rbx, r9
0x18000dbea  mov     rsi, r8
0x18000dbed  mov     rdi, rdx
0x18000dbf0  test    r9, r9
0x18000dbf3  jnz     short loc_18000DBF9
0x18000dbf5  xor     eax, eax
0x18000dbf7  jmp     short loc_18000DC51
0x18000dbf9  test    rcx, rcx
0x18000dbfc  jnz     short loc_18000DC14
0x18000dbfe  call    cs:__imp__o__errno
0x18000dc04  mov     ebx, 16h
0x18000dc09  mov     [rax], ebx
0x18000dc0b  call    _invalid_parameter_noinfo
0x18000dc10  mov     eax, ebx
0x18000dc12  jmp     short loc_18000DC51
0x18000dc14  test    rsi, rsi
0x18000dc17  jz      short loc_18000DC2B
0x18000dc19  cmp     rdi, rbx
0x18000dc1c  jb      short loc_18000DC2B
0x18000dc1e  mov     r8, rbx; Size
0x18000dc21  mov     rdx, rsi; Src
0x18000dc24  call    memcpy_0
0x18000dc29  jmp     short loc_18000DBF5
0x18000dc2b  mov     r8, rdi; Size
0x18000dc2e  xor     edx, edx; Val
0x18000dc30  call    memset_0
0x18000dc35  test    rsi, rsi
0x18000dc38  jz      short loc_18000DBFE
0x18000dc3a  cmp     rdi, rbx
0x18000dc3d  jnb     short loc_18000DC4C
0x18000dc3f  call    cs:__imp__o__errno
0x18000dc45  mov     ebx, 22h ; '"'
0x18000dc4a  jmp     short loc_18000DC09
0x18000dc4c  mov     eax, 16h
0x18000dc51  mov     rbx, [rsp+28h+arg_0]
0x18000dc56  mov     rsi, [rsp+28h+arg_8]
0x18000dc5b  add     rsp, 20h
0x18000dc5f  pop     rdi
0x18000dc60  retn
```
